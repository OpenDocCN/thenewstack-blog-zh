# Cloud Foundry 的第二招:为 Kubernetes 带来成熟的开发者体验

> 原文：<https://thenewstack.io/cloud-foundry-second-act-bring-a-proven-developer-experience-to-kubernetes/>

[云代工厂](https://www.cloudfoundry.org/)赞助本帖。

 [贾里德·拉克尔

Jared 在 VMware 从事产品营销工作，自 2012 年以来一直参与云铸造社区。他在产品管理和产品营销方面拥有超过 20 年的经验。](https://www.linkedin.com/in/jaredruckle/) 

要想找到未来的线索，就去看看过去。[本文](https://siliconangle.com/2011/04/12/vmware-pioneers-open-paas-with-cloud-foundry-launch./)总结了 2011 年云代工厂的目标:

*…Cloud Foundry 旨在简化现代应用的开发、交付和运营，并召集开发者运行和扩展他们的应用。这一概念还将包括公共云和私有云以及行业制定的标准和框架。*

正如上面所写的那样，这个项目的价值已经在一个有意义的范围内完全发挥出来了。根据 [Cloud Foundry 用户调查 2019](https://www.cloudfoundry.org/cloud-foundry-user-survey-2019/) ，该项目“被超过一半的财富 500 强和三分之一的全球 2000 强使用。”

开源项目只有在高度务实的情况下才能达到这些采用和寿命的里程碑。当我想到 Cloud Foundry 社区时，“实用主义”是我脑海中闪现的词。想用 Docker？当然，你可以把它推到平台上。需要跑步。网络应用？让我们为这个框架添加一个构建包。有比当前实现更好的开源技术吗？进行交换而不中断更改。

本着这种务实的心态，Cloud Foundry Foundation 已经完全接受 Kubernetes 作为运行和扩展分布式系统的首选项目。这使得 Cloud Foundry 社区可以专注于真正酷的东西——比如为 Kubernetes 带来成熟的开发者体验。

这是一个有益的背景，因为我们期待着 6 月 24 日至 25 日举行的虚拟活动 Cloud Foundry Summit。([在这里注册](https://www.cloudfoundry.org/events/summit/na-virtual-2020/)，只要 50 美金！)

对于今年的峰会预览，让我们展示详细介绍社区在提供基于 Kubernetes 的 cf 推送体验方面的进展的会议。以下是我最喜欢的一些，排名不分先后。

### K8s 的云代工厂–同样出色的 PaaS。全新的基础

[**安德鲁·威特罗克，VMware &埃里克·普罗姆洛，苏斯**](https://cfna2020.sched.com/event/cHhp/cloud-foundry-for-k8s-same-great-paas-brand-new-foundation-andrew-wittrock-vmware-eric-promislow-suse?iframe=yes&w=100%&sidebar=yes&bg=no)

[阅读会议摘要](https://sched.co/cHhp)

这里是开始的明显地方。面向 Kubernetes 的 Cloud Foundry([cf-for-k8s](https://www.cloudfoundry.org/blog/cloud-foundry-becomes-more-kubernetes-native-with-cf-for-k8s/))是基于 Kubernetes 的 Cloud Foundry 开发者体验的完全原生实现。Wittrock 和 Promislow 向您概述了该项目，并详细介绍了其社区支持。

### 面板:Cloud Foundry——Kubernetes 上菜厨房

**Bernd Krannich，SAP SEDieu Cao，VMware 杰夫·霍布斯，苏斯；西蒙·莫泽，IBM 由工程师出身的丹尼尔·琼斯主持**

[阅读会议摘要](https://sched.co/cHh9)

刚刚风闻 Cloud Foundry 要补充 Kubernetes？这些小组成员概述了最重要的项目，它们所处的位置，以及它们对 Cloud Foundry 用户的意义。想要额外的上下文吗？从去年九月开始观看这一期。

### CRD-为 Kubernetes 制造云

[**安吉拉·钦&康纳·布拉，VMware**](https://cfna2020.sched.com/event/cHhm/crd-ifying-cloud-foundry-for-kubernetes-angela-chin-connor-braa-vmware?iframe=yes&w=100%&sidebar=yes&bg=no)

[阅读会议摘要](https://sched.co/cHhm)

为什么 Kubernetes 的可扩展性这么强？自定义资源定义(CRD)。Chin 和 Braa 讨论了为什么 CRDs 是前面提到的 cf-for-k8s 项目的核心组成部分。如果您想更深入地了解使云铸造 Kubernetes-native 的努力，不要错过这个会议！

### 面向 Kubernetes 云铸造的数据服务自动化

**朱利安·菲舍尔，anynines 有限公司**

[阅读会议摘要](https://sched.co/cHhL)

每个现代应用都需要现代数据服务。观看本专题讲座，了解您在 Cloud Foundry 和 Kubernetes 上对支持服务进行生命周期管理的选择。Fischer 解释了如何理解操作符、舵图、Kubernetes CRDs 和开放服务代理 API。

### 一点关于 Cloud Foundry，一个字节关于 Eirini

[**Julz Skupnjak，IBM & Georgi Dankov，SAP**](https://cfna2020.sched.com/event/cHhg/a-bit-about-cloud-foundry-a-byte-about-eirini-julz-skupnjak-ibm-georgi-dankov-sap?iframe=yes&w=100%&sidebar=yes&bg=no)

[阅读会议摘要](https://sched.co/cHhg)

[Eirini](https://www.cloudfoundry.org/project-eirini/) 是为了让 Cloud Foundry 更贴近 Kubernetes 而推出的首批计划之一。它的目标是:将 Kubernetes 作为一个容器调度程序引入 Cloud Foundry 应用程序运行时。Skupnjak 和 Dankov 给你一个关于这个项目的速成课程，以及它是如何在 [KubeCF](https://www.cloudfoundry.org/kubecf/) 和 [CF-for-K8s](https://github.com/cloudfoundry/cf-for-k8s) 中使用的。

### 与 KubeCF 一起深潜

图利奥·费拉兹·阿西斯，苏斯&恩里克·恩卡拉达，IBM

[阅读会议摘要](https://sched.co/cHhU)

KubeCF 是将 BOSH 版本整合到 Kubernetes 本地 PaaS 的早期尝试。Assis 和 Encalada 分享了他们从这个项目中学到的东西，并解释了如何在当地环境中试用 KubeCF。

### 将“cf 地图路线”的简单性带到 Kubernetes

[**蒂姆·唐尼&尼蒂亚·达努什科迪，VMware**](https://cfna2020.sched.com/event/cHhd/bringing-the-simplicity-of-cf-map-route-to-kubernetes-tim-downey-nitya-dhanushkodi-vmware?iframe=yes&w=100%&sidebar=yes&bg=no)

[阅读会议摘要](https://sched.co/cHhd)

我们喜欢说，我们把 cf push 的魔力带到了 Kubernetes。这是真的，这是一个很好的方法来总结大的想法。当然，这样做的实际工作要复杂得多。

在这里，Downey 和 Dhanushkodi 详细介绍了为 Kubernetes 的 CF 中的新网络层所做的深思熟虑的工程。一个额外的奖励:演示团队如何将 Istio 融入到项目中！

### Paketo 构建包，从源代码到应用程序映像

[**丹尼尔·桑顿**](https://cfna2020.sched.com/event/cHha/paketo-buildpacks-from-source-code-to-application-images-daniel-thornton-vmware?iframe=yes&w=100%&sidebar=yes&bg=no)

[阅读会议摘要](https://sched.co/cHha)

Buildpacks 是 Cloud Foundry 社区逐渐了解并喜爱的技术之一。原因显而易见:一种从源代码构建容器的可重复、自动化的方法使开发人员更有生产力，提高了操作效率，并增强了合规性和安全性。

许多人问“buildpacks 怎么样，但是对于 Kubernetes 呢？”那就是 [Paketo Buildpacks](https://paketo.io/) 。桑顿解释了团队如何为 Kubernetes 的世界重制 buildpacks 概念。

## 四次奖金会谈

云铸造峰会不仅仅是关于工程。下面是你不想错过的另外三个演讲。

### 多元化午餐会:我们是如何走到今天的？种族不平等的制度

**世界信托教育服务社 Shakti Butler 博士**

[阅读更多](https://www.cloudfoundry.org/blog/why-the-cloud-foundry-summit-diversity-luncheon-is-for-you/)

过去，多样性午餐会一直是云铸造峰会的标志，现在这个话题比以往任何时候都更加重要。因此，请与 Shakti Butler 博士一起参加峰会的首次虚拟多元化午餐会，Shakti Butler 博士是社会和种族平等领域的电影制作人和有远见的教育家。

### 你的开发者体验是 COVID 免疫的吗？

**Dormain Drewitz，VMware**

[阅读会议摘要](https://sched.co/cHhs)

在新冠肺炎的推动下，数年的数字化转型在几个月内就发生了。Cloud Foundry 用户是对不断变化的市场环境反应最快的用户之一。Domain 研究了几个案例研究，并提出了一些可行的想法，您可以将这些想法带回您的组织。

### 实现平稳航行的微服务(MSA)布线层实用指南

**康卡斯特公司的迪勒斯瓦拉·阿努波朱**

[阅读会议摘要](https://sched.co/cHhC)

您的应用比以往任何时候都多，并且它们运行在 Cloud Foundry、Kubernetes、VMs 和裸机上。如何将它们连接起来，尤其是当它们运行在云之间时？Comcast 公司的人已经解决了这个用例，并成功地应用了 API 网关、边缘代理和其他模式来改善结果。Anupoju 回顾了您必须考虑的常见挑战和设计因素。

### 为什么换位思考在基础设施技术中很重要

**VMware 的 Craig McLuckie**

[阅读会议摘要](https://sched.co/cHhI)

各地的运营团队都在加大对 Kubernetes 的投入。当他们争论系统的能力(和复杂性)时，他们不能忽视更大的图景:开发人员支持。

McLuckie 讨论了换位思考，以及它如何影响 VMware 的市场策略，为峰会定下了基调。

## 立即注册并加入 6 月 24 日和 25 日的对话

[注册参加 CF 峰会](https://www.cloudfoundry.org/events/summit/na-virtual-2020/)——和往常一样，它有望成为本年度顶级开源活动之一。

为了吊起你的胃口，听听云计算基金会的执行董事 Chip Childers 在谷歌的 Kubernetes 播客上的发言。Childers 和主持人就基金会与 Kubernetes 的合作进行了精彩的讨论。(采访从剩余 39:15 分钟开始，剩余 30:09 分开始讨论 Cloud Foundry)。

网上见！

SAP 和 VMware 是新体系的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>