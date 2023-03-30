# Google 的 Kelsey Hightower 剖析了无服务器的宣传和希望

> 原文：<https://thenewstack.io/googles-kelsey-hightower-dissects-serverless-hype-and-hope/>

[谷歌凯尔西·海塔尔剖析无服务器炒作与希望](https://thenewstack.simplecast.com/episodes/googles-kelsey-hightower-dissects-serverless-hype-and-hope)

无服务器的采用呈爆炸式增长——但是平台是什么以及它如何能够帮助您的组织取决于许多因素。

“对很多人来说，打破‘无服务器’这个词，意味着你想让它表达的任何意思，”谷歌的开发者倡导者[凯尔西·海托华](https://twitter.com/kelseyhightower?lang=en)在由 Alex Williams 主持的播客中说，他是新堆栈的创始人兼主编，该播客在 [KubeCon + CloudNativeCon 北美 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/) 上录制。“但我认为，在这一点上，有这么多的托管服务和所有您可以解决的问题围绕着这一运动……您现在可以给它一个术语，一个流行语。因此，这意味着数据库现在是完全托管的，安全部分是完全通过柜台管理的。”

在许多方面，无服务器产品通常可以简化为将服务器管理任务卸载给第三方的概念。

Hightower 说:“我们正在消除考虑服务器的能力或需要。"所以现在，你有无服务器，因为许多服务也在蚕食这个世界."

Hightower 说，在安全性方面，无服务器也非常适合“最小特权方法”。“这意味着，如果我有一个应用程序，它只需要与这一个数据库交谈，你给它足够的凭证来与这一个数据库交谈，”Hightower 说。“因此，如果您危及这一台服务器的安全，而它又无法访问任何其他内容，那么您可以对它进行某种程度的隔离。”

然而，添加 Kubernetes 层代表了一种不同的动态。“因此，云提供商做了大量工作，以确保做重要事情所需的所有凭证都从您的虚拟机或云功能或应用引擎或 Kubernetes 中分离出来。但想象一下，如果 Kubernetes 是一切为你而生的地方？”高塔说。“你带走了 Kubernetes，现在你要对整个集群负责。所以，你一次做一台机器的事情，现在，你就像是，‘让我们以集群的方式来做吧——我们称之为扩大‘爆炸半径’。"

Hightower 说，当“爆炸半径”很大时，就更容易“一枪摧毁一整套机器”。“所以，这就是人们要小心的地方。“有些人会说，‘我有库伯内特，如果我给库伯内特城堡的钥匙，我就可以破坏库伯内特 API，’”高塔说。是的，这几乎是通过妥协 Kubernetes API 实现的。"

增加限制是减少 Kubernetes 漏洞的一种方法，以防错误的人获得访问权限。“平台可以有更多的限制，因为它们限制了你能做什么和不能做什么，以及那个表面看起来像什么，”Hightower 说。

例如，对于云函数，有可能创建一个可能只做一件事的函数，如“抓取一段数据并与数据库对话”，Hightower 说。“因此，我将使用安全凭证来启动它。Hightower 说:“平台的一部分是明确地为你获取凭证。“[这与]你打电话来拿凭证无关——我把它剪掉了。所以，我限制攻击面。”

Hightower 将限制访问比作签发护照——但要确保只有正确的护照才发给正确的人。“如果我让你走进去，你可以选择任何你想要的护照，你就有可能故意或无意中选错了，”海托华说。“不管怎样，这都是一个安全问题——我要把你的护照给你。所以，这是一种不同的安全模式，对吗？”

尽管如此，仍然有可能“在无服务器上出错吗？”高塔说。“毫无疑问——但是这个系统在某种程度上被很好地定义了，它限制了你能做的事情，”Hightower 说。“任何时候我们都有这种权衡，当表面更小时，就更容易确保安全。”

[https://www.youtube.com/embed/6g4jt3klb9M?feature=oembed](https://www.youtube.com/embed/6g4jt3klb9M?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>