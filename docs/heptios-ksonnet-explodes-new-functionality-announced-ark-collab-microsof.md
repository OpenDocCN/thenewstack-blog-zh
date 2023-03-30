# Heptio 扩展了 Azure 环境的 Ark 灾难恢复

> 原文：<https://thenewstack.io/heptios-ksonnet-explodes-new-functionality-announced-ark-collab-microsof/>

Kubernetes 服务公司 [Heptio](https://www.heptio.com/) 为 Azure 环境扩展了 [Heptio Ark](https://heptio.com/opensource/) 灾难恢复软件。

Heptio Ark 管理 Kubernetes 集群资源和持久卷的灾难恢复，提供了一种可配置的、操作可靠的方法来从一系列检查点备份和恢复应用程序和持久卷。

“多云确实正在发生。但为了实现这一点，我们需要强大的一致性，”Heptio 联合创始人兼 Kubernetes 联合创始人 [Craig McLuckie](https://www.linkedin.com/in/craigmcluckie) 在今年的 Kubecon 上讨论新技术时说。

Heptio 和微软还将合作，使 Ark 项目成为一个高效的解决方案，在内部计算环境和 Azure 之间移动 Kubernetes 应用程序，并确保 Azure 托管的备份是安全的。

通过与 Heptio-微软的合作，他们将努力确保组织能够将内容备份和恢复到 Azure Container Service(AKS)中。此外，使用 Ark 创建的系统快照在静态时是加密的，并将在 Azure 中持久化。

“我很高兴看到 Heptio 和微软推出了一个令人信服的解决方案，满足了 Kubernetes 生态系统中一个重要但尚未满足的需求，”作为 Kubernetes 的创始人之一，微软杰出的工程师 Brendan Burns 表示。“我们正在与 Heptio 合作，以确保 Ark 和 Azure 的集成是将本地 Kubernetes 集群备份到云中的最佳解决方案。”

## 升级到 ksonnet

由 Kubernetes 的另外两个创建者 Joe Beda 和 McLuckie 发起的 Heptio 在 6 月份退出了秘密模式。该公司已经推出了几款产品来帮助工程师使用笨重的 Kubernetes。一套是 Kubernetes 配置工具 [ksonnet](http://ksonnet.heptio.com/) 和用于格式化 JSON 数据的模板语言 [Jsonnet](http://jsonnet.org/) 。Beda 解释说，Jsonnet 是“一种与 JSON 兼容的纯功能、图灵完备的语言”。

8 月份，[公司推出了](https://thenewstack.io/heptio-two-new-tools-make-kubernetes-life-easier/)，以及 [Heptio Ark](https://github.com/heptio/ark) ，另一款名为 [Heptio Sonobuoy](https://github.com/heptio/sonobuoy) 的工具，它可以检查集群状态和配置，以确保一切都已配置好并正常工作。这两个项目都可以在 GitHub 上公开获得。

今年早些时候，Beda 告诉我，Kubernetes 非常适合香草装置，但没有人开箱即用。不幸的是，定制 Kubernetes 非常复杂，通常涉及 Beda 所说的“YAML 之墙”

ksonnet 简化了部署到 Kubernetes 集群所需的配置。Beda 表示，ksonnet 和 Jsonnet 背后的语言和概念可能会让新用户和临时用户望而生畏。“我们今天正在解决这个问题，”他在 Heptio 博客中写道。

## 新的命令行

大多数工程师使用 kubectl run 命令启动 Kubernetes。但是因为是命令，所以对用户集群的更改不能存储在可跟踪的配置文件中，迫使团队成员使用 YAML 文件重新创建他们的应用配置。

“用户必须学习新的概念和模式，这些从来就不是人类创作的，”贝达在发布新 ksonnet 的博客文章中说。

“我们认为 ksonnet 不仅仅是被部署的代码，”他在今年早些时候解释道，“而是我如何创作它，如何使用它，如何跨团队工作的整个体验。”

新的 ksonnet 命令行工具 ks 使配置 Kubernetes 应用程序变得很容易。ks 提供了一套在磁盘上生成和管理文件的方法。现在，用户可以轻松定义一个应用程序，针对不同的集群和环境进行专门的应用程序配置，并随着时间的推移向其中添加新的组件。

Beda 对 Heptio 产品旋风般交付的新概念进行了快速概述:

*   **组件。**组件是一个 Jsonnet 文件，通常是一个大型应用程序中的一个微服务。它定义了一组 Kubernetes 资源(例如，部署、服务或配置映射)
*   **原型。**原型允许用户在不复制任何 YAML 的情况下生成完全成形的组件。
*   **环境。**环境是集群和名称空间的组合，是部署应用程序(通常是开发、试运行或生产)的目标。对于跨多个集群运行的应用程序，用户可以为每个集群创建一个环境。
*   他写道:“原型的**参数**成为生成组件的参数。”"这些参数可以随时更改和更新."此外，参数可以针对每个环境进行特殊化。

你可以通过查看[的深度教程和文档](http://ksonnet.io/)或者参加 [Kubernetes slack](http://slack.k8s.io/) 的#ksonnet 来了解更多信息。

如果你在德克萨斯州奥斯汀的 KubeCon，你可以在 12 月 8 日之前在它的展位#S14 与 Heptio 见面。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>