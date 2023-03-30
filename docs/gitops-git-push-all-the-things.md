# GitOps:“Git Push”所有的东西

> 原文：<https://thenewstack.io/gitops-git-push-all-the-things/>

虽然云原生计算的想法有望改变现代 IT 运营的方式，但对于许多从事该行业的人来说，这个想法仍然模糊不清。上周在哥本哈根举行的 kube con+CloudNativeCon EU 会议上，一个名为“GitOps”的想法引起了一些热议，它可能会给这一领域带来一些急需的关注。

GitOps 的核心是“推动代码，而不是容器”，[的 Alexis Richardson](https://twitter.com/monadic) ，Weaveworks 首席执行官和[云本地计算基金会](https://www.cncf.io/)技术监督委员会主席，在他的 KubeCon 主题演讲中说。Richardson 说，对于开发者和系统管理员来说，这个想法是“让 git 成为云原生操作的控制中心”。

“开发者体验的关键点是‘git-push’，”他说，暗指用于提交代码完成的 git 命令。他补充说，这种方法“完全以代码为中心”

[https://www.youtube.com/embed/qUK-F40oLVQ?list=PLj6h78yzYM2N8GdbjmhVU65KYm_68qBmo](https://www.youtube.com/embed/qUK-F40oLVQ?list=PLj6h78yzYM2N8GdbjmhVU65KYm_68qBmo)

视频

乍一看，开源的 [git 版本控制软件](https://thenewstack.io/tutorial-git-for-absolutely-everyone/)作为云本地计算的前端非常有意义。鉴于 git 命令被开发人员广泛使用，它是开源世界的通用语言。基本思想是，对云原生系统的所有更改都可以通过 git 完成。一旦提交，它就会启动一个自动化的流水线，可能会使用像 [Jenkins X](https://thenewstack.io/jenkins-x-brings-automated-pipelines-to-kubernetes/) 这样的工具来封装和测试代码，并将其压入生产。

这种方法同样适用于基础设施管理:Richardson 称这种方法为“声明式基础设施”通过 YAML 文件对配置进行更改，Kubernetes 可以检测文件中的更改，并根据需要重新调整资源。不变的基础设施变得简单！在这种情况下，Weaveworks 本身已经发布了许多用于比较期望状态和实际状态的工具，例如 [kubediff](https://github.com/weaveworks/kubediff) 。

“GitOps 的基本定理是，如果你能描述它，你就能使它自动化。如果你能使它自动化，你就能控制和加速它。我们的目标是描述一切——策略、代码、配置和监控——然后是版本控制，”网站可靠性工程架构师 [Rob Scott](https://robertjscott.ca/) 写道，这是为了新堆栈的[即将在 Kubernetes 上发布的电子书](https://thenewstack.io/ebooks/kubernetes/ci-cd-with-kubernetes/)以及持续集成和部署。

[weaver works](https://www.weave.works/)本身使用 GitOps 模式来支持自己的商业 Kubernetes 托管服务。是 git 保存了整个系统的世界状态，包括以前的版本，它们是可恢复的。Richardson 说，这种方法建立在“事务提交的原子序列”之上。

“整个系统的期望状态在 git 中，这意味着集群及其观察到的状态可以随时与[期望状态配置]进行比较，适用于堆栈的任何层，”他说。Richardson 吹嘘说他公司的开发人员尽可能少地使用 Kubernetes 的命令行 kubectl。例如，该公司一直在尝试通过 git 管理 Istio 服务网格，尽管这项工作仍在进行中:

[https://www.youtube.com/embed/VkKMf23ZokY?feature=oembed](https://www.youtube.com/embed/VkKMf23ZokY?feature=oembed)

视频

尽管如此，GitOps 的想法似乎正在 Weaveworks 之外流行起来。

 [Alex Ellis](https://www.alexellis.io/)

，的创建者

[OpenFaaS](https://thenewstack.io/openfaas-put-serverless-function-container/)

，构建了一个名为

[OpenFaaS Cloud](https://blog.alexellis.io/introducing-openfaas-cloud/)

它运行可以由 git 命令触发的自动 CI/CD 管道。OpenFaaS Cloud 是许多无服务器功能，位于用户的 git 存储库和 OpenFaaS 部署之间。当用户将无服务器功能推送到 GitHub repo 中时，代码被检出、构建、测试，然后被推送到 Docker 注册表中，在那里它被部署为一个功能。

GitOps 方法的早期采用者之一是《金融时报》的内容平台团队，从该团队的技术负责人 Sarah Wells 的 KubeCon 主题演讲来看。该公司的内容平台由 150 个微服务构建而成。2015 年，报纸将这个平台从虚拟机转移到 Docker。

在转移到集装箱后，英国《金融时报》发现，其发布的数量从每年 12 次增加到 2200 次，这一增加也带来了更低的失败率。敏捷！所有的更改都只是对 YAML 文件进行，而不是启动一个新的虚拟机。虽然她没有提到“GitOps”的名字，但 Wells 说开发者通过 GitHub 推动他们所有的改变。

[https://www.youtube.com/embed/H06qrNmGqyE?feature=oembed](https://www.youtube.com/embed/H06qrNmGqyE?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>