# Civo Navigate 的新功能:加快机器学习的设置速度

> 原文：<https://thenewstack.io/new-at-civo-navigate-making-machine-learning-set-up-faster/>

佛罗里达州坦帕——在建立一个机器学习项目所需的时间中，60%实际上是用于执行基础设施工程任务。

相比之下，Civo 首席创新官 Josh Mesout 在周二的 Civo Navigate 会议上表示，20%的人从事数据工程，他在过去两年半的时间里推出了 300 个[机器学习](https://thenewstack.io/ai-short-term-overhype-but-underhyped-for-the-long-haul/) (ML)模型。

Civo 希望通过一种新的托管服务产品来简化机器学习基础设施， [Kubeflow](https://www.kubeflow.org/) 即服务，它表示这将改善开发人员的体验，并减少从机器学习算法中获得洞察力所需的时间和资源。

## Civo 的机器学习命题

Kubernetes 云提供商打赌开发者不想处理 ML 难题的基础设施部分。因此，它的新产品将作为托管服务运行 ML 的基础设施，同时支持开源工具和框架。它认为这将使小型组织更容易获得 ML，它说由于规模经济的原因，小型组织的价格往往高于 ML。

这是一个有趣的命题，因为 Mesout 也认为机器学习通常部署在内部，而不是在云中。

“普遍的误解——我与人们就此进行了长时间的激烈争论——是机器学习不会在云中结束，”他说。“它最终在本地完成…原因是云的弹性工作负载类型非常适合服务建模，但如果你要将你的机器学习扩展到有 100，000 人在那里，你可能永远也不会完成它。"

他说，从投资回报的角度来看，这也很难证明，而内部投资回报率“很有意义”。

## 解决安全问题

根据 Mesout 引用的一份 Anaconda 调查报告，公司也表达了对 ML 和数据安全的担忧。另一个难题是，公司不想要更多的专有选项:他们想要开源工具，他说，因为它通过避免供应商锁定给了他们更多的自主权，还因为经济效益更好，他补充说。

最后，公司说他们没有使用云，因为他们声称，将 ML 项目与其他架构挂钩太难了，Mesout 补充道。

“作为一家云本土公司，我们喜欢 Kubernetes 的概念来克服这一点，”他说。“当我们试图解决一个问题时，我们已经寻找了许多不同的方法，我们认为支持开源，而不是与之斗争并建立封闭源代码的专有工具生态系统，是解决方案。”

通常在云中，公司为 100%的 GPU 付费，而机器学习模型可能只使用了 24%。他补充说，因此 Civo 正在考虑降低 20%的成本，以帮助公司在他们的 ML 项目上赚钱。

他补充说，该公司还在与 Defense.com 合作提供安全保障。它还将提供一个集成的开发环境，并支持核心的 Kubeflow 组件。

Kubeflow 即服务目前处于私有 alpha 阶段。

## 面向开发者的 Civo 平台

会议上表达的一个抱怨是，Kubernetes 工具目前对开发人员来说太“落伍”了，他们想要更抽象、坦率地说更友好的工具。Civo 的首席技术官 Dinesh Majrekar 说，54%的开发者认为 Kubernetes 的复杂性降低了他们的速度。

Civo 宣布了其新的 Civo 平台，即平台即服务(PaaS)产品，旨在满足这一需求。该平台为开发者提供了一个“负担得起的、灵活的和可扩展的框架，用于在云中运行和开发应用程序，”该公司在[的新闻稿中声明。Majrekar 说，每个托管的 Civo 平台应用程序都部署在自己的 Kubernetes 集群上。](https://aijourn.com/press_release/civo-launches-new-platform-as-a-service-offering/)

新的 PaaS 整合了一个[软件材料清单](https://thenewstack.io/how-to-create-a-software-bill-of-materials/)工具，允许用户生成软件中所有组件的验证记录。(2021 年 5 月，拜登政府[发布行政命令](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)，要求为美国政府购买或代表美国政府使用的任何软件提供 SBOMs。)

然而，PaaS 产品的问题是，项目可能会超出平台，让开发人员不得不在其他地方重新构建。Majrekar 说，为了确保这种情况不会发生在它的平台上，Civo 支持轻松地从 PaaS 切换到完全托管的 Kubernetes 服务，只需点击一个按钮。

## 提出了新的开源标准

Civo 还宣布了 [Open Control Plane，或 OpenCP](https://github.com/opencontrolplane/civo-opencontrolplane) ，它希望制定一个开源规范。它包括 YAML 堆栈规范以及使用 [Kubectl](https://thenewstack.io/introduction-to-kubernetes-imperative-commands/) 与云提供商互动的能力。Majrekar 告诉新的堆栈，如果采用，用户将能够在不重建的情况下更换云提供商。

例如，一个网络在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)上被称为“VPC”，但在 Civo 上却被称为“网络”。最终用户可以使用术语“网络”,云提供商将根据标准进行调整。他补充说，它也不依赖插件。

“我们不想拿你的数据来勒索赎金，”Majrekar 说。“您的数据不会产生出口费用。”

该公司希望其他云提供商也会有同样的感受，因为它计划向他们推广该标准。

Civo 还宣布了一个名为 civo stack in the Edge 的新本地选项。它将被运送到最终用户公司供内部使用，并将纳入安全性，提供多种大小，并提供自动原子备份，这意味着如果第一次不成功，它将继续备份。Majrekar 补充说，它使用基于角色的访问控制(RBAC)的 API 进行访问，以及 Civo 公共云的相同硬件和简单性。

最后，Civo 展示了其 Edge Manage 产品，这是一种基于云的解决方案，用于管理内部部署的物联网设备。Edge Manage 基于 Talos，按每设备成本定价。

与 edge 产品相关，该公司正计划将其数据中心扩展到更多地区，因此集群和数据将更接近最终用户。它目前在伦敦、纽约和德国法兰克福工作，并计划在凤凰城扩展。

Civo 支付了 Loraine Lawson 参加会议的差旅费和住宿费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>