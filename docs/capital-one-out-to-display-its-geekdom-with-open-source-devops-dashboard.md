# Capital One 通过开源 DevOps Dashboard 展示其极客世界

> 原文：<https://thenewstack.io/capital-one-out-to-display-its-geekdom-with-open-source-devops-dashboard/>

在今天的 OSCON 大会上，Capital One 将推出其敏捷团队开发的全面 DevOps 仪表板，作为其第一款开源产品。

据技术执行副总裁乔治·布雷迪(George Brady)称，它旨在成为一个可配置的仪表板，提供整个交付管道的实时状态。

[Capital One 已经接受了敏捷开发](http://www.informationweek.com/strategic-cio/executive-insights-and-innovation/capital-one-it-overhaul-powers-digital-strategy/d/d-id/1141531)，在超过 10，000 人的 IT 工作队伍中拥有超过 1，000 个敏捷团队。

“在查看可用的商业产品时，我们没有发现令人信服的仪表板。… [Capital One]已经接受了大规模敏捷、持续集成/持续交付，因此能够高效地交付软件对公司来说非常重要，”Brady 说。

特别是，该公司在 GitHub 上指出，应用程序生命周期管理工具可以帮助开发人员跟踪代码、测试和构建，但不会从构建跨越到部署；运营工具，提供对服务器和应用运行时健康和分析的可见性，但不提供开发和构建活动；虽然 Grafana 是提供通用框架来构建仪表板的工具之一，但从众多 DevOps 工具中收集数据仍然是一个挑战。

“[有了 Hygieia，]你可以看到你和你的敏捷团队在 sprint 中所处的位置，以及你在代码交付周期中所处的不同方面——代码扫描，在各种开发和测试环境中发生的部署。它让敏捷团队深入了解他们的工厂是如何运行的，并帮助他们以最佳方式工作，”Brady 说。

仪表板分为六个小部件:

*   **特色:**融合了 JIRA、云芝。
*   **构建:**其中使用了詹金斯、哈德森。
*   **代码回购:**其中使用了 GitHub，Subversion。
*   **品质:** SonarCube，黄瓜/硒。
*   **监视器**
*   **部署:**包含城市代码部署。

它还集成了 HP Fortify 以实现安全性。仪表板构建在 MongoDB 数据库上，该数据库使用一组收集器将数据提取到数据库中。它的接口用 JavaScript 编写，调用 REST APIs 从数据库中提取信息。

该项目将拥有 Apache 2.0 许可证。

Capital One 的敏捷团队将仪表板用于其最近推出的卡服务平台和更新的移动应用程序。

“我们提供了许多不同开源工具的连接器，但我们认识到，我们没有覆盖每个企业想要的每个工具，但产品中有能力让其他人为他们在企业中使用的[某些东西]贡献连接器，并将其贡献给社区，”他在谈到开源代码时说道。

该公司自 21 世纪初以来一直使用开源技术，并在过去的两到三年里向开源社区提供修复。它计划以后为开源贡献其他项目。

他说，该公司对开源项目有两大兴趣。

“我们寻找符合以下条件的项目:作为一家基于信息的公司，数据对我们运营业务的方式至关重要，因此我们参与了许多 Hadoop 和 Hadoop 生态系统项目。因此，我们将继续在那里发挥积极作用。我们同样对优质软件和快速交付感兴趣。”

除了重新推出其移动应用程序的升级版本之外，该公司还推出了数字托管快递服务，以帮助托管代理数字化管理托管和租户安全账户；首次购房者的在线信息门户网站，并将其 ShareBuilder 数字平台与其 Capital One investment Services advisor 网络合并，以创建一种融合数字工具和专业建议的服务。

在去年 10 月收购了总部位于旧金山的 UX 公司 Adaptive Path 之后，谷歌最近收购了总部位于加州奥克兰的设计公司 Monsoon，并聘请了前谷歌设计师丹·马科斯基(Dan Makoski)。

在该公司 4 月份的财报电话会议上，创始人兼董事长兼首席执行官理查德·d·费尔班克(Richard D. Fairbank)表示，该公司在数字和移动产品上的重大投资“不仅仅是与此相关的客户体验，而是数字创新背后的所有底层基础设施。”

451 Research 分析师唐尼·伯克霍尔茨(Donnie Berkholz)表示，发布仪表板也可能是一种招聘手段，就像网飞等公司所做的那样。

事实上，Monsoon 创始人 Sandeep Sood 告诉 Re/code，当员工们开会讨论收购交易时，[并不是每个人都对被一家专注于金融服务的公司收购感到兴奋。当他问有多少人认为这个行业是创新的温床时，“最初没有人举手。”然而，大多数人决定搬到首都一号。](http://recode.net/2015/07/08/capital-ones-string-of-mobile-acquisitions-turns-into-a-monsoon/)

Berkholz 说:“当开发人员开始开源他们的代码时，他们在哲学上和实践上都很欣赏它，因为这意味着他们构建的代码可以移植到他们的下一份工作中。”

在公告中，Capital One 提到了招聘潜力，称这是“向世界展示我们开发解决问题的高质量软件”，以及“成为顶级开发者社区中重要一员的旅程”

伯克霍尔茨指出，特别是在金融领域，[彭博一直积极参与开源](http://www.bloomberg.com/company/announcements/bloomberg-open-source-collaborating-better-solutions-code-management/)社区，尤其是围绕云。It
是 OpenStack 巴黎峰会设计峰会部分的主要赞助商。

“在我担任 DevOpsDays MSP(明尼阿波利斯-圣保罗)的联合组织者期间，我看到越来越多的最终用户公司希望作为赞助商参与当地的社区招聘活动，开源服务于类似的目的，具有潜在的更广泛的影响，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>