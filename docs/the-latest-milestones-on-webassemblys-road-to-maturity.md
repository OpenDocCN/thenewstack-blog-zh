# WebAssembly 走向成熟的最新里程碑

> 原文：<https://thenewstack.io/the-latest-milestones-on-webassemblys-road-to-maturity/>

底特律——即使在 kube con+CloudNativeCon North America 为全球经济将如何使初创公司在不久的将来难以获得支持而焦虑不安的时候，关于几家年轻的以网络组装为中心的公司的消息却是令人振奋的。

[web assembly 走向成熟的最新里程碑](https://thenewstack.simplecast.com/episodes/the-latest-milestones-on-webassemblys-road-to-maturity)

Cosmonic 宣布，它已经在由 Vertex Ventures 牵头的种子轮融资中筹集了 850 万美元。Fermyon Technologies 公布了资金和产品新闻:由 Insight Partners(也拥有新堆栈)牵头的 2000 万美元 A 轮投资，以及运行 [WebAssembly (Wasm)](https://webassembly.org/) 微服务的托管平台 [Fermyon Cloud](https://www.fermyon.com/cloud) 的推出。 [Cosmonic](https://thenewstack.io/what-makes-wasm-different/) 和 [Fermyon](https://thenewstack.io/whats-next-in-webassembly/) 都成立于 2021 年。

[https://www.youtube.com/embed/TqLERVqAD6Q](https://www.youtube.com/embed/TqLERVqAD6Q)

视频

“很多人认为 Wasm 是一个很有前途的东西，或者它只是未来会出现的全新事物，”Cosmonic 的董事 Bailey Hayes 在本期新堆栈制造商播客中指出。

但是未来已经在这里了，她说:“这是技术保守得最好的秘密之一，因为你今天正在到处使用它。我们日常使用的许多应用程序——Zoom、Google Meet、Prime Video，我的意思是，它真的无处不在。对于开发人员来说，将要改变的是，这将是他们在构建文件中的编译目标。”

在汽车城的 KubeCon 录制的这一集《创客在路上》中，Hayes 和 Fermyon 的软件工程师 Kate Goldenring 与 TNS 特写编辑 Heather Joslyn 谈论了 WebAssembly 的现状。这一集是由[云本地计算基金会(CNCF)赞助的。](https://cncf.io/?utm_content=inline-mention)

## Wasm 和 Docker，Java，Python

[WebAssembly](https://thenewstack.io/what-is-webassembly/) —大约有五年历史的基于堆栈的虚拟机的二进制指令格式，旨在在网络上执行二进制代码，让开发人员将诸如 [C、C++、](https://thenewstack.io/how-to-compile-c-code-into-webassembly-with-emscripten/)和 [Rust](https://thenewstack.io/using-web-assembly-written-in-rust-on-the-server-side/) 等语言的性能带到网络开发领域。

在 KubeCon 之前举办的 Wasm Day 上，支持许多其他语言，包括 Java。Net、Python 和 PHP——被宣布。在同一场活动上，Docker 还透露[它已经增加了 Wasm 作为开发者可以瞄准的运行时](https://docs.docker.com/desktop/wasm/)；该功能目前处于测试阶段。

这些步骤使 WebAssembly 更接近于实现它对开发者的承诺，即他们可以“一次构建，在任何地方运行”。

“有了 Wasm，开发人员不需要知道这是他们的编译目标，”Hayes 说。但是，她补充说，“你所知道的是，你现在能够将 Wasm 模块移动到任何云中的任何地方。您在桌面上构建的、可能在 Windows 上运行的软件可以在 ARM Linux 服务器上运行。”

Goldenring 指出，在 Wasm Day 上发布的 [CNCF 对 WebAssembly 用户的“迷你调查”](https://www.cncf.io/blog/2022/10/24/cncf-wasm-microsurvey-a-transformative-technology-yes-but-time-to-get-serious/)的发现，证明了该技术的用户案例正在迅速激增。

“尽管 WebAssembly 是为网络而设计的，但第一反应——大约超过 60%——是无服务器的，”她指出。“然后它说，边缘，然后它说 web 开发，然后它说物联网，用例只是继续前进。这是因为这是一个非常强大的便携式目标，您可以将它放入所有这些不同的用例中。它很安全，有即时启动时间。”

## 世界和战争飞船

播客嘉宾谈到了最近为更容易使用 Wasm、共享代码和重用它所做的努力，包括[组件模型的开发，支持者希望这将简化 WebAssembly 在浏览器外的工作方式。](https://thenewstack.io/whats-stopping-webassembly-from-widespread-adoption/) Goldenring 和 Hayes 讨论了正在建设中的成果，包括“worlds”文件和 WebAssembly 的包注册表 Warg。(Hayes [在 Wasm Day](https://youtu.be/lihQEVhOR58) 上共同介绍了 WebAssembly 包管理方面的工作，包括 Warg。)

海斯说，世界档案是定义你的环境的一种方式。“有一种方式认为它就像`.profile`，但对于 Wasm，对于一个组件。因此，它会告诉我，我的 web 模块需要哪些类型的功能才能在运行时成功运行，并且可以读取这些功能并给我正确的信息。”

至于 Warg，Hayes 说:“它实际上是一个协议和一组 API，这样我们就可以将其纳入现有的生态系统。很多人认为这是我们在现有技术上的尝试。事实并非如此。Warg 的目的是能够正确插入，以便您继续在当前的开发环境和体验中工作，并使用您习惯的包。但是获得组件模型的所有优点，这是我们在 W3C 的 WebAssembly 工作组中一直在研究的新规范。

Goldenring 补充了 CNCF 调查的另一个发现:“大约 30%的人想要更好的代码重用。这是一个更成熟的生态系统的标志。因此，拥有像 Warg 这样的东西将有助于所有参与网络组装领域服务器端的人。”

请听完整的对话，了解有关 WebAssembly 的更多信息，以及这两家公司是如何应对开发者面临的挑战的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>