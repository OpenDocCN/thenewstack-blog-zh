# 如何向不必购买的同事推销您的基础架构

> 原文：<https://thenewstack.io/how-to-sell-your-infrastructure-to-the-colleagues-who-dont-have-to-buy-it/>

KubeCon+CloudNativeCon 赞助了这个播客，作为对 Kubernetes 终端用户的一系列采访的一部分。听听以前关于 [Spotify 采用 Kubernetes 的黄金之路有许多曲折](https://thenewstack.io/spotifys-golden-path-to-kubernetes-adoption-had-many-twist-and-turns/)和[从一台服务器到 Kubernetes，一个创业公司的故事](/from-one-server-to-kubernetes-a-startups-story/)。

很多时候，比一个陌生人更难说服你的朋友和家人。第一组通常对你更果断和直接。你的工作家庭也是如此。当您为自治团队构建内部基础设施时，您的工作不仅是提供技术骨干，还包括销售和客户支持。

没人说[内部开发者宣传](/developer-advocacy-inside-and-outside-a-business/)会更容易。

[新堆栈分析师](/podcasts/analysts)最终用户系列的第六集，我们与 [Simone Sciarrati](https://www.linkedin.com/in/dezmodue/) 、melt water media intelligence platform[的工程团队负责人](https://www.meltwater.com/en)讨论了自主工程文化、成型开发人员体验以及那些艰难的技术决策。我们的出版商 Alex Williams 与来自云本地计算基金会的 Cheryl Hung 和万事达卡公司的 Ken Owens 共同主持了这次对话。

[如何向无需购买基础设施的同事推销您的基础设施](https://thenewstack.simplecast.com/episodes/how-to-sell-your-infrastructure-to-the-colleagues-that-dont-have-to-buy-it-w-simone-sciarrati)

大约四年前，Meltwater 从工程和运营两个部门转变为完全自主的产品团队，每个团队都获得了高度信任。考虑到这一点，Sciarrati 的团队的项目实际上是通过构建、维护和支持融水分布式基础设施来服务内部客户——即他们的同事。

随着更大的自主权而来的是更大的决策权。公司转移到了[亚马逊网络服务](https://aws.amazon.com/)，这见证了众多团队采用[弹性豆茎](https://www.chetu.com/solutions/cloud/aws.php?keyword=aws%20beanstalk&gclid=EAIaIQobChMI8pHSi_Ci6wIVYgnnCh3ZCwi6EAAYASAAEgJcEPD_BwE)和[亚马逊弹性容器服务(ECS)](https://aws.amazon.com/ecs/) 。然后，基础设施团队的工作就是构建比这更有吸引力的东西。

Sciarrati 说:“由于我们不能要求其他团队来使用我们的平台，这很有挑战性，因为我们必须出去做客户发现，了解其他团队的需求，然后设计出适合他们工作方式的产品。”

ECS 的这一替代方案是一个自主开发的 Kubernetes 平台，具有日志记录平台、持续交付和持续集成或 CI/CD 指标、警报以及对 HashiCorp 的 [Terraform](https://www.terraform.io/) 的支持。

由于自治团队已经将 GitOps 的原则应用到开发中，这导致两个基金会任务团队在基础设施方面遵循相同的处理代码的方式——一切都通过 Github。他们还选择了 Terraform，Sciarrati 认为这是管理基础设施最成熟的方式，以及用于 CI/CD 的托管版无人机，他说这提供了最快和最好的用户体验。

这是一个显著的成功，因为他估计，每四到五个月，他们的部署数量就会翻一番，导致 70%到 80%的 Meltwater 团队至少使用他们平台上运行的一些服务。但这来之不易，尽管我们在同一栋大楼里，为同一家公司工作。

“当然，这花了很多时间，因为我们需要出去做广告，宣传并说服工程师和工程经理，这是一个好的选择。你应该花时间来使用我们的平台，因为它比其他东西更好，”Sciarrati 说。

这种内部开发人员倡议的一部分是抽象不必要的 Kubernetes 复杂性，同时仍然允许每个自主开发人员检查日志或编写代码，如果他们愿意的话。

”我曾经 注意到 那是 一个 很多只是 复杂 那发展 组队 真的不要弄 任何一个 真的 他们 只是 想要 要， 像 跟他们 只是 想要推 然后他们要 要 把 上的 移到 上的 测试 启动。 他们 真的不要 要 要 要 试试图 出来 如果 他们 那是 真的 不是 他们的 工作，”欧文斯说道。

当你向你的开发伙伴销售时，Sciarrati 发现不要采用他所谓的“大爆炸”方法也很重要，在这种方法中，你试图一次测试并自动化所有东西。相反，接受环境不断变化的事实，Meltwater 的基础设施团队试图在 Kubernetes 的每个版本上进行增量更新。

现在，一旦他的大多数 Meltwater 队友都被卖掉了， Sciarrati 就代表这些内部客户不断做出决定，进行权衡，以及继续改善开发人员体验的方法来完成这个播客。毕竟，如果队友找到了更好的东西，自治不一定意味着忠诚。

[亚马逊网络服务](https://aws.amazon.com/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>