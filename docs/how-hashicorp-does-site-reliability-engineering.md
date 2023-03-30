# 哈希公司如何进行现场可靠性工程

> 原文：<https://thenewstack.io/how-hashicorp-does-site-reliability-engineering/>

HashiCorp 在其年度用户活动 HashiConf Global 上制造了新闻，使[在周三和周四发布了一系列产品公告](https://thenewstack.io/hashicorp-cloud-can-now-spin-up-a-single-sign-on-zero-trust-network/)。

一个新的升级或产品的发布对任何组织来说都是一个成功的事件。但是，如果一家公司的系统不能处理客户争相购买或下载的流量高峰，它就有可能导致大规模、令人尴尬的失败。

幸运的是，HashiCorp 有一个由[站点可靠性工程师(SRE)](https://thenewstack.io/devops-institute-checks-the-pulse-of-sre/) 组成的团队——实际上是几个人——他们预测高流量时刻，帮助优化系统操作以处理它们，并提前询问正确的问题。

例如，据[马丁·史密斯说，](https://www.linkedin.com/in/martinbsmith/)它的一名工作人员说，“当你在 HashiConf 上宣布这个新产品时，你真正想要多少客户？”

史密斯周三在 HashiConf 的一次演讲中说，站点可靠性工程“确实需要大量的产品投入才能做好。”

Smith 和 HashiCorp 工厂可靠性工程高级经理 Patti Borne 分别在公司的核心 SRE 团队工作了三年和两年。Borne 说，核心团队由来自不同学科的人员组成，包括开发人员、架构师以及运营工程师。

“我们只是要求他们对可靠性有热情，”她说。

## 嵌入团队以发现问题

HashiCorp 于 2019 年底开始了它所谓的“生产工程”之旅。起初，伯恩告诉 HashiConf 的听众，它把 SRE 的努力集中在除了产品代码以外的所有事情上。

2020 年 6 月，其 SRE 工作也开始关注基础设施，包括公司“stack”和 HashiCorp 云平台基础设施。

一年前，该公司的 SREs 开始寻找提高开发人员生产力和增加生产时间的方法。除了核心、基础设施和开发人员生产力 SRE 团队，另一个可靠性团队与产品团队合作。

SRE 团队以多种方式工作。他们所做的事情之一是为了特定的项目与其他团队(如产品团队)合作。他们收集数据，提出问题，并帮助识别模式。

Borne 说，它给团队的 SREs 嵌入了“他们代码的另一个镜头，因为他们离它如此之近”。“有时只是第二双眼睛。”

他们还创建工具来帮助开发人员实现更好的可靠性和速度。例如，她说，“我们为他们设置了显示器，只需设置、即插即用。”

![Martin Smith, staff SRE at Hashicorp, presents at HashiConf 2022](img/c59a9f0806ba463af9130bbb019218ca.png)

HashiCorp 的员工站点可靠性工程师马丁·史密斯(Martin Smith)建议 HashiConf 全球观众:“当出现问题时，将数据放在团队面前。用自动化来做。”

Smith 说，构建解决方案是 HashiCorp 的 SREs 所做的大部分工作。他们强调自动化和减少辛劳。“我们希望我们的软件工程师编写代码来解决问题，”他说。“作为 SRE，我们希望你至少有 50%的时间花在编写代码上。”

他补充说，收集和分析关于系统和应用程序如何工作的数据，并识别可以表明效率低下或问题的模式，是 HashiCorp 网站可靠性工程方法的重要组成部分。

“让团队获得这些数据是我们工作的重要组成部分，”他说。例如，他主张“汇总这类事件的数量，并将其放在团队的前面。”这种洞察力可以帮助开发人员和工程师找到重复事件的具体元凶，并帮助他们更快地解决问题。

## SRE 核心团队如何工作

Borne 说，核心 SEO 团队花了大约 40%的时间做咨询工作，例如:

*   控制 SRE 的办公时间。
*   疑难问题的排除。
*   对从架构到服务水平目标(SLO)的所有内容进行征求意见审查。

团队另外 20%的时间花在流程改进上，包括以下任务:

*   事故管理。
*   可靠性审查。
*   提高对新出现问题的认识。

另外 20%的时间花在嵌入整个组织的项目中，处理这样的事情:

*   推出新服务
*   改善可靠性模式
*   SLO 改进

核心 SRE 团队最后 20%的时间花在可靠性工具任务上，例如:

*   创建可重复使用的监视器和组件。
*   事件工具，例如制作状态页面。
*   为自动化创建目录。

![Patti Borne, Senior manager of the Core SRE team at HashiCorp, stands in front of a slide during a presentation at HashiConf Global 2022 that explains how her team plans work. The slide reads; Planning work for an SRE Team. Product requirements, Reliabilty "maturity" list. Define projects. Org review. Execute](img/c926df7d67867cf1ccf080d71af7f39f.png)

“我们不仅仅是被动的，”Patti Borne 告诉 HashiConf 的观众，展示了 SRE 核心团队为其工程师规划工作的过程。

## 可靠性作为产品特性

史密斯说，随着 SRE 团队的建立，他们一直受到一套核心价值观的指导。定义这些价值也有助于定义团队的工作范围。

HashiCorp 的 SREs 将可靠性定义为“系统持续良好运行是值得信赖的”“在与团队交流时使用这个定义很有帮助，”Smith 说。因为不然的话，“有时候感觉什么都包括了。”

他指出，该公司有一种“一开始就对客户的需求做大量研究”的文化。伯恩说，SREs 是“房间里最后一个倡导客户体验的团队。”

SREs 将可靠性视为面向客户的产品特性，并在整个公司推广这一思路。它敦促 HashiCorp 的内部团队在设计时考虑可靠性。“我们围绕建筑产品决策进行了很多讨论，”Smith 说。

每当有东西正在建造时，它的 SREs 要求内部评论。它会问这样的问题，“你有没有想过你正在构建的架构对于维护窗口意味着什么？”

Smith 指出，“每个客户都关心可靠性。当你问‘你希望领事有什么样的特点？’他们可能不会提到这个。但我向你保证，如果停机，他们会说这是个大问题。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>