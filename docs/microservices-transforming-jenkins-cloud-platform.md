# CloudBees 如何使用容器将 Jenkins 转变为服务

> 原文：<https://thenewstack.io/microservices-transforming-jenkins-cloud-platform/>

CloudBees 的营销副总裁安德烈·皮诺(André Pino)说:“随着 Jenkins 的使用越来越多，管理员和 DevOps 人员满足需求的能力正在失控。

周二， [CloudBees 发布了其商业 Jenkins 的云版本](https://thenewstack.io/cloudbees-offers-jenkins-private-saas-self-service-model/)。这个私有的 SaaS 版本是以“即服务”的方式交付的，这一事实说明了组织中存在大量的用例，在这些用例中，基于云的持续集成/持续交付(CI/CD)不仅方便，而且可行。“该产品为他们提供了一种卸载 Jenkins 交付环境即服务的方式，”Pino 继续说道。

Pino 说，CloudBees 的客户希望找到一种方法，既能让 Jenkins 旋转起来，又能让它旋转下来。换句话说，他们希望 CI/CD 像他们正在做的工作一样可扩展，而不是像 Jenkins 在现场所做的那样从固定的防御工事中获得。

CloudBees 发现，通过使用容器和微服务架构可以更容易地实现这些目标。

在封面下，詹金斯私人 SaaS 使用 Docker 容器，解释丹 Juengst，Docker 的产品营销高级总监。“管理所有这些容器的 Mesos 编排引擎。前端就是我们所说的詹金斯运营中心，上面有一个按钮，上面写着‘创建一个新的主服务器。’因此，当项目团队按下 master 按钮时，Mesos 编排引擎将启动一个安装了 Jenkins master 的新 Docker 容器，该团队可以在几分钟内立即开始使用它。"

传统上，CI/CD 作为一种自上而下、执行驱动的道德规范被销售给组织，必须从公司层级的上层强制执行。然而，其最大客户中的许多小型敏捷开发团队需要针对个人工作的即时、短暂的 CI/CD 平台，而不是端到端的企业工作控制。这是来自组织另一端的变革管理——执行官可能认为是“自下而上”的变革。

## 首先是容器

Juengst 告诉我们，在其最初的形式中，私人 SaaS 版将为 OpenStack 部署和亚马逊 AWS 量身定制。Juengst 说，第一代虚拟机所在的环境“不是 it 的理想候选环境”。“但是，如果他们可以建立一个环境，或者利用 AWS 运行私有 SaaS 版，他们仍然可以在 vSphere 和虚拟机中运行他们的应用程序并完成其余的 IT 工作。这在某种程度上独立于我们。”

根据 Juengst 的说法，基于 Azure 的部署以及传统虚拟机都在 CloudBees 未来增强的“待办事项”中。

CloudBees 副总裁 Pino 说:“容器化的美妙之处在于它提供了底层系统的抽象层次，因此我们可以利用容器创建一个基础设施，该基础设施可以轻松适应多种底层配置。这减轻了以前为适应这些配置而需要的大量定制工作。”

Juengst 在这里补充了一点细节:在现有的 [Jenkins Enterprise Edition](https://www.cloudbees.com/products/cloudbees-jenkins-platform/enterprise-edition) 中，一个名为 hot standby 的功能可以让 CI/CD 服务器故障转移到旁路服务器，而不会出现明显的服务中断。这需要一些管理工作和额外的服务器，但它是可行的。在基于容器的私有 SaaS 版本中，整个冗余备用服务器变得没有必要，因为功能是在更精细的级别上复制的，可以按需扩展和缩减。

“Mesos 本身有能力监控所有运行在它自己环境中的容器，”Juengst 解释说。“如果一个容器碰巧不见了或崩溃了，它就知道立即把那个容器旋转回来。如果一个构建节点正在运行一个作业，而它崩溃了，Mesos 通常会重新启动它，重新启动作业，然后它就可以运行了。”

Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>