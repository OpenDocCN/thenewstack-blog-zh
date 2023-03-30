# Kubernetes 在 IPv6 上迎头赶上

> 原文：<https://thenewstack.io/feature-flags-that-promote-teamwork-kubernetes-catches-up-on-ipv6/>

[展示促进团队合作的旗帜，Kubernetes 赶上 IPv6](https://thenewstack.simplecast.com/episodes/feature-flags-that-promote-teamwork-kubernetes-catches-up-on-ipv6)

在本周的[新 Stack Context](https://thenewstack.io/podcasts/context) 播客中，我们将与新 Stack 赞助商[launch blackly](https://launchdarkly.com/)的产品和平台副总裁[Adam zimmen](https://www.linkedin.com/in/adamzimman/)讨论特性标记如何促进跨团队协作和开发。

正如 Zimman [在本周](https://thenewstack.io/how-feature-flagging-transforms-teams-and-supports-devops/)的一篇文章中所写的，特性标志越来越多地被用于发布管理中，以将特性展示与代码部署分离开来。使用特性标志，一个新的特性可以，比如说，在向所有人推广之前，在一个小的友好的用户群中进行测试。但是你知道吗，使用特性标志实际上可以鼓励不同的团队、开发人员和产品经理更紧密地合作？

然后在节目的后半部分，我们将讨论[Mary branscome](https://twitter.com/marypcbuk)本周发表的文章，该文章讲述了由于【Kubernetes 对 IPv6 地址的支持有限而导致公司面临的一些问题。

互联网协议是互联网的基本寻址格式。创始人没有预测物联网或智能手机，也没有想到所有的知识产权都会被使用。他们设计了一个 32 位的地址字段，由四个 8 位字节组成，可以容纳大约 43 亿个可分配的地址。大多数 IPv4 地址都被占用了。今年早些时候，最后一个 IPv4 地址块被出售。只有大约 4300 万只留在野外。

思科估计，仅物联网一项，我们明年就需要 500 亿个地址。不用说，我们缺货。IPv6 拯救世界！这种格式有 128 位地址空间，总共提供 340，282，366，920，938，463，463，374，607，431，768，211，456 个 IPv6 地址，[或 340 个未确定的地址](https://www.ripe.net/about-us/press-centre/understanding-ip-addressing)。所以应该够我们用一段时间了。

几十年来，互联网工程任务组一直在警告我们 Ipv4 的枯竭，尽管企业一直在缓慢地采用它，只是因为企业本身迁移到 IPv6 没有真正的好处。所以 K8s 只在 IPv4 上开始并不是一个有争议的举动。但是，电信公司是 IPv6 的早期采用者之一，因为他们也在考虑 Kubernetes 的 5G，所以他们推动 IPv6 向前发展也就不足为奇了。

在 1.9 版本中，container orchestrator 支持仅支持 IPv6 的集群，而最新版本 1.13 使用 IPv6 友好的核心 DNS。下一个大挑战是对 IPv4 和 IPv6 的双栈支持。“对 Kubernetes 的双栈 IPv6 支持或多或少是设计完成的，”谷歌的 Tim Hockin 告诉 Branscombe。“我们有一个非常好的 Kubernetes 增强提案，但这项工作有点停滞不前。在这项工作完成之前，最好的情况是发布几个版本。”

[TNS 编辑部主任 Libby Clark](https://twitter.com/LibbyMClark) 主持了这场秀，一同主持的还有[TNS 执行主编 Joab Jackson](https://twitter.com/Joab_Jackson) 和 [Alex Williams](https://twitter.com/alexwilliams) ，新书库的联合创始人兼主编。

## 其他头条新闻

*   [如何在科技活动中设计包容性](https://thenewstack.io/how-to-design-inclusion-into-a-tech-event/):让我们假设科技公司和科技会议真的开始理解，拥抱多样性不仅是正确的，而且通过增加创新和其他好处来提高底线。那么，你如何让你的技术会议变得受欢迎和多样化呢？确保你有几张票给那些买不起的人。任命某人负责确保多样性、包容性和可访问性始终是每个规划步骤的一部分。并制定行为准则来描述一个无骚扰环境的存在。
*   [甲骨文如何插入云原生仪表盘 Grafana](https://thenewstack.io/how-oracle-plugs-into-the-cloud-native-dashboard-grafana/)
    本周，为了在洛杉矶举行的 Grafanacon，甲骨文发布了一个 Grafana 的插件，将甲骨文监控服务作为 Grafana 数据源公开。Grafana 是一个针对时间序列数据的开源可视化和警报工具。这意味着您可以在 Grafana 实例中可视化 Oracle 云基础设施数据，并使用它来创建监控仪表板。
*   [如何带领团队走向 DevOps 成熟](/how-to-lead-teams-to-devops-maturity/):在 CircleCI 供稿的这篇文章中，Rob Zuber 讨论了 DevOps 成熟的三大支柱以及它们为何如此重要。三大支柱是:1:合作和信任的文化。2:关注自动化和工具，3:致力于测量和持续改进。如果你没有一种合作和信任的文化，你可能会有一种责备和孤立的文化。自动化解放了员工去解决新问题。自动化系统给你可靠的反馈，而这些反馈就是你改进的方式。

云计算原生计算基金会 CircleCI、LaunchDarkly 和甲骨文是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>