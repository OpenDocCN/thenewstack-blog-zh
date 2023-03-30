# Jenkins World 2017 强调了持续集成的日益普及

> 原文：<https://thenewstack.io/jenkins-world-2017-highlights-growing-ubiquity-continuous-integration/>

2004 年， [Kohsuke Kawaguchi](http://kohsuke.org/) 创建了被称为 [Jenkins](https://jenkins.io/) 的开源自动化服务器。那时它叫哈德逊。[甲骨文](http://www.oracle.com)在 2010 年收购太阳微系统公司时收购了该项目，后来一个巨大的知识产权威胁导致了分叉和更名。甲骨文肯定对自己在这一点上相当失望，因为 Jenkins 现在不可否认地是持续集成/持续交付世界的绝对中心。

CI/CD 社区中的许多主要推动者和震动者本周在詹金斯世界开会。曾经，一个羽翼未丰的会议隐藏在 JavaOne 附近的一个小会议空间里，这个会议已经独树一帜，现在占据了旧金山 Marriott Marquis 的一个特大酒店会议空间。这本身就是持续集成的完美比喻:一旦被归入到实验团队的密室中，这种实践现在被高层管理强制作为区别于竞争对手的一种方式。

Checkmarx 的应用安全战略全球总监 Matt Rose 说 Jenkins 是 CI/CD 领域的领头羊。“我们的大多数客户都在以某种方式使用 Jenkins。我看到很多人处于真 CI/CD 的进化阶段。很少有人觉得自己现在 100%在那里，”罗斯说。他在 Jenkins World 帮助传播静态分析的福音，作为构建和测试过程的一部分。

他不是一个人。德沃普斯的许多大人物都来了，赞助这场演出。从 [Atlassian](https://www.atlassian.com/) 、 [GitHub](https://www.github.com) 和 [CloudBees](https://www.cloudbees.com/) ，到[亚马逊](https://aws.amazon.com/)、 [HPE](https://www.hpe.com/us/en/home.html) 和[红帽](https://www.openshift.com/)，这个活动已经成为软件开发世界中所有不涉及实际编写代码的事情的中心会议。

詹金斯是压倒性的平台，所有这些赞助商必须流入。他们的工具和测试框架都被集中到 Jenkins 的工作列表中，并在每次新代码被检入存储库时运行。当今的前沿是将那些测试环境转储到主分支之外的 URL 中，这样营销、管理或开发中的任何老用户都可以立即访问测试代码，而不需要登录到混乱的测试系统或 VPN。

CloudBees 长期跟踪 Jenkins 的开发，并为开发人员提供自己的基于云的环境来托管他们的 Jenkins 工作。该公司还为企业用户提供了 Jenkins 的策划版本，其中包含经过验证的插件。CloudBees 创始人兼首席执行官[Sacha laboury](https://www.cloudbees.com/team/sacha-labourey)表示，Jenkins 的使用继续增长，并几乎一对一地跟踪企业内部 CI/CD 实践的采用情况。

“几年来，CI/CD 的主要采用基本上是由前沿团队利用影子 IT、下载 Jenkins 或使用 SaaS 来完成的。这是因为将每个人的 CI/CD 标准化对 it 部门来说没有价值，”Labourey 说。

https://twitter.com/stew_cee23/status/902938931787833344

“我们现在看到的是更多的自上而下执行 [DevOps](/category/devops/) 。企业已经意识到他们需要齐心协力。我认为在某些方面，CloudBees 是 Jenkins 采用情况的一个很好的代理:很明显，那些自上而下的为组织中的每个人采用一个通用特性集的情况正在发生:你有吉拉、GitHub、CloudBees 和 Jenkins，然后你有团队特定的解决方案，这取决于它是移动团队、Java 团队、Linux 团队还是其他什么。说到每个人都在使用的公共汽车，那就是詹金斯。

为此，CloudBees 在 Jenkins World 上发布了一系列公告。去年最大的新闻是 4 月份增加了[管道](https://jenkins.io/doc/book/pipeline/)，允许开发者在 [Groovy](http://groovy-lang.org/) 中编写构建指令。今年，这个接口已经被修改，并且与 Groovy 分离，为不太懂技术的用户解决了一些棘手的问题。

“我认为造成最大摩擦的是最初版本的管道，因为你必须学习 Groovy 来定义这些管道。这对高端团队有效，但组织中更大的一部分是做非常愚蠢的管道的人。人们想要的只是几个步骤，所有这些最终都被更复杂的应用程序消耗掉了，但对许多团队来说，学习曲线太高了，”Labourey 说。

为了解决这个问题，今年早些时候，Jenkins 团队推出了一种新的 UI，允许开发人员以图形方式构建管道，而无需学习 Groovy。Labourey 说，这是对平台的一个重大改进，他的公司已经尽快将它引入 CloudBees 平台。

Jenkins 用户的另一个痛苦领域是处理多个插件，使它们协同工作，并维护构建端到端构建和测试机制所需的各种配置。因此，CloudBees 推出了 CloudBees Jenkins 顾问服务。

“詹金斯可能很复杂。有很多配置和插件等等。我们几年来在支持方面所做的是，当我们看到问题时，我们开始在软件中编写规则，知道如何检测这些问题，”Labourey 说。“我们在这里决定做的是使这成为一个 SaaS 产品，可以连接到您的 Jenkins 实例，以注意到已知的问题。”

CloudBees 在展会上的大动作是推出了 [DevOptics](https://www.cloudbees.com/products/cloudbees-devoptics) ，这是一个新的端到端数据分析和聚合平台，与开发流程的每个方面都有[。Labourey 表示，Jenkins 及其各种装备已经在跟踪每一个发生的构建。系统已经知道谁编写了这个版本的变更，谁批准了产品化，以及在那个版本上的测试是如何执行的。](http://sdtimes.com/cloudbees-devoptics-jenkins-world/)

Labourey 说，将这些信息收集到一个单一的仪表板上，可以让经理们看到整个开发过程。CloudBees 希望这一新产品能够增加开发人员和管理人员在构建和测试过程中的透明度。

该公司还引入了与 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 及其生态系统成员的新合作伙伴关系，以允许额外的托管服务覆盖到用户的构建流程和管道中。

詹金斯世界本周继续在旧金山举行。

[![](img/035f781299a0ef3abc9421b5534f4d43.png)](https://www.pagerduty.com/summit/)

[Red Hat](https://www.openshift.com/) 和 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>