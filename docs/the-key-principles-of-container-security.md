# 集装箱安全的关键原则

> 原文：<https://thenewstack.io/the-key-principles-of-container-security/>

KubeCon + CloudNativeCon 赞助了这篇文章，期待在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

 [萨沙·格鲁纳特

Sascha 是 SUSE 的高级软件工程师，在那里他从事许多不同的与容器相关的开源项目，如 Kubernetes 和 CRI-O。他于 2018 年 11 月加入开源社区，在加入 SUSE 之前获得了容器经验。Sascha 的热情包括为开源做出贡献，以及发表演讲和宣传 Kubernetes 相关技术。](https://www.linkedin.com/in/sascha-grunert/?originalSubdomain=de) 

从 2002 年 Linux 内核中第一个名称空间实现开始，容器已经发展成为集群编排系统中全功能云原生应用的底层结构，例如 [Kubernetes](https://kubernetes.io) 。当在 Kubernetes 中构建一个基于容器的工作负载时，会涉及到许多不同的、独立维护的项目。当部署在 Kubernetes 之上时，这大大增加了简单应用程序及其基础设施的攻击面。

但是，如果您在某个集群组件中遇到[常见漏洞和暴露(CVEs)](https://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures) ，现在会发生什么呢？为了理解这种影响，我们还必须理解易受攻击的软件组件的互连，这些组件也与其他接口共享。这并不容易做到。组织必须找到一种以经济的方式处理软件安全的方法。这不仅仅是找到优秀的人来做开发工作，更重要的是全力支持一个开发合作战略。软件工程师需要支持完整的技能集，以便能够处理从概念到操作的整个堆栈。

在本帖中，我们描述了云原生和容器化软件安全性所涉及的不同层面。

## Linux 内核

容器从 Linux 内核开始，将资源隔离到专用的[名称空间](http://man7.org/linux/man-pages/man7/namespaces.7.html)。这正是第一级攻击可能发生的地方，而命名空间资源可能是第一个可能的攻击媒介。存在一些与名称空间相关的已知漏洞，例如与用户名称空间内的权限提升相关的漏洞。这意味着通常好的方法是保持内核最新。然而，基于内核的漏洞并不经常出现，这绝对是一个好现象。

最新的用户命名空间相关漏洞是 [CVE-2018-18955](https://nvd.nist.gov/vuln/detail/CVE-2018-18955) ，它利用了内核到命名空间 ID 转换中的一个 bug。该漏洞适用于在受影响的用户命名空间中拥有 Linux 功能 [**CAP_SYS_ADMIN**](https://lwn.net/Articles/486306/) 的用户，以及可以绕过对命名空间外资源的访问控制的用户。那些所谓的[功能](http://man7.org/linux/man-pages/man7/capabilities.7.html)是我们在限制容器内部安全访问时必须处理的第一批 Linux 内核特性之一。

功能通过完全避免使用根用户和组 ID 0 为超级用户权限增加了额外的控制层。在 Linux 系统上运行软件时，建议以尽可能少的特权功能运行二进制文件，这使得二进制文件对于某个功能子集是无特权的。

可用功能列表[很长。例如，功能 **CAP_SYS_ADMIN** 允许访问像 **unshare(2)** 和 **clone(2)** 这样的系统调用。在比 Linux 3.8 更新的内核上，这些函数根本不需要任何功能。这意味着软件开发人员在为目标平台开发软件时也必须考虑到目标平台，这使得事情变得更加复杂。](http://man7.org/linux/man-pages/man7/capabilities.7.html)

我们在不同的内核名称空间中运行应用程序，这一事实并不允许我们忽略运行应用程序所需的权限集。为了获得更高的安全性，我们还可以将应用程序锁定到更适合的容器映像中。

## 容器图像

除了在容器映像中运行的实际应用程序之外，运行时依赖关系也会带来安全问题。作为首要原则，重要的是不要向容器映像添加不必要的工具或构建时依赖项。指定一个最小的基本映像总是值得的，建议您仔细查看像 node 这样的基本映像。这些基本映像中的大多数依赖于像 Debian 或 T2 Ubuntu 这样的发行版，它们包含了我们可能根本不需要的工具和库，并扩大了部署的攻击面。

如果我们从头开始构建一个容器映像，我们可能会在生产中遇到调试问题。如何调试一个正在运行的容器，这个容器写文件来维护它的状态？通常，这是利用 Kubernetes 更高抽象级别的恰当时机。拥有像[普罗米修斯](https://prometheus.io)、[基巴纳](https://github.com/elastic/kibana)、[格拉法纳](https://grafana.com)或[洛基](https://grafana.com/oss/loki)这样的外部监控和记录门面是很棒的。

还有一点很重要，那就是永远不要将私有秘密泄露到容器映像中，这在映像构建过程中很容易发生。将秘密作为环境变量临时公开仍然会导致在图像历史中显示秘密。为了避免类似的事情，要么使用多阶段构建，要么使用容器构建工具的秘密装载特性。在持续集成和部署(CI/CD)管道中，更好的做法可能是在本地依赖先前的构建步骤，这些步骤提供了秘密文件并将它们复制到构建上下文中。

在缓解中间人(MITM)攻击时，对容器映像进行签名可能很重要。正如在过去的博客文章中已经看到的，很容易就可以挂钩到 Docker 构建过程，并在构建过程中修改内容。拥有单一的信任资源并通过签名图像来验证它是我们真正应该考虑的优势。

与图像签名类似，容器图像加密也可以增加额外的安全级别。这样，本地存储的密钥可以用于在容器运行时级别解密这些层。目前常见的加密技术有三种: [OpenPGP](https://openpgp.org) 、 [JSON Web Encryption (JWE)](https://tools.ietf.org/html/rfc7516) 和 [PKCS#7](https://tools.ietf.org/html/rfc5652) 。

## 容器运行时

容器运行时通常通过在整个堆栈上添加可能易受攻击的源代码来增加与安全相关的攻击面。目前事实上的标准底层容器运行时是 runc，由 Podman、CRI-O、 [containerd](https://containerd.io) 和 [Docker](https://docker.com) 使用。就 Kubernetes 而言，容器运行时 CRI-O 和 containerd 支持任何 OCI (runc)兼容的容器运行时。我们必须根据底层使用的容器运行时来区分安全级别。例如，由于使用范围的原因，runc 中可能存在的漏洞比 containerd 中的漏洞具有更高的影响。使用额外的软件，如 [Kata Containers](https://katacontainers.io) ，通过将工作负载隔离在一个微型虚拟机中，提供了更高级别的安全性。这提高了应用程序的安全性，但也将易受攻击的表面转移到了管理程序和 Kata 运行时本身。

不可能在所有情况下都防止容器运行时问题，但是基于容器的工作负载可以通过其他模式进行安全强化，例如通过应用安全计算(seccomp)配置文件。

[Seccomp](https://en.wikipedia.org/wiki/Seccomp) 提供了一种增强的方式来过滤程序发出的系统调用，以减少内核的攻击面。这在运行不受信任的第三方程序时尤其有用。通过限制可以进行的系统调用，seccomp 为构建现代应用程序沙箱提供了一个很好的补充。

对于容器，支持 seccomp 的运行时可以将 seccomp 配置文件传递给容器，这基本上是指定系统调用的 JSON 白名单。默认情况下，拒绝所有其他系统调用。大多数容器运行时也会在它们的包中附带一个默认的 seccomp 概要文件。

与 Linux 功能特性一样，花时间为应用程序开发 seccomp 过滤器并将其锁定在所需系统调用的最小子集内是很有价值的。明智地知道正在运行的应用程序需要哪些系统调用，也使软件开发人员能够很好地理解他们的应用程序的安全需求。

通过 [SELinux](https://github.com/SELinuxProject/selinux) 和 [AppArmor](https://gitlab.com/apparmor) 可以对应用程序进行更多与安全相关的控制。这两个项目都旨在增强应用程序可能拥有的权限集的粒度，例如与文件或网络权限相关的权限。由于这两种解决方案的目标范围是相同的，发行版通常会决定是使用 SELinux 还是 AppArmor。由于它们是由不同的历史背景产生的，因此不可能认为它们中的一个是更好的解决方案。

## 库伯内特斯

下一层与安全相关的机制掌握在容器编排者手中，可能是 Kubernetes。Kubernetes 在市场中的采用是非常巨大的，现在人们想知道 Kubernetes 的安装到底有多安全。我们不会在这里详细讨论 Kubernetes 的安全性，因为这值得专门写一篇博文。我们可以说，保护 Kubernetes 的集群组件只是在生产中运行工作负载的一个重要部分。

Kubernetes 提供了很好的机制来保护正在运行的工作负载。在[秘密](https://kubernetes.io/docs/concepts/configuration/secret)中存储敏感数据只是其中之一。另一个很好的例子是 pod 安全策略(PSP)的使用，它支持 Pod 创建和更新的细粒度授权。

## 我们的应用

不管我们是否在 Kubernetes 内部运行，我们编写的应用程序代码都是独立地遇到可能的安全漏洞的最高层。云原生应用程序(当然，运行在 Kubernetes 集群内部)需要更深入的安全审计，因为它们可能受到更广泛的攻击。积极的副作用是，整体漏洞堆栈的这一部分为我们提供了最大的控制，我们可以围绕它建立良好的安全意识。

编写不损害我们都需要的隐私的安全应用程序是我们的责任，也是我们的责任。

*要了解更多关于集装箱化基础设施和云本地技术的信息，请参加阿姆斯特丹的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>