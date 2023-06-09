# Cloud Foundry 的安全策略:轮换、修复、重铺

> 原文：<https://thenewstack.io/cloud-foundrys-approach-security-rotate-repair-repave/>

大多数企业都在以错误的速度解决安全问题:他们推出他们认为安全的应用程序和基础设施，然后迟迟不做出任何改变，担心重新配置可能会打开安全漏洞。

但是威胁的格局是不断变化的，企业需要改变他们的安全实践来反映这种流动性，在本周于三藩市举行的[云铸造峰会](https://www.cloudfoundry.org/events/)的开幕式上，一位大量参与云铸造安全的关键安全工程师[贾斯汀·史密斯](https://twitter.com/justinjsmith)说道。

“为了变得更安全，你必须走得更快，而这恰恰与当今组织的工作方式相反，”史密斯说。“持续变化是我们在企业安全中必须接受的一个概念。”

在他的演讲中，Smith 解释了 Cloud Foundry 方法如何不同于企业软件中产生的传统安全实践，以及其整体方法如何有利于遭受网络攻击的公司。

Smith 说，作为一个专注于数据中心的堆栈， [Cloud Foundry](https://www.cloudfoundry.org/) 需要有一个强大的安全策略。为了与 Cloud Foundry 的开发风格保持一致，该软件在安全问题上坚持己见，并且认为应该尽可能频繁地更新。他称这种方法为:“旋转、修复、重铺。”

史密斯提醒听众说，企业经常受到网络攻击。由美国情报部门汇总的年度全球威胁评估现在将网络攻击列为比传统问题(如大规模杀伤性武器或恐怖袭击)更大的威胁。

史密斯说，情报界不太担心网络珍珠港大规模基础设施攻击，而是担心成千上万的公司攻击以“一千张纸杀死一个人”的方式慢慢消耗集体能量。

对于这些攻击，“没有人可以打电话，”史密斯警告数据中心运营商。“你基本上只能靠自己了。”

考虑到这一点，“我们希望 Cloud Foundry 能够抵御攻击，”Smith 说。“并不是说袭击不会发生。你希望能够经受住攻击，付出一点点，然后回到正常状态。从安全的角度来看，这正是您想要的云软件。”

今天典型的“[高级持续威胁](http://searchsecurity.techtarget.com/definition/advanced-persistent-threat-APT)”涉及恶意方偷偷在基础设施中漫游，悄悄学习操作如何工作，并最终窃取敏感数据(或[以此作为赎金](http://www.securityweek.com/its-official-ransomware-has-gone-corporate))。

攻击者需要多种因素来实现这一点。一种是未打补丁或配置错误的软件，其中包含漏洞，可以被利用来获取访问和控制。“打补丁的软件在企业中很少见，”Smith 说。

史密斯指出，策划这些袭击所需的另一个“重要因素”是时间。探测不同的组件，然后找出如何利用它们的弱点需要时间来执行。

企业软件，甚至是企业安全软件的糟糕状态对事情没有任何帮助。“我们已经建立了如此糟糕的软件，以至于不惜一切代价抵制改变，”史密斯说。例如，防火墙配置往往很复杂，所以一旦设置好，管理员就不愿意更改，担心会造成漏洞的意料之外的二阶效应。轮换安全凭证这一讨厌的任务也往往会被搁置到将来。

“我们卖给企业的软件抵制变化，所以文化自然抵制变化，”史密斯说。

监视器可以被放置在适当的位置来突出潜在的易受攻击的区域，尽管它们的有用性对史密斯来说是值得怀疑的。“请注意，监视器[没有]修复问题，它只是发送了一个标志。所以你必须处理大量的通知。企业内部的安全团队脾气暴躁是有原因的。”

史密斯建议说，要走出这个泥潭，我们对如何管理安全的这种看法必须改变。

史密斯认为，Cloud Foundry systems 提供的优势是，由于其快速的发布时间表和自动升级的偏好，漏洞可以在不停机的情况下快速修补，从而剥夺了攻击者检查系统所需的时间。

仅在今年，Pivotal Cloud Foundry 堆栈就获得了 30 次更新，所有更新都修复了漏洞。Smith 本人正在从事一些项目，这些项目将允许更无缝的凭证轮换，同样，他的想法是应该经常更换凭证以阻止攻击。

云代工厂偏向于频繁升级。并致力于使这些升级尽可能轻松，没有停机时间。史密斯说，保持服务器运行多年而不重启不应该是一种“荣誉勋章”。相反，我们应该考虑尽可能缩短服务器或虚拟服务器的最大生命周期。

“如果我的数据中心内的每台服务器的最长寿命为两个小时，会怎么样？”史密斯说。史密斯指出，这种方法将挫败恶意软件作者，因为它限制了在修补已知漏洞之前利用它们的时间。

“这是我们架构的一部分。我们就是这样建立起来的，”史密斯说。

Cloud Foundry 基金会是新堆栈的赞助商。

图片:李·卡尔科特

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>