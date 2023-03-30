# 为什么亚特兰蒂斯如此失败

> 原文：<https://thenewstack.io/why-atlassian-failed-so-hard/>

4 月 4 日[，Atlassian 的网络服务因约 400 名客户](https://thenewstack.io/the-atlassian-outage-just-keeps-going-and-going-and/)或 5 万至 40 万用户而中断。到目前为止，那又怎么样，web 和云服务一直在下降。这一点都不好玩，但它确实发生了。但是这一次，[号和](https://www.atlassian.com/)号的灾难持续不断。10 天后，一些用户仍然无法访问吉拉软件、吉拉工作管理、吉拉服务管理、Confluence、Opsgenie Cloud、Statuspage 和 Atlassian Access。

由于 Atlassian [吉拉的市场份额刚刚超过 bug 和问题跟踪市场](https://www.slintel.com/tech/bug-and-issue-tracking/atlassian-jira-market-share#tech_section_6)的 84%，这真的很烦人。我是说，Atlassian 的业务就是追踪 bug！而且，在很长一段时间里，Atlassian 对这个问题几乎没有什么可说的。第一条评论是两天后发出的，内容很少，“在运行维护脚本时，一小部分网站被无意中禁用了。我们对这一事件造成的挫折感到抱歉，我们将继续通过各个阶段进行恢复。”

## 不是网络攻击

然后，是一片寂静。Atlassian 首席执行官斯科特·法夸尔(Scott Farquhar)在一份据称来自 Atlassian CEO [的声明中表示:“周二上午(太平洋时间 4 月 5 日)，我们进行了一次维护程序，旨在清理遗留功能中的旧数据。因此，](https://www.linkedin.com/in/scottfarquhar/?originalSubdomain=au)[一些网站被意外停用](https://www.reddit.com/r/jira/comments/txz2be/jira_has_been_down_for_days_what_the_fuck/i3yscd5/)，这将使您和我们的一小部分客户无法访问我们的产品。我们可以确认这一事件不是网络攻击的结果，也没有未经授权访问您的数据。”

这是必须的:“T12 这是我们的首要任务 T13，我们已经动员了整个组织的数百名工程师夜以继日地工作来纠正这一事件”。

为什么沉默对待？开发者兼作家 Gergely Orosz(T1)认为，部分原因是，“ [Atlassian 的员工和客户将注意力转向 Atlassian 的年度旗舰活动](https://newsletter.pragmaticengineer.com/p/scoop-atlassian?s=r)、 [Team 22](https://events.atlassian.com/team22) 。在拉斯维加斯举行，许多公司员工、大部分领导团队和许多 Atlassian 合作伙伴亲自前来参加活动。”尽管系统出现故障，Atlassian 似乎仍然专注于第 22 队。

受影响的亚特兰蒂斯顾客并不高兴。一个人在推特上写道，“那里发生了什么？这不是一个几分钟或一小时停机的小问题，[合流和吉拉是字面上的停机一整天](https://twitter.com/gabornadai/status/1511421761690214413?s=20&t=3n6vxxzpCi84IEdm6YLfiw)

然而，亚特兰蒂斯人仍然保持沉默。最后，在 4 月 12 日，Atlassian CTO[Sri viswa Nath](https://www.linkedin.com/in/sriviswanath/)给出了一些关于问题所在的[细节。](https://www.atlassian.com/engineering/april-2022-outage-update)

## 哪里出了问题

该公司已经停用了其独立的遗留应用程序“Insight-Asset Management”，用于客户网站上的吉拉服务管理和吉拉软件。这一过程因为两个关键问题而严重出错:

*   沟通隔阂。首先，请求取消激活的团队和运行取消激活的团队之间存在沟通障碍。该团队没有提供被标记为停用的应用程序的 id，而是提供了应用程序将被停用的整个云站点的 id。
*   错误的剧本。其次，我们使用的脚本既提供了在日常操作中使用的“标记删除”功能(在需要可恢复性的情况下)，又提供了“永久删除”功能，在出于法规遵从性原因需要时，这是永久删除数据所必需的。脚本是用错误的执行模式和错误的 id 列表执行的。结果是大约 400 个客户的网站被不恰当地删除了。

但是 Atlassian 没有备份吗？是的，他们做到了。他们在多个 AWS 可用性区域(AZ)中维护了一个同步备用副本，并维护了独立的不可变备份，旨在支持恢复到以前的时间点。

## 杂乱的备份

那么，有什么问题呢？简而言之，备份很混乱。

如果他们从检查点进行恢复，这 400 名陷入困境的客户将恢复他们的数据，但其他所有人都将丢失自备份以来的所有数据。因此，Atlassian 必须手动从备份中提取数据。

Viswanath 解释说，“我们(还)没有自动化的是在不影响任何其他客户的情况下，将大量客户恢复到我们现有的(和当前正在使用的)环境中。”

他们现在正在实现自动化，但即便如此，速度还是很慢。“目前，我们正在分批恢复客户，每次最多 60 个租户。端到端地，将网站交还给客户需要 4 到 5 天的时间。我们的团队现在已经开发了并行运行多个批处理的能力，这有助于减少我们的总体恢复时间。”

最后，Viswanath 承诺，“我们将进行事故后审查，并分享我们的调查结果和后续步骤。这份报告将会公开。”与此同时，其余停止服务的公司对失败和 Atlassian 糟糕的通信都感到不满。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>