# VMware 聘请无服务器 OpenFaaS 创始人；戴尔关闭了其{code}开源计划

> 原文：<https://thenewstack.io/vmware-hires-openfaas-founder-dell-drops-code-initiative-2/>

虚拟化软件巨头 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 已经聘请 [Alex Ellis](https://github.com/alexellis) 在公司全职工作于他的项目 [OpenFaaS 无服务器软件](https://github.com/openfaas/faas)。此前，他在 ADP 做应用程序开发人员，在业余时间创建并运行 OpenFaaS。

在拥有 VMware 大部分股份的戴尔公司，开源软件的情况并不乐观。该公司刚刚放弃了其 [{code}](http://web.archive.org/web/20180220231349/https://thecodeteam.com/) 开源计划，该计划为云原生开源空间带来了许多重要技术，并支持许多其他技术。

Ellis 将加入 VMware 的[开源技术中心](https://twitter.com/vmwopensource) (OSTC)，这是 VMware 开发和支持开源技术的孵化器。“这个选择是有意义的，因为我将保持对项目和品牌的控制，同时与其他在容器和虚拟化领域有专长的开源领导者合作，”埃利斯在周一的一篇博客文章中写道。

[OpenFaaS](https://thenewstack.io/openfaas-put-serverless-function-container/) 扩展了无服务器服务的概念，最初由亚马逊网络服务的 Lambda 云服务流行起来，它提供了执行代码的能力，这是一种“功能”，无需服务器的支持基础设施。与 [Lamba](https://aws.amazon.com/lambda/) 只能支持少量语言不同，OpenFaaS 可以通过容器的使用，将任何代码打包成“无服务器”的函数。

OpenFaaS 最初是作为一个项目的辅助工具，Ellis 正在利用他的亚马逊 Alexa 语音服务。他有一个在圣诞树上运行多色灯的树莓皮，他想通过 Alexa 来控制它。Ellis 发现在 Lambda 上运行他的代码的准备工作很繁琐——每次更改都需要将代码和 Node.js 实例重新打包成 zip 文件，然后上传到 Amazon。相反，Ellis [将他的代码](https://blog.alexellis.io/functions-as-a-service/)打包在一个容器中，该容器将由 Docker Swarm 管理，并将端点从 Lambda 切换到 HTTP 调用。

[](https://github.com/openfaas/faas)

 [OpenFaaS Stats(聚合)

*   提交:1759
*   分支:51
*   贡献者:78
*   分叉:789
*   许可:MIT](https://github.com/openfaas/faas) [](https://github.com/openfaas/faas)

VMware 是虚拟机技术的领先公司，最近一直在投资无服务器技术，至少在企业级最大限度地减少虚拟机的使用。公司[最近开始了](https://blogs.vmware.com/opensource/2018/02/19/vmware-welcomes-alex-ellis/)在开源 [Dispatch](https://github.com/vmware/dispatch) 上的工作，这是一个在现有的 FaaS 实现之上提供企业特性的框架，比如 OpenFaaS、Riff 和 OpenWhisk。

私有的戴尔目前拥有大约 80%的 VMware 股份，这是作为[戴尔 2015 年收购 EMC](https://techcrunch.com/2015/10/12/dell-buys-emc-for-67b-in-largest-deal-in-tech-history/)的一部分而获得的，尽管戴尔董事会正在[考虑反向合并](https://www.cnbc.com/2018/01/29/vmware-could-buy-dell-in-what-could-be-techs-biggest-deal-ever--a-reverse-merger-that-would-bring-dell-back-to-public-markets.html)，实际上使公开交易的 VMware 成为其母公司。

据公司发言人称，戴尔自己已经停止了自己的开源计划 [{code}](http://web.archive.org/web/20180220231349/https://thecodeteam.com/) 。{code}计划为云原生空间诞生了许多技术，例如 [REX-Ray](https://github.com/rexray/rexray) ，开源[容器存储接口](https://github.com/container-storage-interface/spec) (CSI)的第一个稳定的工作模型。

戴尔发言人在一份电子邮件声明中声称,{code}工作将在其他戴尔产品团队中继续进行:

“{code}计划将在戴尔技术营销团队中继续进行，对集团的 Slack 社区 REX-Ray 进行持续投资，并参与各种开源和开发人员社区活动。{code}是一个 bootstrap 团队，成立于几年前，为开源最佳实践提供建议，当时 DevOps 是客户的新兴趋势。这种产品级别的工作现已整合到业务中，并被逐出戴尔技术产品团队。”

戴尔发言人没有给出关闭{code}计划的原因，也没有说明现有员工是否会被重新分配或解雇。然而，该项目的许多员工在 Twitter 和 Slack 上表示，他们的专业知识现在可以在 T2 用于新项目。据一位接近该项目的匿名消息人士透露，该项目的最后一天将是 3 月 2 日。

尽管戴尔的财务状况依然稳健，但它正面临着一系列财政挑战。随着越来越多的客户转向云计算，EMC 企业存储设备[的销量已经持平](http://searchstorage.techtarget.com/blog/Storage-Soup/Report-Dell-EMC-storage-aftermath-may-trigger-IPO)。此外，据 CRN 称，它预计会受到最近通过的减税和就业法案的冲击。这项新的美国法律严格限制了该公司在 2016 年以 670 亿美元收购 EMC 时可以注销的利息支付数量。行业分析师推测，正是这些因素促使戴尔董事会考虑反向并购。

{code}项目始于 2014 年，旨在培育新的开源项目，其中许多来自戴尔内部，旨在将这些项目集成到更大的开源社区中。存储是最初的重点，尽管团队很快转向了企业开源的其他方面。该团队还支持了 100 多个外部项目，包括许多云原生技术，如 Kubernetes、CSI、Envoy 和 GRPC。

“我们希望确保我们拥有客户想要的、客户需要的东西。所以我们开始创建开源项目，也开始成为其他开源项目的一部分，所以我们以这种方式进入了社区，”开源社区经理 [Jonas Rosland](https://www.linkedin.com/in/jonasrosland/) 在去年 12 月在 KubeCon + CloudNativeCon 录制的[赞助的 TNS 播客](https://thenewstack.io/what-is-code/)中说道。

专题图片:Alex Ellis [宣布 OpenFaaS 功能商店](https://twitter.com/alexellisuk/status/936544880872054784)。

[{code}](http://web.archive.org/web/20180220231349/https://thecodeteam.com/) 和 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>