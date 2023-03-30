# 防火墙后维基百科的基础设施是什么样的

> 原文：<https://thenewstack.io/what-wikipedias-infrastructure-is-like-behind-the-firewall/>

KubeCon+CloudNativeCon 赞助了这个播客，作为对 Kubernetes 终端用户的一系列采访的一部分。听听之前关于【Conde Nast 如何基于 Kubernetes 创建统一基础设施平台的故事。

[维基媒体基金会](https://wikimediafoundation.org/)对文化和媒体共享的影响在全球范围内产生了不可估量的利益。作为管理传说中的维基百科、维基共享、维基资源和许多渠道的基金会，维基媒体的使命是“为世界带来免费的教育内容”。

维基媒体基金会(Wikimedia Foundation)高级安全架构师 Chase Pettet 表示，总的来说，仅维基百科就有大约 300 种不同的语言，每月在 15 亿种不同的设备上有超过 5000 万篇文章，每秒钟有 6000 次浏览，有 25 万名编辑参与。“编辑是这场运动的生命线，”佩特特说。

在这个由 New Stack 创始人兼主编 Alex Williams 和万事达卡云原生工程副总裁 Ken Owens 主持的播客中，Pettet 讨论了 Wikimedia 过去和现在的基础设施管理挑战，以及是什么让世界上最重要的免费信息提供商之一成功。

[Chase Pettet——防火墙后面维基百科的基础设施是什么样的](https://thenewstack.simplecast.com/episodes/chase-pettet-what-wikipedias-infrastructure-is-like-behind-the-firewall)

如今，维基媒体基金会一直积极参与其所谓的“2030 计划”。佩特特说，这是“基金会、董事会和社区之间的合作，每个人都走到一起，找出这件事应该去哪里，朝什么方向发展”。“我所读到的和我的理解是，我们希望成为一个促进免费知识的平台，这有助于整个托管云本机、数据本地性的事情。”

Pettet 说，这样一个大规模项目的基础设施部分包括标准的必要 CI 检查、代码审查和其他过程，依赖于 Puppet。为了安全起见，强调了封锁边界方法。“本质上，一切都知道防火墙规则应该是什么，”佩特特说。"这是动态实例化和管理的."

Pettet 说，OpenStack 的使用也被视为在允许技术社区不断创新方面发挥了关键作用。例如，对于 Kubernetes 来说，OpenStack 和 Kubernetes“非常迷人，因为从本质上讲，它们解决了相同的问题:它们是一个编排和调度以及资源受限的平台，”佩特特说。“只是它们有不同的原生结构，”他说。

佩特特还将维基媒体基金会与 OpenStack 的关系描述为“困境中的婚姻”。“我知道试图用肩膀扛多块石头要花多少钱。如果我可以这么说的话，也许这是一点经验之谈，”佩特特说。“但最重要的是，如果你要跨多个垂直领域解决同一个问题，你应该非常非常确定为什么要这样做，并有办法确定这样做是否值得。”

佩特特说，维基媒体基金会使用 Kubernetes 来运行相对有限的支持主要网站的服务。然而，他举例说，MediaWiki 不能在 Kubernetes 上运行。

“这个问题不仅仅是容器化的单一网络应用程序，因为 MediaWiki 的一个特点是希望我可以在我的家庭服务器上安装 MediaWiki，并拥有一个功能完善的 Wiki，希望它包括搜索组件和其他一切，”Pettet 说。“但另一方面，我们正在以前面提到的巨大规模运行相同的应用程序，拥有可以执行这两种功能的东西是困难和复杂的。”

佩特特还提到，尽管外界压力要求收集用户信息，维基媒体对隐私的承诺仍然坚定不移。“基金会非常重视隐私，”他说。“隐私是我们希望成为领导者的一件事，我们希望能够做到。”

例如，Pettet 说，Wikimedia 不会将用户的网络日志数据保存超过 90 天，其中一些数据只会保存 30 天。“在更大的互联网时代，这是闻所未闻的，”佩特特说。

加入我们的 KubeCon + CloudNativeCon Virtual，我们将与技术专家讨论自动化时代的 DevOps 运动。[现在就注册](https://www.cvent.com/events/kubecon-cloudnativecon-europe-2020/registration-f83a2bca694e4e389f002e61aafcea6f.aspx?r=f0efde22-0652-4eab-b320-afbb48b7ad83&refid=Media&tystub=7hq9h4&fqp=true)！

[![](img/1126c24a27cdc3f9a5d8d73ed7213aec.png)](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>