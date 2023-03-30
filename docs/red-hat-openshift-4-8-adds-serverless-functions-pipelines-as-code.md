# Red Hat OpenShift 4.8 增加了无服务器功能、管道代码

> 原文：<https://thenewstack.io/red-hat-openshift-4-8-adds-serverless-functions-pipelines-as-code/>

本周推出的 OpenShift 4.8 是 [Red Hat 的企业 Kubernetes 平台](https://www.openshift.com/try?utm_content=inline-mention)的最新版本，合并了最近发布的一些版本，如 [OpenShift GitOps 和 Pipelines](https://thenewstack.io/red-hat-delivers-full-gitops-ci-cd-built-on-tekton-and-argo/) ，并添加了一些新功能，如沙盒容器、无服务器功能、管道即代码等等。OpenShift 4.8 基于 Kubernetes 1.21 和 CRI-O(容器运行时接口)1.21。

“OpenShift 4.8 的共同主题是让客户能够交付各种各样的工作负载，”Red Hat 市场洞察总监[斯图·迷你曼](https://www.linkedin.com/in/miniman)说。

“我们 4.8 的重点实际上是工作负载，”他说。“Kubernetes 已经达到了一定的成熟水平。具体来说，数据、数据库、人工智能和人工智能是我们在这一细分市场中看到强劲增长的领域。我们的 GitOps 刚刚正式上市，Argo CD 大约一个月前刚刚推出 1.0 版本，已经有客户前来表示他们正在使用它。”

虽然 OpenShift 4.8 没有引入直接解决这些领域的功能，但 Miniman 表示，“通常，它是两个版本之前的功能，加上我们刚刚发布的一个东西，随着它们一起发展，更多的基础部分都在那里，因此更容易部署更多的应用程序。”

Miniman 指出, [OpenShift 无服务器功能](https://developers.redhat.com/blog/2021/01/04/create-your-first-serverless-function-with-red-hat-openshift-serverless-functions)的技术预览是 OpenShift 4.8 引入的一项新功能，将帮助客户交付更多类型的工作负载。基于 Knative，OpenShift Serverless 以前只提供事件，但现在提供了 Quarkus，Node.js，Python，Go 和 Spring Boot 语言和运行时的功能，并计划很快添加 TypeScript 和 Rust。

Miniman 表示，另一项新功能 IPv6/IPv4 双栈和 IPv6 单栈支持允许拥有传统应用程序的公司在 OpenShift 上运行，进一步实现了支持传统用户的核心承诺。同样，OpenShift 沙盒容器的技术预览版使运行不受信任或特权的工作负载成为可能，这些工作负载“需要极其严格的应用程序级安全性”，根据一份新闻稿。基于 Kata Containers 开源项目，OpenShift 沙盒容器使用硬件虚拟化技术提供工作负载隔离。

除了专注于交付工作负载之外，OpenShift 4.8 还引入了管道即代码的开发者预览版，进一步构建了 OpenShift 管道最近向全面可用的转变。Red Hat open shift 核心平台产品管理总监[图沙尔·卡塔尔基](https://www.linkedin.com/in/katarki)说:“管道即代码允许团队使用 Git 作为他们持续集成(CI)管道定义的唯一真实来源。

“虽然团队已经可以使用 OpenShift GitOps 采用 GitOps 工作流进行应用交付，但 pipeline as code 使他们能够采用 GitOps 工作流来维护其 CI 管道和基础设施。因此，团队可以使用通用的运营流程对 CI 基础设施进行变更和更新，”Katarki 在一封电子邮件中写道。

他进一步解释说，pipelines-as-code 完全自动化了这一过程，消除了用户使用 kubectl 在集群上更新 CI 管道定义的需要，并写道“OpenShift Pipelines 中新的 pipeline-as-code 功能通过直接从 Git 存储库中自动提取和执行 CI 管道并将其作为 CI 基础设施定义的唯一来源，消除了这一额外步骤。”

Katarki 说，随着全面可用，OpenShift Pipelines 还增加了一些功能，如 PipelineRuns 和 TaskRuns 的自动修剪，这使得管理员无需通过 cron 作业来完成相同的任务。

OpenShift 4.8 预计将于 2021 年 7 月全面上市，但开发者可以在发布前在 [OpenShift 开发者沙盒](https://developers.redhat.com/developer-sandbox)中试用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>