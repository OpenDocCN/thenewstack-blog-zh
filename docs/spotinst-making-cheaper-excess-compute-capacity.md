# Spotinst:充分利用廉价的过剩计算能力

> 原文：<https://thenewstack.io/spotinst-making-cheaper-excess-compute-capacity/>

离开以色列国防军的 MAMRAM 基础设施部门后，Amiram Shachar 去了一家 AWS 成本越来越高的公司工作。他还在攻读工程学位，需要完成一个高级项目。

为了省钱，他开始研究 [AWS Spot Instances](https://aws.amazon.com/ec2/spot/) ，AWS 以大幅折扣出售多余的计算能力——它认为节省的费用比按需价格低 90%。问题是:如果 AWS 需要恢复容量，只需提前两分钟通知就可以终止这些实例。

他的顾问非常喜欢将机器学习应用于该问题的想法，因此他与 Shachar 一起参与了该项目。他说，在大约三个月的时间里，他们编写了一个算法来预测这些中断何时会发生，他的雇主完全能够以非常低的误报率发现这些情况。

一个名为 [Spotinst](https://spotinst.com/) 的新公司诞生了，与同为 IDF 老兵的 [Ahron Twizer](https://twitter.com/aharontwizer) 、 [Liran Polak](https://github.com/liranp) 和 [Yakir Daniel](https://twitter.com/yakir_daniel) 。

三年后，该公司拥有 500 多家客户，包括 Ticketmaster、索尼、英特尔和威瑞森。它已经筹集了 1760 万美元，最近一轮是由英特尔投资公司牵头的 1500 万美元的首轮融资。

德勤最近将 Spotinst 评为以色列发展最快的初创公司。

## 自动化资源

该公司的核心产品 Elastigroup 使用算法预测现货行为，并预测中断风险。它在最具成本效益的计算资源上运行应用程序，利用其预测消除停机风险。当价格最优的 Spot 实例可用时，它会使用它们，当价格不可用时，它会根据需要选择，同时优先考虑您可能已经拥有的任何保留实例。它会尽快自动恢复到定点实例。

该公司还提供[负载平衡](https://spotinst.com/products/multai-load-balancer/)和多云[监控](https://spotinst.com/products/spectrum/)解决方案。最近，它已经跳进了“功能即服务”的游戏。在一篇关于新堆栈的[帖子](https://thenewstack.io/funtainers-beauty-running-containers-functions/)中，Shachar 称这种方法为“娱乐容器”它最初是为 AWS 创建的，也可以在微软 Azure 和谷歌云上运行。作为其功能驱动的一部分，它还与阿里巴巴、IBM 和 Equinix 建立了合作伙伴关系

Shachar 说，客户通过三种方式从 it 部门购买云计算资源:

1.  实例，虚拟机的一个单元
2.  容器
3.  函数，每个人都称之为无服务器。

[SpotInst 的功能](https://spotinst.com/products/spotinst-functions/)处于测试阶段。

Shochar 说:“在为开发简化服务器管理的过程中，我们看到了一个很好的机会，我们可以进入我们已经提供实例和容器的领域。

他指出:你可以把优步视为全球最大的出租车供应商，但它没有出租车。Airbnb 提供房产，但不拥有房产。脸书提供内容，但不生产内容。

“我们将成为不拥有服务器的最大虚拟云提供商。我们将使用亚马逊数据中心，”他说，称这是公司的下一步。

在[无服务器领域](https://thenewstack.io/aws-lambda-still-towers-competition-much-longer/)，AWS Lambda 拥有巨大的领先优势，新堆栈的 Lawrence Hecht 最近报道，但竞争对手正在排队。算上 IBM 和 Adobe 推动的开源项目 Apache open whisk，以及其中的 [OpenFaaS](https://github.com/openfaas/faas) 。

## 满足需求

Elastigroup 融合了按需、预留和定点实例，以创建一个始终可用的集群。它将提供服务器，以找到最经济的平衡，但主要取决于现场实例。

与 AWS 上的自动扩展组类似，Elastigroup 使您能够维护承受服务器故障或预测的现场实例替换所需的最少数量的服务器。服务器的数量可能会随着需求的增加而增加，当不需要节省资金时又会减少。

它会根据您定义的最小和最大所需服务器数量的策略，自动增加或减少服务器数量。如果服务器不正常或可能中断，它会自动替换它，以保持最小数量的服务器。

在缩小规模时，它使用一组[因素](http://blog.spotinst.com/2015/10/08/top-10-features-of-elastigroup/)，如最高风险、哪些实例最接近下一个计费时间以及实例的年龄，来确定哪些实例应首先终止。

结合当前现货市场数据和历史数据的算法预测现货市场波动何时发生。如果即时实例价格过高，它会自动提供按需实例，以确保您支付的费用不会超过按需服务器的价格。

它集成了应用程序和服务，包括 Kubernetes、Terraform、Jenkins、Code Deploy、OpsWorks 等。

该公司在旧金山、伦敦和特拉维夫设有办事处。它面临着来自总部位于帕洛阿尔托的 Cmpute.io 的竞争，思科刚刚[收购了 cmpute . io，](https://www.theregister.co.uk/2017/12/08/cisco_acquires_cmpute_io/)，但主要来自 AWS 本身，后者提供 [Spot Fleet](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet.html) ，一种自动化管理服务。

## 生产工作负载

在[白皮书](https://spotinst.com/white-papers/the-state-of-the-amazon-ec2-spot-market/)中，亚马逊声称 Spot 实例不再仅仅用于批处理。它说，客户在生产中使用它们，在应用层使用负载均衡器；Redis、Memcached 等缓存集群；亚马逊 ECS、Kubernetes 等容器平台；NoSQL 集群；CI/CD 管道和大数据工作负载，如 Hadoop 和 Spark。

它报告说，与按需实例相比，Linux 服务器平均节省了 78.4%，Windows 服务器平均节省了 57.3%。

“今天的现货市场已经支持多种用例，如大数据高级金融建模、软件负载测试和 DNA 序列分析。该公司表示:“这个市场创造的效率将继续为各行各业带来巨大的新机遇。”。

在一篇关于新堆栈的客座博文中，Shachar 最近概述了最近在亚马逊 re:Invent 2017 用户大会上宣布的对 Spot Instances 的新功能和变化。它们包括不太频繁的价格变化，使 Spot 实例的投标成为可选的，以及一个名为 Hibernate 的新功能，用于不需要高可用性的工作负载。实际上，当一个实例被终止时，您的数据会被保存，然后在备用容量再次可用时重新启动。

专题图片:2017 年纽约 Serverlessconf 上的 Spotinst 工作人员。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>