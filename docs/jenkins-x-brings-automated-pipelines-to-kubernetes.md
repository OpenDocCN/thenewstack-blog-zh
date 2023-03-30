# Jenkins X 为 Kubernetes 带来自动化管道

> 原文：<https://thenewstack.io/jenkins-x-brings-automated-pipelines-to-kubernetes/>

Jenkins 持续集成服务器长期以来一直是 DevOps 革命的主要部分。作为在持续集成和持续部署环境中自动化任务的中央协调服务器，世界各地的开发和运营团队已经接受并构建了 Jenkins 的扩展和构建包。然而，迁移到基于容器的环境并不是 Jenkins 的初衷。

[James strach an](https://www.linkedin.com/in/jstrachan/),[cloud bees](https://www.cloudbees.com/)的高级架构师，是 [Jenkins X](https://github.com/jenkins-x) 的项目负责人，他一直在思考这次迁移对 Jenkins 用户意味着什么。他说，将 CI/CD 管道转移到基于容器的云托管环境，利用容器和容器编排器，如 Kubernetes，推动了对构建、测试和部署过程中更多自动化的需求。斯特拉坎说，要做到这一点，詹金斯 X 需要比普通的詹金斯更容易理解和合作。

“我们想做的是打破一两个非常了解詹金斯的人和团队中其他可能想做事的人之间的障碍。这个微服务时代的最大不同是，我们需要开发人员能够在他们希望的任何时候启动新项目。我们希望让 Jenkins 像云一样实现自助服务，”Strachan 说。

“Jenkins X 的目标是将 Jenkins 变成一个自助服务设备，因此任何开发人员都可以启动一个新项目，所有的管道和所有的事情都会发生。我们并不是说你的团队中不应该有了解 Jenkins 的人，而是说我们试图让 CI/CD 更像云的其他部分一样。

三月中旬该项目首次向公众公布时，Strachan 在一篇博客文章[中详细介绍了 Jenkins X 的技术细节。他解释说 Jenkins X 可以用来建立 Jenkins 管道，自动生成 Jenkinsfile 和 Dockerfile 来定义应用程序的管道和打包步骤。](https://jenkins.io/blog/2018/03/19/introducing-jenkins-x/)

因为 [Docker](https://www.docker.com/) 和 [Kubernetes](https://kubernetes.io/) 的行为与 Jenkins 成长的一些环境不同，Strachan 说 Jenkins X 就是要将安全性带入有些复杂的容器映像构建过程。Strachan 说，用户可以使用自己的 docker 文件，或者在管道中弹出他们喜欢的容器构造工具。斯特拉坎指出 [Skaffold](https://github.com/GoogleCloudPlatform/skaffold) 是一个构建和标记 Docker 图片的工具，他说这是一件大事，尽管听起来很简单。

“[ska fold]管理 Docker 和安全模型的复杂性。如果你正在使用谷歌云，你可能想使用谷歌的容器生成器。您可能希望在 Kubernetes 集群中使用 SaaS 配置项或本地 Docker 套接字。这具有安全隐患，因为它在某种程度上为您提供了机器上的根，因此您永远不会让他人访问生产集群中的 Docker 套接字，”Strachan 说。“默认情况下，Jenkins S 假设您在一个开发集群上，并且可以访问 Docker 套接字，但是我们知道还有其他选择。”

Strachan 认为这是未来建立 Docker 形象的一个主要问题。“我们需要像 Skaffold 这样的工具来向用户隐藏这种混乱。我希望这个问题能很快得到解决，”他说。他曾听到传言说斯卡福德可能会在几个月后解决这个问题。

“在开发集群上，你让人们使用 Docker 来构建映像。你相信你的开发者不会开采比特币。在生产集群上，您从不构建映像，您只是使用它们。这是一个简单的方法，很容易做到，也不太可怕，”斯特拉坎说。“我认为，从长远来看，最好能够在没有 Docker 守护程序、root 或特殊权限的情况下构建 Docker 映像，从而将 Docker 构建从 Kubernetes 集群中分离出来。”

## 稳定性和兼容性

对于未来，Strachan 说 Jenkins X 团队围绕稳定性和兼容性有很多目标。“最重要的是检查每个人的所有工作。同时支持大量的云是非常具有挑战性的。试图得到一个坚如磐石的集群系统是第一个重点。另一个焦点是支持更多的 git 提供者和问题跟踪器。Strachan 说:“我们正在增加对吉拉的支持，社区中的一些人正在扩展到其他 git 提供商，如 GitLab 和 BitBucket。

“我们更长期的工作是围绕改善反馈和整合等方面展开的。我们有一个大的路线图，主要围绕增加构建包的数量。Strachan 说:“我们需要添加更多的语言。

核心开发团队正在考虑的另一件事是与 Anchore CI/CD 安全扫描软件的集成。Anchore 根据漏洞数据库分析代码和 Docker 图像。

然而，在所有这些复杂的目标中，Strachan 说有一段代码为 Jenkins X 团队节省了大量时间:[更新机器人](https://wiki.jenkins.io/display/JENKINS/UpdateBot+Plugin)。这个小工具跨库运行，更新其他项目中的库依赖关系，自动提交 pull 请求以利用新的依赖关系。

“有时有人在上游库工作，”Strachan 说，“其他团队在下游库工作。如果没有信息交换，经常发生的是，图书馆很少得到更新。如果您正在更新库，您需要为您的库提供 CD。UpdateBot 所做的是将 CD 原则应用于图书馆。库不会被部署为 Docker 映像，但它们会被部署为版本更改、更新的 XML 文件或基本 Docker 映像文件。”

Strachan 说，将 pull 请求推送到正在更新的库的所有下游消费者的简单行为可以防止 bug 隐藏在大的更新周期之后。

“我特别喜欢的一点是，如果上游开发人员破坏了一些东西，他们会知道，因为在发布的版本中，所有这些拉请求都会开始失败。当一个团队为另一个团队打破某些东西时，你避免了摩擦和挫折。今天打破它的团队通常不知道他们打破了什么。因为变革通常需要很长时间才能扩散到整个组织，所以当你意识到有什么东西坏了的时候，你已经做了 700 次变革，却不知道是哪一次坏了。

[![](img/da985f7aaec0fe2f939b9cc34063e060.png)](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/attend/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>