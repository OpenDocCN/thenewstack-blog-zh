# 红帽开放专用于谷歌云平台的 OpenShift

> 原文：<https://thenewstack.io/red-hat-opens-openshift-dedicated-google-cloud-platform/>

当商业和企业开始采用利用容器化的数据中心平台时，那时也只有那时，我们才能最终说容器趋势正在席卷全球。Red Hat 针对容器化平台的首发选项是 open shift Dedicated——这是一个基于公共云的预配置解决方案，去年这个时候在亚马逊 AWS 上推出。

周四上午，该公司宣布谷歌云平台正式上市，作为部署 OpenShift Dedicated 的替代选择。这一举动意味着[红帽在今年结束之前，信守了它在年初](http://venturebeat.com/2016/01/21/red-hats-openshift-dedicated-container-platform-is-coming-to-the-google-cloud/)许下的承诺。

“我们与现在运行在 AWS 和谷歌上的 OpenShift 的区别在于，我们给了客户一个选择。”红帽在线 OpenShift 主管 [Sathish Balakrishnan](https://www.linkedin.com/in/saascloud) 在接受新的 Stack 采访时说

但是选择是顾客真正想要的吗？更具体地说，由于 PaaS 平台的这一特定版本被定位为交钥匙选项——几乎是显而易见的——谷歌或亚马逊的选择对忠诚的客户意味着什么？他们不希望 Red Hat 或其他人向他们解释除了每月都不同的成本因素之外的差异吗？

Balakrishnan 回答说:“我们推出这一产品的原因之一是，在很大程度上，客户已经选择了他们的云平台应该是什么样的。

## 现有选择的新可能性

与产品线中的其他选项不同，OpenShift Dedicated 与 Red Hat 的 IT 资产管理捆绑在一起，不受云提供商的监管。Balakrishnan 解释说，虽然该公司的[认证云和服务提供商计划](https://www.redhat.com/en/about/press-releases/red-hat-launches-expansive-global-cloud-ecosystem-certified-cloud-and-service-provider-program)开放了 OpenShift Enterprise 以部署在多个云平台上，但 OpenShift Dedicated 将平台列表缩小到客户最倾向于选择的平台，“完全知道客户已经对他们想要的云提供商做出了固有的选择，”他解释说。然后，Red Hat 可以将其注意力集中在管理更窄列表中的工作负载上。

换句话说，专门用于谷歌云平台的 OpenShift 支持已经做出的选择。

这听起来像是一种追溯性的修正，但是当你从客户的角度来看事情的发展时，这就更有意义了。今年年初， [RightScale 的云状态调查](http://www.mcit.gov.eg/Upcont/Documents/Reports%20and%20Documents_1252016000_RightScale-2016-State-of-the-Cloud-Report.pdf) [PDF]表明——其他公司的后续调查也证实了这一点——典型的企业同时在几个公共平台上运行工作负载。在 RightScale 的调查中，这个数字平均为 6，而距离 2017 年的调查只有几个月了，两位数也不是不可想象的。

从客户组织的角度来看，“云”由所有这些平台组合而成。即使是小组织也在尝试，至少是多元化。但是，每个组织部署在公共云中的应用程序不容易在单个提供商之间细分和委托，例如，一些特定的应用程序在亚马逊上，其他的在 GCP 上，其他的在 Azure 上，等等。

对于那些已经实施或刚刚开始实施容器化的组织来说，在细分的云平台中编排这些工作负载没有太大意义。

因此，OpenShift 专用于三大公共云平台中的一个以上平台的可用性只是扩展了工作负载的部署选项。OpenShift 选择的 orchestrator 是 [Kubernetes](/category/kubernetes/) 容器编排引擎，Balakrishnan 告诉我们，Red Hat 正准备很快将 OpenShift 从 Kubernetes 版本 1.3 迁移到 1.4。这是 Kubernetes 1.5 的正式发布，时间是周四。

## “不再需要考虑数据中心”

仅从轶事证据来看，Balakrishnan 认为，主要零售商正在向谷歌云平台倾斜的观察是有道理的，家得宝已于去年 3 月签署，梅西百货已在此之前签署。当时，谷歌称赞了这些零售商的选择，理由符合红帽为 OpenShift Dedicated 绘制的轮廓。

“对于我们的客户来说，云意味着不再需要考虑数据中心、服务器、存储和网络，”GCP 负责产品管理的副总裁 Brian Stevens 在去年 3 月的公司博客中写道。“相反，他们能够专注于为客户创造令人惊叹的应用程序、产品和服务。”

这也表明大企业——不仅仅是中小企业——正在选择外包他们的 IT 管理。他们选择 GCP 部署工作负载是否与性能问题有关？Balakrishnan 回答道:“并不是说红帽能够测量。”。

那么，除了对主要零售商的观察之外，OpenShift Dedicated 和 OpenShift Enterprise 的客户组合之间是否还有其他差异，这可以解释 Balakrishnan 所说的客户已经做出的选择背后的基本原理？

“我们看不出申请类别有很大区别，”他回答道。“这不仅仅是消费模式，而是客户真正希望通过他们的容器平台实现的目标。我们有很多工作负载—任务关键型工作负载、电子商务交易。我们有卫星追踪系统。我们在地图上到处都是。因此，我认为任何可以帮助人们实现容器化的东西——无论是已经存在的棕色地带应用程序，还是他们想要开发一个新的绿色地带应用程序——open shift 适合所有这些类型的应用程序。我们不会真的说我们只是一个云原生平台；我们可以做到这两点。”

如果所有这些都有一个潜在的信息，那就是供应商正在继续构建他们的服务平台，预计他们的市场将进入某种模式——这种模式显然还没有开始。

红帽是新堆栈的赞助商。

标题图片由红帽公司提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>