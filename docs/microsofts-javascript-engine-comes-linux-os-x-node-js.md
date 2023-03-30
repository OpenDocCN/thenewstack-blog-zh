# 微软的 JavaScript 引擎来到 Linux，OS X 和 Node.js

> 原文：<https://thenewstack.io/microsofts-javascript-engine-comes-linux-os-x-node-js/>

去年，微软[一直致力于](https://thenewstack.io/microsoft-chakra-javascript-engine-node/)使其 Chakra JavaScript 引擎开源和跨平台。在最近的[节点峰会](http://nodesummit.com/)会议上，来自微软 Chakra 团队的[阿曼达·斯尔沃](https://twitter.com/amandaksilver)和[阿鲁内什钱德拉](https://twitter.com/aruneshc)展示了开源 [ChakraCore](https://github.com/Microsoft/ChakraCore) 解释器和运行时在 x64 Ubuntu Linux 和 OS X 10.9+上的“实验性实现”。

他们还演示了运行一个版本的 [Node.js](/tag/node.js/) 的 ChakraCore。

西尔弗告诉我们，现在还为时尚早。“就 Linux 而言，到目前为止，我们实际上只支持一个版本。我们尚未针对这些操作系统的性能进行优化。我们从物联网类型场景的客户端工作负载入手，但还没有针对服务器端场景进行优化；这是一项正在进行的工作。我们当然不会说这应该在生产环境中广泛应用。”

虽然还很早，但 Chakra 团队希望展示他们正在取得的进展，以使社区保持在循环中。Silver 还指出，在 ChakraCore 上有越来越多来自微软以外的开发者的参与；"它越来越成为一个社区网络项目."

有一个特性在 NodeSummit 上特别受欢迎；时间旅行调试。“这允许您在调试器中创建一个后退按钮，”Silver 解释说，“这是一个很酷的功能，如果您想了解各种生产和测试环境中发生了什么，这也是非常重要的。”

## 一个节点，多个引擎

她认为，让多个虚拟机可用于节点将会促进这种创新。“我们有越多的行业参与者在节点堆栈上工作，越多的开发者在节点堆栈上体验，你就会看到越多的创新。”

她认为，允许多个虚拟机所需的节点标准化也对此有所帮助。“确保有一个广泛的工具生态系统来帮助推动节点社区和体验向前发展，也取决于启用多个引擎。如果你考虑像调试这样的事情，最终会在运行 Node 的 JavaScript 部分的核心 VM 中创建钩子。因此，这其中的一部分就是创建一套跨不同核心引擎工作的诊断功能和 API。”

在 Node 中拥有多个虚拟机可以帮助[避免开发单一文化](https://www.christianheilmann.com/2016/07/27/why-chakracore-matters/)，就像拥有多个浏览器一样。

Web 应用框架 [Ember.js](http://emberjs.com/) 的创建者汤姆·戴尔和 Salesforce 开发者传道者[艾米丽·罗斯](https://twitter.com/nexxylove)都认为这是一个积极的发展。“使节点与引擎无关可以释放有利于开发人员的竞争。我很高兴看到微软正在解决这个问题，”[戴尔发推文](https://twitter.com/tomdale/status/758353553618591744)罗斯[指出](https://twitter.com/nexxylove/status/758392064367218688)这项工作超越了查克拉。

https://twitter.com/nexxylove/status/758392064367218688

正如 Silver 所说，“去年决定由 Node 基金会管理 Node 的目的是提高人们对 Node 的可靠性和信心，因为有多个行业赞助商在管理 Node 的未来。就确保我们能够定义一个通用的 JavaScript 接口，在 JavaScript 运行的任何地方都能工作而言，这确实取决于有多个赞助商。”

随着 Node 在服务器和客户端上的应用越来越广泛，人们对多虚拟机的兴趣也在增加，尤其是对 ChakraCore 的兴趣。“基于 Node 构建自己的堆栈或平台的行业合作伙伴希望能够选择支持替代引擎。”

她解释说，对微软来说，最初的推动力是物联网，这不仅仅是因为谷歌 V8 JavaScript 引擎 Node 目前所依赖的版本不能用于运行在 ARM 芯片上的 Windows。

“有一个针对 Windows 优化的最小 JavaScript 引擎是很重要的。当你考虑物联网中的低端设备时，你真的只想有一个 JavaScript 引擎，”她说。

然而具有讽刺意味的是，将 Node 引入 Windows IoT 意味着将 Chakra 引入 Windows 之外的平台。“对于任何人来说，看到 ChakraCore 并认真对待它，它需要不仅仅是 Windows 的东西，”Silver 解释说。"它需要能够与节点周围已经存在的工具生态系统一起工作."

那会包括像 [Electron](https://thenewstack.io/electron-brings-cross-platform-javascript-apps-to-the-desktop/) 这样的客户端外壳吗？尽管微软没有就此发表任何声明，Silver 将此与微软对待 [Cordova](https://cordova.apache.org/) 框架的方式进行了比较。“我们针对 Windows 的方法是让 Cordova 应用程序本质上是 Windows 上的原生应用程序，这意味着它们使用 Chakra 引擎来执行。这样做的原因是为了确保应用程序的有效负载非常小，并且运行时针对 windows 操作系统进行了优化。因此，这与我们对[节点和]物联网设备的基本原理非常相似，你可以推断出在 Windows 上运行 JavaScript 的各种应用框架意味着什么。”

创建一个可以支持 Node 的 Chakra 版本并不意味着微软试图让开发者停止在 Node 上使用 V8，无论是在 Azure 上还是在他们使用 Visual Studio 和 VS Code 等微软开发工具时。

“关于 Azure 和我们的工具体验，我们的主要关注点仍然是现有的基于 V8 的节点生态系统，”Silver 向开发人员保证。“在 VS 代码中，当您构建节点应用程序时，您是在针对 V8 构建的，除非您有意将其设置为 ChakraCore。我们预计许多人将继续使用 Node 来对抗 V8。我们为此提供了出色的工具体验，我们的承诺是继续为节点开发人员提供最佳的工具体验。”

专题图片:阿曼达·斯尔沃在峰会上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>