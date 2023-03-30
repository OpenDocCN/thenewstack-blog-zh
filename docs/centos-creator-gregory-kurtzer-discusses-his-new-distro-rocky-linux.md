# CentOS 创建者 Gregory Kurtzer 讨论他的新发行版 Rocky Linux

> 原文：<https://thenewstack.io/centos-creator-gregory-kurtzer-discusses-his-new-distro-rocky-linux/>

Rocky Linux 是一个基于 1:1 兼容的 Red Hat Enterprise Linux 二进制文件的新发行版，一个[被设计为 CentOS 的替代版本](https://thenewstack.io/post-centos-rocky-linux-fights-for-community-driven-enterprise-open-source/)，CentOS 曾经是 RHEL 的二进制兼容版本(没有许可费)，直到 Red Hat [去年改变了 CentOS 的路线](https://thenewstack.io/wherefore-art-thou-centos-rocky-linux-cloudlinux-and-centos-stream/)，使其更像是一个[实验发行版](https://thenewstack.io/back-to-the-future-a-look-at-centos-streams/)。 [Rocky](https://rockylinux.org/) 是由 CentOS 的创始人 Gregory Kurtzer 创建的，Rocky 也肩负着提供企业级 Linux 版本的使命。

新的 Stack 很幸运地问了 Kurtzer 几个关于他的新发行版的问题。对于那些一直担心该做什么的人来说，现在 CentOS 不再是以前的平台了，拿起你最喜欢的饮料继续阅读吧。

**说说你对 CentOS 和 Red Hat 之间发生的事情的看法？**

当 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 在 2014 年接手这个项目时，我并没有参与 CentOS，但我相信这是 CentOS 团队的一些有针对性的雇佣，看起来像是 CentOS 的权利(网站、徽标、名称等。)在那时给了红帽。

从那时起，Red Hat 在稳定和组织 CentOS 方面做了出色的工作，但也改变了 CentOS 的一些核心租户。例如，随着时间的推移，一些开发包已经从 CentOS 中移除，并对社区隐藏，这确实是事情发生变化的一些最初迹象。

2020 年 12 月，宣布 CentOS 8 EOL(生命周期结束)已加速到 2021 年底，并将被 CentOS Stream 取代，CentOS Stream 不再是 Enterprise Linux 的克隆，而是将成为 Red Hat Enterprise Linux 的测试场。

这是历史重演的地方。早在 2004 年，Red Hat 做了同样的事情，停止所有版本的“Red Hat Linux ”,并强迫用户使用 Red Hat Enterprise Linux。

Linux 是一个社区项目，它是免费的。在一个 Linux 发行版中有成千上万个独立的项目被构建在一起，但是这个发行版只是这些包的顶点。虽然组装它是有价值的，但它仍然完全由免费软件组成。因此，总是需要不受公司需求控制的自由可用的选项，以确保适当缓解固有的利益冲突。

你在 Rocky Linux 上面临的最大挑战是什么？

第一个挑战实际上与构建一个基础社区有关，该社区是包容性的，专注于支持企业，同时消除重复 CentOS 所发生的风险。

例如，重建 RHEL 并不困难。如果这是我们的首要任务，我们本月早些时候就会完成。相反，我们的首要任务是建立社区、基础设施和信任，让 Rocky Linux 永远保持稳定、开放、协作和安全。

为了做到这一点，我们一直在大力投资构建基础设施。我们今天刚刚达到了构建基础设施就绪性的一个重要里程碑，这是我们在[上一次社区更新](https://forums.rockylinux.org/t/community-update-january-2021/1667)中阐述的。这个构建基础设施将提供构建整个操作系统的基础设施，并允许来自不同组织的社区成员参与所需的维护。

第二个挑战是贡献者的速度。不要误会我的意思，我们喜欢这种支持，我们正在狂热地工作，以确保每个想要参与的人都有一个角色，但这是一个管理练习，我们正在学习如何快速处理。为了展示这一点的范围，在大约一个月的时间里，我们有 10，000 人加入了 HP CNG Slack(Rocky 社区的第一个家)，但我们不得不退出 Slack，因为 Slack 的免费层仅保留最近的 10，000 条消息，这基本上意味着消息保留仅持续了几天。我们负担不起 Slack 的费用(甚至没有折扣)，所以我们转到了 [Mattermost](https://mattermost.com) ，现在我们有了通往 IRC 的桥梁。我离题解释了这个社区在很短的时间内是如何发展壮大的，团队的管理已经被证明是对一大群人的有趣挑战。

【Rocky Linux 和 CentOS 会有区别吗？

从技术上来说，目标很少。过渡应该是完全无缝的，因为两个项目是完全兼容的。但在幕后，有大量的差异。

例如，我之前提到的构建基础设施。CentOS 主要是在个人开发者拥有的资源上手工构建的。开发团队总是很小，因为需要保持 RPM 签名密钥的秘密。这创造了一种文化，在这种文化中，总是有少数核心人物，其他人都是“局外人”。

洛奇非常不同。从一开始，我们就投资于基础设施，这样我们就可以向更大的包容性团队开放开发。将这一点与 FIPS 等安全目标结合起来，就非常强调我们正在构建的体系结构。

最后，Rocky Linux 将保持开放，我们将公布我们的规章制度、承诺和社区章程。我们希望社会对我们负责，以确保我们始终实现我们的承诺和目标，如果我们没有做到，我们希望为此受到谴责。

信任、协作和包容性是我们的一些主要核心价值观，我们希望确保属于社区的东西留在社区中。

对 Rocky Linux 的支持将全部由社区驱动，还是会有某种形式的企业/商业支持？

我们在 Rocky Linux 后面创建了一个实体，叫做“Rocky 企业软件基金会”(RESF)。我们的目标是成为一个 IRS 501(c)(3)组织，我们甚至会尝试快速实现这一目标。这意味着捐赠、赞助和投资在美国都是免税的(在欧盟也是如此)，但也意味着我们在这里不是为了盈利。我们不能销售服务、产品、支持等。

但是一个重要的目标是支持企业组织，其中大多数是商业实体。我们希望许多公司将利用 Rocky Linux 作为产品、支持、服务和 It 组织的基础，我们将尽一切努力帮助这些组织建立成功的产品和业务。这里的目标是确保这些组织可以利用 Rocky Linux，但不能控制它。

老实说，我的公司 [CIQ](http://www.ctrliq.com) 刚刚从秘密行动中走出来，我们有一个面向性能关键型应用的基础架构软件堆栈。我们不仅将利用 Rocky 帮助我们的客户取得成功，而且我们还将把它作为我们产品组合的一部分来提供支持。我希望其他公司也这样做！

只是重申一下，没有公司，甚至我自己的公司，会控制 Rocky Linux，RESF 将永远保持自由，以企业软件社区的最大利益运行。

**用户能够轻松地将 CenOS 迁移到 Rocky Linux 吗？如果是这样，那将如何运作？**

现有的 CentOS 8 系统(或 RHEL 8)将能够通过一个 DNF 命令进行迁移。就是这样。

洛基 Linux 会得到主要云主机提供商的支持吗，比如亚马逊网络服务(Amazon Web Services)(AWS)、谷歌云和 Azure？

AWS 已经公开宣布了他们与我们的合作和赞助，我们已经在与谷歌和 Azure 进行讨论。我很乐观，所有三个主要的美国云，以及至少一个非美国主要的云托管平台，将支持 Rocky 作为一流的操作系统产品。

还与提供 Rocky Linux SKUs 的主要硬件供应商进行了讨论。

**Rocky Linux 的开始和 CentOS 的开始有什么不同？**

CentOS 社区发展缓慢，核心团队通常只有一小撮人。洛基 Linux 从第一天开始就是火箭。在我 20 多年的开源职业生涯中，我从来没有见过这样的事情。每天都有数百名新人加入并提供帮助！

这真的是做这件事的最佳时机。世界上有如此多的人被锁在里面，不能做太多事情，这个项目为创造力、发展、(虚拟)社交以及与一群伟大的人一起学习新东西提供了一个奇妙的出口。

就像一个永久的聚会，每个人都被邀请了！

开发人员如何参与 Rocky Linux？

加入我们的 [Mattermost](http://chat.rockylinux.org) 实例，搜索你感兴趣的频道，或建议一些新的频道或兴趣(SIG)，并加入对话。我们还有论坛、贡献者表单等等。所有这些都可以在我们的主页找到[链接。有很多机会和团队仍在发展，所以来参加派对吧！](https://rockylinux.org)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>