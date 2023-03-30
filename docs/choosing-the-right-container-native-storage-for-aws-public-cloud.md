# 为 AWS 公共云选择合适的容器本机存储

> 原文：<https://thenewstack.io/choosing-the-right-container-native-storage-for-aws-public-cloud/>

随着越来越多的独立软件供应商(ISV)应用被打包成通过 Kubernetes 部署，以允许在执行场所之间进行简单的转换，有状态工作负载正在成为这些集群中的标准模式。随着 Kubernetes 社区上的[数据快速增长，Kubernetes 正在成为管理云原生数据应用的行业标准。](https://dok.community/data-on-kubernetes-2022-report/)

在来自[的关于公共云中容器原生存储性能的架构 IT](https://www.architecting.it/) 的新报告中，克里斯·埃文斯仔细研究了流行的超大规模选择之一亚马逊网络服务(AWS)上的不同存储选项，以及不同[存储](https://thenewstack.io/choosing-between-container-native-and-container-ready-storage/)选项的性能。

提出的问题是:当我们开始将新的以数据为中心的工作负载视为 Kubernetes 本机解决方案时，使用哪种存储最有意义，我们如何选择最具成本效益的解决方案？例如，使用 RDS 之类的服务运行许多托管数据库——虽然简单方便，但如果您使用数十或数百个这样的实例，成本可能会增加。

借助 EnterpriseDB 及其云原生 Postgres (CNPG)运营商等公司的新产品，您能否将这些基于虚拟机的服务整合到 Kubernetes 集群中，以优化您的云支出？比如，建筑；你可以看到一些会谈，比如最近在 KubeCon 关于 CNPG 在 EKS 使用基于 NVMe 的存储和 Ondat CNS [的会谈。](https://sched.co/182GB)

我们还希望了解如何针对需要极高级别的[弹性](https://thenewstack.io/the-rise-of-continuous-resilience/)(区域复制)和性能的工作负载(如较新的人工智能或机器学习工作负载)，优化您的云存储支出成本。

大多数希望在 Kubernetes 中运行应用程序的应用程序团队都希望为他们的应用程序命名一个存储类，以便在他们的 Kubernetes 集群中使用。集群运营团队需要确保该存储类通过容器存储接口(CSI)插件提供动态存储，并确保他们了解该解决方案提供的非功能性。这创建了一个真正干净且定义良好的接口，通过使用多个存储类，可以公开不同的功能。

在报告中，您将看到 AWS 本地存储类以及容器本地存储(CNS)类。解释了每种方法的功能。

例如，CSI 是否提供有弹性的存储，弹性的边界在哪里？例如，EBS 存储提供了令人难以置信的恢复能力，但不跨越可用性区域(AZ)。当然，这开启了一些非常有趣的模式，您可以将不同的存储技术(如 EBS 存储和 Ondat CSI 插件)结合起来，从 EBS 提供可用性区域弹性，并使用 Ondat 提供区域级复制和弹性。

根据 Architecting IT 最近的另一份报告，该公司对 Kubernetes 最受欢迎的存储解决方案进行了一次 [CNS 基准测试](https://www.ondat.io/benchmarking)，这一组合似乎是一个不错的选择，因为 [Ondat 被公认为当今最快的 CNS](https://portal.ondat.io/signup)。

跳转到报告的概述，大部分分析是使用行业标准 [FIO](https://fio.readthedocs.io/en/latest/index.html) 工具模拟 I/O 工作负载规模的两端完成的。在 IOPS 测试案例中，具有 100%随机工作负载的小块用于模拟人工智能/机器学习工作负载或 PostgreSQL/MySQL 数据库等。

延迟测试使用具有较小队列深度的相同随机工作负载，以确保我们获得存储的真实延迟，最后是吞吐量测试，模拟流数据工作负载，使用较小队列深度但非常大的数据块大小对数据进行顺序访问。使用测试结果，并将其与后端数据存储的功能(如弹性和耐用性)相结合，平台架构师应该能够为每个应用程序需求创建一个存储类。

总结报告:使用 AWS 中的原始构建模块和 I3en 等机器类型以及本地 NVMe 驱动器，可以使用 [Ondat](http://ondat.io) 等 CNS 解决方案创建速度更快、延迟更低且具有可用性区域弹性的解决方案，以提供具有区域级弹性的低成本 IOPS 解决方案。EBS 和 EFS 提供了令人难以置信的弹性和非常经济高效的存储解决方案，可衡量每千兆字节的成本，EBS 还可以与 Ondat 等 CNS 解决方案互补，以提供可用性区域故障切换，从而为生产工作负载提供区域弹性。

同样值得注意的是，该报告强调了[性能考虑因素](https://thenewstack.io/why-zoned-storage-and-why-now/)的多维度，超出了我们最初只关注 FIO 存储数量的范围。当我们开始对 NVMe 驱动器使用可用性区域间复制时，写入速度非常快(例如，请注意奇怪的周期性 48 秒性能下降，这看起来像是服务质量或节流问题)，这表明我们还应该考虑和测试可用性区域之间的网络延迟。

使用 iperf 之类的工具重复测试并测量实例的实际网络性能(i3en.xlarge 声称“高达 25Gbps”)并观察内部(噪声邻居效应)和可用性区域间网络流量如何影响性能，这将是非常有趣的。

我建议所有拥有 AWS 托管的 Kubernetes 集群的集群架构师阅读[完整报告](https://www.ondat.io/reports/benchmarking-aws)，因为它有助于以量化的方式解释底层存储的能力。通过阅读该报告，负责在这些 Kubernetes 集群中运行的应用程序的应用程序开发人员应该能够了解并更好地决定要使用的正确存储。

如果你想试试 Ondat，有一个全功能的社区版(高达 1tb 的存储)，你可以在今天免费使用[。](https://portal.ondat.io/signup)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>