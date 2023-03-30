# Node.js Foundation 在 Node.js API、ChakraCore 基础上加倍努力

> 原文：<https://thenewstack.io/node-js-foundation-cites-progress-node-js-api-chakracore/>

[Node.js 基金会](https://nodejs.org/en/foundation/)正致力于使 [Node.js](/tag/node.js/) 服务器端 JavaScript 运行时能够在其熟悉的[谷歌 V8](https://developers.google.com/v8/) JavaScript 引擎之外的环境中运行，这一努力被称为“虚拟机中立”

Node.js 基金会的 Node.js API [工作组](https://nodejs.org/en/about/working-groups/)和 [ChakraCore](https://thenewstack.io/microsoft-chakra-javascript-engine-node/) 项目正在采取措施，确保 Node.js 除了 V8 之外，还可以与不同的虚拟机(VM)一起工作，以便节点开发者可以有更多的选择，并针对不同的移动平台，该基金会在本周于奥斯汀举行的 Node . js Interactive North America 2016 大会上宣布。

Node.js 作为物联网应用程序的首选平台已经很受欢迎，因为 Node.js 可以在三星的 [JerryScript](https://github.com/jerryscript-project/jerryscript) 引擎上使用，这是一种用于物联网的轻量级 JavaScript。

此外，该基金会在一篇博文中表示，当 Node.js 未与特定虚拟机关联时，开发者可以将它与不同的虚拟机配对，以满足移动应用的特定需求，将 Node.js 的优势——易用性、更高密度的编码和性能——扩展到更多的移动应用开发者。

根据 Node.js 基金会的说法，VM 中立性描述了 Node.js 的一种状态，其中节点核心对于通过开放标准和开放 API 驱动它的 JavaScript 引擎是中立的。

“这个想法是在 Node.js 和它的 VM 之间创建一个更正式的接口，”基金会在一份声明中宣称。“在虚拟机中立的世界中，Node.js 生态系统，尤其是本机模块，将继续在各种不同设备和工作负载上的不同 js 虚拟机上无缝工作。”

VM 中立性使 Node.js 能够支持新的设备和工作负载，并使开发人员能够扩展 Node.js 生态系统的范围。它还有助于开发人员重用代码和标准化多虚拟机工作。

Node.js 基金会的社区经理 Mikeal Rogers 在一份声明中说:“基金会的很大一部分工作都集中在提高 Node.js 的通用性和信心上。“Node.js API 努力支持我们将 Node.js 传播到尽可能多的不同环境的使命。这是一个大型社区网络项目的开始，将为虚拟机带来与浏览器领域相同的竞争和创新。”

在 Node.js Interactive 上，Node.js 基金会宣布了其 [Node.js API](https://nodejs.org/api/) (NAPI)努力定义一个独立于 V8 版本变化的稳定模块 API 的新里程碑。这将给模块维护者和开发者更多的稳定性和更多的模块选择，从而使事情变得更容易。

Node.js 模块社区拥有 350，000 个模块和超过 10 亿的每周包下载量。Node.js API 工作使模块能够针对较新版本的 Node.js 运行，而无需重新编译。

IBM 运行时开发人员[麦可·道森](https://developer.ibm.com/node/category/michael-dawson/)在一份声明中说:“由于独立于 Node.js 版本的变化，Node API 的这项工作将导致模块生态系统的更大稳定性，在推出新的 Node.js 版本时给予开发人员更大的灵活性。”。"此外，这一增强是朝着虚拟机中立的战略最终目标迈出的具体一步."

与此同时，Node.js 基金会还宣布，Node.js 构建系统将开始每晚生成 **[node-chakracore](https://github.com/nodejs/node-chakracore)** 构建，使 Node.js 能够与微软开发的 ChakraCore JavaScript 引擎[一起使用。](https://thenewstack.io/microsofts-javascript-engine-comes-linux-os-x-node-js/)

微软[将](https://thenewstack.io/microsoft-chakra-javascript-engine-node/) [ChakraCore](https://github.com/Microsoft/ChakraCore) 描述为 Chakra 的核心部分，Chakra 是一个高性能的 JavaScript 引擎，支持以 HTML、层叠样式表(CSS)和 [JavaScript](/tag/javascript/) 编写的微软 Edge 和 Windows 应用程序，这是网络的三项基础技术。

微软表示，ChakraCore 支持 x86/x64/ARM 的 JavaScript 实时(JIT)编译、垃圾收集和广泛的最新 JavaScript 功能。ChakraCore 还支持 [JavaScript 运行时](https://github.com/Microsoft/ChakraCore/wiki/JavaScript-Runtime-(JSRT)-Reference)(JSRT)API，这使得开发人员可以轻松地将 ChakraCore 嵌入到他们的应用程序中。

微软 ChakraCore 高级项目经理 Arunesh Chandra 在会上展示了 NAPI 和最新的 ChakraCore 开发。

“允许 Node.js 在多个引擎上工作，使 Node.js 能够以高度优化的方式在各种不同的系统上运行——包括物联网系统，”微软的钱德拉在一份声明中说。他指出，微软与社区的合作将刺激更多创新，为 Node.js 开发者创造更多选择。

此外，该基金会表示 **node-chakracore** 正在努力改进 Node.js 中的时间旅行调试。 [JavaScript 时间旅行调试器](https://www.microsoft.com/en-us/research/project/javascript-time-travel-debugger/)项目来自微软研究院。微软表示，该调试器支持调试器中步进操作的反向变化，使开发人员能够轻松逆转程序执行时间，以查看导致错误的语句和程序值的确切序列。

NodeSource 的首席技术官和联合创始人[丹·肖](http://dshaw.com/)在一份声明中说:“在改善 Node.js 如何与底层 JavaScript VM 交互和管理期望的技术状态方面，已经取得了巨大的进步。"查克拉核心的完全开源性质使得测试新功能变得极其容易."

![nodeinteractive](img/1e37a90981582c9a2c70cc96be9eb230.png)

专题图片:[奥斯汀街头艺术](https://www.instagram.com/p/BHvqUfojr2M/?taken-by=joabjack)，由北四。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>