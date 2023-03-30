# CNCF 欢迎基于 WebAssembly 的 wasmCloud 作为沙盒项目

> 原文：<https://thenewstack.io/cncf-welcomes-webassembly-based-wasmcloud-as-a-sandbox-project/>

[Cosmonic](https://cosmonic.com/) ，基于 [WebAssembly](https://thenewstack.io/what-is-webassembly/) 的 [wasmCloud](https://wasmcloud.com/) 微服务分布式应用框架背后的公司，已经宣布[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)已经接受 wasmCloud 作为其最新的沙盒项目。

Cosmonic 的创始人 Liam Randall 说，他相信 WebAssembly (WASM)是分布式计算的未来:“WebAssembly 正在变得像容器一样重要，在企业中无处不在。”

Randall 补充说，wasmCloud 于 11 月推出，提供了一个默认安全、无样板文件的开发人员环境，该环境将使用云原生技术与 WASM 相结合，以构建和部署可插入多云、多边缘和多浏览器环境的可组合应用程序。

英特尔公司首席分析师兼 CMO 杰森·英格利什说:“我们仍然只是对 WASM 的未来略知一二，我们将会看到更多的关注，试点例子将在年底出现。”。“WebAssembly 技术为现有应用程序代码的现代化带来了巨大的潜力，使其成为响应更快、性能更高、可移植的应用程序，可以在任何浏览器中与 JavaScript 并行运行。我可以看到有一天非常复杂的商业逻辑形式可能会使用浏览器支持的资源来执行，但现在 WASM 才刚刚开始用于图形和处理器密集型应用，如虚拟现实和游戏。”

> “在企业中，WebAssembly 将变得和容器一样重要，一样无处不在”
> 
> **—Cosmonic 首席执行官利亚姆·兰德尔**

然而，“云中的 WebAssembly 已经被一个蓬勃发展的开源项目生态系统所推动，我们正站在巨人的肩膀上，”wasmCloud 联合创始人兼技术负责人凯文·霍夫曼在一份声明中说。“通过将 wasmCloud 捐赠给 CNCF，我们希望为该社区的发展做出贡献，并加速 wasmCloud 的推广。”

## “虚拟 CPU”

wasmCloud 项目有近 80 名贡献者，现在是作为沙盒项目加入 CNCF 的四个早期企业 WebAssembly 项目之一，其他三个项目是 [Krustlet](https://krustlet.dev/) 、 [Krator](https://github.com/krator-rs/krator) 和 Orcas。

Randall 说，消除[样板代码](https://en.wikipedia.org/wiki/Boilerplate_code)意味着更快的开发时间和更低的生命周期维护成本。他指出，除了 WebAssembly 提供的增强的可移植性以及 WebAssembly 沙箱的安全性之外，wasmCloud 还提供了接近原生的性能和更小的占用空间以实现快速扩展。

兰德尔是一位连续创业者，尤其是在容器和 Kubernetes 领域，他喜欢谈论“技术时代”以及每个新主题如何建立在上一个主题的基础上。

Randall 说，从虚拟机到容器和 Kubernetes，再到现在的 WebAssembly，“我们正在将堆栈向上移动，让开发人员更少担心，因为我们正在将越来越高的抽象推到堆栈的较低部分”。

然而，他指出，每个时代都有自己的包袱和假设。使得 2021 年的开发者在安全性、不同 CPU 体系结构的增加和分布式能力的可移植性方面面临重大但不一定是新的挑战。

兰德尔说，WasmCloud 通过其 WebAssembly 根，可以帮助开发人员过渡到一个应用程序真正可移植的世界，不仅仅是在它们执行的地方，而且围绕它们构建的库和东西。

“让我们把 WebAssembly 想象成非常类似于虚拟 CPU，”他说。“所以，把它想象成一个执行环境。现在，它的一大价值支柱是安全性。所以首先，它不像 Java，它有一种语言。这是一个编译目标。我们可以用我们熟悉和喜爱的现有语言开发现有的应用程序。我们可以把它们编译到这个虚拟 CPU 上。现在这个虚拟 CPU 带来了一些真正伟大的安全价值道具。”

请记住，wasmCloud 是以默认拒绝模式运行的，在这种模式下，您必须显式地授予功能。兰德尔说:“我们不再让孩子的应用程序拥有与父母相同的权利，我们给他们非常零碎的访问权限，WebAssembly 让你可以在服务器、台式机、小型设备和任何地方这样做。”

wasmCloud 组件包括:一个 WebAssembly 主机运行时、一个 WasmCloud 主机运行时、热插拔功能、可组合的分布式 actors 和一个分布式、自动配置的 lattice 网络。

兰德尔在一份声明中说:“在过去的 30 年里，我们目睹了企业应用程序与其环境的分离——从为特定硬件编写的应用程序到由公共云编排的虚拟机——现在共享容器来运送具有可再生环境的应用程序。”。

WasmCloud 帮助开发人员利用开放、可移植的技术解决新的、不断发展的挑战，他补充说，“更高层次的抽象将特定于供应商的库替换为声明性参与者，这些参与者可以使用数据库、消息队列和 web 服务器等公共功能。”

[https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed](https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>