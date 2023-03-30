# Kubernetes CI/CD 最佳实践

> 原文：<https://thenewstack.io/kubernetes-ci-cd-best-practices/>

[](https://www.linkedin.com/in/ravilachhman/)

 [拉维·拉赫曼

拉维是一名福音传道者。在 Harness 之前，Ravi 是 AppDynamics 的布道者。Ravi 在 Mesosphere、Red Hat 和 IBM 担任过各种销售和工程职位，帮助商业和联邦客户构建下一代分布式系统。](https://www.linkedin.com/in/ravilachhman/) [](https://www.linkedin.com/in/ravilachhman/)

容器化和 Kubernetes 为计算世界带来了新的一致性范式，提高了工程团队的速度和敏捷性。通用声明性语言提供的描述应用程序和操作任务的融合使 Kubernetes 成为运行分布式工作负载的流行平台。

在声明性 YAML 中指定了期望的状态后，Kubernetes 开始解决和实现已声明的状态，例如应用程序的副本数量。如果有任何偏差，Kubernetes 将努力解决实际和申报状态之间的差异，例如一个 pod/container 死亡并被重新旋转。

对于第一次部署到 Kubernetes 的人来说，这种体验可能会非常迅速和虎头蛇尾。编写一个最小部署 YAML，一旦给 kubectl 命令[apply],就意味着您已经开始运行了。当需要做出改变的时候，Kubernetes 将利用它的优势之一，滚动更新，来进行渐进式的改变。如果您习惯于手工编写滚动更新规则的平台，观看滚动更新的发生会让 Kubernetes 变得轻而易举。

尽管 Kubernetes 有这么多好处，但是拥有良好的 CI/CD(持续集成/持续部署)实践是关键。Kubernetes 不应该神奇地抹去你在采用 Kubernetes 之前的 CI/CD 之旅中的纪律。利用 Kubernetes 的优势来推进您的 CI/CD 之旅。

## CI 和 Kubernetes 的最佳实践

持续集成(CI)是构建自动化的过程。例如，一个 Java 应用程序需要被构建到一个 JAR 中，然后如果被发送到 Kubernetes，就需要进行文档化，并可能以一种格式(如 Helm chart)进行打包/描述。在容器化的世界中，由于容器是不可变的，任何需要的改变都会产生一个新的映像——因此您的 CI 过程将被大量调用来构建和打包新的映像。

在 Kubernetes 上运行您的持续集成过程是一个谨慎的举动，因为构建和打包软件会占用大量的计算资源。每一次提交启动一个构建的现代方法可能会对基础设施造成很大的负担，尤其是对于容器化的构建。利用 Kubernetes 构建和打包软件是一个很好的用例，因为现代 CI 工具专注于在 Kubernetes 中创建短暂的构建运行器/节点。当构建请求到来时，只需启动一个新的实例来创建构建工件，然后在任务完成时关闭该实例。

可以在一个短暂的容器中轻松运行的持续集成信任建立步骤是单元测试、集成测试和安全扫描步骤。图像/容器扫描步骤可能是计算密集型的分解和验证 Docker 层，类似于运行计算密集型的构建任务。因为每次构建都可能引入新的依赖项或依赖项的新版本，所以每次构建新映像时运行容器扫描都很重要。

但是，有些物品需要比短暂的容器更持久，并且需要更持久的存储。持续集成的退出步骤是将创建的工件/包发布到工件储存库和/或将清单发布到各自的源代码管理/包管理器解决方案。在 Kubernetes 的世界中，这也可以是创建 Kubernetes 需要部署的所需清单，例如 Helm charts 或 Kustomize/JSONNET 资源。使用 Kubernetes 的 CI 的一个目标是产生一个易于部署的工件，包/配置/模板管理器允许这样做。

除非 Kubernetes 集群上的工作负载可以使用高可用性/持久性存储，否则将工件存储库作为 SaaS 或者脱离 K8s 集群运行是有意义的。阿喀琉斯之踵是工件库被设计成存储繁重。拥有一个可部署的工件/清单只是将您的想法送到最终用户手中的等式的一部分；接下来就是部署了。

## CD 和 Kubernetes 的最佳实践

连续交付(CD)的目标是以安全的方式将您的变更投入生产。Kubernetes 能够非常快速地部署，尤其是在使用[重建策略](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)的情况下，在这种情况下，所有的吊舱都被杀死并替换，而不是使用滚动策略进行增量部署。但是，这会导致停机。我们大多数人都在处理一直在运行的工作负载，因此停机将是一种损失。由于 Kubernetes 的即时性，抑制尽快部署的冲动似乎是违反直觉的，但却是建立信心所必需的。

在您开始使用 Kubernetes 之后，从应用程序在 Kubernetes 之前经历的建立信心的练习开始仍然很重要。例如，仍然需要测试和覆盖需求。对于 Kubernetes，可能会有更多的问题。出于可移植性的原因，运行[一致性测试](https://sonobuoy.io/)来验证您正在部署的 Kubernetes 基础设施并不罕见。首先，可移植性是利用 Kubernetes 的一大吸引力。

类似于在 Kubernetes 上运行持续集成步骤，在 Kubernetes 上运行某些持续交付步骤本身是谨慎的。在 Kubernetes 集群上很容易实现测试基础设施的建立和关闭。根据建立信任步骤的长度，编排可能需要一个工作流方面，它需要长期存在。在 Kubernetes 上或不在 Kubernetes 上运行长期/有状态工作负载的设计原则和决策同样适用于编排。

Kubernetes 可以利用诸如蓝绿色或淡黄色的发布策略。虽然您可以通过几个精心制作的 Kubernetes 清单和这些清单的及时应用来手工完成这项工作，但是涵盖这些发布策略的工具正在增加。构建适当的健康检查，如[活跃度和准备状态](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)探测，以使增量部署能够继续，这是为 Kubernetes 设计架构时的关键。Kubernetes 之前的安全需求不会随着 Kubernetes 的引入而消失。随着生态系统和工具的不断成熟，新的范例将会出现。

## 继续旅程

随着 Kubernetes 模糊了基础设施和应用程序之间的界限，一个常见的系统设计悖论——“作者可以成为系统中的执行者吗”——可以很容易地在 Kubernetes 中出现。在 Kubernetes 之前，开发工程师直接部署到生产中并不常见。通常，它由某种自动化程度不同的 [CI/CD 平台](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)负责，并获得生产许可。

有了 Kubernetes，根据您对单个集群采取隔离的程度，您可以通过[名称空间](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)分离，轻松地在同一个集群上运行构建、信任建立步骤和部署。随着现代工具和 GitOps 运动的发展，作者可以实施一些标准，如漂移检测和部署声明状态的自我修复。

Kubernetes 具有一般意义上的反应能力——例如，由[控制器](https://kubernetes.io/docs/concepts/architecture/controller/)定义。当专注于部署时，理解什么是正常的/可接受的，以进行进行/不进行判断呼叫可能是困难的。一个好的方法是从偏离基线的角度来观察监控/可观测性系统。在今天的 Harness 平台上，以自动化的方式将这些工具编排成判断调用(例如，决定是否需要回滚)是可能的。随着越来越多的组织推进他们的 Kubernetes 之旅，明智的做法是在拥抱这些新范例的同时，不要忘记在 Kubernetes 之前就已经存在的规则。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>