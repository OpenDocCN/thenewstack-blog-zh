# Linux 基金会为所有项目引入了遥测策略

> 原文：<https://thenewstack.io/linux-foundation-introduces-a-telemetry-policy-for-all-projects/>

[Linux 基金会](https://www.linuxfoundation.org/)已经向[介绍了一项关于收集和使用遥测数据的新政策](https://www.linuxfoundation.org/telemetry-data-policy/)，鉴于该政策将适用于 Linux 基金会监护下的许多项目，这可能会产生深远的影响。新政策将遥测数据定义为“关于软件如何使用或执行的数据”，而不是聚合数据，如可以在软件本身之外收集的一个软件的下载次数，现在任何此类数据的收集都必须“经过对拟议的遥测数据和收集机制的详细审查”

除了由 Linux 基金会托管的个别项目，如 Ceph、Rook 和 Etcd，该基金会还托管了许多其他子基金会，包括[云本地计算基金会](https://www.cncf.io/)、 [OpenJS 基金会](https://openjsf.org/)和[持续交付基金会](https://cd.foundation/) (CDF)，其中最后一个基金会在其最近的[技术监督委员会(TOC)会议上讨论了其采用的主题。](https://www.youtube.com/watch?v=Z9ps5sZa0a8&feature=youtu.be&t=421)

在新政策公布后的第二天举行的会议上， [Dan Lopez](https://www.linkedin.com/in/danlopez/) 作为 Linux 基金会的代表发言，向 CDF TOC 解释了该政策的起源，并表示该政策将适用于所有项目，无论他们在此之前一直在进行什么遥测数据收集。该政策本身清楚地表明了这一点，声明“默认情况下，Linux 基金会的项目不应该从代表项目分发的开源软件的用户那里收集遥测数据。”

“由于许多原因，所有的 Linux 基金会项目都属于这一类。[……]我的理解是，不会有任何不受保护的技术或项目被允许在未经审查的情况下继续进行遥测收集，”洛佩兹说。“Linux 基金会对防火墙背后的隐私类型的安全问题，甚至[个人身份信息]的传播有很多担忧。我们需要控制这种情况，并遵守其他政策，比如 GDPR。”

在接下来的讨论中，[CDF TOC 成员和](https://www.linkedin.com/in/ajglover/) [Spinnaker](https://www.spinnaker.io/) 代表 Andy Glover 提到该项目一直在讨论如何将遥测数据收集引入 Spinnaker，对此 Lopez 回应道“这不是巧合，Andy——这种政策是由我们发现如何正确进行 Spinnaker 数据收集而制定的。”

新的 Linux 基金会政策包括许多要点，基金会法律团队将围绕这些要点考虑任何新的遥测数据收集，例如将收集哪些数据、如何通知用户并获得同意、如何存储数据、此类数据的安全性以及数据的匿名化。

Linux 基金会并不是本月唯一谈论遥测数据收集和使用的机构，因为 GitLab 也曾[在此前表示](https://about.gitlab.com/blog/2019/10/10/update-free-software-and-telemetry/)将通过插入 JavaScript 片段来收集数据，并与 GitLab 和第三方 SaaS 遥测服务进行交互，从而开始收集新数据。遥测数据收集将被选择退出，而不是选择加入，遥测数据收集将通过 web 浏览器中的[不跟踪(DNT)](https://en.wikipedia.org/wiki/Do_Not_Track) 机制在每个用户的基础上关闭。然而，这一点是许多 GitLab 用户争论的焦点之一，该公司上周提供了一个更新，称“我们已经听到了你的担忧和问题，并撤销了对我们服务条款的任何更改。我们将处理反馈并重新思考我们的方法。在我们处理反馈并重新评估我们的计划之前，我们不会在 GitLab.com 或 GitLab 上激活用户级产品使用跟踪。”

Linux 基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>