# 更多的 AWS 服务，更多的选择，仍然是一个挑战

> 原文：<https://thenewstack.io/more-aws-services-more-choices-and-still-a-challenge/>

亚马逊网络服务以快速发布新功能而闻名。特别是上周，发布了一系列新功能，目标是 DevOps 和 AWS 上的集成开发环境。

我对 AWS 有着复杂的感情，特别是他们的 UX。要真正有效地使用这个平台，你必须专业化——但是当你把它做好之后，就没那么难了。我遇到的另一个挑战是如何呈现服务；很难找到我要找的那个。

也就是说，上周他们增加了更多的服务，并向 DevOps 观众推出了许多有趣的工具。让我们看看它们是什么:

我理解私有 Git 服务器的逻辑，但它仍然困扰着我。但是只要企业大声疾呼，像[这样的解决方案必然会赚钱，显然就有这种需要。事实上，你可以在 AWS 中把它们和其他东西放在一起。这就是 CodeCommit:基于云的私有 Git 实例。据说最大的优势是安全性和与现有环境的集成，这对企业来说是一大卖点。但它并没有超越这一点。当你构建一个应用程序时，我希望看到自动的 webhooks，这样你甚至不需要连接你的源代码库。](http://www.perforce.com/)

为您的 AWS 应用程序提供内置的持续交付解决方案。我对此有着复杂的感觉，主要是因为我太习惯于在如何将 AWS 发布自动化与发布自动化工具如 [Go](http://www.go.cd/) 和 [Jenkins](https://jenkins-ci.org/) 集成的背景下谈论它。我的第二个担心是 AWS 现在已经搭载了 CD 独角兽。持续交付和部署意味着某些类型的应用程序，以及不适合所有开发车间的应用程序。然而，据我所知，它只是一个工作流工具，这意味着它也可以用于持续集成或部署。从表面上看，它的设置似乎也很复杂。它实际上是 S3 桶和 CodeDeploy 更好地结合在一起的组合。

编写 API 是“容易”的部分。监控、保护、记录和扩展 it 是一项艰巨的任务。也不太好玩。网关处理对运行在 EC2、Lambda 或任何其他 web 应用程序上的应用程序的所有请求。据报道，它还有助于自动化 API 的创建。我没有测试过，但是我知道如果它有效的话是非常有价值的——作为后端开发人员，如果你不喜欢 API 的话。它也是基于 PaaS 的，这太棒了。您可以在前端避免额外的节点，并完全忘记那些服务器。这大大简化了 DNS 架构。最后，它为 CloudWatch 的用户提供了一个“预建”的仪表板，用于进行一些分析。

哇，这个不会让 Perfecto 或 Xamarin 感觉很好。但是，很明显，没什么好惊讶的。Device Farm 是一个物理设备云，是一种在其上轻松部署和测试应用程序的机制。今天，他们支持 250 个设备的测试网格，并可以轻松集成到您的发布自动化工具中，如 Jenkins 和 Go。这也引发了开发人员和 QA 之间的激烈争论，即在模拟器上测试还是在真实设备上测试。这确实使真实设备选项变得更容易，但是它们仍然比模拟器更慢，更不灵活。我目前认为这不是一个或另一个。我认为在 CI 环境中用模拟器以冲洗和重复的方式进行测试——然后在交付过程中在真实设备上使用有限的测试套件——是一个理想的场景。

一个小小的改进。让用户数据协议(UDP)流量到达 Docker 容器的能力。这将为富媒体(视频和语音)应用提供更大的灵活性。另一方面，如果在容器中使用 UDP 的开发人员不考虑安全性，这对许多黑客来说是一扇容易的门。更重要的是，这一声明是集装箱服务集团承诺稳步鼓点。

所有这些，加上两周前在纽约 AWS 峰会上宣布的消息，如在 marketplace 中增加了 Chef，都清楚地表明，AWS 正在考虑单个服务之上的一个层面，更多地考虑整个环境。

但是有太多的服务，很难把它们联系起来。我真正渴望的是 Amazon 将所有的东西组合到一个全面的 DevOps 包中，当你创建一个新的应用程序时，所有的东西都紧密地集成在一起。没有这一点，很难想象一个开发店不是完全脱节的。

随着 AWS 的每一个新的公告，我很清楚，如果你来了，你建立了它，你将永远不会离开。你被卡住了。锁定是戏剧性的；然而，完全值得。您不仅可以为您的应用程序使用 AWS，还可以使用您的开发环境。

Docker 是新堆栈的赞助商。

专题图片: [lyzadanger](https://www.flickr.com/photos/lyza/) 的[美国俄勒冈州波特兰市超市](https://en.wikipedia.org/wiki/Food#/media/File:Fredmeyer_edit_1.jpg)包装食品通道获得 [CC BY-SA 2.0](http://creativecommons.org/licenses/by-sa/2.0/) 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>