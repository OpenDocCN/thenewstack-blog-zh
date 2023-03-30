# 从 CNCF 沙盒到孵化需要什么

> 原文：<https://thenewstack.io/what-it-takes-to-go-from-cncf-sandbox-to-incubation/>

自第一个项目 Kubernetes 以来，[云原生计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 项目的数量已经爆炸式增长，为数百个工具和平台奠定了基础，这些工具和平台已经实现了沙盒、孵化或毕业的各种 CNCF 项目成熟度里程碑。

在最新一集的 New Stack Makers 播客中，我们来看看两个已经从沙盒进入孵化阶段的 CNCF 项目: [Crossplane](https://crossplane.io/) ，这是一个用于基础设施组装的 Kubernetes 附加组件，以及 [OpenTelemetry](https://opentelemetry.io/) ，它支持一系列工具、API 和 SDK 以实现可观测性。

[https://www.youtube.com/embed/hqAG5h1gZtM](https://www.youtube.com/embed/hqAG5h1gZtM)

视频 播客参与项目的嘉宾包括[高级软件工程师 Dan Mangum](https://www.linkedin.com/in/danielmangum) ，云平台提供商[Upbound](https://www.upbound.io/)(cross plane)[Constance Caramanolis](https://www.linkedin.com/in/ccaramanolis)，首席软件工程师 [Splunk](https://www.splunk.com/) ，以及 OpenTelemetry 治理委员会和

《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这次播客。

[从 CNCF 沙盒到孵化](https://thenewstack.simplecast.com/episodes/what-it-takes-to-go-from-cncf-sandbox-to-incubation)

在 OpenTelemetry 的案例中，Caramanolis 描述了最初对申请孵化有一些犹豫。

“我们提供跟踪、指标和日志，但我们承诺 OpenTelemetry 的首要任务之一是完成跟踪。因此，我们正试图平衡我们在追踪其他一切方面取得进展的速度，因为开放追踪社区一直处于暂停状态——我认为这是一个公平的说法——很长时间以来，我们希望确保他们能够开始采用新的遥测追踪方式，“Caramanolis 说。“所以，我们正在努力做到这一点。但我认为我们非常幸运——这个项目从创建到孵化花了大约两年时间，这是一项艰巨的工作。”

由于 OpenTelemetry 与 OpenTracing 完全向后兼容，Young 说，“在更高级的项目 OpenTelemetry 中存在这种奇怪的差距”。“但是如果你看看 CNCF 的项目列表，看起来 OpenTracing 是更先进的项目，”他继续说道。“因此，我们申请了孵化，以便通过将 OpenTelemetry 用于孵化，我们可以对 OpenTracing 项目进行归档。这将在某种程度上清理 CNCF 的景观，使其更好地符合现实。”

Crossplane 主要用于解决云本地 DevOps 团队经常遇到的问题:如何使用用于在 Kubernetes 上供应工作负载的相同 API 来供应基础架构。Mangum 描述了 Crossplane 如何允许开发人员访问数据库的 API，这可以通过 [RDS 实例](https://github.com/crossplane/crossplane/discussions/2209)或[云 SQL](https://cloud.google.com/tools/powershell/docs/sql/setup#:~:text=A%20Cloud%20SQL%20instance%20is,acceptable%20to%20perform%20database%20maintenance.) 实例来满足。曼古姆说:“不需要真的暴露在他们面前——他们需要一种一致的方式来看待这一点。”。“所以，我们通常使用这样的短语，‘构建你自己的 Heroku 或类似的东西，它是建立在 Kubernetes 之上的。’"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>