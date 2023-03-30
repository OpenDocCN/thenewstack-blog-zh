# T-Mobile 向 GitOps 的“大开眼界”转变

> 原文：<https://thenewstack.io/t-mobiles-eye-opening-shift-to-gitops/>

GitLab 赞助了这个播客。

当然，将现有的软件生产管道和操作移植到原生云环境，或者更常见的是移植到云、裸机和本地服务器环境的混合环境，绝非易事。这个假设当然适用于手机服务提供商 [T-Mobile](https://www.t-mobile.com/) 在其数字化之旅中所处的情况。但是，虽然 T-Mobile 的运营规模比大多数组织都大，但 T-Mobile 通过应用许多组织依赖的相同实践取得了成功，无论是 10 人商店还是谷歌。这包括越来越依赖 [GitOps 进行版本控制](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) (VC)和存储库功能，同时也是一种将所有数据访问和功能结合到单一来源的方式，以帮助管理多云和服务器环境的巨大复杂性，当然包括 Kubernetes 部署。

[T-Mobile 的‘开眼’转移到 GitOps](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops)

T-Mobile 的主要目标之一是将“许多这些数据从传统位置转移到存储库中，这些数据可能在某个记录系统的数据库、服务注册中心等位置。T-Mobile 软件首席工程师 [Philip Marc Schwartz](https://www.linkedin.com/in/philip-schwartz-a18126a) 表示:“因此，我们能够在旅途中重新创建东西，以更动态的方式管理我们的用户群。“当您试图让这些系统正常工作时，能够解决您在这些系统中看到的问题，这是一种令人大开眼界的体验。看到这些问题得到解决是非常有趣的，因为你真的可以在有限的水平上解决它们。”

在这一集的[New Stack Makers](https://thenewstack.io/podcasts/makers)播客中，Schwartz 和[git lab 技术宣传总监 Priyanka Sharma](https://twitter.com/pritianka) 讨论了上周在纽约布鲁克林举行的 [GitLab Commit](https://thenewstack.io/new-relic-expands-observability-platform-with-new-logging-tracing-and-services-metrics/) 会议上，当组织在以云为本的环境中进行数字化转型时，他们在依赖 GitOps 和其他流程时所面临的潜在挑战。这一集由《新书库》的创始人兼主编亚历克斯·威廉姆斯主持。

在采用 GitOps 的更直接可量化的结果中，以前，T-Mobile 的 DevOps 用户必须等待几天才能获得服务和完全的目录访问权限。Schwartz 说，现在，随着 GitOps 存储库的使用，入职的滞后时间已经减少到 30 分钟，因此用户可以“立即”开始打开合并请求，以请求访问代码库的特定部分。“我们的目标是在五分钟内让用户能够快速进入系统，并立即开放合并请求，供各个团队批准，”Schwartz 说。

在向完全持续集成/持续交付(CD)流程转变的过程中，GitLab 在转向 Kubernetes 之前实际上[依赖于带有遗留工具的 GitOps。Sharma 说，GitLab 在没有 Kubernetes 的情况下以“老式的方式”转向 CD，“因为我们想开始并建立某种工作肌肉”。具体到 GitOps，“每个人都在 GitLab 的界面中工作，”Sharma 说。](/gitlab-finds-the-best-path-to-continuous-delivery-with-legacy-systems/)

不用说，T-Mobile 在很大程度上依赖于监控和可观测性，以及带有 GitOps 的时间序列数据库来管理其庞大的手机和通信网络的海量数据，这些数据总计可达 500 亿个数据点。Schwartz 说，所有这些都产生了一个巨大的需求，即能够记录存储和记录分析数据，并“试图拥有能够通过整个数据管道工作的工具来真正为我们管理它，以便我们能够看到它”。

“500 亿个数据点”指标让 Sharma“竖起了耳朵”，因为在 GitLab Commit 期间的播客采访结束后，在她即将主持的一次小组讨论中，云原生世界中的数据操作和数据工程变化是关键主题。夏尔马说:“我们设立这个小组的全部原因是，因为每家公司都是软件公司，你越复杂，你的服务就越多，产生的数据点就越多，你做的 GitOps 就越多。”"你如何理解如何理解所有这些信息？"

[https://www.youtube.com/embed/yT5zogF_NT0?feature=oembed](https://www.youtube.com/embed/yT5zogF_NT0?feature=oembed)

视频

### 在这个版本中:

[2:17:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=2:17) 在 T-Mobile 的 GitOps。
[5:25:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=5:25) 吉托普斯，吉特拉布，库伯内特斯。
[9:36:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=9:36) GitOps 降低准入门槛。
[11:50:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=11:50) GitOps 挑战。
[16:45:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=16:45) GitOps 最佳实践。
[21:37:](https://thenewstack.simplecast.com/episodes/t-mobiles-eye-opening-shift-to-gitops?t=21:37) GtOps:前路。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>