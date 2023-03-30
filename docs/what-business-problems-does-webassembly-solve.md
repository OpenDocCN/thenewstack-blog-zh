# WebAssembly 解决了哪些业务问题？

> 原文：<https://thenewstack.io/what-business-problems-does-webassembly-solve/>

B.Cameron Gain 是 ReveCom Media Inc .的创始人，该公司为 Cosmonic 提供咨询服务。

[WebAssembly](https://thenewstack.io/what-is-webassembly/) (俗称 Wasm)当然是云原生界的热门话题。五月份在 KubeCon+CloudNativeCon EU 上发布的一份关于服务网格的 [CNCF 调查](https://www.cncf.io/wp-content/uploads/2022/05/CNCF_Service_Mesh_MicroSurvey_Final.pdf) 表明了服务网格插件对 Wasm 等环境的重要性，有 25%的受访者表示。在最近举行的 KubeCon+CloudNativeCon EU 上，就 wasm 是什么，更重要的是，它能做什么，进行了大量的讨论。

吸引了一些注意力的更有趣的讨论之一是，由于其设计，WebAssembly 如何在许多情况下取代 Docker。但是正如我们将在本文下面看到的，过度关注 WebAssembly 的这一方面是没有抓住重点的，因为更重要的是 WebAssembly 可以支持的业务用途，如下所述。事实上，就像任何有趣的新编程语言或技术一样，Wasm 价值的真正测试是其商业用途(Adobe、微软和提供 [wasmCloud](https://thenewstack.io/webassembly-the-future-of-cloud-native-distributed-computing/) 的 [Cosmonic](https://thenewstack.io/cncf-welcomes-webassembly-based-wasmcloud-as-a-sandbox-project/) 已经将 Wasm 解决方案推向市场)。

WebAssembly 可以用来将[JavaScript(JS)](https://developer.mozilla.org/fr/docs/Web/JavaScript)[c++](https://fr.wikipedia.org/wiki/C%2B%2B)和[Rust](https://www.rust-lang.org/fr)除了 HTML 和 CSS 之外，还可以以二进制格式集成到一个单独的运行时平台，直接在 CPU 上的机器级别上运行。它不仅可以用于支持 Web 应用，还可以扩展到任何运行在 CPU 上的边缘环境和云原生平台，包括服务网格和边缘 Kubernetes 支持。Wasm 也有一段时间了，之前 [万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 将其命名为 2019 年的 web 标准，从而成为与 HTML、CSS、JavaScript 并列的第四个 Web 标准。

## 便携性和一致性

Wasm 提供的主要优势之一是其可移植性和一致性，这使得安全性和合规性更易于管理(同样，它在 CPU 级别上以二进制格式运行)。“从逻辑上讲，WebAssembly 给了你一个你可能以前听说过的承诺:编写一次，在任何地方运行，你以前可能听说过 Java 或 SilverLight，或 Flash，或以前的技术之一，但 WebAssembly 的不同之处在于，这是社区驱动的和开放的，”[Cosmonic 首席执行官兼联合创始人利亚姆·兰德尔](https://www.linkedin.com/in/hectaman)在 KubeCon+CloudNativeCon 期间由 New Stack 主办的播客中说。“如今，它已经嵌入并支持桌面和移动设备上所有最现代的浏览器平台。因此，每个人都可以开始使用 WebAssembly，它的工作方式就像一个小小的 CPU——你甚至可以将 web assembly 放在其他应用程序中。”

然而，虽然 WebAssembly 可以提供一些漂亮的基准测试，并在堆栈级别上提供多种效率，但它只能提供尽可能好的业务用途。边缘计算是 Wasm 开始大放异彩的一个例子。这是因为将编译后的代码分发到任何可以运行标准浏览器的设备的能力为一系列边缘用例创造了条件，Enterprise Management Associates 的分析师 Torsten Volk 告诉 New Stack。

“编译后的代码通常比首先必须由主机设备解释的代码运行得快得多。这使得边缘设备能够实现更高水平的功能，例如企业应用或机器学习能力，因为消耗的 CPU 和电源资源更少，”Volk 说。“Wasm 将现已废弃的 Flash 或 Silverlight 技术的优势引入到任何浏览器中，但不依赖于任何特定的供应商。”

Volk 说, Wasm 的社区驱动方法应该解决“扼杀了这些其他客户端技术”的安全性和兼容性挑战。“此外，这使得 JavaScript 开发人员能够调用编译的 C++函数，反之亦然，从而使 JavaScript 开发人员能够利用编译语言的优势，”Volk 说。

## 商业宣传

那么你能用 Wasm 做什么呢？

在 KubeCon + CloudNativeCon 共址活动“Cloud Native Wasm Day Europe”期间，展示了编译为 Wasm 的 CMS 如何支持云计算公司 [Fermyon 的](https://www.fermyon.com/) 网站。WebAssembly 在该公司提供的产品中也发挥了重要作用。“我们的想法是，作为一家进入新领域的新公司，进行许多 SEO 性能优化非常重要，”[Matt Butcher](https://www.linkedin.com/in/mattbutcher/)Fermyon的首席执行官在他的演讲中说。对我们来说，一件重要的事情是，如果我们要告诉人们关于 WebAssembly 的信息，那么我们需要人们找到我们，以便他们能够阅读关于 WebAssembly 的信息。所以我们花了大量的时间预先设计 CMS，以便资源的排序是正确的。我们决定遵循最佳实践的所有规范……我们将所有这些都内置于其中，这样一来，当一个作者在写一篇内容时，除了“我需要一个好的吸引人的标题”之外，他们就不必考虑 SEO 了。所以，这是我们早期关注的一个非常有趣的焦点。”

Fermyon 的创始人还想给网站设计者“以他想要的方式做事”的自由，允许他选择他想要的主题引擎、CSS 框架和 JavaScript 库。这些都被纳入到“一个系统中使用的非常庞大的一批功能中，人们说，‘我不知道，它可能还没有准备好投入生产。我不确定你能造出什么东西，”布彻在他的演讲中说道。“所以，我们真的接受了这个挑战，说‘我们认为我们可以用今天的 WebAssembly 做一些非常酷的东西。’”

数据堆栈上的计算和数据之间的分离增加了延迟并导致其他问题，这对于流、边缘连接和其他分布式应用来说尤其麻烦。基于 Wasm 的在线计算可以消除数据和计算之间的筒仓，Fluvio 项目的创始人兼数据智能平台提供商的联合创始人[infin yon](https://www.infinyon.com/)seh yo Chang在他的演讲中说道。这是通过数据流开源 Fluvio 的 Wasm 实现来实现的，它创建了一个分布式流平台。

Chang 描述道:商业意义是巨大的。为了创造 Chang 在演讲中描述的“实时经济”，Wasm 的配置可以显著降低数据流之间以及数据库和记录系统之间的现有延迟。由于 Wasm 相对简单的二进制计算结构，应用程序和代码更容易审计和执行安全策略。“这是数万亿美元将被制造或损失的地方，”常说。"拖拉机最重要的部分是延迟."

在一个数据流应用程序中，Chang 展示了 Wasm 是一个“游戏规则改变者”，它将隔离与可移植性结合起来，“允许我们通过将它们扁平化为统一的堆栈来重塑我们的计算基础设施和数据集，”Chang 说。“这种堆栈可以从边缘环境到云环境，并且可以跨越大洲和不同的位置。

## Adobe 将 Wasm 推向边缘

Wasm 在 Adobe 公司也很常用。作为 [Colin Murphy、](https://www.linkedin.com/in/colin-murphy-08b3601b/) 高级软件工程师、[Adobe](https://www.adobe.com)，他在演讲期间详细介绍了 CDN edge compute 和 Wasm/[WASI](https://wasi.dev/)平台，以及现在和未来的 Adobe 应用。“我们在 Adobe 有很多 C++代码，这是人们想要的伟大产品的伟大代码。而 WebAssembly 允许你做的就是将代码带入浏览器，”墨菲说。“因此，如果没有它，我们就无法将 Photoshop 和 Acrobat 引入浏览器……Adobe 做了大量工作来改进 WebAssembly 标准，以实现更高的性能和更好、更快的内存访问，诸如此类。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>