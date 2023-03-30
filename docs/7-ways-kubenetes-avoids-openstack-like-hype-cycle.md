# Kubernetes 避免 OpenStack 式炒作循环的 7 种方式

> 原文：<https://thenewstack.io/7-ways-kubenetes-avoids-openstack-like-hype-cycle/>

[](http://robhirschfeld.com/digital-rebar/)

 [罗布·希施菲尔德

罗布·希施菲尔德是 RackN 的首席执行官兼联合创始人，该公司为以容器为中心的数据中心提供编排软件。他已经在云计算和基础设施领域工作了近 15 年，从早期的 ESX 测试版开始工作，到在 OpenStack Foundation 董事会任职四届。](http://robhirschfeld.com/digital-rebar/) [](http://robhirschfeld.com/digital-rebar/)

Kubernetes 是否面临类似 OpenStack 的炒作周期？不。我们已经到了！但是我有七个理由会很好，为什么宣传没有在交付前进行。

作为一个行业，我们喜欢玩“红对蓝”的游戏。我确信创建一个 OpenStack vs Kubernetes meme 是一个大错误。OpenStack 是关于基础设施的，Kubernetes 是关于应用交付的。如果它们应该是高度协同的，而不是竞争的，那么为什么我们总是回到同一个“vs”的叙述中呢？

KubeCon 上周总结了围绕 Kubernetes 相关活动、社区和供应商的爆炸式增长的明确证据——这是我一直标记为“高峰潮流”的东西虽然有一种强烈的愿望要将这一事件与过去几年的 OpenStack 事件进行比较，但我确实认为这是一种欺骗性的比较。它们类似于开源项目，因为两个项目都在快速发展，由大供应商推动，充满希望；然而，它们有不同的市场动态，因为它们服务于非常不同的用户群体。

**Kubernetes 领导层和管理 Kuberntaes 的[云原生计算基金会](https://www.cncf.io/)正在根据自身需求和 OpenStack 等其他项目做出不同的战略选择。**

任何快速发展、超大规模的开源项目都会面临治理挑战，这让所有参与其中的人都感到害怕。从这个意义上说，相似之处是显而易见的:随着越来越多的不同利益出现，很难保持贡献者和保护项目的完整性。我在 OpenStack 董事会任职了四届(我被提名担任 2018 年的职位——所以投票吧！);作为一个帮助指导项目的积极领导者，我在这些问题上的立场是有据可查的。

让我们探索 Kubernetes 没有重复 OpenStack 历史的七种相互关联的方式。

## 1.关注应用而非基础设施

“云本地 Kubernetes”听起来像一个矛盾修饰法，这是一个非常相关的点。所有 CNCF 项目都以应用交付为中心。这意味着他们参与了一个非常不同的“上层”用户社区。这些用户能够利用常见的基础设施，如亚马逊网络服务、[谷歌云引擎](https://cloud.google.com/kubernetes-engine)或 [Azure](https://azure.microsoft.com/en-us/?v=17.14) 作为起点，因此在开始时操作差异最小。这意味着新用户专注于使用而不是安装。

最终，OpenStack 不可避免的安装和操作挑战造成了采用摩擦。我知道直接获得 OpenStack 基础设施的挑战(参见“ [Crowbar](https://robhirschfeld.com/crowbar/) ”)。我们在创建可重复的底层体验方面的努力导致了 [Digital Rebar](http://rebar.digital/) API 驱动的供应技术，这是 [RackN](http://rackn.com/) 的核心。任何直接依赖于物理基础设施的东西(所有东西最终都会依赖于物理基础设施！)大大增加了社区建设的复杂性。

## 2.API 超过代码和早期一致性

Kubernetes 能够利用 OpenStack 的互操作性工作(见[我的 DefCore 工作](https://robhirschfeld.com/tag/defcore/))来快速建立一个认证的 API 标志。虽然还处于初期，但它发出了一个明确的市场信号，即供应商应该以可移植的方式尊重 API。这有助于建立用户信心和厂商参与。反过来，这些又为活跃的生态系统创造了可寻址的市场，以吸引更多的用户。

我也相信 Kubernetes 更愿意拥抱 API 而不是代码。OpenStack 社区中的一个妥协(在我看来很不幸)是要求所有 OpenStack 供应商使用相同的代码库。我认为两个项目都没有分叉的风险；然而，当需要特定代码时，它向参与者发送了错误的信息 APIs 是用户的交互点，而不是代码。也就是说，我认为 Kubernetes 得益于单一语言 Golang 的使用，并且没有多个发布源。

## 3.Kubernetes 是一个生态系统，而不是一块巨石

Kubernetes 的长老们决定保持这个项目小而集中。他们很乐意将 CNCF 作为 Kubernetes 轨道相关项目的安全阀。典型的设计讨论是从固执己见开始(只有 Docker 和 GCE/AWS ),然后随着模式和范围的扩展推出通用 API。这意味着随着时间的推移，项目越来越小，越来越分离。

大型项目面临着增加特性范围的巨大压力。这就是为什么 OpenStack 不断增加“半核心”服务项目，如数据库、负载平衡器、UX 和业务流程。虽然这些对许多用户来说是基本的服务，但是如果管理协调的话，它们也会形成一个紧密耦合的整体。这些是关键特性，但它们不是基础设施 API 的核心。将它们分离限制了 API 的融合，但它建立了一个关键的生态系统，并允许它们更快地创新。

## 4.没有大帐篷，但有一个项目的“追尾派对”

CNCF 松散的治理方法可能会令人困惑，因为他们选择加入的项目似乎没有什么组织或主题(听听我们最近的播客)。它们不需要项目或公共基础设施之间的协作；然而，这些项目确实有一个共享的架构方法。这种轻量级的治理(自我描述为[“最小可行的治理”](https://github.com/cncf/toc/blob/master/PRINCIPLES.md))不会在社区中创建“in vs. out”思想，因为对项目集成在一起只有最小的期望。相反，它们通常(但不总是)被包含在一个应用程序堆栈中。

与 OpenStack 已经废弃的[“大帐篷”](https://robhirschfeld.com/2014/11/21/big-tent/)实验相比，这种方法非常有利于创新。它们有什么不同？Kubernetes 和其他 CNCF 项目之间没有品牌混淆。这意味着用户不期望项目之间的集成(参见开放基础设施专栏)。

## 5.Kubernetes 即服务的财富

Kubernetes 很早就开始提供“即服务”产品，并且提供商的数量继续快速增长。服务提供商活跃在这个领域有几个非常积极的好处。首先，它们让用户更容易接受。其次，他们非常关心代码库的规模和可操作性。第三，也是最重要的一点，它们使得 API 具有一致性和可移植性。这些实例为社区提供了“参考”实现，鼓励社区进行协调，这样他们就可以在增值特性上竞争。

“即服务”产品也存在风险，如暗箱操作和代码库的隐藏分叉。这对于 OpenStack 公共云来说是一个巨大的挑战，私有云供应商的慷慨让这一挑战变得更加复杂。由于 aaS 供应商的出现较慢且难以标准化，OpenStack 用户发现自己处于定制安装中，而不是构建可移植的基础设施。这一趋势正在慢慢逆转。

## 6.强有力的管理

Kubernetes 受益于谷歌强有力的管理。谷歌深厚的人才、设计验证和财务投资在项目的关键发展阶段推动了 Kubernetes。事实上，谷歌并不直接与红帽、CoreOS、IBM 或三星等公司竞争，这使得它们可以安全地加入该项目，更重要的是支持该项目。项目有受单一供应商影响过大的危险；然而，谷歌也给出了正确的后退信号，允许主要领导人退出。

虽然 OpenStack 是由 Rackspace 和 NASA 推出的，但管理的程度受到设计的限制。作为戴尔团队的一员，我是推动社区快速进入多供应商环境的声音小组的一员。虽然我发现协作环境赋予了我力量，但它也让项目在关键的孵化阶段出现了泡沫。回想起来，我希望我们在技术上更固执己见。

## 7.竞争对手

最后，Kubernetes 受益于相对较晚进入集装箱调度领域。Docker，Mesos，Rancher，Apcera，Cloud Foundry 和其他几个(有人记得[stacken engine](https://techcrunch.com/2015/12/22/oracle-stackengine-acquisition-part-of-expanding-cloud-strategy/)？！)最初有更完整的产品。我记得当 Docker Swarm (v0.12)通过与 Docker 引擎集成而在社区中引发冲击波时，Kubernetes 是一个商业支持不温不火的失败者(直到红帽转向 [OpenShift](https://www.openshift.com/) )。这一强劲的市场使得项目在没有太多聚光灯的情况下成熟(目标？)在上面。

相比之下，OpenStack 似乎完全成型，拥有超出预期的规模和慷慨的风险资本资助的营销预算。合理的开放竞争对手确实存在(CloudStack、Eucalyptus 和 OpenNebula)，但围绕该项目的供应商宣传机器对 OpenStack 进行了积极的定位(是的，我在这里非常内疚)。这烧掉了技术跑道和良好的意愿。现在 Kubernetes 似乎已经“赢得”了集装箱调度战，蜜月显然已经结束。

### 最后

管理开源项目没有唯一正确的方法(向[安娜·卡列尼娜](https://en.wikipedia.org/wiki/Anna_Karenina)致敬)。我们最大的希望是，我们做出的正确选择能够战胜错误的选择。虽然这篇文章重点关注 OpenStack 的挑战，但我们也做出了许多伟大的选择，我对新的开放基础设施方向持乐观态度。Kubernetes 正在根据这些选择和自身需求编织自己的道路。到目前为止，我支持这些选择。我希望我的七点能帮助你更深入地思考这条道路——我想听听你对我做对了什么和错过了什么的看法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>