# Garden 自动化了 Kubernetes 的构建、部署和测试

> 原文：<https://thenewstack.io/garden-automates-kubernetes-building-deploying-testing/>

许多初创公司的创始人会告诉你，他们的公司是在挫折中成长起来的，但根据首席执行官乔恩·埃德瓦尔德的说法，在 Garden.io 的案例中，这是愤怒的产物。

开发人员在设置 Kubernetes 环境和等待测试完成的一天中浪费了太多的时间。

早在 2017 年在柏林的 Clue 工作时，“我最终建立了定制的内部工具，试图保持开发者体验的理智，让我们的团队能够轻松测试他们的变化，获得他们的开发环境。许多我们现在认为理所当然的工具并不存在。这相当艰难，”他解释道。

“我与 DevOps 的一群 CTO 和人员进行了交谈。他们分享了相似的故事……这就是机会所在。”

当时的过程是一系列的 git 提交、推送和等待。人们对 CI/CD 系统中的所有东西是如何组合在一起的知之甚少，而且[开发](https://thenewstack.io/category/development/)和测试环境不一定与生产环境相似。

“在整个行业中，投入到这种乏味的反馈循环中的大量时间是许多沮丧和大量浪费时间的来源，”他说。

“我认为 Garden 解决了云原生空间的一个真正需求，即平台越复杂，开发人员越多，开发人员和生产人员之间的差距就越大。但是如果你想要快速的特性开发和高质量的代码，尽可能缩小这种差距是很关键的。“Garden 解决了这个问题，并且以一种非常好的方式做到了这一点，这种方式符合 Kubernetes 的模式，而且不会让人觉得太过严厉，”浮力公司的首席执行官[威廉·摩根](https://thenewstack.io/author/william-morgan/)说。

## 从“基础设施即代码”中汲取经验

有了 [Garden automation](https://thenewstack.io/garden-the-configure-once-kubernetes-platform-for-seamless-dev-prod-integration/) ，开发人员可以为集成测试、手动 QA 和持续集成工作流建立短暂的测试和预览环境，并更快地获得反馈。他们不必再受调配和管理临时环境的困扰。

“作为开发人员，您可以通过笔记本电脑从头开始构建整个环境。你可以把它拆下来，重新启动，你就有了好的工具，可以尽快地把你所做的任何改变解决到运行环境中。您可以从您的 CI 和 CD 中运行完全相同的工具和配置。这样你就失去了两者之间的摩擦力，”他解释道。

“这基本上意味着您在任何时间点都可以轻松获得 CI/CD 自动化的全部功能。我认为，这是处理越来越分散、越来越复杂的云系统的唯一明智的方法，这些云系统具有所有这些不同的移动部件，它们需要聚集在一起，才能真正拥有一个完全运行的系统。”

Edvald 说，它与声明性基础设施即代码的关系非常类似于 Terraform。

它使用该公司所谓的[栈图](https://docs.garden.io/basics/how-garden-works)，这是一个基于有向无环图(DAG)的框架，允许你将栈的完整描述编码为直观的 YAML 声明，捕捉所有组件之间的关系。

配置文件位于每个模块(基本单元建筑)的旁边。它可以对应于 Docker 文件及其相关代码、远程 Docker 图像、舵图、OpenFaaS 函数等。Garden 扫描这些配置文件，甚至跨多个存储库，验证它们，并将它们编译成一个图表，描述构建、部署和测试应用程序所涉及的所有步骤。

Garden 通过将您的当前代码与之前构建、部署和测试的版本进行比较，使用图表来检测模块何时需要重新构建或重新测试，或者服务何时需要重新部署。

无论是在开发人员的笔记本电脑上还是在 CI/CD 系统中，它的工作方式都是一样的。

当您使用共享的 Kubernetes 集群运行 Garden 时，Garden 有自己的名称空间和一小组服务，每个开发人员在集群中都有一个私有的名称空间，他们可以在该名称空间中运行应用程序的完整实例，并在其中进行开发和测试。

“Garden.io 是我们云原生开发环境不可或缺的一部分。它解决了我们开发过程的内部循环。它允许我们释放开发人员机器上的资源，并在远程 Kubernetes 集群中运行。负责 [InfluxData](https://www.influxdata.com/?utm_content=inline-mention) 部署的工程经理 [Patricia (Pat) Gaughen](https://www.linkedin.com/in/pat-gaughen/) 说:“代码更改不仅部署在这些远程集群中，而且我们还能够不断地将其与组成产品的其他服务集成——所有这些都在开发人员的个人环境中进行。”。

“我们研究了其他解决方案，感觉 Garden 将帮助我们减轻开发人员系统的负担，并允许我们的开发人员快速行动。此外，在我们与他们的整个评估过程中，Garden 非常容易使用。在这个过程中，他们一直是出色的开源合作伙伴，能够快速解决提出的任何问题，并与我们一起为我们的开发人员提供解决方案。”

## 基于 TypeScript 构建

虽然该公司迄今为止一直专注于 Kubernetes 的开发，但它决定采取更广阔的视野，从而使 [Typescript](https://thenewstack.io/typescript-getting-popular/) 成为其主要语言。

“我们仍然能够将它作为一个单独的二进制文件来分发，所以用户通常不必在意。这有点抽象了，”他说。“[但是]首先，我们不仅仅把 Kubernetes 作为目标平台。那正是我们今天的面包和黄油。但我们希望对无服务器平台有更长远的看法，以及各种不同的目标平台。”

尽管 Golang 在该领域占据主导地位，但这一决定在一定程度上是个人偏好。

“我们希望在网站和用户界面上拥有与引擎本身相同的类型和语言，这基本上为我们在开发过程中避免了许多潜在的问题。”

它的许多用户来自于像 [Docker Compose](https://docs.docker.com/compose/) 这样的工具，Kubernetes 生态系统在此期间已经成长起来，产生了包括 [Okteto](https://www.okteto.com/) 、 [Tilt](https://tilt.dev/) 和 [DevSpace](https://devspace.sh/) 在内的竞争对手。然而，埃德瓦尔德说，Garden 看得更远。

“我们希望构建在 CI 期间以及从您的笔记本电脑的内部循环中同样工作的东西。我们想要的是可插入更多平台的东西，而不仅仅是 Kubernetes。…我们从更长远的角度出发，思考无服务器端正在发生的事情。我看到服务器端 WebAssembly 发生了很多有趣的事情。…[我们]也在思考很多关于测试和我们如何改进测试工作流程的问题…很多工具，它们帮助您启动环境，它们负责构建和部署。但我们也想对它的测试方面产生积极的兴趣，让它更快、更容易地运行集成测试。”

## 超越库伯内特

埃德瓦尔德与联合创始人[托尔·西古尔德森](https://www.linkedin.com/in/thorarinn-sigurdsson-a4352123/?originalSubdomain=is)和[巴斯·彼得斯](https://www.linkedin.com/in/bas-peters-08364a104/)一起，在 2018 年发布了 Garden，作为一个[开源项目](https://github.com/garden-io/garden)，使用“copy left”Mozilla Public License 2.0 许可证。Edvald 说，这个核心将永远是开源的，尽管该公司也提供企业版和托管版。

该公司刚刚筹集了 1600 万美元的首轮融资，使其融资总额达到 2090 万美元。其 80%的业务在美国，客户包括 payroll technology Gusto、销售演示供应商 Reprise、英国银行 OakNorth 和德国电子技术供应商 Luminovo.ai。

新的资金将允许该公司在美国扩张，而研发将留在德国。

展望未来，它希望简化开放核心，使新用户更容易访问它，并增加与第三方系统的集成，如[安全](https://thenewstack.io/category/security/)工具。

“我们正在开发一个套件集成，您只需提供一个 API 密钥，Garden 已经知道所有集装箱图像、我们的 Kubernetes 清单和舵图，并且可以将这些数据传输到一个安全解决方案，该解决方案将扫描这些漏洞。这是我们正在探索的途径的一个例子，不仅仅是构建和部署应用程序，还要验证和理解它，”Edvald 说。

它还将进入无服务器领域，并计划对 WebAssembly 进行一些投资，尽管 Edvald 认为这项技术仍处于早期阶段。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>