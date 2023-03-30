# BluBracket:抓住开源代码

> 原文：<https://thenewstack.io/blubracket-getting-a-grip-on-open-source-code/>

新冠肺炎的关闭只是加剧了企业的恐惧，他们担心在不断增长的 git 开发世界中失去对源代码的控制。只需按下按钮，多年来创造知识产权的发展成果就可以释放出来。

[星巴克](https://www.bleepingcomputer.com/news/security/starbucks-devs-leave-api-key-in-github-public-repo/)、[亚马逊](https://www.theregister.co.uk/2020/01/23/aws_engineer_credentials_github/)、[优步](https://www.theregister.co.uk/2018/02/07/uber_quit_github_for_custom_code_after_2016_data_breach/)、 [Capital One](https://www.zdnet.com/article/github-sued-for-aiding-hacking-in-capital-one-breach/) 、[微软](https://www.zdnet.com/article/hacker-gains-access-to-a-small-number-of-microsofts-private-github-repos/)和其他公司最近都经历了与 GitHub 、GitLab 和 BitBucket 等 git 库[相关的漏洞，更不用说黑帽安全会议上的争议了，当时研究人员鲁本·桑塔玛塔(Ruben Santamarta)发布了一篇](/github-open-source-projects-entangled-by-the-octopus-malware-scanner/)[论文](https://www.pcmag.com/news/security-researcher-says-he-cracked-787-airliner-but-boeing-faa-disagree)，称他能够使用“一些聪明的谷歌查询”侵入波音 787 梦幻客机技术(波音【T14

开发人员过去常常在一个特定的物理环境中工作，对单一的源代码库进行锁定访问。公司拥有开发人员工作的机器，并严格控制对代码的访问。

现在，特别是在过去的几个月里，开发人员在家里，在他们自己的机器上工作，“所以人们争先恐后地找出不中断业务的选项……他们需要一种能够在这些远程环境中安全地开发的方法，特别是在这种新的范式中,[负责解决源代码安全问题的](https://www.linkedin.com/in/akaroraka/) [BluBracket](https://blubracket.com/) 的联合创始人兼总裁兼首席运营官 Ajay Arora 说。

虽然公司曾经依赖 VPN 使员工能够远程登录，但它们是决定谁可以访问中央代码服务器的时间点控制。但是一旦代码被克隆到一个端点或者一台开发人员的机器上，“秘密就泄露了。”

“过去非常集中的东西现在已经合并成一种非常协作的体验，开发人员现在可以完全以分布式方式开发，可以拉动并促进开源。就源代码的处理方式而言，它甚至接管了世界上最安全的公司，”阿罗拉说。

他说，在过去的几年里，企业越来越关注这个问题，新冠肺炎在家工作的订单为解决这个问题提供了新的动力。

Linux 基金会的核心基础设施项目(CII)在二月份发布的 T2 人口普查二报告(T3)中发现，在其分析中，10 个最常用的软件包中有 7 个是由个人开发者账户托管的。

“如此严重依赖个人开发者账户的后果不容忽视，”报告警告称。

“软件驱动着从选举到核潜艇的一切，但我们不知道代码在哪里，它来自哪里，其中有什么秘密，谁可以访问它。而且可以一键公开分享。这让我们所有人都处于危险之中，”[联合创始人兼首席执行官 Prakash Linga](https://www.linkedin.com/in/prakashlinga/) 在[博客文章](https://www.linkedin.com/pulse/its-time-get-serious-code-security-prakash-linga/)中写道。

这绝不是唯一一家专注于管理源代码的公司。以稍微不同的方式，以色列初创公司 [Intezer](http://www.intezer.com/) 使用机器学习来识别攻击中使用的代码的[来源。而](https://thenewstack.io/intezer-provides-code-dna-mapping-root-malware/) [source{d}](https://www.linkedin.com/company/source-d/) ，一家专注于在源代码之上应用机器学习的初创公司，从 5700 万个公共 git 存储库中挖掘数据，以帮助公司[了解他们的代码](https://thenewstack.io/sourced-applies-machine-learning-help-companies-manage-code-base/)在哪里以及正在发生什么。

## 能见度，行动

Arora 和 Linga 之前开发了 Vera 软件，用于保护和跟踪跨平台和设备的数字信息。

总部位于加州帕洛阿尔托的 BluBracket 提供了两种可以一起使用或单独使用的产品。CodeInsights 使用户能够创建所谓的代码蓝图，确定他们的代码在哪里以及谁可以访问它。他们可以根据关键程度对代码进行分类，并提供详细的监管链以满足法规遵从性或审计要求。

“理解发展的模式和理解一段时间内会发生什么是极其重要的，”他说。

BluBracket 可以检测秘密、错误配置和其他风险，以确保敏感密码或令牌不被滥用。用户可以创建代码和代码片段指纹，用于持续跟踪和报告。

CodeSecure 使用户能够根据他们的代码分类设置适当的策略，并围绕警告和阻止渗漏来实施这些策略。

他说，公司可能不一定想要封锁一切，但他们希望制定政策来保护业务，同时消除开发人员工作流程中的摩擦。

“所以你可以把它看作一系列同心圆……蓝图实际上是你对代码在哪里、代码发生了什么以及谁在任何时候都可以访问你的代码的可见性，”阿罗拉说。

“我们在开源环境中找到你的代码了吗？是否有人访问了不应该访问的代码？有没有开发人员突然下载了一堆他们不应该下载的代码？因此，所有警报和围绕这些警报的主动补救是我们解决方案的另一部分。”

“代码的重要性和部署速度只会越来越快。BluBracket 在开发和安全方面的知识已经转化为一种产品，可以保护我们业务的这一重要方面，”神奇宝贝国际公司的数据保护官 John Visneski 说。

## 没有增加摩擦

Arora 将传统的数据丢失防护(DLP)工具描述为“几乎能够阻止不同数据从人们的设备中渗透的大锤”，尽管这些供应商正在试图改造他们的产品以适应这一新的现实，但他们太粗糙了，无法理解敏感 PII(个人身份信息)和源代码之间的差异。

“要让这些工具有效工作，它们必须与 git 协同工作。他们不得不使用开源软件，他们不希望在代码速度上增加任何摩擦。

当(传统的 DLP 工具)在文件层面应用时，它们真的无法区分什么是开源，什么不是，什么是文本文件或代码文件，它们在与开发人员工作流共存方面一直相当不成功，他说。

BluBracket 最近获得了由 unregular Ventures 牵头的 650 万美元的种子轮投资，参与投资的有 Point72 Ventures、SignalFire 和 Firebolt Ventures。

全球战略咨询公司 [OODA](https://www.oodaloop.com/archive/2020/03/11/the-2020-ooda-cybersecurity-watch-list/) 最近将 BluBracket 评为最有潜力扰乱网络安全市场并提高组织管理网络风险能力的科技公司之一。

它是 2 月份 RSA 大会沙盒创新大赛的前 10 名入围者之一。你可以在这里找到它的三分钟演讲:

[https://www.youtube.com/embed/c6MOfJ7ISwU?feature=oembed](https://www.youtube.com/embed/c6MOfJ7ISwU?feature=oembed)

视频

BluBracket 在 Google Cloud 上作为 SaaS 提供，也作为内部部署的自我管理版本。

GitLab 和 Linux 基金会是新堆栈的赞助商。

来自 Pixabay 的 Pexels 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>