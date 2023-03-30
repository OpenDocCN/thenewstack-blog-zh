# KubeCon EU 2021 的 3 个关键要点

> 原文：<https://thenewstack.io/3-key-takeaways-from-kubecon-eu-2021/>

GitOps 的采用、API 的改进以及 [WebAssembly (Wasm)](https://webassembly.org/) 的不断扩展正在影响着 Kubernetes 开发者的体验。这些都是本月早些时候在[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的 [KubeCon + CloudNativeCon EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 上的主题。

将所有这些放在一起的是主持人 [Alex Williams](/author/alex/) 和[Joab Jackson](https://twitter.com/Joab_Jackson)TNS 执行主编，在这个新堆栈制造商现场活动中，特邀嘉宾有[VMware 首席工程师 Bryan Liles](https://www.linkedin.com/in/bryanliles) 和[CNCF 生态系统副总裁 Cheryl Hung](https://uk.linkedin.com/in/cheryljhung) 。

[https://www.youtube.com/embed/xSAP9rPmitM?feature=oembed](https://www.youtube.com/embed/xSAP9rPmitM?feature=oembed)

视频

Liles 说，简而言之，Kubernetes 可以被描述为一种 API 服务，允许工作负载在商用硬件或云中运行。通过这种方式，Kubernetes 的功能扩展到网络、日程安排、安全和其他任务。然而，Kubernetes 已经变得“对人们来说在云上旋转它是如此容易，以至于他们认为旋转集群的容易程度应该与部署的容易程度相匹配——不幸的是，这是不可能的，”Liles 说。

开发人员体验的许多改进可以归功于 API 选项的进步。Liles 解释说，有了 Kubernetes API 原型 kcp，现在可以在 Kubernetes 控制平面之上实现 Kubernetes 控制平面抽象，这样“任何点击它的人都会想到他们自己的集群”。Liles 说:“因此，考虑一下多租户的情况，我的集群中安装了不同版本的软件，我们可以将它们安装到单独的租户中。“现在我们可以拥有同一个东西的多个版本，这是我们在 Kubernetes 中无法做到的，现在我们有了一个不同的安全边界。这太神奇了。”

[GitOps，WebAssembly，更智能的 API:开发者体验刚刚起步](https://thenewstack.simplecast.com/episodes/gitops-webassembly-smarter-apis-the-developer-experience-is-just-getting-started)

事实上，很多美妙之处在于 API 是如何工作的，以及如何将抽象放在 API 的前面。“它们看起来像 API，你的所有工具都与它对话，但它在与什么对话呢？唉，谁在乎呢？”莉莉斯说。“外墙后面是 Kubernetes，但现在我们比以往任何时候都更了解这些优点。现在我们拥有了所有的稳定，世界再也不用担心了。”

Wasm 的应用范围也在不断扩大，远远超出了最初主要的多语言使用范围，将 JavaScript (JS) 、[、C++](https://fr.wikipedia.org/wiki/C%2B%2B) 和 [Rust](https://www.rust-lang.org/fr) 集成到一个单一的 web 应用运行时平台中。今天，Wasm 的多功能性正在扩展到服务器和后端应用程序——以及 Kubernetes 集群。Liles 说，有了 Wasm，“无论你有什么语言，我们都可以在任何地方部署它”。“我们不再关心这个问题，这意味着我们也可以为此进行优化，”Liles 说。“我们可以优化如果您部署自己的二进制文件就无法优化的事情和方式。”

作为底层支持和在 CI/CD 循环中实现更多结构的一种方式， [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 继续闪耀。Hung 说:“我认为，能够在 Git 中声明所有基础设施，并拥有审计日志和追溯能力，会带来一些非常好的特性。

然而，GitOps 仍然是一项正在进行的工作。“老实说，我实际上只看到了关于[GitOps]的好意见和好反馈，我实际上真的很想听到更多关于一些缺点的信息，也许是它还不太发达的领域，”Hung 说。“因为总的来说，对于我听说的几乎所有部署，我都听到了非常好的消息。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>