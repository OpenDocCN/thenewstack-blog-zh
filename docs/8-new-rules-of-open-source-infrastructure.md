# 开源基础设施的 8 条新规则

> 原文：<https://thenewstack.io/8-new-rules-of-open-source-infrastructure/>

随着我们进入 2010 年的最后几个月，云计算变得无处不在。在过去的十年里，我一直担任云架构师和产品经理，并近距离观察了这个领域的发展。

所有这些变化对 IT 基础架构的发展意味着什么？我一直在认真思考这个问题，是时候制定新的规则了:

### **1。修改对你不利**

 [斯蒂芬·法贝尔

Stephan Fabel 拥有十年的实践云架构和产品管理专业知识:从在夏威夷大学运行首批生产 OpenStack 数据中心之一开始；界定、设计和管理苹果、威瑞森和 SAP 等主要客户的全球云实施；基于最大云客户确定的需求的混合云监控工具的 led 产品管理流程。Stephan 在 Canonical 的职位是产品经理，主要负责容器、LXD(机器容器)和平台即服务。](https://www.canonical.com/) 

当您听到供应商宣称他们能够通过发布基于上游项目的基础设施软件的“强化”版本，以某种方式使开源项目“企业就绪”时，您不感到不安吗？游戏结束了。例如，OpenStack 在许多版本中都很稳定，甚至能够处理最高级的使用案例和工作负载，而无需任何供应商的干预。

> “手工制作”是为了啤酒，而不是基础设施。

这是最重要的新规则，因为不遵守它是自我限制。为什么要通过引入下游补丁来限制能够在生产中使用您的平台进行工作、支持和创新的人数呢？开放基础设施的全部意义在于能够与更大的社区合作以获得支持，并为下一代基础设施平台上的招聘、培训和创新创造一个共同的基础。不要失去这个优势。

### 2.标准化是王道

“手工制作”是为了啤酒，而不是基础设施。大规模的实现无一例外地基于组件的标准化和架构的简单性。确保集群知识可以转移到新团队或从员工离职中恢复的唯一方法是避免引入技术债务的定制参考架构。

### 3.面向未来的自动化

几乎所有的团队都没有达到他们应该达到的自动化程度。他们中的大多数人在某种程度上意识到了这一点，但却没有采取行动。某些受到操作人员欢迎的工具很好地解决了前 80%的自动化用例，但没有解决其余的用例。结果是生命周期管理事件，如升级、欺骗、扩展等。仍然过于复杂和耗时。

在选择流程编排自动化时，假设技术堆栈会在硬件摊销期(通常为五年)内发生变化。您今天的 VMware 可能是明天的 OpenStack，可能会变成一个位于裸机之上、紧挨着它的 [Kubernetes](/tag/Kubernetes) 集群，甚至被它取代。期望一组特定的硬件在其整个生命周期内都与特定的基础架构相关联是不现实的。

### 4.在内部满负荷运行；将公共云用作溢出

如果在数据中心提供最佳经济效益是一个组织的首要目标，那么尽可能接近容量来运行内部基础架构是很自然的。硬件的选择应确保物有所值，虽然这不一定会带来最低的投资成本，但会带来最佳的总体经济效益，尤其是当目标是实现与公共替代方案相当的成本结构时。

也就是说，不要把这条规则误认为是避免公共云的呼吁。相反，除了拥有实现经济目标的可靠内部战略之外，与至少两家公共云提供商合作是明智之举。拥有两个公共云合作伙伴有利于良性竞争，并在您的运营中实施云中立自动化，这是成功的多云战略的一个关键属性。

### 5.升级，不要反向移植

随着上游项目支持周期的缩短——例如，想想 OpenStack 和 Kubernetes 的受支持版本和维护窗口的数量——养成升级的习惯而不是引入技术债务至关重要，因为技术债务会加剧引入后的每个生命周期管理事件的成本。有了正确类型的自动化流程，升级应该是可预测的，并且在合理的时间内是可解决的问题。

### 6.工作负载放置很重要

云本质上是动态的，因此调试服务级别违规时发生的事情需要考虑基础设施的变化性质。所有合理容量的云都有这个问题，大多数运营团队都忽略了维护裸机级别发生的事情与虚拟和容器级别发生的事情之间的相关性的必要性。在部署租户时考虑工作负载的放置，并建立必要的遥测技术来捕捉其环境中的事件。这将导致预测性分析，最终可能让你将人工智能引入你的运营(你的云基础设施越大/越复杂，这就越紧迫)。

### 7.停止将安全性视为独立的

大多数云项目是在开发人员和运营人员之间设计的，很少涉及单独的安全团队。结果呢？安全专家面对“已完成的交易”,他们的反应大多是对所有这些计划泼水。安全性是一种思维方式和原始姿态，应该从一开始就展示出来，并作为需求分析的一部分继续关注。为了满足涉众的期望，安全性与集群必须满足的任何其他非功能性需求一样重要和关键。因此，尽早、经常参与安保工作，并保持密切联系。

### 8.拥抱闪亮的物体

开放基础设施的全部意义在于促进创新，并通过加速下一代应用程序的部署为公司提供竞争优势。为什么要阻拦呢？如果你的开发者想要容器，为什么不呢？如果您的开发人员想要无服务器，为什么不呢？成为解决方案的一部分，而不是嘲笑新技术堆栈为“闪亮的物体”，只会凸显对现有运营模式和自动化缺乏信心。

通过遵守这八条新规则，企业应该能够在新的十年到来之际将自己定位于最大化的效率和生产力。

图片由来自 Pixabay 的 Hans Braxmeier 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>