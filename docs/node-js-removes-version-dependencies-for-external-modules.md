# Node.js 删除了本机模块的版本依赖性

> 原文：<https://thenewstack.io/node-js-removes-version-dependencies-for-external-modules/>

由于多家公司的合作开源努力， [Node.js](https://nodejs.org/) 开发人员将不再需要在每次升级 Node 时重新编译他们的“原生”模块，这是目前令人头痛的做法。

[N-API 项目](https://nodejs.org/api/n-api.html)将为 Node 生态系统带来更多的稳定性， [Arunesh Chandra](https://www.linkedin.com/in/aruneshc/) 微软高级项目经理[微软 ChakraCore](https://github.com/Microsoft/ChakraCore) JavaScript 引擎，N-API 的贡献者之一，在上周于温哥华举行的 [Node + JS Interactive](https://events.linuxfoundation.org/events/node-js-interactive-2018/agenda/schedule/) 会议上发言。

Node.js 生态系统严重依赖外部模块来扩展为服务器端 JavaScript 运行时编写的程序的功能。大多数是用 JavaScript 编写的，但是有相当一部分——多达 20%——是用其他语言编写的，比如 C (Node 自己的核心语言)和 C++。这些所谓的“本机模块”为节点生态系统提供了丰富的功能。

“Node.js 的成长依赖于这个生态系统。这个生态系统越可靠，Node.js 开发者就会越依赖这个平台，”钱德拉说。

迄今为止，对于维护和使用本机模块的人来说，本机模块都很难维护。每次发布 Node.js 的新版本时，必须为新版本重新编译所有本机模块。因此，包的维护者必须为 Node 的每个版本保留不同版本的模块，而尝试新模块的开发人员会因为模块"[是针对不同的 Node.js 版本](https://stackoverflow.com/questions/46384591/node-was-compiled-against-a-different-node-js-version-using-node-module-versio)编译的消息而不断受挫

IBM Node.js 社区负责人兼 N-API 贡献者麦可·道森解释说，问题是本地模块直接与支持 Node 的 Google V8 JavaScript 运行时引擎交互。所以每次 V8 更新的时候，都会带来一组新的函数调用。基于 JavaScript 的模块不会受到这些变化的影响，因为它们是用 JavaScript 编写的，但是那些直接调用 V8 本身的模块可能需要修改。

“这不是一个成熟的平台应该如何工作，”钱德拉说。

[N-API](https://github.com/nodejs/abi-stable-node) 层(通常读作“皮娜”)旨在通过提供开发人员可以随时写入的稳定 API 来消除这种波动，而不必担心 Node 的底层版本。模块开发人员只需将“node_api.h”头文件添加到他们的 C 代码中，并按照提供的方法照常编译。每个函数都返回一个“NAPI”状态，状态是在模块中用一个作为参数提供的令牌捕获的。

截至上周，LTS(长期支持)Node.js 版本 10、8 和 6(处于“实验模式”)都包含了 N-API 层。

![](img/172ec7d6ebceebd3ef5efe82a1970461.png)

英特尔软件工程师 Gabriel Schulhof。

n-api 只适用于 C 应用程序，尽管一个相关的项目， [node-addon-api](https://github.com/nodejs/node-addon-api) ，提供了一组围绕 API 的 C++包装器，使得 C++程序也可以访问 N-API，英特尔软件工程师 [Gabriel Schulhof，](https://github.com/gabrielschulhof)指出，他帮助了那个项目。Schulhof 还在使 N-API 适应物联网的轻量级[Jerry script](https://github.com/jerryscript-project/jerryscript)JavaScript 引擎方面发挥了重要作用，他在会议上的发言中讨论了这一点。

现在必须做大量的工作来将本机模块移植到 N-API。开发人员应该鼓励他们使用的模块的所有者将他们的模块移植到这个 API，或者开发人员自己也可以这样做。两者的动机都是不再需要担心为每个版本编译模块。开发人员也将享受更快的测试过程，因为模块不再是特定于版本的。该 API 还将使跨不同节点实现使用模块变得更加容易，例如微软的 [Chakracore。](https://github.com/nodejs/node-chakracore)

Dawson 指出，标准化本机模块的 API 层不仅可以使节点开发人员的生活更加轻松，而且由于其易于使用，甚至可以实现一个全新的应用程序类别。例如，一方能够整合一个日志应用程序，这在以前是非常困难的。用 C 语言编写模块会使应用程序具有足够的性能，但是为 Node 的每个版本维护模块是不可行的。在转移到 API 之后，代码变得更容易管理。

“因为你有可能编写一个单独的二进制文件，并让这个二进制文件在不同的版本上运行，人们将开始做他们以前不能做的事情，”Dawson 说。

*Linux 基金会为记者参加这次会议提供了旅行帮助。*

Linux 基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>