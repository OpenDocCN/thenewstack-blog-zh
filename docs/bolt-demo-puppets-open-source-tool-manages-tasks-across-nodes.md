# Bolt 演示:Puppet 的开源工具管理跨节点的任务

> 原文：<https://thenewstack.io/bolt-demo-puppets-open-source-tool-manages-tasks-across-nodes/>

带着木偶的软件工程师露西·怀曼加入了[杰克·沃伦](https://twitter.com/jlwallen)(新堆栈的自由撰稿人)和[拉维·拉赫曼](https://twitter.com/ravilach?lang=en)(harness . io 的布道者)的[螺栓](https://puppet.com/products/bolt)演示。

## 什么是博尔特？

根据 Wyman 的说法，Bolt 的核心是一个任务运行器和编排工具，用于在整个基础架构中运行特定的命令和脚本。Bolt 是开源的、无代理的，并且支持多种平台(Linux、macOS 和 Window ),使得任务的编排和自动化变得容易。Bolt 还具有以下特点:

*   分发和执行用 Bash、PowerShell、Python 等编写的脚本的能力。
*   扩展到超过 1，000 个并发连接。
*   支持行业标准协议(如 SSH/SCP、WinRM/PSRP)以及身份验证方法(密码、公钥)。

Bolt 可以轻松地修补和更新系统、排除服务器故障、部署应用程序以及停止/启动服务。Bolt 可以安装在标准工作站(Linux、Windows 或 macOS)上，并通过 SSH 或 WinRM 连接到远程节点。

通过 Bolt，管理员能够使用 YAML 文件或 Bolt 自己的编排语言，称为“计划”，允许您编写简单或复杂的计划。Bolt 的计划语言允许管理员包含 *if* 语句(为了更好地处理错误)，使得执行更复杂的任务成为可能。已经熟悉 YAML 文件的管理员可以以这种特定格式创建他们的任务，然后使用 Bolt 的内置工具将 YAML 转换为平面图。

[https://www.youtube.com/embed/vFvD5sleNQI?feature=oembed](https://www.youtube.com/embed/vFvD5sleNQI?feature=oembed)

视频

Bolt 由 Puppet 工程师创建，在一个关键方面不同于 Puppet 解决方案。Puppet 被设计成随时间管理资源(例如每 30 分钟检查一次，以确保没有任何变化或者您的基础设施没有漂移)。另一方面，Bolt 更多的是关于时间点的变化。不要使用声明性语句来说“这是我希望我的基础设施始终保持的样子”，而是使用 Bolt 来说，“此时我需要运行 X 命令或部署 X 数据库。”Bolt 使运行和/或编排任务变得简单。

通过使用 Bolt，Wyman 展示了跨三个节点执行一个简单的脚本是多么容易，使用的是 Bolt 附带的默认金丝雀计划。正如她在演示中解释的那样，她还说明了控制部署的许多方面是多么容易，例如错误处理。在简单的脚本成功之后，将 Puppet 部署到三个节点的更复杂的任务说明了 Bolt 的强大。

最后，Lucy 演示了如何通过命令行传递参数，在三个节点上打印出“Hello NewStack ”,然后解释了如何在 Bolt 计划中应用 Puppet 代码。

如果你了解 YAML，你应该不会有任何问题赶上博尔特。请访问 bolt.guide 了解更多信息。

Puppet 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>