# WebAssembly 能解决 Serverless 的问题吗？

> 原文：<https://thenewstack.io/can-webassembly-solve-serverless-problems/>

[无服务器](https://thenewstack.io/serverless/)对于那些寻求创建和运行应用程序，且基础设施管理相对较少的组织来说，各种使用情形对计算的需求持续增长。对于寻求提供软件应用程序、服务或两者兼有的初创公司来说，这是一个好消息，因为它们不需要在本地服务器上进行大量投资，也不需要通过云供应商来配置或管理自己的基础设施。

在预构建的[软件即服务(SaaS)平台](https://thenewstack.io/private-saas-a-new-paradigm/)上添加 API 或服务仅一步之遥，无服务器替代方案允许组织以最少的开销和更少的维护管理任务开始提供自己的业务服务或应用。

根据分析公司 Omdia 的数据，这些优势有助于解释为什么无服务器市场的价值预计将从 2021 年的 100 亿美元翻两番，到 2026 年超过 400 亿美元。

## WebAssembly 闪耀

无服务器在许多方面有助于延续下一个 AirBnb 或 SaaS 供应商成功故事的神话。你可能会想象一个孤独的初创公司创始人用笔记本电脑登录云服务，在创建了一个无服务器账户后开始创业。(如果这听起来好得不像是真的，那是因为在很多方面确实如此。)

不管怎样，无服务器应该比现在更好，原因有几个。除了与云供应商共享策略、数据和网络保护相关的安全挑战之外，对于许多组织来说，无服务器的缺点还包括(但不限于)延迟和供应商锁定问题。

克服这些缺点是 [WebAssembly、](https://thenewstack.io/is-webassembly-really-the-future/)或 Wasm——至少在理论上——真正大放异彩的原因。它的运行时结构被设计为直接在 CPU 上运行，以便提供一种更直接的方式来运行分布在[容器](https://thenewstack.io/containers/)或不同设备和环境上的相同应用和代码(想想[边缘计算](https://thenewstack.io/edge-computing/))。

然而，问题是无服务器通常等同于供应商锁定。当今典型的第三方使用案例意味着无服务器将需要第三方的支持，而第三方通常是云供应商。

对于许多人来说，无服务器架构可能等同于亚马逊网络服务(T2)上的 Lambda，或者其他云供应商的产品，如 Azure、谷歌云、甲骨文(T4)或 IBM。

因此，组织必须满足于将其多个基础架构委托给一家第三方云提供商，而不是多家供应商，以便在许多情况下管理其关键应用。仅仅因为这个原因，避免供应商锁定是 Wasm 的一个关键卖点。

“web assembly 有可能修复当今无服务器计算的一个大缺陷:供应商锁定，”企业管理协会(EMA)的分析师 Torsten Volk 告诉新堆栈。“随着组织采用大量云，WebAssembly 可以提供一种交钥匙的方式来运行和集成所有云。那不是很好吗？”

## 无服务器是开始

Wasm 并不是什么太新的东西。在 2019 年 [万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 将其命名为 web 标准之前，它与 [HTML](https://thenewstack.io/html-markup-tips-for-developing-accessible-websites/) 、 [CSS](https://thenewstack.io/css-frameworks-in-vogue-but-dont-forget-style-fundamentals/) 和 JavaScript 一起成为第四个 Web 标准。但是 WebAssembly 背后的兴趣和动力主要是它在浏览器之外的潜在用途。它不仅可以用于支持 Web 应用，还可以扩展到任何运行在 CPU 上的 edge 环境和云原生平台，包括[服务网格](https://thenewstack.io/service-mesh/)和 edge [Kubernetes](https://thenewstack.io/kubernetes/) 支持。

【Wasm 可以运行的语言包括，除了 JavaScript 之外，[Rust](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/)[Go](https://thenewstack.io/go-1-18-the-programming-languages-biggest-release-yet/)，。NET、C++、Java、[PHP](https://thenewstack.io/php-has-survived-for-26-years-because-it-keeps-evolving/)和[Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)。对这些语言和其他语言的改进即将推出。一年前，Fermyon Spin 只有 Rust 和 go 的 Wasm SDKs。它现在增加了对 JavaScript/TypeScript Python 和[的支持。网](https://thenewstack.io/net-7-simplifies-route-from-code-to-cloud-for-developers/)。 [Matt Butcher、](https://www.linkedin.com/in/mattbutcher/)[Fermyon Technologies 联合创始人兼首席执行官表示，“语言支持正在迅速到来”。](https://thenewstack.io/webassembly-5-predictions-for-2023/)

[Cosmonic](https://www.linkedin.com/in/hectaman)的首席执行官兼联合创始人利亚姆·兰德尔 说:“我们知道 Wasm 在浏览器中的传统，但我们也知道使 Wasm 在浏览器中出色工作的属性，使它在云中、在边缘、在设备上运行得一样好。

得益于 Wasm 的运行效率，组织可以全权在无服务器环境中创建、部署和管理应用，而无需管理基础设施。至少在理论上，Wasm 应该比那些在由云供应商管理的服务器上的无服务器环境中运行的应用程序提供更好的运行时性能和更低的延迟。通过 API 依靠[平台即服务(PaaS)](https://thenewstack.io/pipelines-paas-continuously-delivering-continuous-delivery/) 解决方案，流程变得更加简单。

“Wasm 绝对有潜力成为应用平台中的‘下一个大事件’，因为它在近乎即时的启动时间、跨操作系统和云平台一致工作的超级可移植运行时以及完全基于[零信任认证的紧密安全性方面有着巨大的潜力。EMA 的沃尔克说:“这非常令人兴奋。](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)

Butcher 说，事实上，传统的无服务器功能需要 200 毫秒或更长时间才能启动。“在您的代码开始执行之前，已经过去了 200 毫秒。借助 Wasm，我们已经能够将启动时间缩短到一毫秒以下。再加上出色的开发者体验，你就有了一个放弃 Lambda 的令人信服的理由。”

Wasm 计算结构的设计方式已经“转移”了无服务器领域的潜力，Butcher 说。他说，这是由于 WebAssemby 几乎即时的启动时间，较小的二进制文件大小，以及平台和架构的中立性，因为 Wasm 二进制文件可以用运行今天的无服务器基础设施所需的一小部分资源来执行。

“与重量级(虚拟机)和中量级容器相比，我喜欢将 Wasm 视为轻量级云计算平台，”他指出。“开发人员只打包最基本的东西:一个 Wasm 二进制文件和一些支持文件。Wasm 运行时会处理剩下的事情。”

依赖 Wasm 的无服务器运行时的一个直接好处是更低的延迟，特别是当 Wasm 的覆盖范围不仅超出浏览器，而且远离云时。这是因为它可以以相对较低的数据传输和计算开销直接分布到边缘设备上。

“无服务器计算非常适合真正特定的使用情形。例如，最优先考虑的是云提供商为用户管理基础设施，”Randall 说。“然而，在现实中，如果我们专门为 edge 或[物联网]用例设计应用程序，它们可以运行得更快、更高效。在离用户更近的地方运行应用程序可以减少网络传输的延迟和数据，从而为开发人员带来更好的用户体验和更低的成本。”

## 到达那里

我们可以创建一个应用程序，并在一个无服务器的基础设施中，以您选择的语言(如使用 edge 和机器学习友好的 Python)在许多不同的 edge 设备上直接同时运行它，这一天应该很快就会到来，尽管我们还没有实现。目前，运行在 Wasm 上的应用程序在很大程度上仍然局限于 JavaScript 和 Rust，但仍有许多工作要做。

“Wasm 是‘一次编写，随处运行’口号的新版本。相同的二进制文件可以在 Windows、Linux 或 macOS 上运行。它可以在英特尔或 Arm 架构上运行，甚至可以在更奇特的操作系统和硬件配置文件上运行，”Butcher 说。“这是在 edge 和云中取得成功的关键因素:相同的应用程序可以移动到最适合用户需求的位置。”

Volk 说，Rust 和 JavaScript 代表着“伟大的婚姻”。“Rust 带来了性能和安全性，而 JavaScript 带来了一个庞大的库生态系统，易于使用并拥有庞大的用户社区。这在数据科学、机器学习、图像处理等性能密集型领域开辟了一系列新的用例。”

## 最近的将来

在不久的将来，尽管 WebAssembly 提供了计算性能优势和更低的延迟，但一些组织可能仍会选择屡试不爽的无服务器选项。这在很大程度上是因为我们仍然处于 Wasm 的早期，超出了其最初的浏览器用例。

“使用 WebAssembly，你可能需要管理你的基础设施，包括服务器和网络，这可能会增加你的部署的复杂性和成本，假设 Kubernetes 和其他 orchestrators 对 Wasm 的支持不能更快地采用 Wasm 友好的运行时，[Taylor dole zal](https://www.linkedin.com/in/onlydole),[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)[【CNCF】](https://thenewstack.io/how-a-project-graduates-from-the-cloud-native-computing-foundation/)生态系统负责人在一封电子邮件回复中告诉新的堆栈。

“尽管有许多工具和框架可用于 WebAssembly(得益于协作和活跃的生态系统)，但它们可能不像传统无服务器平台那样成熟或健壮，这可能会影响开发速度和易用性。”

在CNCF[最近发布的年度调查报告](https://www.cncf.io/reports/cncf-annual-survey-2022)中，基金会表示“ 集装箱是新常态，网络组装是未来。”该报告还陈述了“随着容器成为主流，在 2022 年，无服务器架构的采用正在为 WebAssembly 奠定基础，这是在本次调查中首次被问到的。”

Dolezal 说，尽管 Wasm 为应用程序创建了一个统一且安全的运行时，但它“仍然需要一个清晰的流程编排框架”。Dolezal 说，为此， [runwasi](https://github.com/containerd/runwasi) ，它正在 [containerd 项目](https://containerd.io/)中构建，以促进运行由 containerd 管理的 Wasm/WASI 工作负载。

然而，沃尔克呼吁谨慎行事。“Runwasi 是一个充满希望和活力的项目，势头良好，但我们必须记住在其 GitHub repo 顶部显示的警告:Alpha 质量软件，不要在生产中使用。’”他说我们在 WAGI 的数据库中也发现了非常相似的警告，Fermyon 的非常令人兴奋但仍处于试验阶段的 Python SDK 也是几天前才发布的。

“一旦我们可以放心地在 Wasm 和 Kubernetes PODs 中的 containerd 上运行 Python 应用程序，我们将拥有一个真正独立于云的企业级无服务器应用程序平台。”

最终，正如 CNCF 代表所指出的，“无服务器功能和 Wasm 是我们在云进化周期中需要的组合。我们现在已经建立了一个包含虚拟机、容器和 Wasm 的免费套件，因此我们可能不需要新的“用于 Wasm 的 Kubernetes，”Butcher 说。

“我们已经看到像 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) Nomad [这样的现有管弦乐队已经做得非常出色了](https://thenewstack.io/case-study-how-seatgeek-adopted-hashicorps-nomad/)。Kubernetes 社区内 Wasm 势头的增长让我深受鼓舞(也感到惊喜)，因此 Wasm 很可能只是我们现有云原生生态系统的一个补充。”

* * *

从 10 月在 [KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 北美录制的这一集《新堆栈制作人》中了解 Wasm 的更多新内容。

[https://www.youtube.com/embed/TqLERVqAD6Q](https://www.youtube.com/embed/TqLERVqAD6Q)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>