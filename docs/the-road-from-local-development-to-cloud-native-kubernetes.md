# 从本地开发到云本地 Kubernetes 的道路

> 原文：<https://thenewstack.io/the-road-from-local-development-to-cloud-native-kubernetes/>

[](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

 [吐温泰勒

吐温在谷歌开始了他的职业生涯，在那里，他参与了 AdWords 团队的技术支持工作。他的工作包括审查堆栈跟踪，解决影响客户和支持团队的问题，以及处理升级。后来，他建立了品牌社交媒体应用程序和自动化脚本，以帮助初创公司更好地管理他们的营销业务。如今，作为一名技术记者，他帮助 IT 杂志和初创公司改变团队构建和发布应用程序的方式。](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns) [](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

云原生计算、微服务架构、容器化和 Kubernetes 现在已经成为 DevOps 的主流话题。开发者现在必须适应这种根本性的变化。虽然这些方法在原则上听起来很棒，但当涉及到实现时，它们带来的变化是巨大的。尽管这些新方法承诺更快的开发，但是为开发团队建立一个工作的“代码到产品”周期需要花费几天到几周的时间——这可能意味着严重的时间损失。

“对于任何新的设置，开发人员都需要解决两个问题，”谷歌云平台 DevOps 部门的产品经理安德鲁·菲利普斯(Andrew Phillips)说，“第一，开发人员如何在他们的开发机器上快速查看代码更改的结果，第二，他们如何轻松地让代码在稳定的共享环境中运行，而不是在他们的笔记本电脑上运行？”这种共享环境通常是一个暂存或生产环境，托管在云中。

如果您习惯于传统方法，云原生开发会带来新的障碍。配置所需的环境、处理微服务之间的依赖关系、自动化测试和部署任务以及端到端地跟踪流程，所有这些在每一步都面临着挑战。但是现代的工具和模式可以大大减少开始使用一个有效的软件交付管道的时间。其中包括用于本地开发的 [Minikube](https://kubernetes.io/docs/setup/minikube/) 和 [Skaffold](https://www.youtube.com/watch?v=tTNrzEjROCo) ，以及用于在云环境中建立简单部署管道的 [Google Cloud Build](https://cloud.google.com/cloud-build/) 。让我们在上下文中讨论这些工具。

## 通过 Minikube 在本地部署

如今，开发云原生应用的第一步是为目标运行时选择 Kubernetes，这意味着在本地配置 Kubernetes。这是一个下载和修改配置文件的多步骤过程。(家酿、VirtualBox、Minikube 和 Kubectl 等工具会有所帮助，这取决于你运行的是什么系统。)

一旦配置了本地环境，下一步就是在本地运行应用程序。使用 minikube start 命令创建一个 Minikube 集群。这将创建一个在虚拟机中运行的单节点 Kubernetes 集群。

配置好本地环境后，您就可以启动您的第一个 Kubernetes 应用程序了。通常，您必须执行这些任务:首先，构建一个 Docker 容器并标记它。其次，记得更新 Kubernetes 清单以指向新的容器映像。第三，回到命令行执行 kubectl run。可以想象，这个过程非常繁琐，而且容易出错。

一旦应用程序启动，每次你修改代码时，你都希望在部署前在本地预览它。为此，您需要再次重复上述步骤。幸运的是，有另一种工具可以给这个笨拙的过程带来更多的控制和效率。

## Skaffold 自动化本地部署

Skaffold 是一个帮助简化本地环境开发的工具。它会监视代码的变化，一旦检测到变化，Skaffold 会自动启动构建、推送和部署新代码到 Kubernetes 集群的步骤。好处是，作为开发人员，您可以以连续的方式对代码进行迭代更改，而不必亲自手动部署每个更改。Skaffold 可以在连续模式下使用，以便在所有变更发生时自动部署它们，也可以在单一部署模式下使用，在单一部署模式下，它在执行完您要求它部署的变更后退出。这为本地开发带来了新的轻松和简单程度，并加速了新功能的开发。

斯卡福德很有效率。它只能识别和部署已经更改的代码部分。它与本地 Kubernetes 工具或远程集群一起工作，并允许您选择在构建、推送和部署阶段使用哪些工具。Skaffold 和 Minikube 是在本地 Kubernetes 集群中自动化构建、推送和部署阶段的有用工具。

斯卡福德还包括[一些很酷的功能](https://ahmet.im/blog/skaffold/)。例如，当它重建容器映像时，它会自动使用新的标签来更改清单。它了解哪些映像受到了更改的影响，并仅重建已更改的映像。完成后，它会运行一个例程来清理已部署的 Kubernetes 资源。

## 在云中部署

在本地部署应用只是您云原生开发之旅的第一步。最终，您会希望与他人共享您的代码，或者通过将应用程序托管在云环境中，使其对外部用户可用。通常，您会将应用程序部署到试运行或生产环境中。

在云中部署比本地部署更具挑战性，因为部署是在远程集群上进行的，有一个云供应商平台可以使用，还有身份认证和网络带来的所有常见问题。在这个阶段，您需要找到将代码从笔记本电脑转移到云的整个过程的自动化和代码化的方法。

理想情况下，一旦建立了云环境，每次将代码推送到团队的共享代码库中时，它都应该在云中自动更新。虽然 Skaffold 适合在本地环境中起步，但是还有其他选项值得考虑，以便在云中实现自动化。

## 云构建自动化了云中的部署

[云构建](https://cloud.google.com/cloud-build/)是一个自动化工具，是谷歌云平台的一部分。除了在本地机器上开发之外，Cloud Build 允许您基于 YAML 或 JSON 中的简单构建配置文件，在云中运行快速、一致和可靠的构建。基于配置文件中的指令，Cloud Build 构建源代码，运行测试，并将代码部署到目标位置。它还可以在几分钟内从本地机器上的单个构建到云中跨多个项目的多个并行构建。

对于高级用例，团队可以在使用云构建设置持续集成(CI)时包含一个 cloudbuild.yaml 文件。这使他们能够定义自定义构建步骤，通过缓存 Docker 映像来加快构建速度，构建更精简的容器，并直接部署到 Google Kubernetes 引擎、Google App Engine、本地集群(即将推出 alpha)或其他云提供商。

“云构建有助于开发人员避免自行建立和管理 CI 流程的所有复杂性，”Phillips 说。“它使开发人员只需点击几下鼠标，就可以从他们的 GitHub 存储库中配置自动化的 CI 流程。”集成后，您可以直接在 GitHub 中查看部署状态。

类似于 Skaffold 的自动化本地部署特性，Cloud Build 包括构建触发器，它“监视”更新并根据您定义的触发器自动构建容器映像。这减少了部署到云的手动工作，让您专注于开发。

云构建的强大之处在于它能够将从 GitHub 到最终云目标(如 GKE 或 Firebase)的整个过程联系在一起。云构建允许您使用可重复且易于定制的指令来控制和自动化整个流程。

与其花时间设置和配置基础设施和工具，今天的开发人员应该能够专注于快速推出代码并享受云原生 Kubernetes 的好处。像 Skaffold 和 Cloud Build 这样的工具通过为您管理工具并让您控制过程来消除构建自动化的痛苦。这样，您就可以专注于真正重要的事情:编写优秀的代码。

在这一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，由 New Stack 的创始人兼主编 Alex Williams 主持，[T5【Michael Winser](https://twitter.com/michaelwinser?lang=en)[Google 的云构建](https://cloud.google.com/cloud-build/)的产品管理负责人描述了 CI/CD 对 Google 的意义以及这个术语对软件行业的意义。

[一位谷歌产品管理负责人谈 CI/CD 的真正含义](https://thenewstack.simplecast.com/episodes/a-google-product-management-lead-on-what-ci-cd-really-means)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>