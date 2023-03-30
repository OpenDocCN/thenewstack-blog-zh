# Azure 容器实例:微软容器创新的证据

> 原文：<https://thenewstack.io/azure-container-instances-proof-microsoft-innovating-containers/>

与其他企业基础设施提供商的竞争相比，微软在应对容器挑战时处于一个微妙的位置。它已经在受容器使用增长影响的系统中拥有许多既得利益，包括操作系统(Windows Server)、虚拟机管理程序(Hyper-V)、私有云产品(Azure Stack)和公共云(Azure)。

容器对平台公司来说既是威胁也是机遇。从事基础设施交付业务的每个参与者对集装箱化浪潮的反应都不一样。虽然 VMware [比竞争对手花了更长的时间](https://thenewstack.io/vmware-photon-present-kubernetes-service/)，但谷歌、微软和 Red Hat 在拥抱这一新的计算浪潮方面行动迅速。谷歌通过开源 [Kubernetes](/category/kubernetes/) 容器编排引擎，并在其公共云环境中提供其托管版本，坚定地专注于容器管理。红帽意识到 [OpenShift](https://www.openshift.com/) 作为传统的 PaaS 并没有获得足够的牵引力。它几乎改变了一切，包括品牌和改变底层技术堆栈，以转向 Kubernetes。

反映了公司的新文化，微软迅速与 Docker 公司达成协议，使其成为基于 Windows 的容器的默认界面。然后，它努力确保容器[是整个堆栈](https://thenewstack.io/right-click-docker-microsofts-ambitious-enterprise-vision-containers/)不可分割的一部分。一些功能，如 Windows 容器，Hyper-V 容器，Windows Server 2016 中的集成 Docker 引擎，Azure 容器服务，[Visual Studio Tools for Docker](https://thenewstack.io/microsoft-visual-studio-2017-devops-five-star-app/)，一个[容器优化的 Windows Nano 服务器](https://thenewstack.io/changes-coming-nano-server-fall-devops-containers/)，Azure 中的嵌套虚拟化，都是微软正在全力以赴使容器化成为一等公民的迹象。

到目前为止，微软的战略举措一直是雇佣布伦丹·伯恩斯，这位前谷歌员工是 Kubernetes 的创始团队成员之一。这一招聘引起了一些人的惊讶，包括那些在谷歌构建谷歌云平台的人，这是 Azure 的主要竞争对手。但是没有太多的怨恨，因为 Brendan 与 Kubernetes 有关联，Kubernetes 是一个开源项目，在社区中越来越受欢迎。包括谷歌人员在内的 Kubernetes 社区希望看到[微软正式拥抱 Kubernetes](https://thenewstack.io/draft-gives-developers-uplift-containerizing-apps-kubernetes/) 。微软没有让我们失望。在 Brendan 过渡到 Azure 计算团队的几个月内，Redmond 在 Azure 上[开放了 Kubernetes。这几乎挑出了 AWS，他基于 EC2 构建了一个专有版本的容器管理平台 Amazon EC2 Container Service。](https://thenewstack.io/microsofts-burns-azure-breaks-kubernetes-free-exclusivity-lock/)

Brendan 的主要交付成果包括 Windows 与 Kubernetes 的集成，这对微软客户来说是一件大事。他们将能够混合搭配由 Kubernetes 无缝管理的 Linux 和 Windows 工作负载。这个异构环境将运行一个由 Linux 和 Windows 节点组成的 Kubernetes 集群。但是 Windows 的底层网络堆栈使得这种集成很困难。看看如何应对这一挑战将会很有趣。除了将 Kubernetes 引入 Azure 之外，Brendan 还忙于制定微软的整体容器化策略。

最新发布的产品——Azure Container Instances(ACI)——是微软的一个明智之举，它已经打上了 Brendan 的烙印。ACI 允许开发人员启动“无服务器容器”，而不必处理充当容器主机的虚拟机和操作系统。只需两步，[开发者就能在 Azure](https://thenewstack.io/azure-container-instances-spins-containers-cloud-without-vm-overhead/) 中构建一个容器。尽管有容器优化的操作系统，如 CoreOS、Atomic Hosts 和 Windows Nano Server，但它们在运行容器之前都是作为虚拟机提供的。

> 在许多方面，ACI 是微软对 AWS Lambda 的回答。

有了 ACI，开发人员再也不用担心虚拟机或主机操作系统运行他们的应用程序。这是微软将 ACI 定位为“无服务器容器”的主要原因在 ACI 中，您永远无法通过 SSH 或 RDP 进入主机。工作流程很简单——从注册表中拉出一个容器，并根据需要运行它。

ACI 的定价模式符合无服务器理念。每个供应的容器实例每月收费 0.0025 美元。内存持续时间是从容器开始执行的时间开始计算的，直到它终止，每 GB RAM 的费用是 0.0000125 美元。从容器创建之时起，每使用一个 CPU 核心，客户就要支付 0.0000125 美元。每个 ACI 实例最多可以有 3.5GB 的 RAM 和 4 个 CPU 核心。例如，如果您连续一个月每天启动一个具有 1GB RAM 和 1 个 CPU 内核的 ACI 实例 5 分钟，那么您的账单将转换为 0.30 美元，这是非常实惠的。

在许多方面，ACI 是微软对 AWS Lambda 的回答。虽然 Azure Functions 是 Lambda 的一个可比较的替代产品，但微软将其作为对竞争对手的无服务器产品的快速反应。Azure Functions 是 Azure WebJobs 的改进，这是一种为类似但不同的用例而创建的服务。ACI 是无服务器计算的一种优雅形式，因为它允许开发人员以 Docker 映像的形式提供代码和配置。与 Lambda 不同，ACI 不局限于一组预定义的语言和运行时。

## 自带容器

最近，自带集装箱的理念越来越流行。谷歌通过应用引擎灵活环境将[托管的虚拟机](https://techcrunch.com/2014/03/25/google-launches-managed-virtual-machines-gives-developers-a-middle-ground-between-compute-and-app-engine/)添加到其 PaaS 中。亚马逊在 [AWS Beanstalk](https://aws.amazon.com/elasticbeanstalk/) 中支持单容器和多容器部署。但是 Azure 容器实例为容器原生应用程序带来了真正的无服务器能力。开发人员可以将从代码到配置的一切都封装在 Docker 容器映像中，并安排它定期执行。这包括运行配置管理脚本、备份任务、构建自动化、队列处理以及许多其他任务。

ACI 不能取代成熟的容器编排平台，如 Docker Swarm、Mesosphere DC/OS、HashiCorp Nomad 和 Kubernetes。如果你想运行一个复杂的微服务应用程序，它需要一些高级特性，比如持久性、服务发现、金丝雀发布、自动伸缩、自我修复、监控和日志记录，Azure 容器服务是最好的选择。可以把 ACI 看作是一个支持容器的增强的无服务器平台。不用将代码片段压缩并上传到 AWS Lambda 或 Azure 函数，您可以利用 Docker 的工具和调试支持，在云中运行代码之前在本地测试代码。

ACI 证明微软对容器是认真的，它的创新速度比竞争对手更快。这项技术将成为 Azure 计算平台的关键支柱之一。我非常肯定 ACI 会在微软的边缘计算平台 [Azure IoT Edge](https://azure.microsoft.com/en-us/campaigns/iot-edge/) 中找到自己的位置。它最终也将作为一个受支持的计算层出现在 Azure Stack 中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>