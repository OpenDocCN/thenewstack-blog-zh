# 幻影协调剧本自动化的安全软件

> 原文：<https://thenewstack.io/phantom-coordinates-security-software-playbook-operations/>

安全初创公司 [Phantom](https://www.phantom.us/) 解决企业在向其武库中添加越来越多的安全技术时所面临的臭名昭著的互操作性挑战。

该公司喜欢引用一份[思科的报告](http://www.cisco.com/assets/global/UK/events/switchup_challenge/pdf/cisco-msr-2015.pdf)，该报告发现普通企业使用 56 种不同的安全产品。

“所有这些都无法协同工作。大公司通过收购扩张，”幻影产品和营销副总裁 [CP Morey](https://www.linkedin.com/in/cp-morey-0bb417) 说。“你有所有这些装备。它不能互操作。它发出了大量警报。你的团队跟不上。

“由于安全人才短缺，甚至无法雇用足够的人来处理这件事。自动化是实现这一目标的唯一途径。”

例如，Phantom 的投资者之一、私募股权公司黑石(Blackstone)使用该技术来自动化其用于确定一款恶意软件是否需要采取行动的步骤:

*   确定恶意软件的所有收件人
*   使用 Active Directory 从所有受影响用户的配置文件中收集上下文
*   在对 [VirusTotal](https://www.virustotal.com/) 进行文件信誉检查和通过 [Cylance 的 Infinity](https://www.cylance.com/) 模型进行评估之前，在[炭黑](https://www.carbonblack.com/)中策划“搜索文件”行动并查询 iSIGHT Partners 的威胁情报数据库。

然后将结果提交给安全团队，由他们决定是否采取行动。

根据黑石公司的说法，这个过程用 Phantom 需要大约 40 秒，以前需要 30 到 45 分钟。

## Python 基础

Phantom 的关键是剧本和应用程序，它们都是用 Python 编写的。它所谓的应用程序将 API 抽象为各种安全产品，允许 Phantom 连接到它们。它有 100 多个应用程序，连接到 80 种不同的安全技术。行动手册是用户自动化的“配方”或说明。行动手册编写了 120 多种常见的安全操作，例如地理定位 IP、终止流程、禁用用户 ID。

诸如防火墙、端点、沙箱和目录服务之类的资产可以被配置为拥有者，无论是个人还是组，他们都会被通知所采取的操作以及围绕这些操作的上下文。然后，这些所有者可以批准、更改或拒绝这些操作。

莫雷说，政府机构往往不愿意分享他们的剧本，但大多数用户愿意。剧本在 [GitHub](https://github.com/phantomcyber/playbooks/commits/2.1) 上分享，有些用户喜欢建立自己的资源库，比如[这个](https://github.com/joelwking/Phantom-Cyber)和[这个](https://github.com/kranzrm/PhantomShodan)。

451 Research 在对 Phantom 的[评估](https://451research.com/report-short?entityId=88549&referrer=marketing&utm_source=Apply+for+Trial&utm_medium=Website&utm_term=Homepage&utm_content=Organic&utm_campaign=Market+Insight)中指出，连接所有不同的安全产品是劳动密集型的，这使得社区投入对这样一个小公司的成功至关重要。

## 自动化的兴起

“利基和单点产品安全供应商似乎前所未有地致力于实现强大的互操作性，这可能是因为客户调查指出了技能短缺、手动和复杂的工作流、海量数据、产品互操作性低以及不可持续的支出趋势，”451 Research 表示。

该公司的联合创始人在安全领域有着悠久的历史。这是连续创业者[奥利弗·弗里德里希的](https://www.linkedin.com/in/oliverfriedrichs)第四家安全创业公司。其中，Immunet 在 2010 年被 Sourcefire 收购，随后思科在 2013 年收购了 source fire。Phantom 的联合创始人兼首席技术官 Sourabh Satish 是一位多产的发明家，拥有超过 160 项专利，还有大约 60 项专利正在申请中。

这家成立于 2014 年的公司在 1 月份发布了其平台 GA，然后在三周后，在 RSA 大会上赢得了创新沙盒。

幻影与被[火眼](https://www.fireeye.com/)收购的 [Invotas](http://www.pcworld.com/article/3028963/fireeye-acquires-invotas-for-faster-incident-response.html) 等竞争；[六角石](https://www.hexadite.com/)；网络响应和[预见](https://www.forescout.com/)。莫雷说，它对社区的关注是它的主要优势。虽然 Phantom 可以在云中使用，但大多数客户端都在内部使用它。他说，它的一个关键好处是，随着运营和安全团队更加密切地合作，确保一致的移交。

根据 451 Research 的研究，Phantom 出现在一个合适的时间，人们越来越关注安全领域的自动化。它还预测幻影将是一个收购目标。

来自 Hexadrite 的一项[调查](https://www.hexadite.com/resource/security-orchestration-automation-closing-gap-incident-response/)发现，62%的受访者表示，他们的组织正在推动事件响应自动化和数据收集协调，以减少人为错误并提高他们响应事件的能力。

Phantom 是今年早些时候宣布的 [Splunk](https://www.splunk.com/) 的[自适应响应计划](http://www.businesswire.com/news/home/20160301005342/en/Splunk-Announces-Adaptive-Response-Initiative)的一部分，该计划旨在帮助组织调整其对跨多种技术的攻击的响应。

它还参与了集成自适应网络防御(IACD)项目，这是国土安全部、国家安全局和约翰霍普金斯大学之间的一项合作，旨在实现超大规模环境中的自动化安全；莫雷说，In-Q-Tel 是一家由美国政府领导的类似风险投资的组织，在有可能对国家安全产生重大影响的初创公司和联邦机构之间充当渠道。

思科是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>