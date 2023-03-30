# CoreOS 的 rkt 如何为 appc 容器开辟一条安全之路

> 原文：<https://thenewstack.io/coreoss-rkt-blazes-secure-trail-appc-containers/>

对于任何人来说，很难在支持行业标准的同时，接受多个这样的标准在资本主义市场中相互争斗的概念。为了成功，一个人的名字通常必须像“谷歌”一样

去年，在 CoreOS Inc .发起建立一个名为 **appc** 或 App Container 的容器化标准(Docker 的 **libcontainer** 的替代品)的努力后，就第二个标准(或第三个，如果你仍然把 **lxc** 计算在内)对这个概念的发展是有益还是有害进行了一些公开辩论(这在任何开源市场都很常见)。

周四，CoreOS 宣布其具有竞争力的 **rkt** (仍读作“rocket”)集装箱引擎[将作为版本 1.0](https://thenewstack.io/coreos-container-runtime-rkt-reaches-1-0/) 正式发布，它正式揭开了覆盖其具有竞争力的集装箱化平台的剩余面纱。它的[构造](https://thenewstack.io/coreos-debuts-tectonic-a-commercial-kubernetes-distro/)编排系统，是 CoreOS 的谷歌 Kubernetes 的商业化身，现在整合了一个完整的 **rkt** 容器引擎。它支持开放容器倡议和 appc 格式，适用于分布在其 Quay 和 Quay Enterprise 注册表上的容器，自然包含 CoreOS 本身作为它们的 Linux 内核。

## 共存

现在 CoreOS 的平台已经正式退出了萌芽阶段，它的竞争力会有多大，能有多大？这种竞争会推动集装箱业向前发展吗？

在 rkt 1.0 发布前的一次采访中，CoreOS 首席执行官 Alex Polvi 提到了单一标准容器图像格式的重要性，同时将标准化的范围缩减到了最低限度。

“虽然我们总体上百分之百支持标准，”Polvi 说，“开放容器倡议中正在进行的工作实际上集中在运行时方面。这意味着，像 **rkt** 和 Docker 这样的项目可能会共享用于运行容器的执行插件——所以有一个模块化的、基于标准的插件接口，你可以如何执行容器，工具供应商能够共享它。这才是 OCI 真正关注的。

“What we think is the most important part of a container standard is the actual image format — the end-user format that a company uses to build its container, and then it’s able to take it and run it in **rkt** or Docker or Amazon EC2 Container Service or whatever, and it works in a similar way.”

Polvi went on to say, however, that he believes the OCI as an organization has been more focused on the development of the universal runtime (another of Docker’s contributions from last June) than the image format itself. By contrast, **appc** in its current incarnation includes an open image format that contains elements he believes should eventually be included in OCI.

First and foremost, Polvi says, OCI images should include a key feature of **appc**: cryptographic signatures.

“Docker does have some signature validation capabilities,” the CEO told us, “but it’s not implemented in such a way that an administrator can enforce a policy that says, ‘Only run these images that are allowed.’ And that’s the type of requirement that we think production operations teams need — they’re honestly just basic requirements of any of these sorts of standards. The image format has to have some properties that allow security to be implemented, at even a basic level.”

In [a company blog post Thursday](https://coreos.com/blog/rkt-hits-1.0.html), Polvi set out to distinguish **rkt** as the alternative container platform for the more security-minded organization. He politely chastised the OCI for “creating standards for the container runtime environment, rather than the container image,” and portrayed **appc** as actually going further toward establishing an open container image format than OCI.

Then Polvi went on to bolster his case for CoreOS’ “security-minded” approach, advocating for a renewal of the goals that gave rise to containerization in the first place: process isolation.

Polvi described a sophisticated, tiered model of process isolation that incorporates the work CoreOS has been doing with Intel. This work enables **rkt** to support Intel’s Clear Container platform in addition to OCI and **appc**, leveraging Intel’s VT technology for hosting containers within a lightweight virtualization layer at the hardware level.

“It is about stronger isolation,” he told us. “We’re able to provide virtualization-level isolation on the container, but still keep it a lightweight, quick-to-launch, low-overhead experience that you get with a normal Linux container, combining the best of both worlds.”

## Back to Stage One

第一个 **lxc** 容器背后的原始灵感是进程隔离:特别是，给应用程序它们自己的、独占的名称空间。当容器首次大获成功时，反对者提出了一个难以反驳的异议:可以想象，一个在容器内部工作的恶意行为者可以攻击托管它的 Linux 内核，这样做威胁到该内核运行的所有工作负载的稳定性，无论是虚拟的还是其他的。

通过将 **appc** 的签名图像与 **rkt** 的分层虚拟化模型配对，CoreOS 开辟了一种可能性，即编排引擎可以为容器的分阶段测试和部署实现更细粒度的策略。

在 **rkt** 模型中，正如 Polvi 向我们描述的那样，第一阶段为从注册中心下载的容器提供完全的托管权限。对于某些类别的应用程序(如系统代理程序)来说，这一阶段可能是必要的，这些应用程序根本不应该独立运行。下一阶段采用第一个额外的隔离层，其中名称空间和其他 Linux 资源被呈现为应用程序专有。

这种渲染是通过 **[rkt 对安全增强的 Linux (SELinux)](https://coreos.com/blog/container-security-selinux-coreos.html)** 的原生支持而成为可能的。默认情况下， **rkt** 在 SELinux 上下文下运行容器，使它们无法与共享同一内核的其他进程或容器直接通信，也无法与内核本身直接通信。

然后是下一步，CoreOS 为透明容器设计的。英特尔设计了这种格式，以便工作负载可以直接由英特尔处理器的底层硬件托管。Polvi 表示，一个极其轻量级的操作系统(意味着比 CoreOS 本身更简约)可以在低级虚拟机管理程序的帮助下作为英特尔 VT 虚拟机运行。这样的容器可以像主机上的任何其他容器一样进行编排，但是它并不真正由主 Linux 内核托管，这一事实是从编排器中抽象出来的。

对于任何有潜在危险的应用来说，这听起来似乎已经足够隔离了。但是，如果一个组织打算使用容器部署一个类似网飞的微服务模型，其中的“应用程序”是超越云和内部数据中心的交互式服务的组合，该怎么办呢？这种级别的隔离不适合微服务模型吗？

“如果你正在构建一个多租户云服务，比如平台即服务，”Alex Polvi 回应道，“我会打开虚拟化引擎的隔离。您不必在裸机环境中，在自己的物理服务器上这样做。但我们确实有客户在裸机上构建多租户云服务，他们可以使用基于虚拟机的隔离来获得与虚拟机一样好的隔离，但没有传统虚拟化的开销。”

## 适度服用

另一方面，他说，对于一个组织正在解构其单一的应用程序，而只是需要一个更安全、更现代的平台来运行传统模式的服务的情况，Polvi 说，“SELinux 方法可能已经足够好了。您正在运行的应用程序在某种程度上是可信的。你必须相信你在自己的环境中运行的一切；你知道他们没有恶意，[*除非*第三方正在损害这些应用程序。在这一点上，SELinux 在防止应用程序跳出容器并在主机上做事情方面做得非常好。"

如果客户不确定先尝试什么，波尔维建议将隔离旋钮调到最大，看看会发生什么。

“如果您可以利用完整的第三方云服务提供商的严格安全性优势，但您可以在自己的环境中做到这一点，为什么不呢？”他说。“把它全部打开。虚拟化的性能开销，特别是在超轻量级的虚拟机管理程序和内核上，在这一点上是最小的，因为它都是硬件加速的。”

CoreOS 的价值主张是面向那些希望“全进”的组织，即那些愿意投入使用 constructive 和 Quay 的服务模式的组织。与竞争对手“从小规模起步，扩大规模”的客户相比，CoreOS 可能最终会发现自己与集装箱化市场的其余部分形成了适当的对比，而不必为此发动战争。

Docker 是新堆栈的赞助商。

特征图片:[双子座-泰坦 11 号火箭](https://commons.wikimedia.org/wiki/File:Gemini-Titan_11_Launch_-_GPN-2000-001020.jpg)，美国宇航局通过维基共享，公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>