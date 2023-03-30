# 借助云铸造平台简化 Kubernetes

> 原文：<https://thenewstack.io/making-kubernetes-easier-with-cloud-foundry-platform/>

[](https://www.cloudfoundry.org/)

[Childers](https://www.cloudfoundry.org/)

[Childers 在大规模计算和开源软件方面已经花费了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache CloudStack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。Chip 是 OSCON、LinuxCon North America、LC Japan、LC EU、ApacheCon、O ' Reilly Software Architecture Conference 等活动的资深演讲者。在空闲时间，奇普喜欢带着他的黑色实验室徒步旅行，驾驶双体船和太阳鱼，并试图跟上他年轻的女儿。](https://www.cloudfoundry.org/)

[](https://www.cloudfoundry.org/)[](https://www.cloudfoundry.org/)

Kubernetes 是长期以来冲击 it 行业的最大的技术颠覆者之一——可能是自亚马逊 EC2 以来，现在已经超过十年了。它帮助将容器从一种方便的打包方法转变为现代应用程序架构的构建模块，并将许多领域的讨论从云计算转移到了云原生计算。

如果这看起来像是一种技术上的吹毛求疵，它不是。云原生技术和架构是更传统的业务(如保险、金融服务甚至重型机械)从简单地消耗云资源过渡到像云提供商一样运营的手段。这正在改变他们经营业务的方式，使他们更加敏捷、分散，并随时准备通过软件解决他们的业务需求。然而，与大多数新技术一样，用一些观点来看待 Kubernetes 是很重要的。

特别是对于大型企业来说，Kubernetes 及其不断发展的生态系统只是一个持续几十年的连续统一体中的最新发展。它可能是希望以一种很好的方式管理集装箱船队的团队的首选工具，但它仍然只包含企业工作负载的一小部分。尽管大规模迁移到 AWS 和 Google Cloud 等云平台，但在可预见的未来，企业将需要一定程度的控制和灵活性，而托管云服务和以开发人员为中心的技术根本无法提供这种控制和灵活性。

## 使用 Cloud Foundry 简化 Kubernetes

我们看到这些事情在 Cloud Foundry 用户社区中直接发生，这是一个不断增长的公司集合，包括超过一半的财富 500 强。对于大多数企业来说，选择像 Cloud Foundry 这样的平台的决定可以归结为三个相对简单的愿望:

1.  拥抱开源技术和致力于创新和解决企业计算需求的大型开源社区。
2.  让开发人员可以自由地专注于他们的代码，而不是管理机器(虚拟的或物理的)。
3.  为运营商提供工具，利用微服务、CI/CD 和零停机升级轻松管理 IT 环境，并跨越虚拟机、裸机、私有数据中心和公共云。

进步永不停息。随着 Kubernetes 等新技术的成熟和普及，开发人员变得兴奋起来，他们的雇主也感到有必要测试这些技术。如果 Kubernetes 能够帮助实现上述三个目标，这并不奇怪！)可以——他们将寻找一种方法将其集成到他们的 it 环境中。与此同时，公司需要各种选择来帮助他们将当前的基础设施与未来的计划结合起来。

## 通过应用运行时和开放服务代理 API 与 Kubernetes 交互

家得宝(Home Depot)和康卡斯特(Comcast)等用户的 IT 现代化工作已经进行了好几年，这些工作始于利用 Cloud Foundry 的平台即服务应用程序运行时和 BOSH 基础设施管理工具。到目前为止，他们所看到的改进是真实而有意义的，这意味着随着他们现代化工作的扩展，他们在云铸造平台上的投资只会增加。

这是开源软件真正闪耀的地方。2017 年，在客户需求的推动下，Kubernetes 的创造者谷歌与 Pivotal(广泛采用的商业云铸造发行版的提供商)合作了一个名为 Kubo (Kubernetes + BOSH)的项目，顾名思义，该项目使用 BOSH 来管理容器编排引擎 Kubernetes，就像它管理原生云铸造应用程序运行时一样。今天，这项工作已经作为 Cloud Foundry 容器运行时与开源 Cloud Foundry 平台集成在一起。

从最终用户的角度来看，这意味着开发人员与 Kubernetes 的交互就像没有 Cloud Foundry 时一样。然而，运营商能够通过 BOSH 管理底层的 Kubernetes 基础设施，这带来了一些重要的好处。我们已经看到 Cloud Foundry 用户达到了一个运营商对 1000 多个应用程序的比率，我们希望随着集成的成熟，这些类型的结果能够转化为 Kubernetes 应用程序。

我们还围绕 Cloud Foundry 开放服务代理 API 与 Kubernetes 社区携手合作，该 API 现在是标准途径，云提供商和应用程序供应商可以通过在 Cloud Foundry、Kubernetes 和 Red Hat 的 OpenShift 上运行的应用程序来提供服务。这里还有更多的内容需要解释，但简单的解释是，如果您想将 Google BigQuery 等服务集成到运行在 Kubernetes 或 Cloud Foundry 中的应用程序中，开放服务代理 API 是实现这一目标的方法。

这里的要点是，在一个充满开源和开放 API 的 IT 环境中，没有一种技术可以满足所有人的需求。无论是 Cloud Foundry 和 Kubernetes，还是其他任何一套技术，权力都在于用户，他们会以这样或那样的方式得到他们想要的东西。大型企业总会有许多他们喜欢和依赖的其他技术；认真对待企业采用的公司、基金会和项目知道他们的工作是在这个现实中工作——否则他们可能成为一个脚注。

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>