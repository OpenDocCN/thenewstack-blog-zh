# 使用 BOSH 部署 Cloud Foundry 堆栈

> 原文：<https://thenewstack.io/using-bosh-to-deploy-the-cloud-foundry-stack/>

[Cloud Foundry](https://www.cloudfoundry.org/) 赞助了这个播客。

[用波什搞定堆栈](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done)

Cloud Foundry 的 [BOSH](https://bosh.io/) 继续为许多组织提供服务，作为一个缺失的[云提供商接口(CPI)](https://bosh.io/docs/bosh-components/) 环节，用于管理跨多云环境的整个生产周期中的部署。

[云服务咨询公司](https://www.linkedin.com/in/drnic) [Stark & Wayne](https://starkandwayne.com/) 的首席执行官 Nic Williams 博士和软件巨头 [SAP](https://www.sap.com/index.html) 的开发人员 [Marco Voelz](https://github.com/voelzmo) 上周出席了在巴塞尔举行的[Cloud Foundry Summit Europe](https://www.cloudfoundry.org/event/eusummit2018/)会议，并在播客中讨论了为什么 BOSH 和新堆栈的创始人兼总编辑 Alex Williams 继续处于 Cloud Foundry 的核心。

Voelz 说，BOSH 仍然是[Cloud Foundry](https://www.cloudfoundry.org/)multi Cloud 战略的关键部分，这主要归功于它的 CPI，CPI“从 BOSH 代码库本身抽象出所有那些本质的基础设施细节”。通过这种方式，BOSH 可以运行在 AWS、Azure、OpenStack 或“任何你喜欢的地方——只要有 CPI，”Voelz 说。

Voelz 说，作为对 BOSH 为那些不熟悉生命周期管理工具的人提供的总结，BOSH 最初由 VMware 为 Cloud Foundry PaaS 开发，允许开发人员“启动您的部署，而您的所有虚拟机都负责为您配置复杂的集群，因此您不必这样做”。BOSH“还具有恢复能力，如健康管理”，因此部署保持“正常运行”

威廉姆斯说，他是 2012 年 Cloud Foundry 首次亮相后不久发现波什的第一批人之一，并描述了自那以来发生的许多变化。“那时候只有一朵云，”沃兹说。"现在，有许多云，所以抽象已经发展到适合这些."

威廉姆斯当时在帕洛阿尔托工作，他描述了自己是如何“与一些 VMware 人在一起，我会非常兴奋。”

“Cloud Foundry 出现了，他们谈到 Cloud Foundry 是内壳，有一个神秘的外壳管理着生命周期，照看这个叫做 Cloud Foundry 的东西，”Williams 说。

Williams 描述了他的团队在构建 AMIs 时遇到的问题，并且“没有工具”

"还有一个叫 BOSH 的东西，它承诺围绕构建 ami 或基本映像开发工具."威廉姆斯说。“此后，我们的整个包装系统不需要(开发者)念咒语，除此之外非常简单。”

回顾到今天，Voelz 说“没有一种工具能在一次体验中给你所有的属性。沃兹说，对于替代方案，部署需要了解“实际的基础设施和云之间的差异”。我认为波什做得最好的是把这些都抽象出来，不要泄露太多的细节。"

Williams 说，BOSH 提供的一个关键好处是它如何“拥有和运营云的外部以及虚拟机的内部”。“在外部，它将在亚马逊上提供一个磁盘并连接它，”威廉姆斯说。但在内部，它会装载并格式化磁盘，通过这个简单的原语，它可以拥有并操作磁盘，调整其大小并进行缩放

BOSH 的下一个前沿将包括拓宽和优化管理部署和构建版本的用户体验，因为这两项任务都是由多个用户管理的。“例如，这与按需服务代理的当前发展有很大关系，而以前，BOSH 是运营商在需要改变系统状态时使用的工具，”Voelz 说。

随着越来越多的用户使用 BOSH，未来的一个关键挑战将是在一个组织的保护伞下处理“越来越多的部署”。

[https://www.youtube.com/embed/hoXX83tEvdM?feature=oembed](https://www.youtube.com/embed/hoXX83tEvdM?feature=oembed)

视频

### 在这个版本中:

[2:34:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=2:34) 对于可能不熟悉的人来说，波什是什么？
[6:32:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=6:32) 今天的波什是什么让它仍然独特而重要？
[13:01:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=13:01) 在 Cloud Foundry Container Runtime 和 Kubernetes 中使用 BOSH 有什么适应性？
[17:17:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=17:17) 在 Kubernetes 上运行 Cloud Foundry 的背景是什么？
[23:51:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=23:51)BOSH 如何帮助开发者大规模工作。
[31:15:](https://thenewstack.simplecast.com/episodes/using-bosh-to-get-the-stack-done?t=31:15) 复杂性在今天的堆栈中去了哪里。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>