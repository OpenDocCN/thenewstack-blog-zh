# 开发人员可以避免的 Kubernetes 陷阱

> 原文：<https://thenewstack.io/kubernetes-traps-developers-can-avoid/>

本文是两部分系列的第一部分，探讨了 Kubernetes 的开发者体验。下周一回来看第二部分。

这个咒语已经被灌输给了开发者:Kubernetes 可以为许多制作团队提供前所未有的机会来扩展、协作和加速软件的部署。但是随着平台继续被采用，只有少数组织还没有采用容器(K8s 毕竟是一种在容器上协调部署的方式)。

但是对于那些可以利用 Kubernetes 提供的潜在巨大优势的组织来说——除了它基于 pod 的概念魔法和底层结构是如此简单以至于许多人挠头为什么以前没有人想到它——开发人员需要注意一些警告。事实上，不幸的是，Kubernetes 可能成为开发团队的部署噩梦，否则它将是完美的选择。

在本帖中，我们来看看开发团队在转向 Kubernetes 时可以避免的一些常见陷阱。

## 提前计划您的工具集

向 Kubernetes 的转移显然是一个以 DevOps 为中心的项目，因为这一转移在许多方面涉及到运营人员和开发人员。对于开发人员和运营人员来说，一个关键问题是从为 Kubernetes 平台提供的数百个开源工具集中进行选择。关于开发人员需求的一个常见思路是避免生产管道中的任何手动步骤，以及必须承担与操作相关的任务。

[企业管理协会(EMA)](https://www.linkedin.com/company/enterprise-management-associates/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 说，代码只有对开发者来说才是完整的，例如，当它包括一套完整的自动化代码时，从直接运行时需求到监控关键 KPI，扩展和升级应用程序或服务，以及定义关键参数，以优化应用程序与 Kubernetes 集群和 pod 的匹配。“简而言之，Kubernetes 是一个构建工具包，而不是现成的解决方案，但如果你投入工作并避免对临时问题的快速手动解决方法，你就能在一天中释放出大量损失的 50%的生产力。”

事实上，大多数开发者显然“真的只想让容器化的应用程序运行起来，”基础设施即代码平台供应商[的首席执行官兼联合创始人](https://www.pulumi.com/)[乔·达菲](https://www.linkedin.com/in/joejduffy/)说。事实上，帮助组织建立容器基础设施是创建 Pulumi 的主要动机。“虽然 Kubernetes 有助于实现这一目标，但一开始并不明显的是，这是一项重大承诺，而且往往比初看起来要困难得多。”

然而，Kubernetes 给开发者带来的潜在问题是，K8 就像“从消防水管里喝水”，[VMware](https://www.linkedin.com/in/bryanliles/)的高级员工工程师 Bryan Liles 说。

正如 Liles 所指出的，归根结底，开发人员关心的是他们的容器映像中是否有二进制文件，并希望在一个或多个集群中运行一个到 100 多个副本。大体上就是这样。但是，Liles 说，“作为一名开发人员，在这个领域起步并不容易”。

现有的底层框架，比如 Docker 和微软的 Helm，已经进行了改进，使得创建图像变得更加容易。但就 VMware 而言，它一直在开发工具包，以更好地帮助开发人员入门。“我们现在正在做的是寻找创造更好的 Kubernetes 工具包的方法，”Liles 说。“这个工具包应该做的是，当我启动 Kubernetes 时，我有一套特定的工具，可以让我作为一名开发人员立即提高工作效率”。

## kubectl 连接

访问微服务的解耦和 API 特性显然是 Kubernetes 的精髓，而 [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 命令行界面就是这样一个工具，在部署到 Kubernetes 上之前，您必须提前掌握它。虽然对在容器上开发平台(通常是通过 Docker)有一个扎实的理解是必不可少的，但是要准备好了解和使用 kubectl。事实上，它很难学，因为它太强大了，太实用了。

在开始依赖于 **kubectl** 接口之前， [Rancher Labs](https://rancher.com/) 的软件工程师[Rajashree mandagane](https://www.linkedin.com/in/rajashreemandaogane/)，利用她对容器的工程级别的理解和经验来学习只有 **kube-apiserver** 如何与集群的数据存储 **etcd** 通信。这确保所有组件通过**kube-API server**查询 **etcd** 获得一致的数据。我研究了 Kubernetes 如何遵循规范与状态的方法，然后开始编写自己的定制资源定义(CRD)和围绕它们的定制控制器，”Mandaogane 说。

然而，尽管 kubectl 可用于按名称检索特定对象，或属于一个名称空间或跨所有名称空间的一类对象的列表，Mandaogane 说，“有时您可能希望在一个字段中查找具有某个值的对象”。Mandaogane 说，问题是“你不能执行基于字段的查询”。

作为一个解决方案，Mandaogane 提供了下面这个她在调试过程中经常使用的技巧:假设你想寻找带有 nginx 映像的 pods，你可以做**kubectl get pods-o YAML | grep nginx**。这将给出具有该图像的 pod 的数量，而不是 pod 名称本身。您可以使用**ku bectl get pods-o YAML | grep-A20-B20 nginx**进一步提高输出质量。标志 A 和 B 控制包含“nginx”的行之前和之后的输出中包含的行数。

## 拿好你的东西

对开发人员来说很明显，“你应该知道并掌握一个 git”这条戒律对 Kubernetes 也适用。但由于 Kubernetes 仍然是一个相对较新的平台，无论是从开发者还是行业的学习曲线来看，都还有很多工作要做。

“现在的问题是，我们目前正在等待我们的工具赶上这一新范式，就像 Git 刚推出时一样。“Kubernetes 不仅代表了应用程序运行方式的转变，也代表了应用程序编写方式的转变，”[git lab](https://www.linkedin.com/in/ashishkuthiala)市场总监阿希什·库西亚拉说。“任何云原生开发团队在选择托管 Git 解决方案时，最重要的问题应该是:‘这适合我们的新工作流程吗？’而不是“我能让它适应我们的新工作流程吗？”"

再次，如上所述，成功转移到 Kubernetes 取决于 DevOps，这也意味着，在运营方面，开发人员需要注意以下问题，因为问题不可避免地“在这种规模的转变发生时出现”，Kuthiala 说。库蒂亚拉描述了面临的以下问题包括:

*   复杂性:Kubernetes 在安装、集成和操作方面很复杂。除了教育，别无他法。
*   自动化灾难:自动化在理解人类意图方面并不完美(参见 2017 年 S3 大停电)，但它是 Kubernetes 上生产应用部署的核心。
*   有状态应用程序很难，因为您真的不想在容器中运行数据库。
*   不同的云提供商之间的存储和联网方法可能(并且通常会)有所不同，从而导致对可移植性和弹性的担忧。
*   在负载情况下扩展部署可能具有挑战性，因为您面临硬锁定调度程序的风险。
*   应用程序需要进行更多的运行状况检查，以确保微服务结构完好无损。
*   许多组织希望通过服务网格增加更多的复杂性。

## 创造历史

Kubernetes 可以给开发团队带来巨大的好处。开发人员可以利用 Kubernetes 的解耦能力和现有的许多 API 来访问整个团队可以单独工作的微服务。但是，开发商也意识到了 Kubernetes 可能带来的风险。更多的警告——几乎总是会有更多的安全漏洞——将会在未来公之于众，但是随着它们的传播，Kubernetes 将会变得更加稳定和可靠，最终变得更加强大。

换句话说:敬请关注。

VMware 和 GitLab 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>