# 关于 Kubernetes 的数据:下一个前沿

> 原文：<https://thenewstack.io/data-on-kubernetes-the-next-frontier/>

[DataStax](https://www.datastax.com/) 赞助本帖。

 [巴瓦尼·拉奥

Bhavani 是 DataStax 的产品营销总监。](https://www.linkedin.com/in/bhavanirao/) 

在最近两集的[开放| |来源| |数据](https://www.datastax.com/resources/podcast/open-source-data)播客中，DataStax 首席战略官[萨姆·拉姆奇](https://twitter.com/sramji)首先[与](https://www.datastax.com/resources/podcast/our-best-selves)[谷歌云首席工程师凯尔西·海托华](https://twitter.com/kelseyhightower)[交谈，然后](https://www.datastax.com/resources/podcast/data-on-kubernetes)与[微软 Azure 首席项目经理拉克伦·埃文森](https://twitter.com/LachlanEvenson)交谈。讨论深入探讨了 Kubernetes 上的数据、Kube operators for data 的兴起，以及这一切对数据驱动的应用程序开发的未来意味着什么。

由于 84%的开源开发者在生产中运行容器，所以越来越多的开发团队使用 Kubernetes 进行编排也就不足为奇了。在过去几年中，企业已经转向了多云环境和微服务架构的应用程序，这在很大程度上是因为 Kubernetes 使这一切变得易于管理。他们这样做是为了充分利用每个云服务提供商提供的最佳服务，同时加快开发运维工作流程，并能够更快地发布新版本。

虽然这种方法带来了显著的好处，但也存在一些挑战。有这么多不同的团队在从事数千种不同的微服务——而且每个团队都使用不同的工具，其中许多都位于不同的云生态系统中——利用所有相关的数据似乎是一项不可完成的任务。

你的组织下一次成功的秘密可能就在你服务器的某个地方。但是如果你不知道在哪里，你就不能释放潜力。你可能是世界领先的鞋类制造商，坐拥一座数据金矿，但最终仍在猜测人们喜欢买什么样的鞋。

## 使用微服务，数据会被捕获

在非常基本的层面上，数据可以帮助您解决业务问题。但是，如果你不能快速找到你的数据或对其进行分析，它不会给你带来太多好处。

虽然当今的组织了解数据的重要性，但很少有人能够最大限度地利用他们所拥有的数据。在很大程度上，这是因为他们有一个充斥着数据孤岛的笨重的架构。

Hightower 说:“数据是流经我们正在构建的所有系统的业务命脉。“奇怪的是，大多数人发现自己已经收集了所有这些精彩的数据。它被困住了。我们从一个高度协作的系统开始，然后数据就堆积在这扇隐藏的门后面，再也没有人能够访问。”

## 目前，Kubernetes 中的数据限制

对于 Evenson 来说，Kubernetes 是可替换的(可互换的)。你应该能够使用 Kubernetes 口味，简单地用一个 API。

但是我们还没到那一步。

“你看不到太多关于模式可移植性或数据交互的东西，”Evenson 说。"目前，这在库伯内特斯确实是不透明的."

然而，未来是不成文的。

“我在 Kubernetes 生态系统中看到了有趣的机会，”Evenson 继续说道，“随着定制资源和 Kubernetes 的出现，您可以非常容易地为您的应用程序构建定制 API。我们处在运营商爆炸的世界。本质上，它使 Kubernetes 应用程序能够感知。”

有一点是肯定的:Kubernetes 中的数据越来越多，这意味着显然需要 API 来使每个人都可以轻松访问数据。

“我的挑战将是那些对在开源中构建数据感知 API 感兴趣的人，Kubernetes 可能是一个你可以开始建模这些 API 的地方，”Evenson 解释道。“事实上，Kubernetes 在生态系统中被广泛采用，生态系统中的其他公司可以使用它们运行、测试它们并给出反馈。”

如果您有兴趣了解更多关于人们如何利用 Kubernetes 上的数据的信息，[太平洋时间 1 月 12 日星期二上午 9 点，请加入我们与新堆栈](https://events.datastax.com/DataManagementK8)共进煎饼早餐。《新书库》的创始人兼发行人亚历克斯·威廉姆斯(Alex Williams)将与拉姆奇(Ramji)联手； [Mya Pitzeruse](https://www.linkedin.com/in/mjpitz/) ，effx 的软件工程师，GRPC 和 GitOps 的 OSS 贡献者；还有[汤姆·奥弗曼](https://www.linkedin.com/in/tom-offermann/)，新遗迹的首席软件工程师。

与此同时，你可以在这里收听拉姆奇对埃文森的采访:

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>