# Devs 和 Ops:这场婚姻还有救吗？

> 原文：<https://thenewstack.io/devs-and-ops-can-this-marriage-be-saved/>

底特律——我们还在向左转吗？期望开发人员承担安全和基础设施供应以及编写应用程序的负担现实吗？平台工程是拯救 DevOps 梦想的答案吗？

[https://www.youtube.com/embed/laqo-cjiL74](https://www.youtube.com/embed/laqo-cjiL74)

视频

一句话:开发人员和运营人员真的互相交流吗——或者只是被动-主动地交换吉拉入场券？

[Devs 和 Ops:这段婚姻还有救吗？](https://thenewstack.simplecast.com/episodes/devs-and-ops-can-this-marriage-be-saved)

周四，在汽车城的[kube con+CloudNativeCon North America，](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)New Stack 召开了一个名为“开发人员和运营人员:是时候进行一些 Kubernetes 夫妇治疗”的小组会议，讨论了这些话题。

小组成员包括 [Saad Malik、](https://www.linkedin.com/in/saad-a-malik)首席技术官和 [Spectro Cloud 的联合创始人；](https://www.spectrocloud.com/?utm_content=inline-mention) [Viktor Farcic，](https://www.linkedin.com/in/viktorfarcic/)[Upbound 的开发商代言人；](https://www.upbound.io/?utm_campaign=2022_Q3_EVER_GBL_The-NewStack-GENERAL&utm_medium=The-New-Stack&utm_source=referral&utm_content=inline-mention) [Liz Rice，](https://www.linkedin.com/in/lizrice/)Isovalent 的首席开源官， [Aeris Stewart，](https://www.linkedin.com/in/aeris-stewart-%F0%9F%8C%88-083487187/) [Humanitec 的](https://humanitec.com/?utm_content=inline-mention)社区经理。

最新的 TNS 煎饼早餐由新书库的创始人兼发行人[亚历克斯·威廉姆斯主持，TNS 特写编辑](https://thenewstack.io/author/alex/)[希瑟·乔斯林回答观众的问题。该活动由 Spectro Cloud 赞助。](https://thenewstack.io/author/hjoslyn/)

## 减轻开发人员的认知负担

DevOps 结构中的一大痛点——跨职能团队中前端和后端的结合——是所有的开发人员不一定愿意或能够承担所有要求他们承担的额外责任。

Stewart 说，许多组织已经“复制粘贴了这种一刀切的开发运维方法”。

“如果你看看工具领域，它不仅在工具数量方面，而且在工具本身的复杂性方面都在快速增长，”他们说。与此同时，开发人员被期望接管越来越多的软件交付过程。所有这些加在一起，对他们来说是太多的认知负荷。”

这种情况也对运营工程师产生了影响，他们必须帮助减轻开发人员的负担。“这导致了这些组织的许多低效率，”他们补充道，“以及许多 DevOps 应该消除的同样的低效率。”

平台工程(Platform engineering)——运营工程师为开发人员提供一个内部开发人员平台，抽象出一些复杂性——是“希望的迹象”，Stewart 说，对于那些难以实施 DevOps 的组织来说。

Farcic 说，DevOps 背后的概念是“让团队自给自足，这样他们就可以完全控制他们的应用程序，从想法一直到在生产中运行”。

但是，他补充道，“你不能指望他们在 Kubernetes、 [AWS](https://aws.amazon.com/?utm_content=inline-mention) 等领域有 17 年的经验。这就是平台的用武之地。这就是其他具有一定专业知识的团队提供服务的方式，以便那些…开发人员和操作人员能够真正做他们应该做的工作，就像今天的操作人员使用 AWS 的服务来完成他们的工作一样。因此，对于我来说，AWS 对于 Ops 的意义就像内部开发平台对于应用程序开发人员的意义一样。”

## 一致性与创新

小组成员承认，平台工程一直是 DevOps 圈子(以及 KubeCon)的热门话题，但定义仍然有点模糊。(“在许多组织中，‘平台工程’只是‘运营’的一种别出心裁的新说法，”赖斯说。)

观众向小组提出了关于 DevOps 模型的局限性以及平台工程如何融入讨论的问题。一位观众问及如何平衡为组织的开发人员提供一致平台的需求，同时允许开发人员进行定制和创新。

Malik 说，在一个平台工程结构中，一致性和创新都是可能的。“一个组织将决定他们希望能够在哪里提供这种抽象，”他说，并补充说，“当他们考虑他们希望作为一个整体在哪里时，他们可以考虑，嘿，当我们提供我们的平台时，我们将从 GitHub、从存储库管理提供从安全性到 CI/CD 的一切，如果你使用我们的 IDP 或平台本身，这就是你将得到的。

但是“将会有独特的使用案例，”Malik 补充道，比如开发人员正在开发新的区块链技术或者运行 T2 的 WebAssembly。

“我认为让那些开发团队有能力运行他们自己的平台是没问题的，只要你告诉他们，这些是你必须负责的领域，”他说。“您要对自己的安全、自己的备份、自己的保留能力负责。”

一位观众提到了[《团队拓扑》](https://teamtopologies.com/book)，这是一本由 [Manuel Pais](https://www.linkedin.com/in/manuelpais) 和 [Matthew Skelton](https://www.linkedin.com/in/matthewskelton) 撰写的 2019 年工程管理书籍，并问小组成员平台工程是否与 DevOps 相关，因为它更像是一种工程管理方法，而不是目的地。

“平台工程正处于发展的萌芽阶段，”斯图尔特说。“现在，它真正关注的是解决组织在实施开发运维时遇到的问题。

他们补充道:“我认为，随着我们看到社区越来越多地走到一起，并获得更多关于如何开发平台的最佳实践，你将看到它不仅仅是开发运维的一种不同方法，而是变得更加独特。但我认为它还没有完全到位。”

查看完整的小组讨论，从我们的 DevOps“咨询会议”中了解更多信息

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>