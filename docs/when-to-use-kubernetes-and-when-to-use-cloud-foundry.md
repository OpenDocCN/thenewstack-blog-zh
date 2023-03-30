# 何时使用 Kubernetes，何时使用 Cloud Foundry

> 原文：<https://thenewstack.io/when-to-use-kubernetes-and-when-to-use-cloud-foundry/>

云原生服务提供商 [anynines](https://www.anynines.com/?utm_content=inline-mention) 的首席执行官 [Julian Fischer](https://www.linkedin.com/in/julianfischer) 表示，虽然 Kubernetes 为应用管理带来了极大的灵活性，但 [Cloud Foundry](https://www.cloudfoundry.org/?utm_content=inline-mention) 平台即服务(PaaS)软件提供了最佳的标准化水平。

在最新一集的 [The New Stack Makers](/podcasts) 播客中，我们与 Fischer 进行了交谈，以了解该公司在管理 Kubernetes 和 Cloud Foundry 的大规模部署方面的经验。

“今天的很多话题都是关于 Kubernetes 的。但是云铸造生态系统已经非常强大，“特别是对企业而言，”Fischer 指出。

[什么时候用 Kubernetes，什么时候用 Cloud Foundry](https://thenewstack.simplecast.com/episodes/when-to-use-kubernetes-and-when-to-use-cloud-foundry)

Cloud Foundry 是一个重量级平台。它不是你下载并作为一个业余爱好项目建立起来的东西。但是它在大型企业项目中工作得非常好，提供了一个集中的平台，开发人员可以在这个平台上构建应用程序。拥有数千或数万开发人员的组织使用 Cloud Foundry 作为中心开发平台。许多管理员都可以轻松管理它，尤其是由 [Bosh](https://bosh.io/docs/) 管理的部署。

“许多大型组织在其数字化转型之旅中投资了 Cloud Foundry，以提高应用程序开发人员的工作效率。有了这种无操作体验，开发人员可以专注于他们的应用开发，而不是摆弄复杂的基础设施自动化平台。这对于实现数字化转型的第一步非常有吸引力，”费舍尔说。

Cloud Foundry 特别擅长部署一种 [12 因素方法](/12-factor-app-streamlines-application-development/)来构建应用程序，其中应用程序是无状态的，并且配置是以声明方式完成的，以实现部署自动化。对于符合这些标准的应用程序，没有什么比 Cloud Foundry 更能提高运营效率。

“它提供了显著的规模经济效应，”费希尔总结道。

然而，许多应用程序不符合这个标准的 12 步模型，尤其是遗留应用程序。这就是 Kubernetes 的用武之地。“有一些应用程序与 Kubernetes 有密切关系，”Fischer 说。Kubernetes 具有标准 PaaS 所不具备的灵活性。例如，许多遗留应用程序不太适合 12 因素模型。他们需要“提升并转移”到云原生环境中，Kubernetes 可以轻松满足他们的特殊需求(当然，需要做一些初始调整)。

使用 Kubernetes，可以针对不同的应用程序需求调整不同的集群。一些应用程序团队可能想要一个标准发布的集群，而另一些团队可能想要保持对集群的完全控制以满足他们自己的需求。

“有了 Kubernetes，我们需要根据组织的需求定制自动化解决方案，”Fischer 说因此，理想的 Kubernetes 平台更多地反映了特定客户的 IT 内部结构。"

除了讨论 Cloud Foundry 和 Kubernetes，我们还讨论了一致的数据服务战略的重要性、GitOps 的作用以及 anynines 的起源故事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>