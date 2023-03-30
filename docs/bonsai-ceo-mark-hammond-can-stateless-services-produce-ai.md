# Bonsai 首席执行官马克哈蒙德(Mark Hammond):无状态服务能产生一个 ai 吗？

> 原文：<https://thenewstack.io/bonsai-ceo-mark-hammond-can-stateless-services-produce-ai/>

[Bonsai CEO 马克·哈蒙德:无状态服务能否产生一个 ai？](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai)

大多数开发人员可能都没有想到这个问题:在一个组件之间不共享状态的分布式系统中，如何开发一个应用程序，如果你愿意的话，这个应用程序的目标是创建和维护一个状态，具体来说，就是学习到的东西？

我们已经知道，像决策树这样的人工智能例程不需要预先评估它们的状态，就可以呈现出看起来足够合理的结果。例如，国际象棋走法算法不需要在内存中保留活动棋盘的概念，就可以评估潜在走法的质量。他们可能不会产生市场上最好的国际象棋程序，但他们可以评估移动，他们可以击败业余选手。

嗯，根据定义，一个*机器学习*应用程序应该保留一些东西——这就是整个“学习”部分应该表达的意思。

在最新一期的 [The New Stack Makers](https://www.linkedin.com/in/markisaachammond/) 播客中， [Bonsai](https://bons.ai/) 联合创始人兼首席执行官马克·哈蒙德告诉我们:“你真正想做的事情是，做出几个决定。“第一个问题是，你会有一个在线学习很重要的系统吗——也就是说，系统需要在用户使用系统的同时进行学习？或者会有滞后吗？当用户使用系统时，您是否可以记录输入的数据，然后在更具批处理风格的操作层中学习这些记录？”

不是什么深奥的点。任何机器学习应用都要经过训练；例如，如果它的工作是确定一个系统的正常行为，如电信网络，那么它必须显示代表正常的数据。不要管为什么数据代表正常状态，训练算法需要看到它。哈蒙德的观点是，如果数据可以随着时间的推移而积累，那么记录机制肯定可以被想象为无状态的微服务。

“下一件事是理解当你为请求服务时，维持状态对你正在做的事情是否重要，”哈蒙德继续说。例如，搜索某个产品的评论和需要得到结果之间有很大的区别，即使在这种情况下，你仍然希望系统具有智能。”使用自然语言学习算法来提炼查询结果非常容易。但是如果您的应用程序属于一个持久的物理对象，比如一个机器人制造系统，那么需要有一个底层来确保微服务层中的事件被正确地路由到其他服务。这些层可能不是我们所知道的微服务。

“当你建立这些机器学习系统时，这比我应该使用哪种机器学习算法以及我应该如何构建我的训练数据要复杂得多。”哈蒙德说道。

播客结束后，请务必下载 [Bonsai 关于为企业构建真实人工智能](https://bons.ai/industrial-applications-whitepaper)的挑战的白皮书，不要迷失在隐喻中，该白皮书来自 **bons.ai** 。

### 在这个版本中:

[2:55:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=2:55) 人工智能(AI)和机器学习在当前分布式系统和容器化环境中的扩展。
[13:06:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=13:06) 什么类型的组件可以使机器学习场景的分布式环境成为可能？
[17:13:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=17:13) 当一个开发人员选择 Bonsai 时，有多少决策是从桌面上拿下来并为他们自动化的？
[27:36:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=27:36) 自适应性如何与人工智能协同工作？
[33:03:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=33:03) 在无监督的机器学习环境中，接受系统告诉你的东西的危险。
[38:36:](https://thenewstack.simplecast.com/episodes/bonsai-ceo-mark-hammond-can-stateless-services-produce-an-ai?t=38:36) 机器学习平台是否可以在 Kubernetes 等容器编排平台上运行，或者是否应该在不同于目前可用的平台上运行？

特色图片:[Rushil 的一个印度收割机蚁巢](https://commons.wikimedia.org/wiki/File:Indian_Harvester_Ant_Nest.JPG)，在知识共享 3.0 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>