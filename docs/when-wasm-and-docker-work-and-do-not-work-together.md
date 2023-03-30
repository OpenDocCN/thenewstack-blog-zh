# Wasm 和 Docker 何时一起工作(或不一起工作)

> 原文：<https://thenewstack.io/when-wasm-and-docker-work-and-do-not-work-together/>

披露:B. Cameron Gain 是 ReveCom Media Inc .的创始人和所有者，该公司为 Cosmonic 提供咨询服务。

最近有很多关于 WebAssembly 是否会最终取代 Docker 容器的讨论。人们经常拿容器做比较——由于其卓越的可移植性、资源节约和其他属性——容器经常被吹捧为有一天会淘汰虚拟机，但显然它们没有。

“回到 2014 年:当容器第一次得到一些关注时，所有早期的对话都是关于它们是否能取代虚拟机，” [Fermyon Technologies，](https://www.fermyon.com/)的首席执行官[马特·布彻](https://www.linkedin.com/in/mattbutcher/)告诉新堆栈。“这些年来我们学到的是，这两种技术更多的是互补而不是冲突。”

虽然有一些关于 Docker 容器和 Wasm 将如何互补的讨论，但这可能不会是一个大规模的情况。相反，看起来 Docker 将在分布式应用的主要部分保持优势，而 Wasm 将开拓越来越广泛的用例，特别是在 Wasm 的安全优势超过容器的情况下，以及某些 edge 和其他应用用例。

## 重叠用例

“在维恩图中，容器和 WebAssembly 肯定是重叠的，在接下来的几年里，我们将会看到一些斗争，以找出如何处理一些重叠的情况，”Butcher 说。“但在我看来，重叠部分很小。不重叠的领域揭示了这两种技术将如何共同发展。”

然而，目前有许多重叠的用例，[Docker](https://www.linkedin.com/in/jakelevirne)的产品负责人 Jake Levirne 在一封电子邮件回复中说，他坚持认为任何思考 Wasm 是否有一天会取代 Docker 容器的人都没有抓住要点。Levirne 说，使用 Docker 的开发、测试和部署工具链可以更容易地维护应用交付的可再生管道，而不管应用架构如何。“数以百万计的预建 Docker 图像，包括数以千计的官方和经验证的图像，提供了核心服务的主干——如数据存储、缓存、搜索和框架——可以与 Wasm 模块一起使用，”Levirne 说。“随着时间的推移，容器运行时和注册表将扩展到包括本机 Wasm 模块支持。事实上，今天这已经在发生了。”

## 优势和劣势

从一开始，就像 Docker 容器一样，Wasm 具有非常具体和自适应的计算结构。它可以容纳许多不同的编程语言，例如除了 HTML 和 CSS 之外，还可以将 [JavaScript (JS)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) 、 [C++](https://en.wikipedia.org/wiki/C%2B%2B) 和 [Rust](https://www.rust-lang.org/) 集成到单个运行时平台中，以二进制格式执行功能。它可以用于支持 web 应用，并扩展到任何运行在 CPU 上的边缘环境和云原生平台，包括服务网格和边缘 Kubernetes 支持。Wasm 也有一段时间了，在 2019 年[万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 将其命名为 web 标准，从而成为与 HTML、CSS、JavaScript 并列的第四个 Web 标准。

Docker 容器和容器的结构和功能通常有助于解释为什么竞争用例之间没有太多的重叠。Docker 和 containers 也是 DevOps 的两个选项。如今有许多不同的应用计算架构在使用，如裸机、虚拟机、功能即服务(“FaaS”)以及除容器和 Wasm 之外的其他架构，并且“肯定会有更多，”Levirne 说。“开发人员在选择如何运行代码方面将继续拥有更大的灵活性。容器提供了执行丰富应用程序的能力，这些应用程序使用了当今 Linux 可用的所有开源和商业库、包和工具，同时提供了相对轻量级的隔离能力，”Levirne 说。“Wasm 提供了一种更轻量级的隔离方法，但仅适用于某些类型的绿地应用，这些应用不会利用成千上万个非 Wasm 开源项目中的任何一个。”

Butcher 说，集装箱在两种情况下继续表现出色，“这些情况可能会持续至少几年”。首先，容器仍然是打包未修改的现有应用程序的最简单的选择。因此，现有的“棕色地带”应用程序更容易打包、分发和作为容器运行，”Butcher 说。“第二，数据库和持久数据存储可能会在容器中得到更好的处理。PostgreSQL、MongoDB 和 Redis 都是受益于传统服务器模型的数据服务的例子，在传统服务器模型中，一个进程启动一次，然后不间断地运行几天、几个月甚至几年——我认为 WebAssembly 在相当长的一段时间内不会涉足这两个领域，因为这样做不符合 Wasm 的优势。”

与此同时，Wasm 继续证明自己是一个有价值的选择，可以在许多方面利用其目标二进制结构。这些包括它如何在 CPU 级别上运行，以及消除与容器映像中易受攻击的代码相关的许多风险，以及其他被吹捧的优势。也就是说，Wasm 是“许多人所说的‘业务逻辑’，也就是组成 web 服务产品的应用程序代码”的优秀候选人，[科林·墨菲，](https://www.linkedin.com/in/colin-murphy-08b3601b/)高级软件工程师， [Adobe](https://www.adobe.com/) 告诉新堆栈。在 Adobe 的例子中，这包括使用 Wasm 和 [WASI](https://wasi.dev/) 来允许用户在 Adobe Sign 中签署文档或在 Lightroom 中编辑图像。Murphy 说，与此同时，Docker 将“仍然是其他所有东西最需要的”，例如数据库、代理和网络服务器，它们只运行 NGINX 或 Apache。墨菲说:“更具体地说，这包括任何不符合 WASI 基于能力的安全模式的东西。”。此外，由于 Wasm 的安全模型或其他限制，许多传统应用程序不容易移植

SingleStore 的首席软件工程师 [Bailey Hayes 说，用任意用户代码扩展系统有许多不同的方式，而 Wasm 的独特之处在于它提供了一个可移植的、安全可靠的沙箱，能够以接近本地的速度在进程内运行。](https://www.linkedin.com/in/baileyhayes/)

“对于一个数据库来说，高性能只能通过避免其他解决方案的缺点来实现，例如数据复制、网络通信或进程间通信，”Hayes 说。"这就是为什么我们选择 Wasm 来驱动 SingleStoreDB 中的代码引擎."

同样，安全性是 Wasm 的主要卖点。“wasm 优于 Docker 的主要优势是安全性、性能、模块化和大小，”Murphy 说。"在什么是允许的方面，它也更加严格."

与 Docker 不同，“你不能简单地构建一个大规模的应用程序，将其复制到一个容器中，然后在生产中运行它，”Murphy 说。“这样做有一些好处，因为它防止了低效率，例如运行一个具有 128GB 堆的 JVM，但它也使移植这样的应用程序变得更加困难。原因是 Wasm 本身就是一种语言，”墨菲说。“尽管许多语言都可以编译成 Wasm，但它们最终会受到 Wasm 规范的限制，而且不幸的是，那些已经针对容器化进行了优化，因此获益最少的应用程序最容易移植。也就是说，目前已编译且范围有限的应用程序。”

## 现在的未来

如上所述，Docker 容器和 Wasm 将会有非常独特的用例。当一个容器可以在几分钟内完成这项工作时，为什么有人想开发一种变通方法来用 Wasm 工具启动 Kubernetes 集群呢？这是许多例子中的一个。未来，Wasm 将被广泛采用，因为大多数“应用程序和业务逻辑人员为他们的公司或他们自己的副业项目编写程序”，[首席执行官兼联合创始人](https://www.linkedin.com/in/hectaman)[、](https://cosmonic.com/)利亚姆·兰德尔说。“Wasm 更小，真正跨平台，重量更轻，允许您在任何地方的任何设备上运行它。兰德尔说:“更大和更成熟的工具可能会作为自己的二进制文件或容器运行——想想 Nginx、Postgres、Redis 和其他不太可能从编译到 Wasm 中获得巨大价值的东西(至少在短期内)。”另外，对于那些需要针对数据库之类的东西编写应用程序的人来说，容器仍然是一个很好的开发工具。docker run Postgres 在接下来的一段时间里仍将是一个很棒的开发者体验。换句话说，在不久的将来，构建应用程序将在 Wasm 中完成，而支持工具和软件将可能在容器中运行。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>