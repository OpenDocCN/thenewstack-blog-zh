# ContainerDays 2019: Knative 发布解决了 Kubernetes 的现实世界无服务器问题

> 原文：<https://thenewstack.io/containerdays-2019-knative-release-addresses-real-world-serverless-for-kubernetes/>

Kubernetes 版本 0.7.0 的无服务器连接器背后的社区开发人员希望新发布的特性能够更好地满足那些自从无服务器框架最近首次亮相以来一直使用它的人的现实需求。

本周在汉堡举行的[集装箱日](https://www.containerdays.io/)的间隙， [Matthias Wessendorf](https://developers.redhat.com/blog/author/mwessend/) ，Red Hat 的首席软件工程师，Knative 贡献者，告诉新的堆栈，v0.7.0 继续根据继续旋转其轮子的用户的反馈，为 Kubernetes 带来新的无服务器能力。对话和会议的地点在汉堡哈芬博物馆(Hafenmuseum Hamburg )( T7 ),这是一个修复的装载平台，也是这个历史港口的集装箱和船只仓库。

在周二与 Red Hat 工程师 Roland Hu 的集装箱日谈话中，Wessendorf 指出，当他在 Knative v0.7.0 正式发布前几个小时提到该版本时，他回答了很多关于 Knative v 0 . 7 . 0 的问题。这些包括事件特性，一个新的序列 API(将有更多的 API 改进)和更好的扫描能力。下面列出了更完整的改进列表。

此外，考虑到用于 CI/CD 的 [Tekton](https://cloud.google.com/tekton/) 越来越受欢迎，并且现在扩展到无服务器开发，Knative 社区现在也推荐使用 Tekton 而不是 Knative Build。

此版本和后续版本背后的概念是帮助进一步简化在无服务器框架上运行的应用程序的任务。这些包括构建容器、编排工作流、扩展 API、改进流量管理和其他新功能。

自从去年第一次发布以来，Knative 经历了许多变化，现在开源替代方案已经过商业应用的现场测试。Knative 社区开发人员，包括支持者 Google、Red Hat、Pivotal 和 IBM，以及许多其他贡献者，都试图为开发人员和服务提供商提供 Kubernetes 上的全套无服务器应用程序和功能。今年早些时候，红帽推出了 OpenShift 4，包括在其开发者预览版中包含 Knative 的可能性。以前，许多这些功能需要访问 AWS 的付费 Lambda 服务。到目前为止，Knative 在 GitHub 上有近 2000 颗星。

Knative 推出的其他新功能和 GitHub 上描述的[包括:](https://github.com/knative/serving)

*   API 现在包括 *`v1beta1`* 字段；
*   非根容器，支持“更严格”的 pod 安全策略；
*   已弃用的状态字段“不再填充”；
*   支持“基于并发的扩展”，HPA 可以使用这些指标。

Pivotal 和 Red Hat 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>