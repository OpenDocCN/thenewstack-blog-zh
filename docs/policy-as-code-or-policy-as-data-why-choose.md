# 策略即代码还是策略即数据？为什么选择？

> 原文：<https://thenewstack.io/policy-as-code-or-policy-as-data-why-choose/>

[](https://www.aserto.com/)

 [奥姆里·加齐特

奥姆里是授权创业公司 Aserto 的联合创始人/首席执行官，也是他的第三次创业。他 30 年职业生涯的大部分时间都在从事开发人员和基础设施技术方面的工作，最近的职位是 Puppet 的 CPO。此前，他是惠普云原生平台的副总裁兼总经理(负责 OpenStack、Cloud Foundry、CloudSystem 产品和服务的业务、产品和工程监督)，也是微软的总经理，负责 Azure、SQL Server、应用服务器和。NET 框架。](https://www.aserto.com/) [](https://www.aserto.com/)

授权是一个古老的问题，多年来我们已经看到了许多旨在为其提供某种结构的模式，包括访问控制列表(ACL)、基于角色的访问控制(RBAC)和基于属性的访问控制(ABAC)。

每个授权解决方案都需要代码和数据的组合:代码根据用户上下文控制对受保护资源的访问，数据描述允许哪些用户对哪些资源执行哪些操作。

最近，我们看到了两个对现代授权系统越来越重要的重要趋势:

*   将策略从应用程序中提取出来，用特定于领域的语言来表达，并将其作为代码来存储/版本化。
*   以更标准的方式表达主体(用户)、谓词(动作或角色)和对象(资源)之间的关系。

## 作为代码的策略

21 世纪初，Web 2.0 的兴起带来了一套针对网络身份和访问的互操作性标准。XACML 包括基于属性的策略的文本表示，以及与策略决策点交互的协议。

在云原生运动的背景下，[开放策略代理](http://openpolicyagent.org) (OPA)项目已经成为将策略表达为代码的事实上的标准。OPA 策略是用一种被称为[减压阀](https://www.openpolicyagent.org/docs/latest/policy-language/)的受 Datalog 启发的语言编写的，可以像配置或基础设施代码一样存储和版本化，如 Puppet、Chef、Ansible 和 Terraform 所开创的。

Policy-as-code 提供了一个强大的抽象概念，用于将授权逻辑从应用程序中分离出来，并将其集中在一个不同的源代码存储库中，从而允许应用程序开发人员和安全工程师之间的职责分离，前者只需担心通过向其传递正确的输入来执行策略，后者可以在没有开发人员直接参与的情况下发展策略。

将策略表达为代码本身就更容易推理——熟悉语言语法的工程师可以很容易地确定策略如何工作，并可以用不同的输入测试策略以确定它将做什么。

提供一种将策略构建到不可变映像中并对其进行签名的标准机制，是确保策略工件的安全软件供应链的一个重要方面。[开放策略注册中心](http://openpolicyregistry.io)为 OPA 策略提供了这种能力。

最后，拥有完整的决策日志(包括用于做出每个决策的策略映像、用户上下文和资源上下文)有助于审计员重建和重放这些决策，从而更容易证明做出每个决策的原因。

由于这些原因，策略即代码现在正成为现代授权体系结构的一个重要方面。

## 策略作为数据

归根结底，代码是对数据进行操作的。无论该代码是嵌入到应用程序中，还是单独取出并存储/版本化，您都需要将数据以用户上下文、资源上下文或两者的形式引入策略。

访问控制列表是最古老的访问控制形式，从 60 年代就已经存在了。受 ACL 模型启发的系统有一个固定的策略:资源和用户之间的关系仅限于少数“角色”，如查看者、编辑者、所有者。在这些系统中，策略逻辑被硬编码在授权引擎中。问题从创建和发展授权策略转移到定义将数据元组输入引擎的标准数据格式，通常是“alice 是 document:roadmap 的所有者”这样的形式。

谷歌在 2019 年发布的[桑给巴尔](https://research.google/pubs/pub48190/)论文描述了支撑谷歌文档的授权系统，围绕授权的 ACL 模型创造了一个复兴，并激发了该领域最近的创新。正在定义新的 DSL 来编纂资源模式，并且正在出现编码{ subject，predicate，object }三元组的标准符号。

在这个上下文中，授权意味着回答一个问题，比如“允许 Alice 查看路线图文档吗？”通过遍历用户和资源之间的关系图。这是一种更加以数据为中心的授权方法。

## 哪个更好？

一如既往，答案取决于用例。为了避免复杂性爆炸，授权系统通常应用一组约束。

在 Google Docs 的例子中，系统是围绕一组固定的“角色”(查看者、评论者、编辑)进行优化的，这些角色应用于文件夹和文档的层次结构。要解决的难题包括交付一个全球一致、高度可伸缩的系统来管理和实施这些权限；灵活的策略不是需求集的一部分。

其他系统要求在用户属性和这些用户可能拥有的权限(作为全局角色或对资源组)之间的映射具有更大的灵活性。例如，许多系统定义资源“范围”，如组织、项目或团队，并为用户分配属于这些范围的资源的一组权限，这些系统通常具有许多特定于域的资源，每个资源支持一组不同的操作，并且可以定义几十个或几百个离散的权限，这些权限通常被分组为一个较小的角色集。这些系统需要以策略为中心的设计。

## 作为代码和数据的策略

要回答最初的问题，授权最好是将策略作为代码和策略作为数据结合在一起。当授权策略需要灵活并随应用程序需求而发展时，策略即代码的方法是这种发展的关键推动者。同时，每个授权系统都需要有一个策略来定义做出授权决策所需的数据，以及一个可伸缩的方法来将数据引入授权上下文。

## 试试阿塞托

在 Aserto，我们为那些想要探索两个世界的开发者建立了一个授权 API。它将策略即代码工作流与将用户和资源上下文引入授权引擎的规定方法结合在一起。[注册一个免费账户](https://aserto.com/#sign-up)并查看一下吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>