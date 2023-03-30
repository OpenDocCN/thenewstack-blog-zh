# HPE 的 ChatOps 旨在用 Slack 取代开发协作平台

> 原文：<https://thenewstack.io/hpes-chatops-aims-to-replace-dev-collaboration-platforms-with-slack/>

除了他们现在已经在使用的平台之外，开发人员真的需要另一个协作和交流平台吗？你可能会从从事软件推广业务的公司那里找到一个更令人吃惊的回答，[惠普企业](https://www8.hp.com/us/en/solutions/business-solutions.html)实际上已经说了，不

事实上，成为上一届 HPE 探索大会热门的服务——HPE 的 ChatOps——实际上是该公司现有自动化和事件管理工具的开源实现，与 Slack 整合在一起，[似乎最终打破了工作场所聊天工具市场大战中的平衡。](http://poll.pollcode.com/43115736_result?v)

在 Discover 上，三位 HPE 软件架构师向新堆栈演示了 ChatOps 的运行。我们*没有*看到的是一个中央平台，上面有一个大大的“聊天”横幅和一些卡通图标，为用户提供了另一个实时评论流，并辅以笑脸和变幻无常的手指。相反，我们看到 Slack 被用作项目中开发人员之间的一种常见的交流方式；在生产中维护软件的 DevOps 专业人员；还有几个轻量级的“机器人”执行单独的任务，主要集中在自动向 Slack 发送数据和从 Slack 接收数据。使用 Slack 现有的自动化，一些数据被用来触发自动化过程，其中一些将在真实软件事故的情况下进行补救。

“企业客户正在考虑如何利用他们现有的资产和 HPE 产品，并能够利用这种新的做法，”HPE 在内容管理领域的首席架构师之一柯克奇解释说。

## 事件报告

“在你的服务台售票系统中，你记录了一个‘严重’的缺陷，你的应用程序停止了，”HPE 的威尔·祖尔让我们假设。“它会在你的 Slack 聊天室里自动创建一个作战室，并开始邀请批评的人到那里。然后，它将发布关于该特定缺陷的信息；比如，它会从你的服务台和售票系统获取信息，并把它们发送到房间里。”

在补救过程中，任何人都不需要离开松弛状态，进入某个具有自己的 GUI 的独立应用程序。请注意，HPE 实际上有这样一个计划——具体来说，一个基础设施自动化工具[PDF]称为 Operations Manager i (OMi，除了作为后缀之外，还有一个类似于“iPhone”中的小“I”)，它确实有必要的性能试探法，有圆圈和箭头以及摘要仪表板。

但是 ChatOps 实际上以一种自动化的方式与 OMi 合作。虽然 DevOps 中的一些人可能会全职使用 OMi 仪表板，但开发人员只需要通过向 ChatOps *[hubot](https://thenewstack.slack.com/apps/A0F7XDU93-hubot)* 发布命令来处理数据。这是 Slack 创造的一种风格的对话工具，非常像几十年前创建的那种，当时所有的网络监控和管理都是在命令行上进行的。

Slack Hubot 的机器人脚本是用 CoffeeScript 编写的，coffee script 是一种精简的语言，可以编译成 JavaScript。 [CoffeeScript](http://coffeescript.org/) 中的变量可以被动态调用，而无需先声明；服务器端的 CoffeeScript 编译器认识到了这一事实，并自己添加了 JavaScript 声明。Hubot 本身是用 CoffeeScript 编写的，并使用 Node 的 **npm** 打包。将一个新机器人附加到 Hubot 的过程已经自动化，作为一个[约曼](http://yeoman.io/)工作流。因此，一旦管理员获取了机器人的 **npm** 包并将它们放在适当的目录中，她就可以运行 Yeoman 的 **yo** 命令来自动化构建过程，这就像 Slack 中的其他事情一样，是对话式的。

Hubot 代码附加了定制的 CoffeeScript(现在编译成 JavaScript ),成为一个单节点包。在 Slack 服务器上部署它就变成了使用 **npm** 部署包，并用包的标题修改 JSON 文件。

## 少了一个平台

在很大程度上，ChatOps 是对开发人员和开发人员已经在使用的工具的改编，至少在部署正在打包并且工作流已经流水线化的组织中是如此。这就是问题的关键所在:HPE 自己也承认，它正在响应客户的呼吁，请不要将全新的平台注入到他们的工作流程中(推而广之，就是新的许可证)，而这可能只需要几个轻量级的链接。Qi 正在考虑使用这种更具对话性的方法来自动访问 HPE 的其他工具。

然而，在桥的 OMi 端，企业客户可能需要进行更多的调整。OMi 被设计成一个“单一窗口”应用程序，将图表和性能指标混合在一个屏幕上。它可以通过 API 调用的方式来提供数据，但是到目前为止，[API 的使用一直被视为事后的想法](http://certification-learning.hpe.com/tr/datacard/Exam/HP0-M77)——这是管理员需要知道的事情列表中的最后一项，以获得 HPE 在 OMi 使用方面的认证。

Qi 对这个问题的解决方案是将有知识的 API 用户的智囊团聚集到一个在线社区中，该社区为管理员发布 bot 集成包，以便他们自己与 Slack 集成。这样，他们就不必经历认证过程，这样他们就可以解释从他们的 hubots 得到的信息。

![160609 06 HPE Discover (Will Zuill)](img/af0a2c58ea55df8873036c64e934d698.png)

“现在，这里有一些工作需要完成，”Zuill 继续说道。“我们需要在其中加入一些安全措施……但是中间件实际上是这样的，它是一种社区驱动的、开源的东西。这就是为什么，你不仅可以参与其中，而且如果你使用不同的售票系统——例如， [ServiceNow](http://www.servicenow.com/) 而不是[【HPE】Service Anywhere](http://community.hpe.com/t5/Service-Anywhere/ct-p/service-anywhere)——那么他们就支持这个特定的流程。因此，在这些行业中，这些企业级软件，如果他们要以某种方式支持 ChatOps，他们需要在 hubot 过程中有一些表示…但最终，我们有一些公开的 API，这只是这些 API 的一个接口。”

Zuill 相信，大多数 HPE 的客户已经在 API 的使用上做了很好的投资，因为他们正在积极地寻找将他们现有的软件与他们的过程集成的方法。因此，ChatOps 对他们来说并不是一个真正的平台，而是一种方法。

HPE 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>