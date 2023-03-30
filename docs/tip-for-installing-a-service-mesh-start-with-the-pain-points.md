# 安装服务网格的技巧:从难点开始

> 原文：<https://thenewstack.io/tip-for-installing-a-service-mesh-start-with-the-pain-points/>

雷根赞助了这个播客。

[安装服务网格的技巧:从痛苦开始](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain)

在本期[新堆栈制造商](https://thenewstack.io/podcasts)播客中，我们将与[扎克·布彻](https://www.linkedin.com/in/zachary-butcher-339a2180/)对话，他长期以来一直参与并倡导云工程。他是 Tetrate 的创始工程师，也是谷歌 Istio 团队的工程师。我们在最近的[服务网格日](https://servicemeshday.com)采访了 Butcher，在那里他主持了一个关于安装和使用 Envoy、Istio 和服务网格的四小时培训。

Butcher 说，选择服务网格的原因与您运行的服务数量或系统的复杂程度无关。当你不明白你的分布式系统出了什么问题的时候。因此，选择它不是因为它很酷，而是因为它将解决可见性、可靠性或安全性方面的实际问题。

根据 Butcher 的说法，以下是需要采取的步骤:

1.  弄清楚你到底要部署到哪里，为什么要部署。
2.  调查实现本身。谁将管理它？谁将使用它？
3.  开始计划向开发人员公开服务网格的子集。一个常见的错误是把所有的复杂性一次交给他们的开发者。他说:“最成功地采用信息技术的组织是那些管理开发人员与系统交互方式的组织。”。“他们一开始提供小块的。”所以为了最成功的采用，限制初始发布的范围。
4.  开始熟悉数据层。大多数公司为此使用 Envoy，风险最低的地方是入口。“让它在那里运行，”他说，“学习它是如何运行的，你的团队是如何处理它的，建立流程，然后当该把它搬进去做边车部署的时候。你会更有信心，因为你一直在操作控制平面，你一直在操作数据平面，所以你了解旋钮和故障点。”并开始计划如何部署到您的开发人员。
5.  一旦您对数据平面有了信心，并希望部署网格，请选择三大支柱中最棘手的问题:安全性、流量管理或可见性，并从那里开始。使用服务网格来解决这个问题，获得如何使用和操作它的信心，然后继续处理下一个棘手问题。

听一听这个播客，了解更多关于它是否真的像看起来那么复杂，服务网格如何帮助提高安全性，安装基础设施后该做什么，以及 canaries 如何与服务网格相结合。

### 在这个版本中:

[2:51:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=2:51) 公司在什么时候需要服务网格？
[7:24:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=7:24) 您如何决定准备好安装服务网格？
[14:27:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=14:27) 如果我是一名工程师，我在服务网格的船上，我需要注意哪些事项？
[19:27:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=19:27) 有这三个支柱和痛点，你挑一个最疼的，从那个开始。然后呢？
[22:12:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=22:12) 您能谈谈金丝雀部署吗？
[25:51:](https://thenewstack.simplecast.com/episodes/tips-for-installing-a-service-mesh-start-with-the-pain?t=25:51) 人们去哪里获取更多信息？

图片由来自 Pixabay 的 enriquelopezgarre 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>