# Chef 将重点转向安全性、合规性、桌面添加

> 原文：<https://thenewstack.io/chef-turns-its-focus-to-security-with-compliance-desktop-additions/>

今年的某个时候， [Chef](http://chef.io) 不再自称为“DevOps 中的领导者”，而是开始自称为“DevSecOps 中的领导者”，本周，在该公司的用户大会 [ChefConf](https://www.chefconf.io/) 上，该公司推出了许多新功能，有助于将安全性和合规性添加到其关注的焦点中，所有这些功能都以 Chef Compliance 的名义捆绑在一起。

Chef Compliance 构建于 Chef InSpec 之上，旨在帮助企业保持合规性并防止跨基础架构的安全事件，本周推出的主要新功能包括 Chef 合规性审计和 Chef 合规性补救。

“我们在四年前启动了 InSpec 项目，我们在代码中创建了这个强大的安全性和合规性验证框架，但实际上我们去年所做的工作主要围绕内容本身，”首席技术官[科里·斯科比](https://www.linkedin.com/in/coreyscobie)在接受采访时解释道。

具体来说，Chef Compliance Audit 提供了对法规遵从性状态的可见性，可以针对特定需求进行调整，而 Chef Compliance Remediation 旨在通过简化对审核期间发现的问题的补救，而无需编写代码，从而提供持续的法规遵从性。这部分是通过引入基于互联网安全中心(CIS)和安全技术实施指南(STIG)标准的审计内容来实现的。

在同一个版本中，Chef 还推出了 Chef Desktop，Scobie 说，这是在疫情期间在家订单导致远程工作增加之前很久就开始的。Chef Desktop 将 Chef 的 as-code 方法用于从一个中心位置部署、管理和保护整个笔记本电脑、台式机或工作站群的任务，并强制执行配置和合规性要求。Scobie 说，虽然公司使用 Chef Infra 完成这项任务已经有一段时间了，但现在是“开箱即用的解决方案”的时候了。

“越来越多的客户将他们的台式机、笔记本电脑和非数据中心系统视为其整体安全和合规制度的重要组成部分，”Scobie 说。“我们在某种程度上跟随了开始开发这种模式的客户的脚步，大约六、八个月前，我们意识到确实需要一个统包解决方案来大规模管理系统。”

Chef Desktop 提供了通过控制面板管理此部署的能力，并且还包括一个补救工具，该工具提供了 Chef 合规性补救工具中提供的一些相同功能，但用于边缘设备部署。Chef Desktop 提供零接触注册和配置流程、自动化软件部署、管理和策略设置，以及通过配置文件执行安全策略等功能。

最后，Chef 在其 Chef Enterprise Automation 堆栈中引入了一些应用交付特性的更新。这些更新包括对断开服务的增强分析，改进的包管理，以及 Chef Habitat 1.6 中执行快速回滚、包清理和分层容器支持的能力。

Scobey 解释说:“分层容器是一种架构，它允许您真正构建部署在边缘环境中的应用程序的增量更新，因此，您不必交付一个包含所有内容的整个容器，而是可以实际创建一个层次结构，在这个层次结构中，您可以更容易地更新容器环境中经常更改的组件。”

由 [Roman Bozhko](https://unsplash.com/@romanbozhko?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/desktop?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>