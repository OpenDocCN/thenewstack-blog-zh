# 学习 Kubernetes:需要一个现实的游乐场

> 原文：<https://thenewstack.io/learning-kubernetes-the-need-for-a-realistic-playground/>

根据团队的经验，Kubernetes 可以是陡峭的学习曲线，也可以是令人耳目一新的简单。不管团队的背景如何，能够在 Kubernetes 操场上快速安全地进行实验是快速变得高效的关键。

## 从 PaaS 到 K8s

 [丹尼尔·布赖恩特

Daniel Bryant 在 Datawire 担任产品架构师。他的技术专长侧重于 DevOps 工具、云/容器平台和微服务实现。Daniel 是一名 Java 拥护者，是 TechBeacon DevOps 100 的影响者，并为几个开源项目做出了贡献。此外，Daniel 定期为行业出版物撰稿，并经常在 KubeCon、QCon 和 JavaOne 等国际会议上发言。](https://www.datawire.io) 

如果一个开发团队习惯于通过平台即服务(PaaS)如 [Heroku](https://www.heroku.com/) 或 [Cloud Foundry](https://www.cloudfoundry.org/) 来构建和发布应用程序，Kubernetes 带来的额外复杂性可能会很麻烦。简单的抽象已经不复存在，部署代码不再是简单的“git push heroku master”我听到一些工程师用一个类比来说明，从 PaaS 到 Kubernetes 就像从坐火车旅行到自己驾驶一辆必须用零件组装起来的汽车。

有这种经验的团队需要能够试验一个[应用就绪的 Kubernetes 集群](https://itnext.io/building-a-kubernetes-based-platform-focus-on-progressive-delivery-the-edge-and-observability-3a702e0c19a7)，他们可以快速重复地向其部署服务，测试并观察用户流量将如何处理。这里一个关键的早期目标是建立构建管道部署机制，并理解本地开发人员的体验如何映射到远程部署体验。

## 从虚拟机(和胶带)到 K8s

如果一个组织的开发人员习惯于通过一系列配置虚拟机、网络和其他硬件的脚本(通常需要手动干预)来构建和部署应用程序到基础架构，那么 Kubernetes 可能是一个大赢家。Kubernetes 有清晰的抽象，比如入口、Pods 和服务，所有的配置都是由声明性的配置文件驱动的。Kubernetes 中的集成控制循环(可以通过实现“[操作符](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)”模式的定制实用程序进行扩展)也提供了持续的“检查和设置”机制，以防止配置漂移。

具有这种背景的团队通常需要能够部署一个实验性的应用就绪的 Kubernetes 集群，该集群可以被配置和定制为与他们现有的基础设施一起运行。这里的核心目标将是能够创建具有不同配置的集群，并快速部署和测试服务，以查看现有应用程序(和相关的开发人员工作流)是否可以轻松地转移。

## 每个人的 K8s 游乐场

不管团队的经验如何，在学习过程中有一件事显然是有益的，那就是需要一个操场。像 [Katacoda](https://www.katacoda.com/) 、 [Go playground](https://play.golang.org/) 和[开放政策代理人减压阀 playground](https://play.openpolicyagent.org/) 这样的网站已经成功地开创了云时代互动学习的模式。

然而，Kubernetes 游乐场需要适应组织将如何部署和操作这个框架。与 GCP 相比，在 AWS 上运行 Kubernetes 是一种不同的体验，尤其是在将用户流量引入集群和安全配置方面。一个游乐场还必须易于工程师通过自助服务机制创建和破坏。

### 构建和维护 K8s 平台

创建一个 Kubernetes 游乐场并不像指引开发者到 [Minikube 安装页面](https://kubernetes.io/docs/tasks/tools/install-minikube/)，交给他们一个漫游脚本，然后说“开始吧”那么简单。这种非结构化的方法会很快导致混乱，积极性很高的工程师将各种工具集成到集群(现在是雪花集群)中，而刚进入这个领域的工程师不知道从哪里开始。

构建和维护 Kubernetes 游乐场的三大方法包括:利用现有的 K8s 游乐场产品，使用[舵图](https://helm.sh/docs/topics/charts/)创建定制游乐场，以及使用 Kubernetes 初始化器或环境快速启动服务。

### 利用现有的 K8s 游乐场

有几个受欢迎的 Kubernetes 游乐场产品，如 [Katacoda](https://www.katacoda.com/courses/kubernetes/playground) 和 [Play with Kubernetes](https://labs.play-with-k8s.com/) 。这些通常提供最少的摩擦来开始，并提供最结构化的训练方法。对于大规模或企业用例来说，这通常是一个很好的起点，目标是快速构建 Kubernetes 生态系统的开发和交付“心智模型”。

这种方法的缺点包括，这些类型的操场通常在特别实验方面是最受限制的(并且不允许工程师通过执行“脚本外”动作来学习)，并且所创建的底层环境通常不太可配置或不像产品。通常，这种类型的游乐场被视为良好的第一步，随后会增加一个更灵活、更全面的平台。

### 使用舵图建造一个定制的游乐场

使用[舵轮图](https://helm.sh/docs/topics/charts/)定义和构建定制游乐场通常与引导集群和通过基础设施作为代码工具与云服务集成相结合，如 [Terraform](https://www.terraform.io/) 和 [kudeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/) 。这为工程师提供了更多的实验范围。它还提供了灵活的集群配置和可重复的构建，非常适合意外破坏集群的情况！

这种方法的挑战是与创建操场相关的学习曲线。通常，这需要一个平台“先锋”团队比组织中的其他人早几个月开始 Kubernetes 学习之旅。这些平台工程师通常还会构建某种 UI 或 CLI 驱动的平台配置外观，以实现工程师的自助服务，否则每个人都必须像 Kubernetes 一样同时学习 Helm。

## 使用 Kubernetes 初始化器或环境快速入门

使用 Kubernetes 初始化器或环境快速启动服务，如 [K8s 初始化器](https://app.getambassador.io/)、 [OpenShift 快速启动模板](https://docs.openshift.com/container-platform/3.6/install_config/imagestreams_templates.html#creating-instantapp-templates)或 [RancherLabs Rio](https://rio.io/) ，可以快速为工程师提供类似生产的集群。通常，您可以通过 UI 回答几个问题，或者在一个简单的文件中指定配置属性，转动手柄，就会弹出一个完全成型的 K8s 集群，准备进行实验。这种方法很受工程师们的欢迎，他们已经获得了 Kubernetes 的基本心智模型，并希望尝试更适合应用程序或类似生产的体验，但不必全力以赴地致力于 Helm 之类的东西。

这种方法的局限性包括，作为初始化过程的一部分，可以安装什么工具，这是一个潜在的有限选择。此外,“第 2 天”支持选项或平台组件升级途径可能会有所限制。

## 从哪里开始？

带着与数千名学习 Kubernetes 和相关技术的工程师一起工作的经验，以及许多超级有用的社区讨论，我通常建议人们通过使用 Kubernetes 初始化器或环境快速启动来创建一个游乐场。

如果您使用的是“普通的”上游 Kubernetes 发行版或云托管产品，初始化器方法在学习使用实际 Kubernetes 原语的完整体验(相对于虚拟化的浏览器内游戏场)之间取得了良好的平衡，而不必学习额外的工具来引导平台(例如 Helm)。

如果您已经选择了一个在 Kubernetes API 之上添加额外抽象的平台(例如 OpenShift)，那么这种方法也是显而易见的，因为您从第一天起就可以获得类似生产的体验。

## 包扎

提供一个 Kubernetes 游乐场对于与这个框架相关的学习之旅是必不可少的。Kubernetes 是现代平台的一个极好的基础，但正如学习任何复杂的东西一样，你需要一个安全的操场，奖励实验和结构化学习，同时最小化任何负面后果的可能性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>