# 从一台服务器到 Kubernetes，一个创业公司的故事

> 原文：<https://thenewstack.io/from-one-server-to-kubernetes-a-startups-story/>

KubeCon+CloudNativeCon 赞助了这个播客，作为对 Kubernetes 终端用户的一系列采访的一部分。听听之前关于 Box 的 Kubernetes 之旅的[起伏以及防火墙后](/the-ups-and-downs-of-boxs-kubernetes-journey/)[维基百科的基础设施](/what-wikipedias-infrastructure-is-like-behind-the-firewall/)是什么样子的故事。

开始的时候很简单，但是很快这个网站需要的不仅仅是一台服务器来管理一切。今天， [EquityZen](https://equityzen.com/) 在 Kubernetes 上运行，并且正在考虑它的下一步行动，特别是探索容器即服务如何为他们服务。

在本期 [The New Stack Analysts](/podcasts/analysts) 播客中，EquityZen 的 DevOps 工程经理 Andy Snowden 讨论了他如何帮助该公司开始其云原生之旅以及与迁移相关的挑战。 [Alex Williams](/author/alex/) ，新书库创始人兼发行人；[云原生计算基金会(CNCF)](https://uk.linkedin.com/in/cheryljhung) 生态系统副总裁 Cheryl Hung 和[云原生工程副总裁 Ken Owens](https://www.linkedin.com/in/kenowens12/) 、[万事达卡](https://www.mastercard.us/en-us.html)主持了播客。

[从一个服务器到 Kubernetes，一个创业公司的故事](https://thenewstack.simplecast.com/episodes/from-one-server-to-kubernetes-a-startups-story)

当斯诺登加入 EquityZen 时，他立即开始运用他管理 Kubernetes 环境的背景来帮助解决该公司的一个主要问题:其基础设施的可靠性。

“在我们最初的谈话中，他们向我解释说‘嘿，我们有这些问题，我们有这些大的网站点击量，网站将会关闭’，这对我们的客户来说真的很糟糕。他们还会问“你过去做过哪些对你有益的事情？””斯诺登说根据我对 Kubernetes 的了解，我说这听起来是一个非常好的使用案例，并解释说这些是我可能会考虑做的事情。"

一旦确信 Kubernetes 环境既能提高可靠性，又能帮助公司更好地扩大运营规模，斯诺登就发现，实现这一转变当然是一项艰巨的任务。

“这无疑是一个巨大的提升，核心 Django 应用程序的最初容器化可能是我们必须考虑的更大更长期的项目之一，”斯诺登说。

然而，他说，从代码的角度来看，迁移到 Kubernetes 环境是非常无缝的。

“我的开发人员真的不需要改变他们看待 Django 或 Python 的方式以及他们编写 Python 的方式，”斯诺登说。“这主要是[让]他们意识到可能有新的限制，或者如果有*限制被消除，那是如何工作的，就像‘现在，你没有无限的记忆，你现在只有有限的记忆。所以，你和 Postgres 说话的方式要更有效率一点。"*

EquityZen 在[亚马逊网络服务(AWS)](https://aws.amazon.com/) 上运行 Kubernetes。在前端，它利用 React、Redux 和 GraphQL 和 Django，在后端利用 Celery、PostgreSQL、ElasticSearch 和 RabbitMQ。EquityZen 的大部分业务都在 Kubernetes 上运行。

EquityZen 还得到了[云计算本地计算基金会终端用户社区](https://www.cncf.io/people/end-user-community/)的支持。

斯诺登说:“我们最初加入的原因之一是，无论他们是像我们这样的小公司，还是像万事达这样的大公司，我们都有一群志同道合的人，有着同样的问题，这是一种优势。”“很高兴看到对同一个问题有不同的看法，我对一个问题的解决方案可能与大公司的解决方案不同，但我们正在努力解决同一个问题。”

[亚马逊网络服务(AWS)](https://aws.amazon.com/) 和[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

[Ravi Palwe](https://unsplash.com/@ravipalwe?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的照片。](https://unsplash.com/s/photos/podcast?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>