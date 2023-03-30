# Webhooks:事件驱动架构的构建模块

> 原文：<https://thenewstack.io/webhooks-the-building-blocks-of-an-event-driven-architecture/>

蜘蛛并不总是去捕捉食物，它们只是在网上得到通知。当我们把冷冻食品放进微波炉时，我们不会一直检查它。我们设定时间和温度，我们只知道什么时候完成。

这些是开发者支持者 T2 尼古拉斯·格雷尼总结 T4 网络钩子的方式。当平台或服务上发生某些事情时，webhook 以编程方式提供通知。

程序员 Jeff Lindsay 在 2007 年创造了这个概念，当时他正在寻找一种他称之为“管道”的网络等价物，这种管道将由一系列命令创建。[他创造了短语“web 钩子”](https://web.archive.org/web/20180630220036/http://progrium.com/blog/2007/05/03/web-hooks-to-revolutionize-the-web/)作为这些“用 HTTP POST 进行的用户自定义回调”的名称他认为这种“开放的基础设施”对于 Web 和当时仍在发展的 API 生态系统来说是成熟的。

Grenié说，如今在 Typeform，[回复一份在线表格](https://www.typeform.com/forms/)会触发一个第三方服务的网络挂钩，向你发送一条感谢短信，代理会被告知你发送了一张支持票。这种 webhook 集成将 Typeform 与客户关系管理系统(CRM)、数据库和内容管理系统(CMS)联系起来。它帮助您处理数据流，并将两个系统连接在一起。

Webhooks 驱动服务，如 [Zapier](https://zapier.com/home) 和 [IFTTT](https://ifttt.com/) 。[事件驱动架构的基石](https://thenewstack.io/gwen-shapira-on-the-power-of-event-driven-architecture/)旨在简化构建复杂的用户体验链，将您的服务连接到其他生态系统和数以千计的服务。

Grenié说:“Webhooks 让人们更容易与你的产品集成，因为他们知道他们会从你那里接收数据，而这只是‘数据输入，数据输出’。

## API 策略的 Webhooks

Grenié告诉新的 Stack，通过 Zoom，webhooks 可以利用无服务器功能，如亚马逊网络服务上的 Lambda 或谷歌云功能。

他说，webhooks 是组织启动应用程序编程接口(API)策略的一种简单方式。它允许更简单的构建块，这些构建块可以在以后转化为 API——或者甚至没有必要。

Grenié说:“在 Typeform，如果我们在 API 之前没有 webhooks，我们可能不会增加对该平台的采用。”

他认为你应该围绕 webhooks 建立一个更好的开发者体验。他说这从一致性开始。

“大约两年前，当有人输入一个类型表单时，我们会发送一个 webhook 事件，它有一个相邻的有效负载，包含该类型表单的答案。您将使用相同的输入再次回答表单。webhook 有效负载会有所不同。答案会有不同的顺序，”他说。因此，开发人员无法利用这种不一致性来构建可靠的应用程序。

> “拥有一个管理 Webhooks 的 API 应该和拥有 webhooks 本身一样重要。正如我们之前看到的 webhooks 是一种与您的产品集成的简单方法，让开发人员代表用户自动创建 webhooks 有助于减少摩擦。”— Nicolas Grenié，字体

就基础设施而言，这意味着有效载荷必须按照您定义的方式、按照相同的问题顺序进行组织。

为了帮助增强开发者的体验，TypeForm 后来在它的平台上增加了一个“测试 Webhook”按钮。当有人放入一个 URL 时，会出现一个选项，首先用一个模拟负载对其进行测试。

"没有虚假的提交-玩它，直到你准备好了."Grenié说这“尊重你的类型表单上相同的格式和数据类型。”

现在，开发人员也有办法查看所有事件和所有有效负载，发生了什么，以及数据是如何发送的。他说，这也会延续到调试阶段，以确定错误在哪一边。

为了帮助开发者，Typeform 去年修改了他们的 webhook 面板，以展示双方:由 Typeform 平台发送的事件和你的应用程序返回的内容。

Grenié继续说，webhooks 驱动的开发人员体验“让你及时回到过去，看到所有这些事件的历史”，这使得调试变得容易。

## VMWare 使用 Webhooks 众包代码示例

VMWare 的产品经理 Richard Thomchick 在伦敦举行的 [DevRelCon 2019](https://london-2019.devrel.net/) 上讲述了他的组织如何利用 webhooks 构建代码样本库。当他加入公司时，他们正在分发光盘样品。他说他们“跟不上所需代码样本的数量、种类和速度。”

这使得人们经常在论坛上交换代码样本。

Thomchick 在 JAMstack 解决方案上领导了作为聚合器的样本交换的开发——“就像 Github 用户的 Github，”他说。

考虑到这一点，VMware 开始创建贡献者角色。这不仅仅是开发人员和产品团队的问题，还有其他技术含量较低的上游消费者的问题。只有大约一半的 VMware 开发人员了解 git 版本控制系统。

“我们知道我们希望所有的内容最终都出现在 GitHub 上。熟悉 Github 的贡献者不会加倍努力去添加账号。没有 Github 的人不会学习它来贡献代码样本，”他说。

Thomchick 建立了一个示例交换贡献工作流，该工作流用一个简单的表单抽象出了 pull 请求流程，这个 pull 请求被自动批准。

但是，VMware 突然失去了负责传播所有这些新贡献的社区经理。开发团队使用了条件语句链应用 IFTTT，因此如果 VMWare feed 中有一个新项目，它会自动发布一条关于它的推文。这些自动化的推文很快成为参与度最高的推文。

Thomchick 说，“当一个样本被发布时，它就成为了开发者的推广平台和宣传平台。”

VMware 甚至为专业渠道创建了一个新的交换即服务示例。他说，REST API 可以为特定内容创建定制的样本交换。您可以在 VMware 控制台中测试这些 Webhooks 示例。这些是由产品经理手工选择的，以突出最高质量和代表性的用例。

Thomchick 建议其他专注于 DevRel 的团队创建一个 Github 组织，找到 RSS 提要，然后通过 Webhook 连接到 Twitter。

VMware 是新体系的赞助商。

来自 Pixabay 的 Myriam Zilles 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>