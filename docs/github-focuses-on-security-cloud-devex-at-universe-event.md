# GitHub 聚焦安全、云、DevEx

> 原文：<https://thenewstack.io/github-focuses-on-security-cloud-devex-at-universe-event/>

一年一度的 [GitHub Universe](https://www.githubuniverse.com/?false=120820&reg_type_id=120820) 大会到了，使用流行的 [git](https://git-scm.com/) 存储库托管服务的开发人员可以看到该公司为使他们的工作生活更轻松而添加的所有新功能和改进。

自去年的活动以来，GitHub 已经为超过 7300 万使用它的开发者提供了超过 20，000 个改进，GitHub 首席产品官 [Thomas Dohmke](https://www.linkedin.com/in/thomas-dohmke-24855b10/) 说。今年的重点是改善开发者体验、在云中编码和确保安全开发等问题。

Dohmke 说，安全性是 GitHub 最关心的问题，并指出该公司一直在努力提高由革命性的[GitHub Copilot](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/)AI 驱动的自动完成工具生成的代码的安全性，GitHub 将其称为“AI 对程序员”。

有报道称，Copilot 可能会生成可能引入漏洞的代码，Dohmke 告诉新堆栈，GitHub 已经采取了双管齐下的方法来解决这个问题。

“我们在 GitHub 中有一项名为 [CodeQL](https://codeql.github.com/) 的技术，它允许我们扫描代码，过滤掉安全问题，或者实际标记这些安全问题，回到用于合成代码的开源项目，”他说。“所以我们正在利用这些数据来提供越来越安全的代码。”

此外，随着时间的推移，GitHub Copilot 最终将比普通程序员编写更安全的代码，Dohmke 说。

“如果你想一想，许多程序员所做的就是进入互联网，寻找解决方案，然后复制和粘贴代码，复制和粘贴代码——类似于 Copilot 代码——可能是也可能不是完全安全的，”他说。“正如副驾驶这个名字所暗示的，是副驾驶，而不是飞行员。开发人员仍然负责理解搜索的意图。所以我们基本上采取了双管齐下的方法。一方面，我们正在让 Copilot 变得更好，我们显然在 GitHub 中提供了安全解决方案，当你提交带有不安全代码的 pull 请求时，无论是你的[GitHub]操作工作流还是你的高级安全工作流，它都会在将代码合并到主分支之前向开发人员标记问题。”

Universe 2021 的具体安全改进包括扩展代码扫描以支持 Ruby 编程，以及改进企业云访问控制。GitHub 为 CodeQL 引擎增加了 Ruby 支持，该引擎支持 GitHub 代码扫描。Ruby 加入了 C/C++、C#、Java、JavaScript/TypeScript、Python 和 Go 等支持 CodeQL 语言的行列。

同时，也是在测试阶段，GitHub 企业云客户现在可以创建自定义的存储库访问角色，为团队提供他们需要的权限，Dohmke 说。这意味着 GitHub 管理员现在可以为团队、组织成员和外部合作者创建自定义权限级别。此外，新的企业管理用户功能提供了一个管理企业身份的新选项，企业管理员可以拥有和管理身份的生命周期，同时提高供应和取消供应能力，他在一篇博客文章中说。

### 和副驾驶一起坐车

GitHub 继续利用 Copilot 的流行，在技术预览中宣布了对 JetBrains IntelliJ 编辑器平台的扩展 ide 支持，包括 IntelliJ IDEA 和 PyCharm 的最新版本，以帮助支持无论在哪里工作的开发人员。该公司还增加了对 Java 多行补全的支持，未来几个月将支持更多语言。

“好吧，我忘了我安装了 GitHub Copilot，然后去写一个函数……伙计们，我们有麻烦了。这不仅仅是它在 GitHub 上找到的某种通用的 checkForUpdates 功能。这是专门用 Gluegun 风格写的。这太不可思议了，”[无限红](https://infinite.red/)的首席技术官杰森·霍尔姆格伦在推特上说。

在[的另一条推特](https://twitter.com/__________siah_/status/1453220562403160066?t=A7wVnwa1Fc-i7DsyC-DwGQ&s=03)中，另一名副驾驶轮胎踢球者指出，“神圣的狗屎 GitHub 副驾驶很有趣！它真的加快了简单样板类的东西。我正在用 JavaScript 开发一个小游戏，核心功能用 Copilot 花了我大约 30 分钟，而不用它可能要花几个小时。我只是在捣 tab！”

多姆克说，自从今年夏天发布 Copilot 技术预览版以来，GitHub 已经有了显著的改进。他指出，对于一些语言，特别是 Python，该公司已经看到，大约 30%的新编写的代码是由 Copilot 建议的，这一数字在未来几年内可能会超过 50%。

此外，“你现在可以使用 GitHub Copilot 和 Neovim 以及最新版本的 JetBrains IntelliJ IDEA 和 PyCharm，”多姆克说。GitHub Copilot 最初是作为 Visual Studio 代码扩展提供的，或者在 [GitHub Codespaces](https://github.com/features/codespaces) 上的云中提供。

### 代码空间的增强

说到 Code spaces——GitHub 用于直接从浏览器或通过 Visual Studio 代码构建开发环境的平台——该公司在这方面提供了几项增强功能，包括更轻松的开发环境创建、CLI 支持、beta 版 REST API 支持、对转发端口的访问控制以及对 GitHub 容器注册表的访问。

“我们已经在 GitHub CLI 中添加了代码空间支持，以帮助那些喜欢命令行和直接 SSH 访问他们的开发环境的开发人员，”Dohmke 说。

Codespaces 是云中一个即时可定制的基于容器的开发环境。他说，代码空间的真正力量在于，你可以在几秒钟内从零开始变得高效并编写代码。

Dohmke 说，GitHub 在今年早些时候将其所有的工程团队迁移到 Codespaces，并将新项目的启动时间从 45 分钟缩减到 10 秒。“我们现在有超过 600 名自己的内部开发人员使用代码空间来构建云计算，”他说。

### GitHub 问题的公开测试版

此外，GitHub 已经发布了其 [GitHub Issues](https://github.com/features/issues/) 项目规划平台作为公测版。

Dohmke 说，GitHub 问题彻底改变了开发人员进行规划和跟踪的方式。它基于列表的简单思想。“我们提供了一个类似电子表格的用户界面，开发人员、项目经理和产品经理可以简单地将项目添加到待办事项列表中。它真的很快，因为你可以用光标键来完成它，”他说。

总的来说，新的 GitHub 问题工作流体验包括项目板和动态表格等功能，使开发人员能够对问题和拉式请求进行过滤、排序和分组。其他关键特性包括迭代支持、新的报告和数据可视化以及公共项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>