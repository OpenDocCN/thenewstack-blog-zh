# Node.js vs TypeScript |新堆栈

> 原文：<https://thenewstack.io/what-typescript-brings-to-node-js/>

StackOverflow.com 根据每月被问问题的数量对计算机语言进行排名。虽然 Python 语言已经领先了一段时间，但是 JavaScript 仍然稳坐第二的位置。这既代表了开发人员的兴趣，也在某种程度上代表了对不同语言细微差别的熟悉。经验丰富的开发人员不像新手那样依赖 StackOverflow.com 来完成他们的工作，但它仍然可以提供快速帮助。

理解这两种技术的互补性需要对术语进行定义。Node.js 和 TypeScript 都深深植根于来自 Java 语言的 JavaScript。对于本文的剩余部分，我们将把术语工具归属于 Node.js 和 TypeScript，即使您可以将 TypeScript 定义为一种语言，将 Node.js 定义为一个平台或运行时环境。

## Node.js 和 TypeScript 的历史

检查 Node.js 和 [TypeScript](https://thenewstack.io/what-is-typescript/) 的遗产需要一点历史教训。这两种工具都将它们的语言语法追溯到 Java，Java 是詹姆斯·高斯林在 20 世纪 90 年代中期在太阳微系统公司开发的。Java 语言[的设计者](https://thenewstack.io/typescript-vs-javascript/)设想了一种语言，这种语言能够实现“一次编写，随处运行”的概念(WORA)。这将需要一个适用于每个操作系统的运行时系统，以允许跨各种平台的语法兼容性。

WORA 最初的想法在现代网络浏览器中依然存在。目前使用的所有流行的 Web 浏览器都支持在浏览器中运行 JavaScript 或 TypeScript。作为 JavaScript 语言的超集， [TypeScript](https://docs.microsoft.com/en-us/learn/modules/typescript-get-started/2-typescript-overview) 采用静态类型检查来允许变量的一致使用，并减少编程错误的潜在来源。

## 静态打字

TypeScript 将静态类型的概念引入了 JavaScript 语言。其他包含静态类型的流行语言包括 C、Java 和 Rust。静态类型要求变量在声明或第一次使用后保持类型一致。相反的是像 Python 这样的动态类型语言，它允许变量动态地改变类型。维护类型一致性可以通过像 [Flow](https://flow.org/) 这样的工具来验证，以寻找有问题的代码。

将 TypeScript 与 Node.js 结合使用，可以将这两种工具结合起来构建服务器端应用程序。Node.js 平台完全支持在构建应用程序时将 TypeScript 作为一个选项。例如，流行的 JavaScript 框架 Angular 可用于创建单页面 web 应用程序，并且完全是用 TypeScript 编写的。

Node.js 带来的不仅仅是运行时。Node.js 的标准安装包括用于处理库或模块依赖性的节点包管理器(NPM)。它还使得在服务器和浏览器中运行代码成为可能。Node.js 生态系统类似于您在 Python 社区中发现的免费可用的库和包，以解决广泛的编程任务。

## Node.js 用法

当您看到这两个工具是如何用于开发应用程序时，您会开始感觉到它们是如何适应大环境的。Node.js 已经在小型应用领域得到了广泛应用，包括物联网和 Raspberry Pi 等小型设备。当用于基于浏览器和用户界面的应用程序时，TypeScript 大放异彩。

首字母缩写词 NPM 代表了一个工具和一个公司。NPM 公司成立于 2014 年，2020 年被 GitHub 收购。设备 NPM 是 Node.js 包中使用最多的部分之一。如果你正在寻找一些执行特定任务的代码，你应该从 NPM 网站开始。在搜索栏中输入你需要的功能，你会看到几个选项。

为了测试这个站点，我们搜索了 JSON，找到了 41，920 个包。结果按受欢迎程度、质量、维护或软件包接收更新的最近/频率进行排序。在您的项目中使用其中一个包需要一些简单的命令行指令。

## Node.js 和 TypeScript 部署

部署应用程序将因目标环境而异。部署打算在本地运行的 Node.js 应用程序通常需要安装 Node.js 运行时和支持工具。Linux、macOS 和 Windows 的安装程序可以从主 Node.js [网站](https://nodejs.org/en/download/)下载。安装程序完成后，您将可以使用几个 Node.js 命令行工具来构建和运行您的代码。

Docker 图像是 Node.js 下载站点提供的另一个选项。这为使用 Docker 或云服务提供商(如亚马逊的 AWS 或微软的 Azure)在本地运行代码提供了广泛的可能性。使用 TypeScript 和 Node.js 开发一个应用程序并在本地或云中运行是合理的。

## Wrapup: Node.js 和 TypeScript

微软创建了 TypeScript 来为基础 JavaScript 语言添加静态类型。通过收购 GitHub，微软在 Node.js 世界中也有既得利益，从而产生了 NPM。根据您尝试构建的应用程序，您可以同时使用 TypeScript 和 Node.js。

使用 TypeScript 开发企业级应用程序的好处远远超过您可能遇到的任何潜在问题。

想招聘 Node.js 开发人员吗？我们在 Toptal 的朋友有一些很棒的资源，你可以去看看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>