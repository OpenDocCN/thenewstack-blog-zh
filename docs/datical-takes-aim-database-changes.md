# Datical 的目标是为数据库带来 DevOps 速度

> 原文：<https://thenewstack.io/datical-takes-aim-database-changes/>

尽管有各种 DevOps 工具来提高构建、测试和部署应用程序的速度，但自理查德·尼克松(Richard Nixon)入主白宫以来，企业对数据库进行更改的方式基本上没有改变。

总部位于德克萨斯州奥斯汀的自动化供应商 Datical 旨在通过数据库更改代码可以像应用程序代码一样处理的概念，为数据库管理过程带来更大的清晰度和速度。

“虽然组织只需按一下按钮就能更快地发布应用程序是件好事，但这真的没那么简单。他们必须找到一种方法来确保应用程序更新中的每个数据库变化都与应用程序本身保持同步，而这不是今天正在发生的事情，”Datical 营销副总裁[本·盖勒](https://www.linkedin.com/in/bgeller/)说。

传统上，开发人员编写脚本来对模式或逻辑进行修改，这些修改必须由 DBA 进行审查。这对开发人员来说产生了几天或几周的“等待状态”,他们在此期间开始做其他的事情，然后不得不被打断，回到最初的变更请求。Datical 解决了这个“速度差距”

它在今年早些时候进行了一项调查，其中 91%的受访者报告说更新和其他数据库更改会延迟应用程序发布时间，67%的数据管理员说该过程需要更长时间，大多数人报告说更改的数量正在增加。

其最新产品[部署监控控制台](http://www.datical.com/press-release/delployment-monitoring-console-to-further-expand-devops-to-the-database/)，将所有关于数据库和项目的信息整合到一系列基于角色的仪表板中。

“为了了解[客户]是如何管理变更的，我们会问，‘数据库最近的四五次变更是什么？’他们会通过售票系统、电子表格或电子邮件来查找信息。然后我们问，“执行了哪些脚本？”Datical 联合创始人兼产品战略副总裁 Pete Pickerill 解释道。

然后他们必须去找到脚本，打开它们告诉他们做了什么。他们不能告诉你他们遇到的问题，因为他们当场就解决了问题，而且没有相关记录。

他们需要花费数小时甚至数天的时间来获取他们所拥有的信息。

因为许多人需要深入了解公司的数据库操作，所以监控仪表板提供了三种不同的视图:

*   企业级:对企业中所有数据库正在发生的事情的概述。
*   项目层面:洞察具体项目和管道。
*   部署级别:提供有关每个数据库部署的特定详细信息的报告。

Datical 不仅收集了关于每个部署的大量信息，还收集了软件交付生命周期中的变更流程。

Datical 的其他产品包括:

*   **数据库代码打包器** —它允许团队将他们的 SQL 脚本签入应用程序的源代码库，使开发人员能够像创建应用程序代码一样创建、分支和合并代码。它检索、验证和标记数据库更改，从而可以轻松地将更改追溯到相应的应用程序任务或业务需求。
*   **动态规则引擎—** 有点像 DBA 遇到人工智能，规则引擎确保提议的数据库代码更改符合公司标准、公司合规性要求，并且不会使数据面临安全风险。
*   **变更管理模拟器** —它创建了一个数据库的数字副本，在其上模拟提议的变更，并在这些变更部署之前预测它们的影响。开发人员可以立即获得反馈，减少审查脚本的等待时间。

Datical 意味着一旦使用现有工具进行部署，它就会退居幕后——有针对 Jenkins、Puppet 和其他持续集成/持续部署软件的插件。

https://www.youtube.com/watch?v=o_7EQY3E24o

它可以在 Linux 和 Windows 上运行，包括 Oracle、SQL Server、DB2 和 Postgres 的商业变种 EnterpriseDB。其客户包括通用运输公司、索尼 NBC 环球公司和 LabCorp。

据该公司称，虽然大多数客户在内部使用它，但云部署的数量正在增长。

“我们能够展示我们如何使用客户已经拥有的现有工具和流程，因此当企业采用 Datical 时，他们不必做任何不自然的事情，也不必发明一种新的方法来处理数据库或如何部署更改，”盖勒说。“这真的成了他们今天所做事情的一部分。”

在一份关于[应用发布自动化](https://offers.automic.com/ppc/gartner-critical-capabilities-for-ara-tools-report-ara)解决方案的报告中，Gartner 敦促供应商优先考虑组织中不同角色的易用性，并与现有的开发和 IT 运营工具集成。

这份报告涵盖了诸如 [Automic](https://automic.com/) 、 [Xebia Labs](https://xebialabs.com) 和 [CA Technologies](http://www.datical.com/press-release/datical-announces-integration-with-ca-automic-release-automation/) 等公司，这些公司最近成为了正式合作伙伴。数据库部署自动化方面的对手包括 [DBmaestro、](http://www.dbmaestro.com/) [Redgate](http://www.red-gate.com/products/dlm/dlm-automation/) 和 [Liquibase](http://www.liquibase.org/) 。 [DBDeploy](http://dbdeploy.com/) 是一个开源的部署项目。

CA Technologies 是新堆栈的赞助商。

特征图片:Jaro 的“ [DSC03575](https://www.flickr.com/photos/superselect/14436735487/in/photolist-nZJ3ux-9Tnbzy-8nzWnC-axd8cp-957Lf6-9Tnfxm-9TjoHX-eZ8tkW-bUwG37-9TjpeX-9TnfCq-9Tjqrn-axdaNH-nZH4si-axdeiR-9TnfrG-h3ySrk-9Tnbus-9TjmJZ-awEVfs-9TnbGq-9TexB2-g8FuQa-cvR9yW-bxBfFv-dUApSo-bxBatc-g8Gmb2-ViMBU4-g8FPAf-g8FMgs-g8G6La-g8FAwu-bxB4mx-5dopRY-SsdWqP-6MepGL-95aQ5C-g8Fy7R-g8FtzK-g8FJgs-g8FNnd-ryw5gm-957LfF-95aQ6o-g8Fx23-g8FwZk-bjG9XU-g8Fz6e-bxBaR6) ”，在 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>