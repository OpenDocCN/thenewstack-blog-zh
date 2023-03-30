# 电云自动化滚动部署，实现零停机更新

> 原文：<https://thenewstack.io/electric-cloud-automates-rolling-deployments/>

[Electric Cloud](http://electric-cloud.com/blog/2016/07/new-announcing-electricflow-industrys-first-native-push-button-rolling-deployments/) 希望通过消除发布新软件所涉及的繁重的脚本编写和手动步骤来解放部署团队的周末时间。

其 [ElectricFlow](http://electric-cloud.com/products/electricflow/) 发布自动化软件的最新功能是按一下按钮即可滚动部署，允许客户选择最适合他们的部署策略——包括滚动、[蓝/绿、金丝雀](http://blog.christianposta.com/deploy/blue-green-deployments-a-b-testing-and-canary-releases/)。

“我们听说了 Facebooks、Etsys、Twitters、unicorns，以及他们在交付软件方面所做的一切精彩的事情，”Electric Cloud 首席技术官安德斯·瓦尔格伦(Anders Wallgren)说。

“他们已经能够通过大量的资源做到这一点。他们花了很多年来构建这些定制系统，以便通过他们的交付管道非常有效地将软件推向生产。过去几年，我们一直专注于将这些能力带给那些不是独角兽的公司，这些公司没有资源或能力从头开始构建这些东西。”

他指出，DevOps 报告的最新状态发现，高性能 IT 组织的部署频率是低性能 IT 组织的 200 倍，并且整个行业在实现更快发布软件的要求方面记录不佳。

其客户是大型企业，包括高通、洛克希德·马丁、华为、思科、通用电气和 Gap。E-Trade 的系统工程经理 Manuel Edwards 在 DevOps 企业峰会(DOES15)上讲述了电子云如何帮助他的组织[将构建、测试和部署周期](http://electric-cloud.com/customers/etrade/)加快 12 倍。

“公司告诉我们，他们需要进行零停机部署。他们无法承担关闭网站进行部署的费用。他们的规模越来越大，很难在规定的时间内部署所有需要的软件，也无法做到这一点，”Wallgren 解释道。

许多公司仍然通过脚本进行部署，同时使用 Excel 电子表格煞费苦心地记录流程中涉及的数百个步骤。

“他们让 15 个人在周五或周六晚上打电话，试图通过非常容易出错、缓慢的手动流程来部署软件。从竞争的角度来看，这已经行不通了，”瓦尔格伦说。“如果您只能每个月或三个月或六个月部署一次软件，而您的竞争对手的部署频率是您的 10 倍或 100 倍，这将是一个巨大的竞争劣势。”

## 实践部署

滚动部署功能允许团队在 QA、试运行和预生产环境中“实践”部署，因此全面部署不是第一次完成，使其更加可靠。

它允许团队对部署进行建模，自动或手动地对资源进行分组，并定义阶段的顺序，然后自动或手动地执行它们。

您可以选择阶段，将有针对性的精选机器作为某些组的一部分，以指定的批量(比如一次两台机器)或按百分比推出，或者确定每个阶段使用哪些机器。

您可以跳过阶段、更改顺序或插入手动或自动验证。

根据电云产品营销高级总监山姆·菲尔的说法，该公司有一个银行客户，到 2017 年底，该客户希望在两小时的时间窗口内每天完成 320 万次部署。

“想一想从在不同环境中进行 320 万次部署的手动过程中获得的节约，以及试图管理什么在哪里、什么版本在哪里运行、没有满足什么依赖关系的混乱局面。让运营团队不再担心这些，这样他们就可以让开发和 QA 团队从测试的角度做他们需要做的事情。了解这些人工制品的保真度，这些环境和过程的保真度，以便当他们将其推广到生产中时，这不是他们第一次尝试的全新事物。这是已经实践过的东西，”他说。

他说:“我们将同样的心态带到部署过程之上的这些部署战略中。”

## 加快步伐

Wallgren 说，公司本身大约每月发布一次新版本。

具有滚动部署的最新版本的 ElectricFlow 现已通过邀请计划提供，并将于八月份正式上市。它的其他新功能包括环境日历，以减少团队调度冲突；自动环境发现，它用新的可扩展插件体系结构自动填充资源和环境参数；依赖关系的可视化。

据 Fell 说，这家总部位于加州 Sunnyvale 的 14 岁公司，大约三年前将其重点从持续集成转移到“最后一英里——如何发布软件”。

“我们开始关注‘我们如何让运营部的人更容易接受这个速度？’您不必放弃合规性或速度。这是为了帮助运营人员更适应，法律和安全团队、财务团队对更快的交付速度更适应，”他说。

在 OS X、Linux 和 Windows 的[免费社区版](http://electric-cloud.com/products/electricflow/)中，可以测试 ElectricFlow，它运行在 VirtualBox 上。

特征图片:“[闪电](https://www.flickr.com/photos/joevahling/9153370287/in/photolist-eWRq66-fKod5s-4FSSGh-9KnHx4-6JsfKE-dezao9-nt8E9i-bTyMMK-bTyPYP-7o2Qjr-bWugk2-bEE5fA-4VnFYQ-4ZDgwo-bEE7Dm-bTyQiF-bTyNy8-bEE6if-bTyNVe-bEE6DA-qTYvH7-6G2zjd-S3J8V-6Umx8c-9GeEk6-4YSv3E-gK1D2y-6Jo9ut-6w39dy-9QKnAD-6yQ7Bd-ahBXWr-56r8GN-88isW2-8JAyJo-8JAyXC-7wkrwj-fK6CLr-ce4KAq-6yQ8Cb-8JAyPC-4Kus7-y2SRb-7nYUdx-6d6JZh-abdH5w-aewo2i-8JAz3U-foPMRK-aBCgBp)”由[乔·瓦灵](https://www.flickr.com/photos/joevahling/)制造，许可证号为 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>