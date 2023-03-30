# Accurics 通过政策即代码保护云基础设施

> 原文：<https://thenewstack.io/accurics-secures-cloud-infrastructure-through-policy-as-code/>

首席执行官兼联合创始人 Accurics， [Sachin Aggarwal](https://www.linkedin.com/in/sachinyaggarwal/) 谈到了“不可改变的安全性”，这似乎与云原生技术不断变化的本质不符

它基于不可变基础设施的思想，在这种基础设施中，不是对部署进行更改，而是启动一个新的实例。****

正如[德勤咨询](https://www.linkedin.com/in/michael-liedike-3791b531/)的创新和平台团队经理[迈克·李代克](https://www2.deloitte.com/global/en/services/consulting-deloitte.html)在最近一期的 [The New Stack Makers](https://thenewstack.io/why-well-oiled-devops-rides-on-immutable-infrastructure/) 播客中描述的那样:

“不可变的基础设施使您能够在整个系统群中拥有一致的环境，这使您的部署更简单、更可预测。它允许您更加一致地进行测试，并从开发到测试再到生产提升您的环境。”

Accurics 的平台利用基础设施作为代码，在整个云原生体系(包括无服务器、容器、服务网格等)中实现策略、安全性和补救措施的标准化。

## 从代码到产品

总部位于加利福尼亚州普莱森顿的 Accurics 成立于 2019 年，4 月份从 stealth 中走出来，宣布获得 ClearSky，WestWave Capital，Firebolt Ventures 和 Secure Octane 的 500 万美元投资。

这是一批创业公司中的一部分，他们接受了新基础设施的[安全和治理挑战](https://thenewstack.io/why-the-age-of-the-cloud-native-security-platform-is-here-to-stay/)，包括[护栏](https://thenewstack.io/guardrails-security-for-the-devops-age/)； [Octarine](https://thenewstack.io/octarine-offers-a-platform-for-securing-kubernetes-workloads/) ，被 VMware 收购；和 [EnvO](https://thenewstack.io/env0-self-service-for-infrastructure-as-code-plus-cost-visibility/) 。例如，旧金山的原子学家正在研究云漂移的问题。

Accurics 的客户包括点对点借贷网站 [Lending Club](https://www.americanbanker.com/news/lendingclub-reinforces-its-cyber-defenses) 、IT 服务提供商 [Unisys](https://www.unisys.com/) 、现场服务技术供应商 [ServiceMax](https://www.servicemax.com/) 以及航运跟踪公司 [Roambee。](https://www.roambee.com/)

“我所说的不可变安全性有两点:你需要处理整个堆栈。不应将其视为修补解决方案或单点解决方案。但它应该被认为是…你的基础设施层，你的网络存储和计算，你的编排平台，你的服务器层和服务网格层，”Aggarwal 说。

“其次，你应该考虑从代码到云的安全性，因为正如我们所知，人们正在使用基础设施自动化工具，如 Terraform、Ansible 等。]所以你必须对你的代码和云进行代码和治理的评估。

“一旦你在云中建立了对代码的信任，那么你就不应该偏离这种姿态，这意味着当人们做出改变时，从代码到云的信任会得到保持。”

Alcide 联合创始人兼首席技术官 [Gadi Noar](https://twitter.com/gadinaor?lang=en) 最近指出了持续集成(CI)和持续交付(CD)的不同安全需求，为[在 CD](https://thenewstack.io/ci-checks-are-not-enough-combat-configuration-drift-in-kubernetes-resources/) 中使用 Kubernetes 的安全特性提供了理由。

Aggarwal 认为，安全性必须从代码开始，并在生产中持续监控，以确保应用程序不会偏离基线代码和策略护栏。

## 设定基线

Accurics 最初在定义为代码的整个堆栈中创建实时拓扑，以识别要解决的问题。一旦完成，这将成为用于实施安全和治理策略的基线。

Accurics 称之为政策即代码。

“策略即代码是您定义所有安全需求的地方，并且您以一种您可以在您的开发团队编写代码时正确评估[安全和治理问题]的方式对它们进行编码。Accurics 的开发人员宣传主管 Caesar Rodriguez 解释说:“当他们将基础设施编写为代码时，您就向他们提供了反馈，这样他们就能够在开发生命周期的一部分修复代码。

通过其配置管理数据库，Accurics 持续扫描代码文件，如 Terraform、Kubernetes YAML、Dockerfile 和 OpenFaaS YAML，以查找错误配置和违反常见合规性和网络安全实践的情况，包括 SOC 2、GDPR、PCI、HIPAA、ISO、CIS 基准、AWS 最佳实践。

它还识别身份访问和管理角色，并标记过于宽松的实例。

该公司最近的 [发展状况](https://start.accurics.com/CT-2020-05-Research-Report_LP-Reg2.html) 报告指出，公司仅解决了 4%的云错误配置，威瑞森在其最新的[数据泄露报告](https://enterprise.verizon.com/resources/reports/2019-data-breach-investigations-report.pdf)中发现这个问题正在增长，并且是导致漏洞利用的主要问题之一。

Aggarwal 将这种低比率归因于进行修复的时间和费用，但也担心改变一个东西会破坏其他东西。

最近，它还把它的补救功能标榜为代码功能。除了在早期提醒开发人员注意问题之外，它还会持续监控运行在 AWS、Azure 或谷歌云平台上的应用程序的配置变化。系统根据 IaC 基线绘制变更图，评估其风险，并向相关人员发出警报。

使用 Slack、JIRA、Splunk、webhooks 或电子邮件发送的警报不仅识别问题，还识别将修复问题的代码。Aggarwal 说，这是为了帮助减轻在修理时对打破东西的恐惧。

人类仍然必须确定这是好的还是坏的变更，然后可以更新基线代码以反映合法的产品变更，或者回滚到最近已知的安全版本。

Rodriguez 对快速反转的需求有一些经验:

“在几年前的一个项目中，我们的重点是确保安全控制在云环境中自动应用，”他回忆道。“由于我们不关心开发团队试图做什么，我们只是直接改变云。

“我们试图实施的控制措施之一是静态加密，我们自动部署了它。我们意外删除了一个生产数据库，这是一件大事，尽管我们能够快速恢复。”

他说，向开发团队提供反馈是一个更好的方法，可以直接集成到开发人员正在使用的工具以及安全编排和自动化工具中。

## 使用上下文进行补救

“如果你自动修复，但你没有在你试图建立的环境中这样做，这可能是危险的，”他说。“如果您正在生成如何将其应用于您的基础设施的代码，它会为开发团队提供一个更好的画面。这是一种学习[体验]。从长远来看，这将有助于你的公司变得更好，因为你不会做出可能损害环境的改变。”

该平台还具有违规路径预测功能，使用通过分析漏洞馈送、访问权限和其他数据开发的威胁模型来检测和关闭基础架构代码中的潜在暴露路径。

展望未来，Aggrawal 表示，该公司计划专注于三个领域:深入到堆栈的每一层，根据客户的架构提供更多的风险管理，并通过让用户更好地了解不同资源之间的关系和依赖关系来改善违规预测。

Accurics 的联合创始人兼首席产品官 Piyush Sharrma ，最近发表了关于[基础设施作为代码的顶级安全风险](https://thenewstack.io/author/piyush-sharrma/)的帖子。

“保护云基础设施非常复杂，因为涉及到越来越多的依赖关系，并且不同的参与者使用不同的工具来保护它，”企业管理协会的研究总监[保拉·穆奇](https://www.enterprisemanagement.com/about/team/Paula_Musich.php)说。“尽管许多初创公司和成熟的安全供应商正在试图解决具体问题，如扫描可重复使用的代码以查找漏洞，或管理对应用程序和数据的访问，但需要不同控制台的零敲碎打的方法只会增加混乱。”

“我们需要一个工具来管理开发运维生命周期早期的风险和政策违规，并确保开发人员想要的原始配置在离开他们的手并投入生产后仍然真实(和安全)。这是 Accurics 正在解决的更广泛的问题，它应该会让 it 高管对他们妥善保护云基础架构的能力更有信心。”

Accurics 是新堆栈的赞助商。

专题图片:[布拉德·帕雷特](https://www.flickr.com/photos/bradparrettphoto/)的[烟花](https://www.flickr.com/photos/bradparrettphoto/34794416986/in/photolist-V1EtX9-LM2fgS-ZTYmS2-25iHxzz-s6a1gw-6NAcR-4cBfEH-2hPnnwV-2i7NVh4-6FD931-4Ktsw3-wNVd1-p9nU2-hrvkCe-6yn4mM-93cZi8-LMq7x-8XBWh1-nfdMeD-9sg6L-uunK-agKych-7fRrXo-9eHb3U-p8oZLx-agKzru-iu69AB-hruPdh-fbTE-hrvqSn-hruN55-7MYzUf-22eBV14-K1tc5F-N38uHa-aZfPx6-p9ohg-2bzrPwy-962ach-fH9kzq-3eWCre-6bjVi4-LXBa2t-5w7NTn-4rRmVH-5SxDcY-yeizWS-63PzHo-azpr5d-j4yhB4)。根据 CC BY-SA 2.0 获得许可。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>