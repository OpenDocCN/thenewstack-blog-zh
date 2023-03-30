# WebAssembly 真的是未来吗？

> 原文：<https://thenewstack.io/is-webassembly-really-the-future/>

[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 最近的[年度调查](https://www.cncf.io/reports/cncf-annual-survey-2022/)包括一个关于 [WebAssembly (Wasm)](https://thenewstack.io/how-webassembly-could-streamline-cloud-native-computing/) 的大胆声明:“容器是新常态，WebAssembly 是未来。”

这个声明预示了很多事情，不仅是关于 WebAssembly 的路线图和开发，还有它在计算中的当前位置。据《CNCF》报道，已经有 37%的最终用户组织拥有使用 WebAssembly 部署应用程序的经验。根据 CNCF 的报告，虽然这些用途中有许多是为了测试 Wasm 的优点，但是 [WasmEdge](https://wasmedge.org/) 和 [WAMR](https://github.com/bytecodealliance/wasm-micro-runtime) 是使用最多的运行时。

“WebAssembly 是未来的趋势，因为它越来越多地用于无服务器、容器化和插件技术，预计将对 web、无服务器、游戏和容器化应用产生重大影响。CNCF 生态系统负责人 Taylor Dolezal 在一封电子邮件回复中告诉新堆栈。

但是 WebAssembly 的采用将走向何方，它的路线图和未来在计算中的位置是什么样的？再来看看 Wasm 在[容器](https://thenewstack.io/containers/)、 [edge](https://thenewstack.io/edge-computing/) 等应用、[编程语言](https://thenewstack.io/25-most-popular-programming-languages-used-by-devops-pros/)和无服务器方面的集成和未来。

## 未来现在

可以说，Wasm 不是关于未来的，但当它在所有主要的 web 浏览器中使用时，它已经非常关于现在了。但是，尽管 Wasm 在浏览器方面已经成熟，但在它成为未来的一部分之前，它在后端应用程序中的使用还需要做更多的工作，例如在边缘设备中的使用和部署。

事实上，这并不像将 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) 添加到 Wasm 中，然后通过 Wasi 运行包那么简单，Wasi 托管 Wasm 运行时。对于 Python 专门适应的后端应用程序，如[机器学习](https://thenewstack.io/machine-learning/)和数据分析，其在 Wasm 中的应用非常依赖于一系列第三方依赖项，这些依赖项目前正在开发和编译中。

Wasm [平台即服务(PaaS)](https://thenewstack.io/pipelines-paas-continuously-delivering-continuous-delivery/) 产品或平台尚不存在，无法轻松用于将 WebAssembly 借给后端应用程序。换句话说，Wasm 在浏览器之外的应用才刚刚兴起。

Enterprise Management Associates 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉 New Stack 说:“在可靠、高效地支持生产用例方面，还有很多工作要做。”。“我们将在前进的道路上发现到底还缺少什么。这时，开源项目和商业供应商就来弥补这些差距，并提供最好的开发人员和 [DevOps](https://thenewstack.io/the-what-why-and-how-of-devops/) 体验。”

区分服务器端(ss-Wasm) WebAssembly 与浏览器应用的 Wasm，ss-Wasm 有很大的前景，尽管 ss-Wasm 的采用道路是漫长的，而且“它的大部分仍然需要映射，” [Wiqar Chaudry，](https://www.linkedin.com/in/wiqar?miniProfileUrn=urn%3Ali%3Afs_miniProfile%3AACoAAACh3tYBq_83ujeBLYcODDpkucuxdpr-KhU&lipi=urn%3Ali%3Apage%3Ad_flagship3_detail_base%3B1rTin6PqQiaHocGCcz1%2FHA%3D%3D)Xymbia 的首席执行官和创始人告诉新的堆栈，xy mbia 提供一个项目协作平台。

“有两个非常简单的衡量标准:在创建软件时，Wasm 是否有明确的经济价值主张？它是降低了成本，帮助公司和开发者赚了更多的钱，还是有助于释放其他类型的未实现价值？”乔德里说，他也参与了 Wasmer 项目，目前担任顾问。

“第二是它的技术价值主张。它是否吸引了足够多的开发人员，并解决了足够多的技术难题，让他们承担使用 Wasm 作为其堆栈一部分的开销？”

## 找到 WASI 了吗？

目前，WASI 已经成为将 Wasm 延伸到浏览器之外的最佳候选人。被描述为 WebAssembly 的[模块化系统接口](https://wasi.dev/)，它被证明有助于解决在任何有正确配置的 CPU 的地方运行 Wasm 运行时的复杂性——这是 WebAssembly 自创建以来的主要卖点之一。

Fermyon Technologies 的联合创始人兼首席执行官马特·布彻(Matt Butcher)对新堆栈表示:“我认为，将 WebAssembly 作为通用技术解锁的关键特性是支持 [WebAssembly 系统接口(WASI)](https://thenewstack.io/mozilla-extends-webassembly-beyond-the-browser-with-wasi/) 、[。“WASI 允许开发人员在他们的代码中使用熟悉的系统习惯用法，比如打开文件和读取环境变量，但不会破坏 WebAssembly 安全模型。随着 WASI 支持的普及，我们将看到 WebAssembly 用例的激增。”](https://www.linkedin.com/in/mattbutcher/)

然而，WASI 仍在不断成熟。“WASI 的第一版让我们看到了 WebAssembly 的潜力。第二个版本 preview 2 将在几个月后推出，”Butcher 说。"在 preview 2 中加入网络将会带来大量的新用途."

Cosmonic 首席执行官兼联合创始人 [Liam Randall](https://www.linkedin.com/in/hectaman) 表示，WebAssembly 将利用组件和 WASI，将通用应用程序库抽象为通用可插拔组件。他说，像发布-订阅消息或特定的 SQL 服务器这样的组件是作为抽象提供给应用程序的，而不是紧密耦合到特定的库。

兰德尔说:“当容器出现时，它们更小，启动更快，给开发人员提供了比虚拟机更小的配置和维护空间。”。“WebAssembly 模块延续了这一趋势，更小，启动更快，并利用组件减少开发人员编写和维护的代码量。

“更重要的是，组件模型是一种新的应用程序方法，支持功能驱动的安全性，并使平台运营商更容易安全地运行应用程序。”

Dolezal 说，Wasm 将 WASI 用于系统级集成 API 进一步增加了其作为通用运行时的可行性:“WebAssembly 在安全环境中托管不可信代码的能力也是一个显著的优势。”

## 容器关系

正如 CNCF 报告所说，容器确实是“新常态”，尤其是在云原生空间。在某些用例中，Wasm 可以取代容器，但总的来说，WebAssembly 和容器的采用将同步增长。

“我绝对相信 Kubernetes 和 Wasm 是互补的产品，其中一个 Kubernetes 负责提供和扩展基础设施，而另一个 Wasm 在此基础设施上提供应用程序，包括其运行时，”Volk 说。

Kubernetes 的采用路径可以作为 Wasm 如何以及何时大规模采用的可能模型。“Kubernetes 被广泛采用，因为使用 Kubernetes 和工具来使用它，扩展它和支持它是广泛可用的，”Chaudry 说。“如果 Kubernetes 不像 AKS、EKS 或 GKE 那样容易获得，我们会看到更少的采用和使用。WebAssembly 将沿着相同的弧线运行。

Wasm 也只解决了容器所面临的一些问题，他说:“容器更复杂，运营开销也更大。两者之间的权衡使得两者协同发展似乎是合理的。”

Butcher 说，当 DockerHub 开始支持新的工件存储规范时，Wasm 社区意识到，现在可以将 Wasm 运行时存储在[开放容器倡议](https://thenewstack.io/oci-reveals-governance-structure-amid-debate-focus/)注册表中，如 Docker Hub。

例如，本月，Fermyon 的 Spin 0.8 开始支持 OCI 注册表。“虽然我们最初不确定 OCI 注册中心是否是正确的分发机制，但标准的演变加上 Docker Hub 的支持改变了我们的想法，”Butcher 说。"我们致力于使用 OCI 注册中心分发 WebAssembly 应用程序，并且现在就可以做到."

* * *

要了解关于 WebAssembly 的更多信息，请查看 2022 年北美开源峰会上对 Fermyon Technologies 的 Matt Butcher 关于 Wasm 未来的采访:

[https://www.youtube.com/embed/ldtcX5s2SVM](https://www.youtube.com/embed/ldtcX5s2SVM)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>