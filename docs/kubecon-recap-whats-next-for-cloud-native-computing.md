# KubeCon 回顾:云计算的下一步是什么？

> 原文：<https://thenewstack.io/kubecon-recap-whats-next-for-cloud-native-computing/>

[云原生计算](https://thenewstack.io/category/cloud-native/)的下一步是什么？上个月在最近的 [KubeCon+CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 上，我们有机会与 [Chris Aniszczyk](https://www.linkedin.com/in/caniszczyk/) 交谈，他是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的首席技术官，他有自己的一点看法。请点击此处观看我们的回顾，随后是经过轻微编辑的视频记录:

[https://www.youtube.com/embed/0XUIHwIf1Ss?feature=oembed](https://www.youtube.com/embed/0XUIHwIf1Ss?feature=oembed)

视频

Aniszczyk 在他的谈话中提出了三个主题。一个是 [Rust](https://thenewstack.io/microsoft-rust-is-the-industrys-best-chance-at-safe-systems-programming/) 编程语言和 [WebAssembly](https://thenewstack.io/what-is-webassembly/) 。二是基于云的集成开发环境( [Cloud IDEs](https://thenewstack.io/integrated-development-environments-moving-cloud/) )。第三是[安全](https://thenewstack.io/category/security/)，尤其是[软件供应链安全](https://thenewstack.io/generate-a-software-bill-of-materials-for-a-container-image-with-syft/)。

**Alex Williams(主持人):**现在，Rustlang，一种越来越流行的语言，我们已经写了很多关于它的文章。显然 CNCF 的很多新项目都在使用 Rust。这对生态系统意味着什么？

Chris Aniszczyk: 我看到了生锈在项目中变得越来越普遍的趋势。其中一部分也与目前的 WebAssembly 和许多核心 WebAssembly 社区有关。那里有很多铁锈。所以我认为很自然地把它带到了 CNCF。

威廉姆斯:我们就拿几个项目来说吧。比如微软实验室的[项目 Akri](https://thenewstack.io/microsoft-akri-brings-kubernetes-to-tiny-edge-leaf-devices/) 就是用 Rust 编写的设备发现技术。 [parsec](https://www.cncf.io/projects/parsec/) 也是用 Rust 写的。

它被描述为安全平台抽象，为硬件安全和加密服务提供 API。 [Krustlet](https://thenewstack.io/krustlet-brings-webassembly-to-kubernetes-with-a-rust-based-kubelet/) ，也是用 Rust 写的，是运行 WebAssembly 的 [Kubernetes](https://thenewstack.io/category/kubernetes/) Kubelet。

WebAssembly 来自 Mozilla，用于浏览器中的沙盒标签。今天，WebAssembly 经常与 Rust 一起使用。众所周知，WASM 很受欢迎，因为以前从未出现过像它这样的运行时。

现在，通过像 [WASI](https://thenewstack.io/mozilla-extends-webassembly-beyond-the-browser-with-wasi/) 这样的项目，它被用来适应云原生环境，这是一个在网络外运行 WebAssembly 的系统接口。

这是一个非常精简的运行时，可以支持多种语言，它非常轻量级，可以在非常受限的环境中运行，这是我们以前没有过的。这是我们第一次拥有轻量级的东西，而且默认情况下非常安全。

**Williams:** 云原生 ide:无论是配置管理还是安全性，都有向代码代劳的趋势。它正在转变，它正在向开发人员工作的地方靠近。

[例如，GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 定义了一个应用程序的配置，然后由服务如 [Flux](https://thenewstack.io/flux-takes-its-continuous-delivery-and-operations-to-cncf-incubation/) 或 [Argo](https://thenewstack.io/argo-the-kubernetes-native-workflow-engine-joins-the-cncf/) 进行协调。这种变化在开发者环境中也很明显，比如 [GitHub Codespaces](https://github.com/features/codespaces) 和 [Gitpod](https://www.gitpod.io/) 。

> “这里的整体趋势是，许多东西正在向开发人员进行正常编程的地方转移。”
> —Chris Aniszczyk，云计算原生计算基金会首席技术官

**阿尼斯奇克:**惊人。就像活在梦里一样。你知道，我花了很多年的时间在开发工具上，比如很久以前的 Eclipse，但是能够拥有一个已经预先构建的开发环境，加载一些你可以在其他团队和其他开发人员之间作为可重用的工件共享的东西，这真是太棒了。

但是，这里的整体趋势是，许多东西正在向开发人员进行正常编程的地方转移。

**威廉姆斯:**安全！云原生安全性可以说是最热门的话题，它指出了云原生世界的未来。在 KubeCon 有很多云原生安全初创公司。

Rust 的流行证明了这种新的兴趣。我们看到越来越多的项目开始关注安全问题。你只要看看[开放政策代理](https://thenewstack.io/open-policy-agent-authorization-for-the-cloud/)就知道了。如果你看一下会前活动，几乎每一个都涉及到安全话题。

**Aniszczyk:** 这是开发环境一致性的一种方式。此外，它还可能更加安全。你不需要真的在本地检查所有的东西，把它们都调整一下。

您实际上从云中提供了一个开发环境。我认为很多公司会倾向于这种方式，因为如果他们能够锁定它，会更加安全。所以我认为这是你将会看到的巨大变化。

威廉姆斯:总之，让我们再回顾一下这三个。我们有编程语言 Rust 基于云的 IDEs 和安全。接下来是什么， [GitHub 动作](https://thenewstack.io/github-expands-into-continuous-integration-and-deployment/)？这是未来的征兆吗？一个完全可编程的世界即将到来吗？机器会为我们编写程序吗？你可以把所有这些配置输入神经网络，对吗？

**Aniszczyk:** 正是，[【GitHub】副驾驶](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/)式。你得到了你的 ide，你得到了一个小机器人朋友去写你一天中需要完成的大部分东西。太棒了。敬请关注。

*这里听完整个采访[。](https://thenewstack.io/what-the-future-of-cloud-native-is-about-to-bring/)*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>