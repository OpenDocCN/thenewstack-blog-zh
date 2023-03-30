# Kubernetes 如何帮助减少云的碳足迹

> 原文：<https://thenewstack.io/how-kubernetes-can-help-reduce-the-clouds-carbon-footprint/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待于 8 月 13 日至 16 日在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

在过去的几年里，Kubernetes 的采用已经占据了企业愿望清单的首位。大多数公司采用 Kubernetes 是为了寻求生产率提高、便携性、资源效率和规模。这些好处在 Kubernetes 网站上的多个[案例研究](https://kubernetes.io/case-studies/)中有详细记录。

我更感兴趣的是看到 Kubernetes 在企业技术堆栈中的引入如何潜在地影响与其云和私有基础设施相关的碳排放。

## 数据中心和碳排放

2020 年，数据中心预计将消耗约 3%的全球电力输出，导致 1 亿吨二氧化碳排放。然而，并不是所有的数据中心都有同样的责任。

例如，相对于私有数据中心来说，云在二氧化碳排放方面无疑是一个进步。以 Jeff Bar 的文章为例，该文章指出，当公司在亚马逊网络服务(AWS)上运行其工作负载，而不是在自己的数据中心运行时，碳排放量减少了 88%。

该文章中引用的原因是更高的服务器利用率、更低的能源使用效率(PUE)以及云数据中心中更节能的组合。尽管观点不同:云资源供应的便利性有时会导致消费增加和相应的更大的碳足迹。

## Kubernetes 能在云上改进吗？

然而，更重要的是，Kubernetes 能在碳排放方面改善云吗？如果是这样，又是如何做到的？为了弄清楚这一点，让我们更深入地了解公共云环境和内部数据中心的碳排放机制。

内部和云数据中心环境中的碳排放是四个变量的函数:电力使用效率(PUE)、服务器利用率、它们所连接的电网的碳排放强度以及整体功耗。让我们仔细看看这些变量。

## 服务器利用率

云提供商的服务器利用率数据很难获得，并且可能因每个客户而有很大差异。例如，[这份](https://www.nrdc.org/sites/default/files/NRDC_WSP_Cloud_Computing_White_Paper.pdf)报告指出云数据中心的最佳实践利用率为 70%,最差情况利用率为 7%。然而，云环境在本地数据中心上有明显的优势，其利用率通常在 5%到 25%之间。

云中各个客户环境的服务器利用率差异甚至更大。以 Nordstrom 为例，它在 AWS 上运行 1000 个虚拟机，平均 CPU 利用率为 [4%](https://kubernetes.io/case-studies/nordstrom/) 。

## 用电效率

[用电效率](https://en.wikipedia.org/wiki/Power_usage_effectiveness)衡量数据中心消耗的总电量与实际服务器基础设施消耗的总电量之比。PUE 指出了数据中心在降低非服务器基础设施功耗方面的效率。

据 NDRC 称，与私有数据中心相比，公共云提供商的 PUE 比率要低得多(最高为 1.1)。这实质上意味着云数据中心在运行相同规模的基础设施时消耗的电力比内部数据中心少。

## 碳排放强度

碳排放强度是指发电 1 千瓦时所排放的碳量。由于大多数数据中心接入当地电网，排放强度通常由发电所用的燃料组合决定。然而，这一规则也有例外，例如当云提供商和一些数据中心从专门为此目的设置的可再生能源系统获取电力时。

既然我们已经掌握了数据中心内部碳排放的驱动因素，那么让我们来看看 Kubernetes 的引入如何影响这些变量，进而影响碳排放。

## Kubernetes 有什么帮助？

 [帕特里克·基尔霍夫

Patrick 是 Replex 的联合创始人兼首席执行官，这是第一个专门为云原生和 Kubernetes 基础架构构建的治理和成本管理平台。Patrick 拥有业经验证的执行管理记录，并在 IT 运营部门拥有超过 20 年的经验。在加入 Replex 之前，Patrick 创建了 Conversis，这是一家 IT 运营公司，为 IT 领导者提供管理复杂应用程序和在线门户的高级解决方案。此外，Patrick 还是 YTILI(跨大西洋青年领袖计划)的成员，YTILI 是美国国务院与美国德国马歇尔基金会合作开展的一个项目。](https://www.linkedin.com/in/patrickkirchhoff/) 

将 Kubernetes 引入云环境对上一节中强调的三个变量中的两个有影响:服务器利用率和排放强度。我们将在下面的段落中研究这两个问题。

美国国家资源保护委员会(National Resources Defense Council)强调服务器利用率是决定服务器基础设施效率和碳足迹的最重要因素。更高的利用率意味着更少的资源浪费、更少的机器、更少的基础架构占用空间以及运行基础架构所需的更少的电力。这反过来又会减少与运营基础设施相关的碳排放。

Kubernetes 显著提高了基础设施的利用率。事实上，这是企业期待[采用 Kubernetes](https://www.replex.io/blog/announcing-state-of-kubernetes-report-replex) 的最大原因之一。

让我们使用来自 [Nordstrom](https://kubernetes.io/case-studies/nordstrom/) 的 Kubernetes 案例研究来量化这些改进。这家公司在 Amazon Web Services 上运行数千个虚拟机，平均 CPU 利用率为 4%。在 Kubernetes 之后，这些服务器的平均利用率跃升至 40%。

高利用率意味着 Nordstrom 只需要 Kubernetes 之前 1/10 的虚拟机就可以运行相同的工作负载，并允许他们缩减基础架构。这对于 Nordstrom 本身的碳足迹来说是一个奇迹，它现在可以报告与使用 AWS 虚拟机相关的碳排放减少了 90%。

Kubernetes 可能影响的另一个与碳排放相关的变量是排放强度。由于 Kubernetes 固有的可移植性，它允许对工作负载放置的决策进行更大的控制。

如前所述，排放强度因云提供商地区而异，因为它们通常接入当地电网。ITDMs 可以使用[开放排放 API](https://www.electricitymap.org/?page=map&solar=false&remote=true&wind=false)根据区域的排放强度对其进行评估，并做出工作负载放置决策。

在这种背景下,[低碳 Kubernetes scheduler](https://hub.packtpub.com/low-carbon-kubernetes-scheduler-a-demand-side-management-solution-that-consumes-electricity-in-low-grid-carbon-intensity-areas/) 项目是一个有趣的项目，它根据各地区的排放强度做出规模决策。这种方法有明显的好处，例如将工作负载扩展到被指定为碳中和的云提供商区域，或者选择排放强度较低的区域，例如[加利福尼亚州](https://www.electricitymap.org/?page=map&solar=false&remote=true&wind=false)(221 克)，而不是排放强度较高的区域，例如俄亥俄州(387 克)。

## 结论

预计 2020 年数据中心将消耗全球电力输出的 3%,导致 1 亿吨二氧化碳排放。由超大规模 IaaS 提供商运营的云数据中心在排放方面的得分要低得多。

然而，当然还有很大的改进空间。

在这篇博文中，我们回顾了 Kubernetes 对云和本地数据中心碳排放相关的两个最重要变量的影响:服务器利用率和排放强度。Kubernetes 显著提高了服务器利用率，从而减少了基础设施占用空间，并相应减少了碳排放。可移植性和对工作负载放置的更大控制也允许 ITDMs 根据排放强度和碳足迹挑选区域。

*要了解更多关于集装箱化基础设施和云原生技术的信息，请考虑参加 8 月 13 日至 16 日在阿姆斯特丹举办的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。*

亚马逊网络服务(AWS)和管理 KubeCon + CloudNativeCon 的云原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>