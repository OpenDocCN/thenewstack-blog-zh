# 未来就在眼前:企业中的混合、边缘和多云运营是战略性的，也是真实的

> 原文：<https://thenewstack.io/future-hybrid-edge-multicloud-operations-enterprise-strategic-real/>

[](http://www.portworx.com)

 [苟饶，Portworx

苟饶，Portworx 联合创始人兼首席技术官，曾任戴尔数据保护部门和思杰系统 ASG 公司首席技术官；Ocarina Networks 和 Net6 的联合创始人兼首席技术官；也是英特尔和洛克希德·马丁公司的主要架构师。他拥有计算机科学学士(班加罗尔大学)和硕士(宾夕法尼亚大学)学位。](http://www.portworx.com) [](http://www.portworx.com)

今天 [Mesosphere](https://mesosphere.com/) [发布了 DC/OS 1.11](https://mesosphere.com/blog/dcos-1_11-overview/) ，这是世界上一些最大、最复杂的组织使用的旗舰软件的最新版本。该版本侧重于三个主题:无缝混合、边缘和多云操作、生产就绪的 Kubernetes 以及任务关键型状态应用程序的改进安全性。

所有这些主题都与我的心息息相关，因为我们正在与自己的客户一起解决这些需求。这些客户中有许多也是中间层 DC/OS 用户，如无人驾驶汽车公司 NIO[和革新商业房地产的创新物联网提供商 Beco](https://thenewstack.io/3-devops-insights-nio-maker-self-driving-cars-kubernetes-power-user) 。但是我们从几乎所有的 Portworx 客户那里听到了对 Kubernetes 管理的安全、混合和多云操作的需求。这就是为什么我认为中间层的最新版本如此重要。混合、边缘和多云运营不仅仅是企业的理想之选，它们还是战略性的。最近的一次经历让我明白了这一点。

来自 Portworx 的代表最近参加了由世界领先的风险投资公司之一[梅菲尔德基金](https://www.mayfield.com/)组织的美国联邦政府和政府相关机构首席信息官峰会。财政部、国土安全部、中央情报局、国际货币基金组织、布鲁金斯学会、InQTel 和其他机构出席了会议，我们就人工智能和机器学习、如何在政府和私营部门建立创新文化以及大规模云计算带来的可能性进行了广泛的讨论。在最后一个话题上，人们并不一致认为云是政府最想要的最终状态，但一些与会的首席信息官，特别是来自情报机构的首席信息官，从成本、运营效率和敏捷性的角度令人信服地论证了云的优势。

随着大多数政府首席信息官支持向云迁移变得越来越明显，一股谨慎的暗流出现了。政府机构非常担心被局限于一家云提供商。当你谈论数十亿美元的 IT 预算和数十亿字节的数据时，这些都不是理论上的问题。

当我们问观众谁在调查他们组织中的集装箱时，90%的人举手了。当被问及为什么答案是一致的:更高的敏捷性和[应用程序可移植性](https://portworx.com/application-portability-kubernetes/)。应用程序的可移植性是 Mesosphere 最新版本如此重要的原因之一。

只有当你能够在多种环境下可靠地运行一个应用程序时，你才能真正拥有服务提供商的优势。这就是我之前提出的观点，混合云和多云操作不仅仅是企业想要的，它们是战略性的。能够突发到云以访问额外的计算是可取的。能够在数据中心之间故障转移应用程序是可取的。但是，获取工作负载并在不同环境之间转移的能力也具有战略意义，因为它限制了组织面临的来自云提供商的锁定。如果云提供商参与竞争，组织将获得更好的支持、更优惠的价格，并最终获得更好的体验。

我们很自豪成为一个中间层合作伙伴，让有状态服务的混合、边缘和多云操作成为数十家企业的现实，不仅是明天，而是今天。借助运行马拉松或 Kubernetes 的 Mesosphere DC/OS，客户可以在不同环境之间实现应用程序的真正可移植性。例如，对于中间层和 Portworx:

*   像 Cassandra、Kafka、ElasticSearch、HDFS 等有状态的应用程序可以跨容错域部署，确保如果服务器、机架、数据中心甚至区域停机，应用程序可以继续运行或重新安排到另一台主机，并提供最新的数据副本。
*   大数据、快速数据和 TensorFlow 等机器学习工作负载可以使用 [Portworx CloudSnap 功能](https://docs.portworx.com/cloud/backups.html)突发到云，该功能可以在环境之间移动数据，以便 DC/操作系统可以按需调度计算作业。
*   DC/操作系统 Kubernetes 即服务用户可以利用 Portworx 的[计算与数据的强制超融合](https://docs.portworx.com/scheduler/kubernetes/stork.html)来确保他们的任务关键型、性能敏感型数据服务始终以快速本地存储运行，即使由于服务器或网络故障而被重新安排。

我对最新的 DC/操作系统版本感到兴奋，并帮助客户实现混合和多云计算。你呢？

[波特沃斯](https://portworx.com/)赞助了这个故事。中间层是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>