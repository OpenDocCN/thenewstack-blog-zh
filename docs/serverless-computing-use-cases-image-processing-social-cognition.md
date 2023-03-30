# 无服务器计算用例:图像处理、社交和认知

> 原文：<https://thenewstack.io/serverless-computing-use-cases-image-processing-social-cognition/>

当谈到新兴技术[无服务器计算](https://thenewstack.io/serverless-computing-growing-quickly/)时，从上周在纽约举行的 ServerlessConf 上的演示来看，图像处理正迅速成为一个杀手级应用，至少是为了演示目的。

从展览来看，似乎目前无服务器的早期采用者大部分是初创公司，他们已经在使用这种新兴的应用开发范式构建完整的价值链应用[。与此同时，企业似乎对采用无服务器的特定工作流程以及触发和管理自动化操作表现出了浓厚的兴趣。](https://thenewstack.io/year-ahead-stateless-computing/)

在创业公司和企业中，图像处理已经成为无服务器用例的早期领跑者，特别是在与某种形式的认知分析(如对象或面部识别)结合使用时。正在构建的无服务器应用程序也倾向于具有某种形式的社交网络组件。

作为会议的开始，[AWS 无服务器计算总经理 Tim Wagner](https://twitter.com/timallenwagner)[强调了图像处理是他对无服务器最感兴趣的用例领域之一](https://thenewstack.io/amazon-debuts-flourish-runtime-application-model-serverless-computing/)。

那天剩下的时间提供了一些进一步的例子:IBM 的无服务器工具 [OpenWhisk](https://thenewstack.io/ibm-launches-bluemix-openwhisk-event-driven-program-service/) ，在 Bluemix 上运行，展示了一个无人机拍摄空中照片，然后使用认知 API 分析这些照片中的数据的用例。[IBM Cloud 的开发者倡导者 Andrew Trice](https://twitter.com/andytrice) 表示，这是 IBM 全球业务服务迫切需要与客户分享的用例之一。

Trice 表示，无人机拍摄图像并立即进行处理，适用于今天的企业基础设施检查，记录保险公司的洪水和火灾风险，搜索和救援活动，并被用于精准农业，以高效地绘制地图和勘测田地。

到目前为止，Trice 还没有看到一个完整的无服务器业务解决方案出现在这个用例中。企业对整个过程中的一两个步骤感兴趣:例如，使用无人机，拍摄图像，并将这些图像存储在云存储中。

然而，完整的业务解决方案尚未进入企业:“基本上，任何时候你向 Cloudant 写入数据，我们都可以调用自动触发图像复制过程的操作，将其同步到云，启动物联网传感器读数，调用 OpenWhisk，然后是 Watson 函数。但是这太新了。到目前为止，还没有人要求这样做，”Trice 说。“有趣的是，我一把它展示给 GBS，他们就说我们现在就有客户在询问。”

同样在会议上，新 Stack 贡献者和连续创业者 Joe Emison 分享了他创建的两个利用无服务器环境的创业公司。其中之一，[商业搜索](https://www.commercialsearch.com/)，是一个商业房地产列表网站，其核心是图像处理和社交功能的结合，使用户能够上传或查看房产列表，发表评论或保存搜索结果。该应用程序和另一家获取房产清单并创建外观书籍(更多图像处理任务)的初创公司都是使用一系列第三方 API 和无服务器基础设施构建的，包括 [Algolia](https://www.algolia.com/) 、 [Netlify](https://www.netlify.com/) 和 [Google Firebase](https://firebase.google.com/) 。

第二天从另外两个图像处理示例开始:[SparqTV 的联合创始人兼首席技术官 Don Ferguson](https://www.linkedin.com/in/fergusondonald) 博士描述了他当前项目背后的无服务器应用架构，这是一个视频内容平台，其功能包括用户帐户、评分、广告等社交评论组件以及允许观众直接与内容创作者联系的交互元素。

随后，谷歌的 Firebase 倡导者 Mike MacDonald 和 Frank van Puffelen 分别做了一个报告。上周，在 I/O 大会上，Firebase 已经成为“一套 14 到 15 个 Firebase 产品:存储、应用邀请、崩溃报告、测试实验室和其他帮助你建立用户群和赚钱的产品”，van Puffelen 说。他们演示了如何构建一个无服务器的应用程序，该应用程序可以将视频上传到云存储，从每一帧中创建静止图像，将这些图像存储在同一个云存储中，并对物体和面部识别应用认知机器学习。

同样，微软 Azure 的首席项目经理 Yochay kiri aty(T1)表示，尽管其无服务器产品 [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) 仍处于预览模式(今年 4 月刚刚推出)，“我们看到客户在很多情况下使用无服务器进行图像处理，以及任何涉及对事件做出反应的操作，如存储或数据库中项目的变化。”

Kiriaty 描述道:“Azure 功能可以从数据流中触发动作，运行认知服务和图像分析，使用定制的业务逻辑并触发进一步的动作。所有可以放在 Azure 存储中的输出可以启动另一个功能，该功能计算出下一步该做什么。您可以使用 Azure Logic 应用程序将所有这些联系在一起，以协调所有这些并维护工作流的状态。”

## 无服务器变成无权限

但像 Trice 一样，Kiriaty 说，迄今为止，很少有企业用例在无服务器环境中构建这种完整的业务解决方案。相反，企业对利用无服务器来执行特定任务感兴趣:“图像处理和内容处理以及在后台进行任何内容操作都非常常见。存储一幅图像，然后调整大小，再把它放回存储器就是一个很好的例子。

因此，今天这里出现了两种无服务器应用:初创公司正在通过构建全功能应用来获得业务优势，这些应用将 API 菊花链在一起，以创建一个应用，如 SparqTV 和 CommercialSearch。在企业中，迄今为止的焦点更多地集中在特定的任务上，就像 [Iron.io](https://thenewstack.io/iron-io-redefining-serverless-experience/) 在无服务器环境中批量处理和任务管理的商业客户中看到的牵引方式一样。

来自[雷德蒙克](http://redmonk.com/)的技术分析师[詹姆斯州长](https://twitter.com/monkchips)说，这一切都表明了向无许可行业格局的转变。企业内部的员工被鼓励回避请求 IT 许可来构建新的工作流任务，并且正在利用无服务器来创造创新和效率机会。创业公司正在利用无服务器来获得商业模式的许可，这种模式不需要风险投资来建立可行的业务。[一位云计算大师](https://acloud.guru/)在他的演讲中展示了这一点:在一个学习管理平台上提供视频培训(同样，图像处理和社交网络功能)，完全在一个无服务器的环境中，已经发展成为一项可行的业务，只有当客户购买培训课程时，才会产生业务成本。

无服务器正在降低应用程序的复杂性和准入门槛，并加速 IT 部门以外的初创公司和业务部门的开发。在 Governor 看来，这种新的应用程序开发范例展示了创新的力量:无服务器变成了无许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>