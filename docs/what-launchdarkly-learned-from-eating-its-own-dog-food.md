# launch black 从“吃自己的狗粮”中学到了什么

> 原文：<https://thenewstack.io/what-launchdarkly-learned-from-eating-its-own-dog-food/>

在《新栈制造者》的这一集中，[launch Daryl，](https://launchdarkly.com/?utm_content=inline-mention)的产品负责人[卡里什马·伊拉尼说，功能标志——写在条件语句中的开/关开关，允许组织在代码部署后对用户体验进行更大的控制——正在激增，变得越来越复杂，需要强大的功能管理。](https://www.linkedin.com/in/karishmairani/)

[https://www.youtube.com/embed/5vckZIB-cuA](https://www.youtube.com/embed/5vckZIB-cuA)

视频

LaunchDarkly 在 11 月份对 1000 多名 DevOps 专业人员进行了调查， [69%的参与者表示功能标志对他们的组织来说是“必备的、关键任务的和/或高优先级的”](https://thenewstack.io/launchdarkly-feature-management-is-a-must-have/)。

[从《吃自己的狗粮》里学到了什么](https://thenewstack.simplecast.com/episodes/what-launchdarkly-learned-from-eating-its-own-dog-food)

“[，](https://thenewstack.io/whats-the-future-of-feature-management-feature-flags/)我们认为，功能管理是一种现代实践，对于那些希望更频繁地部署、更快地创新，并保持一支健康的工程团队的公司来说，这种实践越来越普遍，”伊拉尼说。

伊拉尼说，功能管理的理念是“在最小化风险的同时最大化价值”

她说，LaunchDarkly 使用自己的软件，正如俗话所说，吃自己的狗粮在洞察用户需求方面取得了回报。

作为 11 月 LaunchDarkly 虚拟会议轨迹的一部分，伊拉尼加入了新堆栈的功能编辑希瑟·乔斯林，就功能管理的最新发展进行了广泛的对话。

《创客》这一集是由 LaunchDarkly 赞助的。

## 自动化审批

作为对如何使用他们公司产品的第一手知识的好处的例子，伊拉尼指出了 2022 年年中的一个内部项目。

当该公司从 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 迁移到 CockroachDB 时，它在功能工作流产品中使用了新的功能，允许用户定义一个工作流，该工作流可以计划在未来的日期和时间逐步发布功能标志，并自动批准请求。

“所有这些围绕批准时间表的异步过程，对发布软件至关重要，但它们确实会减慢你的速度，并增加手动错误或人为错误的可能性，”伊拉尼说。“因此，我们的功能工作流目标是从本质上自动化功能发布的整个过程。”

## 大修实验

她说，今年 6 月，该公司还修改了其实验产品。伊拉尼说，在 LaunchDarkly 的实验负责人詹姆斯·弗罗斯特(James Frost)的带领下，该团队“对我们的统计引擎进行了彻底的检查，他们增强了我们客户现有数据集和指标的整合途径他们重新设计了我们的 UX，并将模型和实验最佳实践编入产品本身。"

例如，一个新的度量导入 API 有助于防止一个公司内的多个团队或用户使用不同的工具进行 A/B 和其他实验的问题。伊拉尼说，它“大大减少了为实验导入指标时的手工重复工作”。“这样你就可以更快地准备好。”

她说，实验产品的另一个补充是样本比率不匹配测试，因此“你可以确信你的所有实验都正确地将流量分配给了每个变体。”

这些创新以及该公司核心平台的新功能现已全面上市。在地平线上——现在可以通过[launch crystally 的早期访问计划获得,](https://launchdarkly.com/EAP)是 Accelerate，它让用户跟踪和可视化关键的工程指标，如部署频率、发布频率、代码更改的提前期和标志覆盖率。

“我相信你已经明白了，”伊拉尼说，“但其中一些是[朵拉指标，](https://thenewstack.io/googles-formula-for-elite-devops-performance/)显然对我们的用户非常重要。”

查看整集，了解 LaunchDarkly 的新内容以及功能管理领域的创新者仍然需要解决的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>