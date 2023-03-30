# Docker 完全接受 Kubernetes

> 原文：<https://thenewstack.io/docker-fully-embraces-kubernetes/>

在过去的几年中，Docker 开始构建自己的容器管理和编排层。这是该公司路线图中非常重要的一部分，也是大多数投资者认为以高价引入企业买家的最后一着。今天，当该公司宣布将 Kubernetes 引入其企业平台时，这一愿景发生了巨大变化。

今天，在哥本哈根举行的 DockerCon Europe 大会上，Kubernetes 开源容器编排引擎成为了焦点。[谷歌](https://cloud.google.com/kubernetes-engine)首先开发了 Kubernetes，现在由[云本地计算基金会](https://www.cncf.io/)管理。现在 [Docker 将在其当前的 Docker 企业版中包含 Kubernetes](https://thenewstack.io/kubernetes-vs-docker-swarm-whats-the-difference/) 1.8。

以前， [Docker](https://www.docker.com/) 曾推出自己的 Swarm 作为许多编排困境的解决方案，但随着宣布它现在将提供和支持 Kubernetes，许多这些 [Swarm](https://github.com/docker/swarm) 功能现在被吹捧为 Kubernetes 之上的增值。

“我们将 Kubernetes 纳入我们的产品线。Docker 首席运营官 [Scott Johnston](https://www.linkedin.com/in/scottcjohnston/) 表示:“我们将 Kubernetes 作为一流的管弦乐队加入 Docker Enterprise Edition，与 Docker Swarm 齐名。他还指出，Kubernetes 将被整合到该公司的桌面 Windows 和 Mac 产品中。"

以前，Swarm 被宣传为一个集群管理器，而不是一个完整的云协调系统。Swarm 和 Kubernetes 的结合允许将 Swarm 管理器节点和 Kubernetes 主节点包含在一起，以在部署的系统中实现高可用性和安全性。

约翰斯顿说，这主要是为了响应客户对 Kubernetes 的要求。“这也为 Kubernetes 带来了我们在其他发行版中看不到的功能。它使用户能够在节点和集群级别利用 Swarms 安全特性。此外，Docker 企业版用户可以通过同一个控制台管理 Windows 和 Linux 工作负载，”Johnston 说。

这是 Docker 的一个主要区别点，自 2016 年与[微软首次合作以来，它一直在努力实现这一点。Docker 当时签约将其容器运行时引入](https://thenewstack.io/docker-changed-windows-windows-change-docker/)[微软的 Azure 云平台](https://azure.microsoft.com/en-us/?v=17.14)，但我们当时并没有完全看到 Windows 平台会获得多少 Docker 支持。这一公告表明，Docker 将 Windows 视为企业开发者的标准桌面开发环境。

Johnston 说，用户将能够独立地在编排功能之间进行选择。“Kubernetes 界面将提供给那些想开始使用它的用户，并且是本地可用的。我们不包 Kubernetes 或分叉 Kubernetes。这是该项目的普通版本。有兴趣从业务流程层入手的客户可以直接开始。与此同时，我们目前的数百家企业客户将继续享受 Swarm 的好处。约翰斯顿说:“我们并不是告诉顾客做这做那，而是给他们选择的权利。”。

约翰斯顿说，今后，Kubernetes 将每六个月更新到最新的稳定版本。这将从今天包含在 Docker 企业版中的[版本 1.8](https://github.com/kubernetes/kubernetes/milestones/) 开始，下一个稳定版本将在一年两次的 Docker 企业版发布时间表中被采用到平台中。

对于桌面用户来说，他们通常利用 Docker 进行基于开发环境的测试设置，该平台的 Windows 和 Mac 版本可能会直接从主平台集成 Kubernetes，确保开发人员能够及时获得新功能，而不会给主线生产平台带来可能的复杂性。

当被问及该公司对 Kubernetes 的回报计划时，Johnston 指出，Docker 的创建者和创始人 Solomon Hykes 已经是 CNCF 的技术指导委员会成员，这是一个非营利组织，除了管理 Kubernetes，还管理 T2 的 Linkerd 和 T4 的 container 以及其他流行的以容器为中心的开源基础设施项目。约翰斯顿说:“(所罗门是)创始成员。“我们已经为 CNCF 的几个项目做出了贡献:containerd 和 runc。我们已经开始行动了。随着这一声明的发布，这一趋势将继续并加速发展。我们打算成为一等公民，并作为正式成员参与。”

“我们的供应商 ed Kubernetes，”Johnston 说，“利用了我们在 Swarm 上的基础设施投资:集群中单个节点的安全性。我们在 Kubernetes 基地建立了一流的安全措施。我们还使安装、配置和架设 Kubernetes 变得非常容易。Kubernetes 并没有对底层集群做太多假设，所以用户可以自行决定。我们已经将设置群集、群集周围的安全性以及节点上的安全性变成了一个命令。”

虽然这对客户来说是一个受欢迎的补充，但它表明 Docker 随着时间的推移会有轻微的方向变化。

“也许这也是三年前我们在企业年轻的一种反映。随着我们在企业中的成长，我们看到安全需求越来越大。这增加了我们在这些功能集上的投资。我会说这对我们来说是一致的，但三年前大多数企业都在集装箱上踢轮胎。现在，您确实看到企业希望使用 Docker 将他们的第一、第二或第三个工作负载迁移到云中。当你这样做的时候，你的安全需求就变成了赌注。

他补充说，Docker Enterprise Edition 内部的大部分安全工作是由该公司三年前从 Square 收购的一个安全团队完成的。Johnston 说，该团队一直在 Docker 内部合作，致力于改善平台的整体安全模型，并将继续这样做。

该公司的 DockerCon Europe 将持续到本周剩余时间，明天的主题演讲也将发布更多公告。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>