# KubeCon 圣地亚哥煎饼:将云原生安全性一路向左转移

> 原文：<https://thenewstack.io/kubecon-san-diego-pancakes-shifting-cloud-native-security-all-the-way-left/>

[帕洛阿尔托网络公司](https://www.paloaltonetworks.com/prisma/cloud)赞助了这次播客。Palo Alto 的 Prisma 是业内最完整的云安全套件，通过风险可见性和一致的安全性帮助客户加速他们的旅程。

许多 IT 团队在他们的经理要求转换之后，开始将他们的应用程序转移到容器和 Kubernetes 上。然后，在匆忙部署的过程中，他们可能会忘记或只是推迟一些基本原则。仅在 6 到 12 个月后，将安全性集成到他们的 CI/CD 渠道中才成为优先事项。

这种向云原生安全最佳实践的逐渐演变令人担忧，但这是当今采用 Kubernetes 的组织的常态。这是我们本周在 KubeCon+CloudNativeCon 北美的 New Stack 的 pancake 和 podcast 上从云原生安全专家小组那里了解到的。New Stack 创始人兼发行人 Alex Williams 也加入了讨论小组，他们是:

[KubeCon 圣地亚哥烙饼:游云原生安全一路向左](https://thenewstack.simplecast.com/episodes/kubecon-san-diego-pancakes-shifting-cloud-native-security-all-the-way-left)

## 云原生安全性左移

安全实践随着基于 DevOps 实践的云原生技术一起发展。开发人员现在希望云原生技术的所有方面都以相同的迭代、声明性和自动化方式工作，包括安全性，小组成员同意这一点。他们需要快速部署到生产环境中。

同样，安全不再仅仅是运营团队的领域。随着安全性“左移”到软件开发生命周期的开始，开发人员越来越多地负责保护他们构建的应用程序。

Kaczorowski 说:“理想情况下，你应该尽早向开发人员反馈他们做的事情不安全。“因为除非你已经建立了一个从代码到构建真正完全集成的 CI/CD 管道来测试一切，否则你今天可能没有能力做到这一点。你可能会在最后一步给他们反馈。”

“如果你要左移，就一直左移，”肯纳打趣道。

## 开源工具有助于云原生安全性

Kaczorowski 说，虽然从一开始就将云原生安全实践集成到软件交付管道中更容易、更快，但大多数团队在将更多工作负载迁移到 Kubernetes 并熟悉开发方法和工具时，都会构建这些实践。“然后[他们]走向成熟，进入 CI/CD 渠道，进入更复杂的策略管理。”

然而，开源项目、供应商和 IT 团队本身有几种方法可以改进软件开发生命周期中的安全实践，这样团队就不再需要在快速和安全之间做出妥协。

Allen 认为，构建工具使软件开发实践“默认安全”不仅有帮助，而且对 Kubernetes 生态系统的健康也是必要的。构建这些工具的公司有责任使安全实践更容易实现。

她说:“开源项目和工具必须更加努力地建立在安全的实践中。”“我们不能把一切都留给开发商……”好吧，这里有一把尖刀。两头都尖，戴手套，我们没有手套给你。"

使用云原生安全工具，IT 团队还可以设定迁移到云原生的目标，并跟踪各种指标，如修补工作负载中的漏洞需要多长时间。您的修补速度是否加快了，这是否改善了您的安全状况？团队还需要一个良好的沟通计划和适当的策略，以便组织中的其他人可以知道什么需要修补。

“也许不是默认安全，而是有意安全，”肯纳说。它可以提供一组策略来帮助开发人员独立地构建和部署，同时仍然保持降低风险的控制水平。

虽然将安全性集成到 CI/CD 管道、流程和工具中的做法仍在出现，但开源项目，如云计算原生计算基金会的[开放策略代理](https://www.openpolicyagent.org/)和 [In-toto](https://github.com/in-toto/in-toto) ，以及谷歌的 [Grafeas](https://grafeas.io/) 和 [Kritis](https://opensource.google/projects/kritis) ，正在帮助解决这些需求。

但重要的是要记住，工具不是答案，托雷斯阿里亚斯说。“你不能用工具抓住一切。你必须和你的团队(一群人)一起评估风险。”

莫克里斯同意了。“第一步，就像这里的每个人都分享的那样，我想获得知名度。我想开始优先考虑风险，”他说。“但最终，我如何让我的组织中的这些团队进行沟通，以了解我们在所有这些不同的抽象层中都有不同的角色和责任，这也是一个挑战。”

[https://www.youtube.com/embed/6QKqLk8Jn0Y?feature=oembed](https://www.youtube.com/embed/6QKqLk8Jn0Y?feature=oembed)

视频

KubeCon+CloudNativeCon 和云原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>