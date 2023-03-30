# GitLab 为其 Git 管理服务增加了持续集成，并筹集了 400 万美元

> 原文：<https://thenewstack.io/gitlab-returns-4m-series-new-release-adds-continuous-integration/>

Git 存储库管理公司 GitLab 获得了 400 万美元的新一轮融资，并发布了其最新版本 GitLab 8.0，该版本速度更快，内置持续集成，使用的磁盘空间减少了 50%。该公司还为移动设备增加了“通过电子邮件回复”的功能。

> GitLab 联合创始人兼首席执行官 Sytse "Sid" Sijbrandij 表示:“在 GitLab now 中，人们合作并就代码应如何更改提出建议，持续集成允许您直接测试这些内容。

“这是 GitLab 的一个非常重要的功能，”他说。“我们认为将它直接集成到产品中是有意义的。…它将允许人们不必运行另一个应用程序。”

他还解释了它如何让产品运行得更快:

“对于 GitLab 中的每个存储库，我们都有一个附属存储库，在那里我们执行许多操作。…因为 Git 生态系统已经改进了很多，所以我们现在可以直接在 Canonical(原始存储库)上执行这些操作。这意味着我们可以摆脱所有的卫星。您节省了一半的磁盘空间，而且速度快得多，因为我们从来不需要更新卫星存储库…普通操作只需 10 秒到半秒。…卫星是一项艰巨的任务，我们真的很高兴它能如此完美地组合在一起。”

该公司表示，在内部使用 GitLab 的客户超过 10 万人，包括美国宇航局、欧洲核子研究中心、阿里巴巴、SpaceX、O'Reilly、IBM 和 Expedia。

它的产品有三种版本:免费的开源社区版、免费的 GitLab.com版和企业版。GitLab 的功能包括:

*   GitHub，Bitbucket，Google Code，Gitorious importers。
*   SAML 和 Kerberos 身份验证。
*   合并请求审批者。
*   审核日志记录。

为了提高透明度，该公司一个月前宣布将其整个开发过程转移到公开问题追踪器上。

Sijbrandij 说，反应是积极的。

“我想不出对此有任何负面的回应，”他说。“非常投入的贡献者喜欢他们能够了解发生的一切。

> “通常情况下，如果有什么需要改进的地方，我们会在公开场合提出一个问题，而在私下提出另一个问题，因为我们正在帮助客户解决这个问题。通过一个共享的问题跟踪器，每个人都可以参与。它避免了大量的重复和反复。所以整个社区都对我们开放一切充满热情。”

他还表示，他对其保护客户数据的方法充满信心:

“我们不会把客户的要求放在网上。客户请求将留在我们的支持软件中；我们放在网上的是它的要点。…我们将描述问题，以便如果其他人有类似的问题，我们可以就此进行协作。在我们发布之前，我们将会删除任何可识别客户身份的信息。”

## 新资金

GitLab 的 400 万美元资金来自科斯拉风险投资公司。两个月前，Gitlab 筹集了 150 万美元的种子资金。种子资金也来自 Khosla Ventures 以及 500 Startups、CrunchFund、阿什顿·库彻的 [Sound Ventures](http://techcrunch.com/2015/03/14/sound-ventures/) 和 Liquid 2 Ventures，后者是一家投资集团，包括前 NFL 四分卫乔·蒙塔纳。

Sijbrandij 表示，该公司正在快速增长，它需要现金来保持领先地位。该公司计划继续执行早些时候宣布的计划，扩大开发、销售和营销。这家总部位于荷兰的公司此前也宣布了在旧金山开设办事处的计划，并在种子期宣布后增加了 8 名员工，使其员工总数达到 28 人。

3 月， [GitLab 收购了竞争对手 Gitorious](https://about.gitlab.com/2015/03/03/gitlab-acquires-gitorious/) ，后者更大的项目包括 Qt、openSUSE 和 XBMC。

该公司面临来自 GitHub 及其数百万用户的激烈竞争，还面临 BitBucket、微软和其他公司的挑战。

在去年冬天关闭了 Google Code 之后， [Google 宣布带着它的云资源仓库服务](http://venturebeat.com/2015/06/24/google-has-quietly-launched-a-github-competitor-source-code-repositories/)重返这个领域。测试版允许开发者在谷歌的云平台上托管 Git 存储库，并与 GitHub 和 BitBucket 上的存储库同步。

亚马逊已经宣布了 2015 年的 [CodeCommit](http://aws.amazon.com/codecommit/) ，一个类似的源代码托管系统，以及 [CodePipeline](http://aws.amazon.com/codepipeline/) ，一个运行在云中的持续集成系统。

7 月，GitHub 宣布了一轮 2.5 亿美元的融资，使其总投资达到 3.5 亿美元。本月早些时候，它宣布将推出一项名为[受保护分支](http://venturebeat.com/2015/09/03/github-introduces-protected-branches-to-prevent-force-pushes-to-certain-parts-of-code-repos/)的功能，该功能将使存储库管理员能够禁用对特定分支的强制推送，防止它们被覆盖。

八月下旬， [GitHub 遭到了 DDoS 攻击](https://www.zdnet.com/article/github-combats-ddos-cyberattack/)，但是服务在几个小时内就恢复了。三月份的一次类似袭击持续了将近一周。

IBM 是新堆栈的赞助商。

特征图片: [sinisterbluebox](https://www.flickr.com/photos/10075621@N06/) 的[共享](https://www.flickr.com/photos/10075621@N06/3810402230/in/photolist-6NHiQb-9qyB7i-4Q93h1-9LDQtJ-8V7LDE-oNa7Yh-p7cwXH-7MXHHo-8h5YKD-4Pi2fW-pYPXbM-dz19kc-fEx24o-c46cbC-foyBt7-7G8YRv-fZwzGt-3pJxU-tiUqKb-q3WiGr-meM1zy-oFNqkn-fEzEtu-kondTU-eUst1X-8CEoyR-dXrCSR-rk4rmN-o3Hdr4-q1QVrN-3bn6sg-hxDSKy-4S6rba-fiW3GU-6m8BSu-9oZWYi-3b6CPq-4TdGsp-fiFQKV-fiFQx4-7L5Fb9-fqoQBs-pLB3nN-fgWpYS-fiFQUv-dYKZcR-6WvB7e-h3MN9t-aaFNEk-fpekjE)由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>