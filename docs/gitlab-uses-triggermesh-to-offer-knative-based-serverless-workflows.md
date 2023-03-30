# GitLab 使用 TriggerMesh 来提供基于 Knative 的无服务器工作流

> 原文：<https://thenewstack.io/gitlab-uses-triggermesh-to-offer-knative-based-serverless-workflows/>

多亏了最近发布的 Knative 的强大和灵活性，GitLab 已经为用户提供了从他们的存储库到 Kubernetes 集群上自动执行他们的无服务器代码的能力

一家名为 [TriggerMesh](https://triggermesh.com/) 的新公司已经为 GitLab 提供了这种能力。

GitLab Serverless 于上个月底随着 GitLab 11.6 的发布而上线，它可以使用谷歌的开源软件 [Knative](https://cloud.google.com/knative/) 在 Kubernetes 上执行无服务器功能，该软件提供了一种方式[和其他功能](https://www.youtube.com/watch?v=CylT5O6IfkU)、[来封装然后无服务器地运行 Kubernetes](/with-knative-google-brings-multicloud-serverless-to-the-enterprise/) 的工作负载。

这是一个及时的提议。随着 GitHub 在今年早些时候推出了自己的高级工作流工具 [GitHub Actions](https://github.com/features/actions) ，GitHub lab 正面临着越来越激烈的竞争。

开发人员可以使用 GitLab Serverless 来编排整个“GitOps”风格的生命周期，其中代码一旦提交，就可以自动投入生产，或者自动转移到一组测试中，或者进行进一步的审批。这些服务为您提供了对权限和运行时间表的细粒度控制。

该服务建立在 TriggerMesh 的无服务器管理平台上，该平台提供编排功能、事件库和用于管理无服务器功能的 web 控制台。它可以运行在用户自己的数据中心，或者作为 TriggerMesh 本身的托管服务。目前，该服务支持 Python 和 JavaScript/Node.js。

第一个目标将是 Knative/Kubernetes 在[谷歌云平台](https://cloud.google.com/)上的部署。之后，该公司将考虑支持其他环境，如亚马逊网络服务的 Lambda。该公司已经有了一个开源项目，在配备了 Knative 的 Kubernetes 集群上运行 Lambda 函数。

随着时间的推移，TriggerMesh 可能会变成一辆“跨云活动巴士”，TriggerMesh 联合创始人马克·辛克尔(Mark Hinkle)在最近于西雅图举行的[kube con+CloudNativeCon 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/)会议期间的一次会议上表示。用户可以拥有一个跨越多个云的事件驱动架构，其中一个云中的事件可以触发另一个云中执行的服务。“我们在那里看到的许多研究表明，无服务器将是跨云和多云的，”他说。

今后，TriggerMesh 可以帮助用户对他们的云使用做出高级决策，例如允许他们比较多个不同提供商的相同工作负载，以确定哪一个成本最低或执行时间最快。

Hinkle 说:“这是我们在很长一段时间内看到的云的第一次演变，我们认为这对企业来说是真正的变革。”“在内部为开发人员部署自助式 IT 仍然需要一定程度的系统管理知识。无服务器真正允许企业开发人员自助服务。他们可以将代码放入常规工作流程中。”

该公司是在 KNative 发布后不久成立的，创始人认为 kna tive 有助于使 Kubernetes 在企业环境中易于使用，而 Kubernetes 的专业知识仍然短缺。TriggerMesh 的目标是减少企业开发人员获取部署代码所需的运行时资源的时间。该公司的另一位联合创始人[塞巴斯蒂安·戈阿斯根](https://twitter.com/sebgoa)曾致力于 KNative 的前身 [Kubeless](https://kubeless.io/) 。

“它允许开发人员直接部署，你允许操作人员进行检查和平衡，允许开发人员单独操作，”Hinkle 说。无服务器可以提供更短的价值实现时间，但它仍然需要一个支持开发者的结构，TriggerMesh 正在提供这种结构。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>