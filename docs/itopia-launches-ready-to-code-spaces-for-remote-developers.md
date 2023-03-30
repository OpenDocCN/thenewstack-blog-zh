# Itopia 为远程开发者推出现成代码空间

> 原文：<https://thenewstack.io/itopia-launches-ready-to-code-spaces-for-remote-developers/>

疫情从根本上改变了对远程工作或混合模式的开发人员的期望，他们期望来办公室的次数比过去几年少得多。

从 11 月更新的 Harness [开发人员满意度调查](https://harness.io/blog/news/2020-developer-satisfaction-report/)来看，74%的受访者表示，一旦他们的公司完全恢复面对面工作，他们希望继续远程工作。(新的堆栈已经[报道了远程工作的好处](https://thenewstack.io/2022-forecast-whats-next-for-tech-workers/)。)

让开发人员远程工作也给公司带来了一些挑战，增加了潜在希望随身携带项目的员工泄露代码的风险，以及在没有更同质的基础架构的情况下配置开发环境的潜在复杂性，这种基础架构来自于支持单个园区的团队。

为了应对这些挑战， [itopia](https://itopia.com/itopia-spaces/?utm_content=inline-mention) 发布了全新的完全托管、可直接编码的 [itopia Spaces](https://itopiaspaces.com/) 云环境。这些环境是设计为从浏览器启动的云工作区，具有所有必要的预配置依赖项和可配置的[安全](https://thenewstack.io/category/security/)控件，有助于决定开发人员在远程工作区工作时能做什么和不能做什么。

## 提高远程团队的安全性

Spaces 基于 Google Cloud 团队开发的开源有状态工作负载操作符 [Selkies](https://github.com/selkies-project/selkies) 。这种实现利用了服务器端呈现，这意味着源代码不以文本格式发送到浏览器，从而降低了脚本攻击和浏览器漏洞的风险。

“由于 Spaces 是一个 web 应用程序，因此在 Spaces 上进行开发本质上比传统的开发工作流更安全，”itopia 的开发人员关系负责人 Jan Van Bruggen 告诉新堆栈。

“通过将开发环境转移到浏览器中，项目源代码被下载并存储在云中，而不是所有开发人员的笔记本电脑上。这种端点隔离可防止代码从丢失、被盗、未归还的笔记本电脑中泄漏出来，确保查看项目代码库时始终需要有效授权。”

## 平衡安全性和生产力

在拥有无缝工作体验的开发人员和保护公司利益的系统管理员之间保持微妙的平衡是一个持续的挑战。Spaces 允许管理员定义网络策略，防止复制/粘贴，实现会话超时，并为即将离职的开发人员提供一键式离开服务。

关于潜在的开发人员摩擦，Van Bruggen 说，“唯一的生产力/安全性权衡与团队管理员的选择性安全特性有关。

例如，严格的网络政策可能会阻止开发人员从他们信任的网站上即时下载有用的可执行文件。然而，任何这样的生产力障碍都可以通过管理员更新空间的配置来克服，以准确地提供他们的开发人员需要的东西。”

Spaces 使用单点登录，开发人员被授予每个空间内的超级用户权限。下面的视频提供了内部开发环境的预览。

[https://www.youtube.com/embed/SQciEuB3Qis?feature=oembed](https://www.youtube.com/embed/SQciEuB3Qis?feature=oembed)

视频

## 迁移到空间

对于正在考虑从他们现有的开发环境转移到空间的团队，itopia 推荐一种增量方法。

“现有的开发人员将希望通过移植他们的个性化功能或尝试每周几个简单任务的默认功能来适应他们的新‘虚拟第二笔记本电脑’，”Van Bruggen 说。

与此同时，新团队成员可以通过从他们的个人电脑登录来避免等待公司硬件，直接使用团队的空间作为他们工作所需的唯一开发环境。"

迁移的时间表可以通过[自动化环境配置](https://thenewstack.io/local-environment-as-code-is-it-possible-yet/)压缩。通过利用[预先配置的映像](https://github.com/itopia-inc/spaces-images)，过渡得到进一步简化。

## 减少对多种环境的需求

迁移到空间的一个潜在好处是消除了在同一台物理机器上维护多个开发环境的复杂性。

“许多开发人员从事多个项目/子项目，具有不同的环境需求，因此目前由这些人来执行这些项目环境之间的本地分离，”Van Bruggen 说。

“然而，如果不手动容器化、切换用户帐户或完全切换笔记本电脑，很难防止系统级依赖关系跨越这些人为边界。”

Spaces 通过将单个项目容器化来应对这一挑战，并减少了判断某些东西在本地机器上是否工作的需要。这减少了硬件和操作系统的调试，这通常伴随着为特定项目配置环境。

Itopia 估计，通过使用空间，可以减少大约一半的维护劳动和几乎所有与新项目相关的入职劳动。

启动客户包括 Neustar 和 8base。“我们在全球各地都有软件开发人员，”8base 的创始人兼首席执行官阿尔伯特·桑塔洛在谈到 itopia Spaces 时指出。“在当今的混合工作环境中，提高他们的工作效率，同时保护我们代码库的安全性，这对我们来说至关重要。

“Itopia 帮助我们更快、更安全地交付产品，而不会中断我们现有的开发人员工作流程。”

Spaces 托管在专用 Google Kubernetes 引擎(GKE)集群上的 Google Cloud 中。如果你对这种开发环境的方法感兴趣，itopia Spaces 可以通过 itopiaspaces.com 的[或在](https://itopiaspaces.com/)[的谷歌云市场](https://console.cloud.google.com/marketplace/product/itopia-public/itopia-spaces)进行为期 14 天的试用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>