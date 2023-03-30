# 重新审视流程编排、PaaS 和新堆栈的业务

> 原文：<https://thenewstack.io/the-new-stack-analysts-show-17-revisiting-orchestration-paas-and-the-business-of-the-new-stack/>

在他们的 [2014 云客户峰会](https://thenewstack.io/centurylink-hopes-to-be-the-telco-that-makes-it-in-the-cloud-world/)上，CenturyLink 的乔纳森·金、云战略和业务发展；云平台副总裁 David Shacochis 与 New Stack Analysts 的共同主持人 Alex Williams 一起在现场观众面前录制了这一集，他们回顾并探讨了前几集首次提出的话题。

这是录音。更多信息，请查看[播客部分](https://thenewstack.io/podcasts/)。

[#17:重新审视业务流程、平台即服务(PaaS)和业务的新堆栈](https://thenewstack.simplecast.com/episodes/17-revisiting-orchestration-paas-and-the-business-of-the-new-stack)

反思从[“PaaS 世界中微服务的崛起”](https://thenewstack.io/the-new-stack-podcast-show-2-the-rise-of-microservices-in-the-paas-world/)开始，这是由 [Apprenda](http://apprenda.com) 首席执行官 Sinclair Schuller 和 DigitalOcean 的 Jeff Lindsay 以及 AppScale 首席执行官 Woody Rollins 和 New Stack Analyst 联合主持人 Donnie Berkholz 在 GlueCon 2014 上录制的。

“那是一个有趣的时期(2014 年 5 月)，”Alex 回忆道，这是一个观察“市场开始走向的时期，不仅仅是 Cloud Foundry 或 OpenShift，而是我们现在开始看到的这种全新的本土平台即服务。”Alex 提到 [Deis](http://deis.io/) 是严重依赖 Go 和 CoreOS 的平台即服务。

Jonathan 提到 CenturyLink 自己的 PaaS 世界之旅，他们收购了 AppFog，并随后将其集成到原生 IaaS 环境中。他详细阐述了播客中以 PaaS 为中心的那一集提出的一个核心问题:“IaaS 正在成为 PaaS 吗；PaaS 正在成为 IaaS 吗？还有区分吗？”乔纳森想知道亚历克斯和唐尼目前对这个问题的看法。

“房间里的大象是 AWS，”作为分析师参加活动的 Donnie 断言，“增加越来越多更高级别的服务。”Donnie 说，客户希望 PaaS 层有更多的透明度，以及更多的曝光度和灵活性，“例如能够在 IaaS 的基础上构建自己的 PaaS，并引入有趣的服务。”

Alex 认为，像 Salesforce 这样的公司，现在正在采取“移动应用程序开发方法”并“希望将这一代开发人员或准开发人员带入这个领域”，正在利用 PaaS/SaaS 组合。他说，这种新型开发人员可能更习惯使用拖放工具，而不是命令行。向“这种快速而简单的构建应用程序的方式”的演进，是新堆栈所看到和覆盖的趋势，“完全抽象了基础设施本身。”Alex 想知道这些变化对后端即服务意味着什么，以及哪些现有或未来的服务将真正构成后端。

Dave 指出，PaaS 层依赖于外部服务，例如数据存储，运行 PaaS 需要有一个可行的生态系统战略，他发现一个附加引擎如何在 PaaS 层或 IaaS 层绑定和编排外部服务非常有趣。

关于[“API 无处不在带来了什么”](https://thenewstack.io/the-new-stack-analysts-what-comes-with-api-ubiquity/)，Alex 说这个节目涉及了一个他已经思考了一段时间的概念:如今运营一个新的堆栈业务意味着什么？

“我们看到(行政部门)大量采用 SaaS 技术进行财务管理，”他举了一个例子，称首席执行官们“不得不在一个与以前完全不同的背景下考虑数据”，公司“不得不更多地考虑这些与生态系统和这些平台相关的商业问题。”

“生态系统会让你大吃一惊，”戴夫说。“生态系统中需要一些环境创造力，它们来到你的平台，做一些你可能没有想到的事情，有点像‘野花综合症’"

“平台可以让你创造出生态系统类型的效果，”戴夫继续说道，“这是生态系统发生的地方。”

亚历克斯比较了 AWS 和谷歌如何对待他们的生态系统，并表示观察 Docker 对这些已建立的关系的引力效应将是有趣的。

“波特兰的 CenturyLink Labs 真的把全部注意力放在了 Docker 上，并在那里开发了大量内容，”Jonathan 说，回忆起新的 Stack Analysts Show 7，[“Docker 的未来在于编排。”](https://thenewstack.io/the-new-stack-analysts-dockers-future-is-in-the-orchestration/)“人们倾向于将 Docker 视为一种新的虚拟化方式，”Jonathan 说。“失去的是，”他指出，“真正让它引人注目的是编排和 Docker Hub 以及所有其他属性。”

“我们开始谈论编排，这变得非常清楚，”Alex 回忆起播客对话，“编排有许多不同的风格:“ [Diego 的应用管理编排](https://thenewstack.io/docker-on-diego-cloud-foundrys-new-elastic-runtime/)，Google Kubernetes 的更通用的编排，以及 Apache Mesos，它适用于更大规模的编排。这种多样性意味着询问更多关于编排应该做什么的问题，以及关于如何管理这些容器中的应用程序数据并了解其行为方式的问题。

戴夫亲眼目睹客户面临这些难题。“除了业务流程层的所有不同潜力之外，您还拥有外形优势，这让首席信息官们很难决定:‘我该如何部署这个应用？我应该在哪一层部署它？"

他认真对待细节。“我是在裸金属云上做实验吗？我看到的是某种虚拟化容器吗？我看到的是在存储层优化的虚拟化容器吗？我看到的是码头集装箱吗？我看到的是平台即服务容器吗？”戴夫建议，拥有一个平台和一个生态系统战略是至关重要的，它可以在这些容器中的任何一个内进行协调，并在它们之间提供选项，因为答案可能是“以上所有的”。

Alex 想知道，在与这种基础设施进行对话的应用程序不断增长的过程中，开发人员与这种转换基础设施的关系将会如何。

“(就像)正在制定一项普遍政策。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>