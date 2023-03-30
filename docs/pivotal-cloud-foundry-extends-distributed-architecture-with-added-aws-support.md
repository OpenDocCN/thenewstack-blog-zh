# Pivotal Cloud Foundry 通过增加 AWS 支持来扩展分布式架构

> 原文：<https://thenewstack.io/pivotal-cloud-foundry-extends-distributed-architecture-with-added-aws-support/>

大规模应用程序开发和管理的分布式特性意味着工作负载应该在本地、公共云或两者上运行。客户需要这种能力，这给 Pivotal 今天宣布在亚马逊网络服务(AWS)上提供托管云基础设施作为其 Pivotal Cloud Foundry 平台的一部分提供了一个很好的理由。

Pivotal 不对 AWS 上的托管服务收费。现在，它与软件订阅捆绑在一起，无需额外费用。目的是允许混合云场景和从内部到公共云环境的可移植性。

来自 Pivotal Cloud Foundry 的服务现在在 AWS Marketplace 中作为可扩展的 Amazon 机器映像提供，具有一键安装功能。

Pivotal 副总裁兼云平台集团总经理詹姆斯·沃特斯(James Watters)表示:“我们认为，凭借这种便携性，我们现在拥有了市场上最完整的混合故事。“我们非常兴奋，这可以以多种不同的方式在 vSphere 和 OpenStack 或 Amazon 上运行。”

Watters 补充说，该公司正在与其他公共云供应商谈判，以添加类似的功能。

他说，虽然以前在 AWS 上使用 Pivotal CF 是可能的，但这不是一次完美的体验。

> “我们看到许多人希望使用我们的纯托管版，这种版本在几秒钟内就可以启动，而无需运营他们自己的平台。”

他说，Pivotal CF 的自动化意味着为客户运行增量工作负载几乎不会增加成本，除了亚马逊的一小部分，因此该公司决定将其包括在企业支持订阅中，该订阅包括在内部使用它或在公共云中运行工作负载的权利。

一些客户希望 Pivotal 托管服务的可移植性，但希望在亚马逊上他们自己的专用平台上使用。他说，通过提供一个亚马逊机器映像，Pivotal 可以减少所需的时间，尽管它不只是安装一台机器。

“当你打开这个机器映像时，你可以将你的亚马逊凭证插入虚拟机，它将在大约一个小时内为你构建一个任意大的平台。因此，你可以使用我们的自动化工具，在亚马逊上从零到 700 个 Cloud Foundry 节点，为你构建平台，”他说。

“因此，我们推出了这种混合方案，在这种方案中，您可以使用我们通过 API 提供的托管服务，您可以在不到半天的时间内在亚马逊上构建自己的实例，或者像我们的许多客户已经在做的那样，在您的私有数据中心大规模运行。”

他说，这表明高度自动化和集装箱可以共同产生“令人难以置信的经济效益”。它包括使用更少的容器，以便亚马逊的容量被分割成超高效的小块，而没有浪费开销。

他说，自安装功能以及安全性和自动化功能意味着 IT 和业务线最终可以在平台上达成一致:业务线开发人员可以立即在 AWS 上开始，而私有云构建已经完成或完全在那里运行。

## “自然延伸”

RedMonk 的高级分析师 Donnie Berkholz 表示，鉴于 AWS 的庞大客户群以及对支持的预期需求，Pivotal 在亚马逊网络服务上提供受支持版本的 Cloud Foundry 的举动非常有意义。除了在 AWS 上运行的共享 Pivotal Web 服务之外，它还支持在 AWS 上安装 Cloud Foundry 一段时间，因此这是在公共云上添加专用产品的自然扩展。阿普瑞达对阿祖尔做了类似的事情。

“由于大量数据传输的时间和费用，数据引力在迫使计算转向数据方面的重要性不断增长，”他说。“这一产品使现有 AWS 的 Pivotal 客户更容易、更便宜地将他们的数据与 Cloud Foundry 集成，这很少是一件坏事。添加一个更简单的安装程序，而不是手动使用 Bosh，将大大降低经验不足的客户的入门门槛，特别是如果他们来自 Pivotal Web Services，他们以前不必自己维护 Cloud Foundry。”

伦敦 CohesiveFT 的首席技术官克里斯·斯旺(Chris Swan)指出，进入 AWS 市场使潜在客户很容易尝试，因此他们可以进行概念验证和试点，而不必正式与 Pivotal 合作。

“这表明 Pivotal 增强了对产品的信心，因为他们觉得没有必要通过入门来指导每个潜在客户。”

他说缩放的问题不太清楚。

“当然，客户可以选择运行 Pivotal CF 的实例大小以及实例数量，但除此之外还有什么呢？当一个应用程序变得繁忙时，系统是否可以增加新的实例？它能自动从本地安装溢出到按需云实例吗？”他问。

该公司表示，Pivotal Cloud Foundry 的最新更新包括自动扩展的升级，允许应用程序在繁忙时扩展，该产品的未来版本将包括所有云。

Swan 说:“比例问题提出了一大堆关于混合动力真正含义的问题。”。

除了在本地部署一些应用程序和在 AWS 中部署其他应用程序之外，“当试图跨多个云管理单个应用程序时，情况会变得更加复杂，具体而言，不同的部分如何安全地相互连接，以及应用程序组件如何跨该连接进行集成？”

## 构建丰富的投资组合

Pivotal 最出名的可能是领导 Cloud Foundry 开源平台即服务(PaaS)项目，该项目最近[成立了一个由 Linux 基金会运营的基金会](https://thenewstack.io/cloud-foundry-outsources-its-foundation-as-open-source-management-continues-to-evolve/)。

Pivotal 将 [Pivotal Cloud Foundry 吹捧为有史以来增长最快的开源产品](http://www.prnewswire.com/news-releases/pivotal-cloud-foundry-reports-record-breaking-2014-fastest-first-year-sales-growth-for-an-open-source-product-300027875.html)，在不到一年的时间里，该产品的软件销售额约为 4000 万美元。作为 Pivotal 的高级技术专家之一，安德鲁·谢弗(Andrew Shafer)告诉新堆栈的南希·戈林(Nancy Gohring)，Cloud Foundry 服务于[类型的企业，这些企业将在具有不同业务部门和合规要求的多租户环境中运行数千个应用](https://thenewstack.io/docker-is-driving-a-new-breed-of-paas/)。

Pivotal 是 EMC 和 VMware 的衍生产品，从丰富的资产组合开始，而不是从头开始构建。它表示，其客户包括美国三大保险公司中的两家，北美三大电信公司中的两家，以及七家专注于物联网(IoT)建设的财富 500 强工业公司。其中之一是通用电气，该公司已投资 1.05 亿美元与 Pivotal 合作建设工业互联网。

IBM 为其 BlueMix 服务构建了自己的 Cloud Foundry 发行版，正如惠普为其 Helion cloud 所做的那样。

该公司已经吸引了云技术领域的一些知名人士，最近聘请了亚马逊网络服务的云先锋本杰明·布莱克；OpenStack 联合创始人 Joshua McKenty 和 Puppet Labs 联合创始人 Shafer。

根据戈林的帖子，其他开源的自助服务计划——Deis、Flynn、鹤、Dawn 和 octo host——与第二代 PaaS 计划如 Cloud Foundry 和 OpenShift 有一些相似之处。

Pivotal 是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/jz909/2076707157/in/photolist-4avEFP-dtmAgu-6nDw8D-aQbwCM-jRb3t-qexmC-q8Aw19-4LihFn-r5bQGk-iowFMc-3NoW5-ntYski-brLhZT-DAro-iFLMPw-9gLNYT-dpPYN5-ame8aV-izWnwF-3jVZTa-67WVdL-jT5QGf-pwQ5UK-5HpfK8-fbJLz-5piDE-9TgamQ-hzRfdD-puMTnJ-b6nVNP-cofK7w-4f2vVf-p8L6Ug-hteGJA-5BZ132-d2G6F-7KrafP-9daMkd-cey7G-9d7AtH-hzPAWD-p8BcFi-6gaCfw-6QyXN3-dphtN9-mYLtGH-5MTGX8-N4MJ3-676Miv-p6Rxiz)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>