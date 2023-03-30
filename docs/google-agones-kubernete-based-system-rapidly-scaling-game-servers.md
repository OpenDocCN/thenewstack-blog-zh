# 进入 Google Agones，这是一个基于 Kubernete 的系统，用于快速扩展游戏服务器

> 原文：<https://thenewstack.io/google-agones-kubernete-based-system-rapidly-scaling-game-servers/>

当考虑规模时，很少有系统像游戏发布日那样快速而疯狂。任何订阅过《全新 MMO》的人都可以证明这种综合症:即使有最好的计划，许多首发日游戏也会被过度宣传的消费者的意外需求淹没。这可能是谷歌试图通过 Agones 来接触游戏开发者的原因之一，Agones 是一个基于 Kubernete 的容器编排系统，专注于游戏服务器。

在其成功的 Kubernetes 项目的基础上，谷歌和育碧联合他们的开发力量来构建 Agones。这个新的开源项目允许游戏开发者使用 Kubernetes 来管理这个过程，从而构建他们服务器的新实例。

这里最大的变化是关注生命周期短的有状态服务器，而不是生命周期长的无状态服务器。对于像 DOTA 2 或[英雄联盟](https://play.na.leagueoflegends.com/en_US)这样的游戏，玩家登录一个服务器，一次十个，通常在一个小时内完成。其他游戏运行的时间甚至更短。此外，负载平衡器不能参与进来，因为它们会降低速度，而且游戏玩家沉迷于速度和每秒帧数。

在本周于三藩市举行的[游戏开发者大会](http://www.gdconf.com/)上，谷歌花了整整一天的时间详细介绍它可以帮助初出茅庐的游戏开发者满足其产品不断增长的需求的方法。与企业和商业软件世界不同，游戏通常通过市场营销向大众进行宣传，导致第一天就出现不可预测的销售曲线。因此，许多游戏公司可能会淹没在过度热情的结果中，因为玩家会创建新帐户，在线聚集，并通常会测试 1.0 产品。

这是因为大多数游戏开发者不像亚马逊和谷歌内部的团队那样精通高度可扩展的服务器技术。亚马逊早在 2015 年的 GDC 上就已经通过介绍[木材场](https://aws.amazon.com/lumberyard/)提出了这个话题。Crytek 的 [CryEngine](http://www.crytek.com/cryengine) 和对 Amazon 的 Web 服务 API 的点击式 IDE 支持相结合，为开发人员提供了一种从头开始构建高度可扩展系统和服务的方法。不幸的是，Lumberyard 是开发人员的一个大项目，很难与观众建立联系。

输入谷歌和育碧的 Agones。这似乎是在看谁能为游戏开发者搭建通往云平台的最佳桥梁。

谷歌是新堆栈的赞助商。

特征图片:[英雄联盟](https://play.na.leagueoflegends.com/en_US)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>