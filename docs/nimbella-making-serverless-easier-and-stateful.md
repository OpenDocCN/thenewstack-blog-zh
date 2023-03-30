# Nimbella:让无服务器更简单、更有状态

> 原文：<https://thenewstack.io/nimbella-making-serverless-easier-and-stateful/>

总部位于加州圣克拉拉的 Nimbella 的创始人着手解决无服务器计算的一些痛点:入门、开发有状态应用程序以及从一个云迁移到另一个云。

在该公司的四位联合创始人中，[安舒·阿加瓦尔](https://www.linkedin.com/in/anshuagarwal/)和[埃里克·斯维尔登斯](https://www.linkedin.com/in/eric-swildens/)最初在 Speedera 共事，Speedera 是一家被 Akamai 收购的内容交付网络公司。罗德里克·拉巴和[程伊兵](https://www.linkedin.com/in/perry-cheng-70999a13a/)是 IBM 开源无服务器平台 OpenWhisk 的共同创造者，现在是 [Apache OpenWhisk](https://openwhisk.apache.org/) 。

Nimbella 的首席执行官 Agarwal 说:“我们真的希望为所有不同背景的开发人员揭开云的神秘面纱……一旦开发人员体验到无服务器的滋味，我们的论点是，这是一种非常愉快和令人敬畏的体验，因为它让他们专注于他们的价值创造，而不是让开发人员慢下来的基础设施和服务器细节。”。

该公司在 9 月份发布了其首款产品 early access，并计划在 1 月份全面上市。这是一个集成的解决方案，用于构建有状态、无状态、JAMstack、长期运行、流式或高性能的无服务器应用程序，可跨云和内部环境工作。它旨在提供一种简单的方法，从传统迁移到现代 API 驱动的无服务器云软件。

“采用所有现有云提供商的无服务器计算面临的挑战之一是太难了。对于开始使用这个模型的人来说，它的威力是非常明显的。而且让人上瘾。一旦你开始这样开发，我不认为你真的想回到老的开发方式，”Nimbella 的首席技术官拉巴说。

Rabbah 说:“我们希望消除那些让你慢下来的摩擦和流程，让你只需一次点击就能轻松部署一项功能，甚至无需在我们的云上拥有账户。”。

### **OpenWhisk 和更多**

他说 OpenWhisk 只是等式的一部分。

“我们公司没有将 OpenWhisk 作为一项服务。但是我们确实使用 OpenWhisk 作为我们放在一起的技术堆栈的一部分，允许您以无服务器的方式部署和开发功能。[我们]扩展服务体验，这样您不仅可以部署功能，还可以构建应用程序，这些应用程序是状态管理和数据流中的组合或编排、功能和 API。因此，您可以开发更引人注目、更有趣的前端、后端、反应式、多事件等应用程序。，”他说。

Nimbella 云部署在 Kubernetes 之上，作为一种标准化不同云和内部环境差异的方法。

有几个组成部分:

*   一个**函数编排器**主要构建在 OpenWhisk 上，它允许你执行函数并将函数分配给资源来运行它们。
*   一个**容器协调器**，它允许用户运行容器化的应用程序，并拥有相同的体验。然而，该平台负责底层技术、实现细节和基础设施。
*   一个**编排引擎**，部分使用增强开源技术，在其模型之上支持长期运行的工作流。

“这实质上包括让应用程序被视为更经典的应用程序，因为它们有程序计数器、状态和堆栈。管理工作的一部分是平台的责任，由工作流程编排者来完成，”拉巴说。

“然后是有状态方面。所以我们希望应用程序本质上具有在函数间共享状态的能力。…在现有的功能服务平台上，这在用户层面上实际上是很难做到的，”拉巴说。

他是这样解释的:

“假设您有一个实现 web 应用程序或电子零售网站的功能，您有一个购物车的概念，购物车中有内容。您可以编写函数，使每次执行都有三个步骤:从内存中读取状态，计算逻辑，然后将状态写回内存。为了提高效率和速度，您需要将数据与功能放在一起。

“当你在一个无服务器的平台上运行时，根据定义，函数有短暂的驻留。因此，作为用户，你不知道你的功能实际上在哪里运行:哪些单元、哪些虚拟机、哪些地理位置、哪些云区域。所以你很难进行局部性优化，也很难让你的数据和你的函数放在一起。

“因此，我们的有状态方面的一部分是实际管理键值存储、对象存储和文件系统抽象，它们与功能位于同一位置，以便实现高效的低延迟通信。我们正在引入记忆层次的概念，”他说。

它建立在开源的基础上，使用 Redis 作为键值存储。它使用 S3 兼容的 API 进行对象存储抽象。

对于在神经网络模型等应用中进行机器学习和人工智能的功能，引擎所做的部分工作是管理这些数据块，并确保这些功能可以以只读模式访问数据，因此数据只加载一次。该平台包含一个状态管理引擎。…有许多组件组合在一起，形成一个抽象层和一个中间件，允许您在其上构建应用程序。"

其他部分包括:

*   **Developer workbench** 是对 IDEs 的补充，拥有强大的插件，可以提升开发体验，实现全栈应用的“活”本地开发，可以直接在云端测试。它最近增加了一个[开发者园地](https://api.nimbella.io/wb)，允许用户用 Node、Python、PHP、Java、Go 和 Swift 创建、共享和发布 API。对于编译语言(Go、Swift、Java)，Nimbella cloud 也负责编译。
*   **操作员仪表盘**提供单一界面来监控和管理一切，无论您是将 Nimbella 用作托管服务还是用于私有云及专用基础设施。
*   组合引擎允许开发者将 API、函数和容器放在一个熟悉的编程抽象中。
*   **日志记录引擎**提供结构化日志，这些日志会自动编制索引并可从工作台获得，或者路由到现有的日志记录服务，如 Elastic 或 Splunk。
*   **身份和访问管理(IAM)与 Auth0 等常见 IAM 工具的集成**。
*   **云控制器负载平衡器**自动提供公共云或公共云和私有云之间的负载平衡。

### 向边缘望去

该公司已经筹集了大约 400 万美元。其客户包括医疗器械制造商 [Caputron](https://caputron.com/) 和就业验证公司 [Empinfo](https://www.empinfo.com/) 。

展望未来，该公司正着眼于为开发人员提供熟悉的编程体验的边缘计算。

“在云中运行无容器功能的能力在提高效率方面提供了经济和其他激励。…因此，在平台层面上使其可访问，并有一种自以为是的方式来选择哪个功能应该在哪个底层资源中运行是非常重要的，”Rabbah 说。

它正致力于与像[page duty](https://pagerduty.com/)和 [Twilio](https://www.twilio.com/) 这样的提供商整合，以便能够从不同的提供商那里获取事件并对其采取行动。该公司最近在 early access [发布了 Commander](https://nimbella.com/resources-commander/overview#what-is-commander) ，这是一个用于构建和管理定制 Slack 应用的开发平台。

你可以在 GitHub 上找到 Nimbella，包括一个[股票交易演示](https://github.com/nimbella/demo-projects/tree/master/trade)和[聊天应用演示](https://github.com/nimbella/demo-projects/tree/master/chat)。

分析师 [贾纳基拉姆·MSV](https://thenewstack.io/author/janakiram/)对新堆栈的[open whish 架构](https://thenewstack.io/behind-scenes-apache-openwhisk-serverless-platform/)进行了深入研究，该架构还提供了关于无服务器技术的[免费电子书](https://thenewstack.io/guide-to-serverless-technologies-free-ebook-on-the-new-stack/)。

Redis 实验室是新堆栈的赞助商。

来自 Pixabay 的 TeeFarm 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>