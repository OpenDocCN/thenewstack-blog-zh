# 是时候让网络攻击数据正常化了

> 原文：<https://thenewstack.io/its-time-to-normalize-cyberattack-data/>

这里有攻击，那里有攻击，到处都有攻击。如今，仅仅跟踪安全问题就已经够痛苦的了。更糟糕的是，协调攻击数据几乎没有任何意义或理由。一个网络安全和技术团体的联盟希望通过开源努力打破数据安全孤岛来解决这个问题:开放网络安全模式框架(OCSF)。

如今，安全组织没有一种通用语言来讨论他们面临的威胁。我们知道这个问题已经存在很长时间了。之前也有过修复的努力，比如[MITRE](https://attack.mitre.org/)Att&CK 框架，但是还需要做更多。

## 在黑帽发布

因此，在 [Black Hat USA 2022](https://www.blackhat.com/us-22/) 、 [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) (AWS)和 [Splunk](https://www.splunk.com/) ，在 Broadcom/ [Symantec 的 ICD 方案](https://icd-schema.symantec.com/)工作的基础上，创建了一个方案来帮助组织更快、更有效地检测、调查和阻止网络攻击。他们不是唯一支持 OCSF 的人。其他 15 家公司——cloud flare、CrowdStrike、DTEX、IBM Security、IronNet、JupiterOne、Okta、 [Palo Alto Networks](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 、Rapid7、Salesforce、Securonix、Sumo Logic、Tanium、Trend Micro 和 z scaler——也支持该项目。

为什么有这么多支持？简单。Rapid7 负责检测和响应的副总裁 Sam Adams 在一篇博客文章中解释道:“有效检测和快速响应当今威胁和攻击的关键是数据以及如何使用这些数据。”

但是，说起来容易做起来难。这是因为 AWS CISO 办公室主任马克·瑞兰德(Mark Ryland)写道:“(T2)安全产品之间的互操作性和数据标准化是一个挑战。安全团队必须以一系列专有格式关联和统一来自不同供应商的多种产品的数据；这项工作的成本越来越高。安全团队不再主要关注检测和响应事件，而是花时间将这些数据规范化，作为理解和响应的先决条件。”

因此，Ryland 继续说道，“我们相信使用 OCSF 模式将使安全团队更容易从不同来源获取和关联安全日志数据，从而实现更高的检测准确性和更快的安全事件响应速度。”

## 框架

为了实现这一点，OCSF 是一个开源项目，致力于创建一个开放标准。其目的是提供一个简化的、独立于供应商的分类法，帮助所有安全团队实现更好、更快的数据接收和分析，而无需耗时的前期标准化任务。

为此，OCSF 由一组数据类型、一个属性字典和一个分类法组成。虽然不限于网络安全，但其最初的重点是为网络安全事件建立一个模式。该框架与存储格式、数据收集以及提取、转换、加载(ETL)过程无关。网络安全事件的核心模式与模式框架定义文件的实现无关，其规范模式被写成 JSON。更多关于 OCSF 的技术细节，请看[了解](https://github.com/ocsf/ocsf-docs/blob/main/Understanding%20OCSF.pdf) [OCSF](https://github.com/ocsf/ocsf-docs/blob/main/Understanding%20OCSF.pdf) 。

## 纳入标准

希望作为一个开放的标准，它能被现有的安全标准和流程所采用和使用。然后，随着开发人员和用户将 OCSF 整合到他们的产品和流程中，安全数据标准化将变得更简单，负担也更轻。反过来，这将使安全团队能够更好地分析攻击数据，识别威胁，并保护他们的组织免受网络攻击。

最后，Cloudflare 的首席技术官 John Graham-Cumming 在一份声明中说，“每个企业都应该有一种简单、直观的方式来分析和了解安全形势，而这要从他们的数据开始。通过参加 OCSF，我们希望帮助整个安全行业专注于做重要的工作，而不是浪费无数的时间和资源来格式化数据。”

我希望这是真的。我讨厌浪费时间。当我们处理安全问题时，时间是永远不够的。如果 OSCF 能够成功实现其目标，这将是在处理大规模安全问题方面向前迈出的一大步。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>