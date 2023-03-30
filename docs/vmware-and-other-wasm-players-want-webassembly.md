# VMware 和其他 Wasm 玩家想要 WebAssembly

> 原文：<https://thenewstack.io/vmware-and-other-wasm-players-want-webassembly/>

到处都有迹象表明:WebAssembly 将会是一件大事。在万维网联盟(W3C)在 2019 年将 WebAssembly 或 Wasm 命名为 HTML、CSS 和 JavaScript(Wasm 迄今为止的基本语言)的 Web 标准后不久，这一点已经变得很明显。因此，虽然 web 浏览器应用程序代表了 Wasm 的核心和历史用例，但这并不是 Wasm 的潜力所在。

因为它被设计成允许在 Wasm 中运行的应用程序在任何有适当配置的 CPU 的地方运行，所以有一个 Wasm 运行时用于 CPU 架构。Wasm 有望成为一个非常重要的计算结构。这是因为 Wasm 允许部署和分发的应用程序需要管理的安全层更少，同时在众多设备上部署所需的配置更少，运行时结构相对较小，因此在跨网络部署时具有较低的延迟。很明显，它可以很好地适应无服务器应用程序的新目标环境或代码可能在处理器上运行的任何地方，如物联网或其他边缘设备。

## VMware Wasm 实验室

在这种背景下，大约两年前， [VMware](https://www.vmware.com/) 的高级主管、 [Bitnami](https://bitnami.com/) 的首席执行官[丹尼尔·洛佩斯·里德鲁埃霍](https://www.linkedin.com/in/ridruejo)是 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 和其他地方的少数工程师和技术高管之一，他认识到 Wasm 不仅仅是帮助广泛改善浏览器体验。VMware Wasm 实验室是由 VMware 首席技术官办公室的一个团队组建的。

“没有人真正弄清楚一切将如何运作，但我意识到已经发生了变化，”Ridruejo 说。“我来到 VMware 的领导层，我说‘嘿，我们应该关注这一点。’"

在不需要创建一个正式部门来支持 Wasm 相关的开源项目、开发、与基础设施和网络拓扑的集成或为 Wasm 开发应用的情况下，技术领导者几乎总是在生产中使用 Wasm，或者作为 VMware 之外的沙盒项目。

“Wasm 是一项强大的核心技术，它延续了 Bitnami 最初设想的企业应用商店的辉煌故事。企业管理协会(EMA)的分析师 Torsten Volk 表示:“这些人接近于创建一个通用的应用商店，用于复杂企业应用的简单和一致的跨平台部署，但由于目标基础设施环境的极端多样性，最终未能实现交钥匙部署。”。“Wasm 消除了这种复杂性，并最终使这种针对企业应用的交钥匙应用商店成为可能。”

## 没有保证

在这一点上，我们仍然没有处于 Wasm 复兴时期。虽然使用 JavaScript 运行浏览器应用程序变得非常流行，但要让 Wasm 正确地集成其他语言，还有许多工作要做。仍然需要在 Wasm 上正确地创建层，这将允许它充分发挥其潜力，允许跨多个设备和网络创建和部署单个应用程序配置。

“当然，在语言和基础设施集成方面还有很多功课要做，但 Wasm 的人在正确的道路上，所有这一切都需要一些耐心和对目前创建这些集成的人的一些投资，”Volk 说。“Wasm 不仅有效，而且编程和部署都非常简单，这将是关键所在。”

为了帮助提供缺失的链接，为 Wasm 的采用铺平道路，VMware 的 Wasm 实验室发起了 Wasm 语言运行时项目。Ridruejo 说，这个想法是“为寻求采用 WebAssembly 的开发者提供基本的构建模块”。Ridruejo 说，语言运行时项目可以与其他项目一起使用，如 mod_wasm(用于运行传统的 web 应用程序，如 WordPress)，Wasm Workers Server(用于运行 edge/serverless 应用程序)或其他开源项目，如 Fermyon 的 Spin。

“增加语言支持对整个 Wasm 社区非常有益——Wasm 要取得成功，必须支持大约 20 种语言，” [Fermyon Technologies，](https://thenewstack.io/webassembly-5-predictions-for-2023/)的联合创始人兼首席执行官马特·布彻说。“Wasm 实验室首次为 Wasm 发布了 PHP，这是一个辉煌的开局之举。我放下了一切，去尝试它，甚至添加了对 [Fermyon](https://www.fermyon.com/?utm_content=inline-mention) Spin 的支持。”

与此同时，在 Fermyon 的 Spin 案例中，VMware 的 Wasm 语言运行时项目是有益的，因为“在不需要大量设置和集成工作的情况下，Spin 不支持运行固定的 web 应用程序，”Volk 说。“Wasm 语言运行时为流行的企业应用程序提供交钥匙运行时，我相信，它支持安装当今最热门的数据科学库，如 [Pandas](https://pandas.pydata.org/) 和 [Numpy](https://numpy.org/) 。”

## Python 连接

为了让 [Wasm](https://thenewstack.io/wasm-for-the-frontend-a-look-at-developer-uses/) 实现其在浏览器之外的潜在用例，如[边缘设备](https://thenewstack.io/the-benefits-of-using-microservices-for-edge-devices/)，后端服务器应用和物联网，Wasm 将需要能够比现在更好地适应 Python。

“Python 是一种灵活的语言。它在服务器端 web 开发、UNIX 系统中的数据和 ML、脚本和其他地方都发挥着重要作用，”Butcher 说。“当像这样的通用脚本语言在 Wasm 中得到很好的实现时，我们可以看到 Wasm 的应用范围。”

至此，围绕 Python 的核心工作已经完成(感谢 VMware，也感谢发起 CPython 工作的[Christian Heimes](https://www.linkedin.com/in/christianheimes/?originalSubdomain=de)), Butcher 说。“也就是说，我们有运行时间。有粗糙的边缘需要打磨，但 Python-in-Wasm 是可用的，”Butcher 说。“在接下来的几个月里，我们将开始看到开发人员如何在 Wasm 领域应用 Python。如果说在 Wasm 领域 Python 需要一个主要的东西，那就是对 Numpy 和 Pandas 的支持。”

Volk 说，Python 的巨大吸引力在于“有一个用于一切的库”。“因此，开发人员可以围绕这些库创建功能丰富的应用程序，而不必担心幕后的工作原理。例如，如果我想从不同的 API 中获取数据，以便在我自己的应用程序中使用，我不必创建大部分的 API 集成，也不必考虑如何将结果数据流写入我的 SQL 或 NoSQL 数据库——有现成的库可以为我完成所有这些工作，”Volk 说。“我需要做的就是将它们链接在一起，并给它们传递一些参数。一旦我在 Wasm 中有了做这一切的自由，我们将很快实现大规模采用。”

[VMware](https://thenewstack.io/vmware-targets-the-platform-engineer/) 最近增加了对 Wasm 语言运行时的 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) 支持。根据该项目的文档，在其文档中，Wasm 语言运行时提供了流行的语言运行时，如 Ruby 和其他语言以及 Python，它们预编译为 WebAssembly，经过兼容性测试，并在上游语言的新版本发布时保持最新。

它为 wasm32-wasi 目标提供了一个 Python 构建。基于 CPython(Python 的主流、基于 C 的实现)中已经可用的 WASI 支持，额外的库和使用示例使其尽可能易于使用，以增强运行时，VMware 的员工工程师 [Asen Alexandrov](https://www.linkedin.com/in/asen-alexandrov-5546a122?originalSubdomain=bg) 在一篇博客文章中写道。

“我们的目标是尽可能与上游项目合作。去年晚些时候，CPython 增加了对 WASI 的支持，这非常棒，”Ridruejo 说。" SingleStore 和 Fermyon 是这一领域 Python 工作的先驱."

Ridruejo 说，有趣的是，VMware 并不关注运行时性能，而是关注与最大数量应用程序的兼容性。“为此，我们目前正致力于添加尽可能多的第三方库支持和相关依赖项，如 libXML 和图形处理库。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>