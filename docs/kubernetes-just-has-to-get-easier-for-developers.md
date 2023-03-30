# Kubernetes 只需要让开发者变得更容易

> 原文：<https://thenewstack.io/kubernetes-just-has-to-get-easier-for-developers/>

Kubernetes 很难理解——套用 Kubernetes 的主要创造者之一乔·贝达(Joe Beda)几年前在一篇关于 Kubernetes 的开创性论文中写的话。几年后，Kubernetes 对于大多数组织来说仍然难以管理。然而，工具和平台的出现使得 K8s 更容易让开发人员在很少或没有 Kubernetes 知识的情况下完成他们的开发工作。这些解决方案还旨在促进实现必要基础设施的运营人员的任务，以便允许开发人员以最少的学习曲线来开始创建在 Kubernetes 上运行的应用程序。

“组织将现有应用程序迁移到 Kubernetes 容器是最大的挑战，无论是否将它们分割成微服务。企业希望这些应用能够遵守相同的 SLA，并提供与在裸机或虚拟机上运行时相同的性能、安全性和合规性，"[Torsten Volk](https://www.linkedin.com/in/torstenvolk)，[Enterprise Management Associates(EMA)](https://www.enterprisemanagement.com/)的分析师告诉新堆栈。“没有一种工具可以将这项任务从开发运维团队、运营团队和安全团队手中接过来。

最近创建的[Acorn Labs](https://acorn.io/)就是为此而推出的。Acorn-Acorn Labs 的“第一个开源项目”-介绍了一种在 Kubernetes 上部署应用程序的“开发人员友好”的方法，[Acorn Labs 的首席执行官](https://www.linkedin.com/in/shengliang) 和 Acorn Labs 总裁[Shannon Williams](https://twitter.com/smw355)(两人也是 Rancher Labs 的联合创始人)说。Acorn 还被设计用来帮助解决一个典型的痛点:可怕的 [YAML](https://thenewstack.io/from-yaml-engineer-to-yaml-herder/) 配置。事实上，开发人员一般都习惯于构建 Docker 容器，但经常发现直接使用低级别的 Kubernetes YAML 文件很有挑战性，梁说。开发人员同样也在为 Helm 这样简单包装 YAML 文件的工具而苦恼。他说，Acorn 代表了一种新的工具，允许开发人员在没有任何 Kubernetes 知识的情况下使用更高级别的结构。

看看这件事如何发展会很有趣。例如，这个作者反复学习为不同版本的 Kubernetes 配置 YAML 文件，很快就忘记了，然后每次都必须重新学习这个过程。如果 Acorn Labs 确实能够简化这一过程，那么这对于开发者来说可能是一个潜在的福音。然而，一些观察人士仍保持谨慎乐观。“虽然 Acorn 背后的原则是只有一个控制开发、测试和生产环境的工件，但开发人员仍然需要编写大量的 YAML，但至少他们不必为每个云分别编写，”Volk 告诉 New Stack。

对于试图与 Kubernetes 合作的 DevOps 团队来说，最大的问题之一是开发人员、运营和安全团队成员仍然各自为政——这不是因为他们不想一起工作，而是因为他们各自可能采用不同类型的工具来完成工作。Volk 说，事实上，开发、测试和生产环境之间的不一致性在今天仍然是一个大问题，即使在大多数标准化的 Kubernetes 环境中也是如此。每个 [Docker Desktop](https://thenewstack.io/docker-defends-desktop-pricing-says-support-led-to-faster-features/) 、 [AKS](https://thenewstack.io/azure-kubernetes-service-replaces-docker-with-containerd/) 、 [EKS](https://thenewstack.io/kubernetes-as-a-service-using-amazon-eks/) 、 [GKE](https://thenewstack.io/run-a-google-kubernetes-engine-cluster-for-under-25-month/) 、 [OpenShift](https://thenewstack.io/red-hat-offers-a-complete-kubernetes-stack-with-openshift-platform-plus/) 、 [Rancher](https://thenewstack.io/rancher-labs-rio-an-application-deployment-engine-for-kubernetes/) 或 [Tanzu](https://thenewstack.io/the-new-stack-context-tanzu-the-vmware-kubernetes-distro-for-developers/) 都以开发者服务、服务联网能力、入口控制器、存储集成、灾难恢复等形式自带秘方。比如说。“如果 Acorn 可以解决这些问题，让开发人员可以定义一次部署指令，然后他们可以在开发人员的笔记本电脑、测试和产品环境中工作，这肯定会是一个重大进步，”Volk 说。

Acorn 实验室的创始人说，这些工具的另一个关键技术挑战是如何在不损害 Kubernetes 功能的情况下提供简单的用户体验。Acorn 旨在支持许多类型的应用程序，包括 Kubernetes 和微服务无状态和有状态应用程序，如存储和数据库。为了描述复杂的应用程序构造，Acorn 有自己的配置语言，松散地基于 [CUE](https://thenewstack.io/solomon-hykes-dagger-brings-the-promise-of-docker-to-ci-cd/) ，支持循环、条件和函数，而 Acorn 的范围将随着时间的推移而扩展。例如，创始人说 Acorn 的当前版本不支持定制资源，这是相当多的 Acorn 早期用户要求的功能。根据 GitHub 上公布的计划，开发团队正在致力于为 Acorn 添加自定义资源支持。

“Acorn 的另一个好处，除了对开发者来说易于使用，是它能够在使用 Kubernetes 时强制执行最佳实践，从而使应用程序更加安全可靠，”梁说。“一旦开发人员将其应用程序打包为 Acorn 映像，就可以放心地在生产环境中部署这些 Acorn 映像。”

## k8 兄弟会

自从几周前启动以来，Acorn Labs 项目已经吸引了一些人的兴趣。“Acorn Labs 最近的发布看起来超级有趣，似乎他们的目标是填补微服务和容器技术出现的‘应用程序打包’差距，” [Daniel Bryant，](https://www.linkedin.com/in/danielbryantuk/)Ambassador Labs 开发人员关系负责人告诉 New Stack。“像 Kubernetes 这样的平台基础设施提供的应用程序原语对于只想编写代码并让代码部署和运行的‘99%开发人员’来说太低级了。”

布莱恩特说，尽管如此，Acorn 实验室希望实现的目标并不是一个容易解决的问题。其他人以前也试过。例子包括 HashiCorp 的 Otto 和 Docker 的 Stacks。关键是在云原生 SDLC 的编码、交付和运行等必要阶段创造‘金发女孩’开发者体验，”Bryant 说。

不同的 Kubernetes CI/CD 平台提供商也可以互补。“CNCF 使者入口和我们的 Edge Stack API 网关解决方案可以很容易地打包为 Acorn 文件应用程序定义的一部分，因为每个人都需要将用户流量传输到后端服务，”Bryant 说。

Bryant 说:“Acorn 还可以用来打包和部署应用程序，而[网真](https://thenewstack.io/telepresence-brings-the-kubernetes-cluster-to-developers/)将使开发人员能够轻松地弥合本地到远程开发和调试的差距。”。通过简单的 CLI 或基于 web 的 UI，开发人员可以使用 Telepresence 来调试本地运行的服务，该服务依赖于远程大规模 Acorn 管理的 K8s 部署

## 隧道尽头的光？

正在取得进展，但仍有许多工作要做。即使对于那些已经实施了正确的工具、培训和文化，让他们的开发人员以最小的摩擦在 Kubernetes 上创建和快速部署优秀应用程序的组织来说，容器化的环境仍然是一场斗争，除了谷歌——甚至仍然是——那些没有像 Netflixes of the world 这样烧钱跑道的组织。

“屈从于 Kubernetes 必须让开发者变得更容易’是目光短浅的。”几年前，在与首席信息官交谈时，我经常听到这样的话，“我们觉得自己已经怀上了容器，却无法实现这一计划。我们正在积极寻找退出的方法，“ [John Steven，](https://www.linkedin.com/in/m1splacedsoul/)CTO at[threat modeler，](https://threatmodeler.com/) 一家自动化威胁建模提供商。”所以，是的，Kubernetes——像任何新的技术平台一样——将不得不发展，或者它可能会简单地被取代，因为它在努力/利益权衡方面辜负了工程师。Docker 或 Heroku 曾被认为是世界杀手，但现在不再是了:他们无法超越自身的局限和复杂性。”

史蒂文说，的确，像许多技术一样，Kubernetes 的致命弱点源于它的强大。“Kubernetes 设计了‘Google By Google’来协调人类规模的应用程序操作，”Steven 说。“考虑到其数据中心的局限性，组织误解了他们对 Gmail、Search 或 Drive 所体验的“云原生基础架构灵活性”的渴望。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>