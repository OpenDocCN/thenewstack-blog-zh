# Sudo Update 提供 Python 插件、扩展日志、审计

> 原文：<https://thenewstack.io/sudo-update-offers-python-plug-ins-extended-logging-auditing/>

最初是“超级用户 do”的简写， [Sudo](https://www.sudo.ws/) 是任何使用过基于 Linux 或 Unix 的操作系统的人都熟悉的一个命令，但是现在，这个最初在 40 多年前由纽约州立大学水牛城分校开发的项目远远不只是作为根用户运行命令的一种方式。对这个组合词的另一种解释是“替代用户做的”，它更接近地描述了这个项目的现代功能，尽管它仍然有所欠缺。

在过去的 25 年里，[托德·米勒](https://www.sudo.ws/todd)一直是 Sudo 项目的维护者，该项目由他的雇主 [One Identity](https://www.oneidentity.com/) 赞助了近十年，根据[项目的历史页面](https://www.sudo.ws/history.html)，该项目“增加了 I/O 日志记录、插件接口、额外的回归测试、对二进制包和更多常规版本的支持。”

当 Miller 接任维护者时，Sudo 是 1.3 版本，本周发布了 Sudo 1.9，它提供了许多关于集中式日志记录、审计和命令批准的增强功能，以及用 Python 而不是 c 编写第三方 Sudo 插件的能力。

正如 Sudo 最新版本中提供的改进所暗示的那样，该项目不仅仅允许单用户 Linux 操作者安装软件包或删除文件，否则他们可能无法删除。相反，米勒说，Sudo 长期以来一直被企业和其他大型组织用来“提供更细粒度的控制，并控制谁被允许做什么以及拥有哪些特权。”事实上，除了开源的 Sudo 项目，One Identity 还提供了一个商业项目，Sudo 的[特权管理器，这是该公司更广泛的 Unix](https://www.oneidentity.com/products/privilege-manager-for-sudo/#) 特权访问套件和身份访问管理(IAM)产品的一部分。

关于 Sudo 1.9，Miller 解释说，主要特性之一是集中日志记录，它扩展了 Sudo 1.8 中引入的记录击键和相关输出的特性，包括一个可以用来合并和简化日志记录的日志服务器。Sudo 1.9 还引入了即时命令批准，这使管理员可以选择为 Sudo 命令启用即时授权，以及丰富的审计，这允许第三方软件提供商使用审计插件来编写第三方插件，以从 Sudo 会话中提取详细数据。

然而，除了这些特性，One Identity 的高级产品工程师泰勒·里斯(Tyler Reese)说，增加 Python 作为 Sudo 插件的支持语言确实是一个关键点。

“我总是开玩笑说 Todd 在 C 中生活和呼吸，但大多数玩这个的 IT 人员都不这样。我认为，当我们将它转移到 Python 时，它确实使编写插件的能力民主化，因为这只是 it 分析师和安全分析师用户角色的选择语言，”Reese 说。

里斯说，到目前为止，为 Sudo 编写的插件数量屈指可数，尽管他说支付应用 [Square](https://squareup.com/us/en) 也在其中，它在 Rust 中编写了一个 Sudo 插件，以帮助它满足各种合规要求。Reese 说，在未来，One Identity 希望成为 Sudo 新插件的集中中心，他预计随着 Python 支持的引入，Sudo 将会发展壮大。Reese 提供了一个插件的例子，通过 Sudo 插件使用用户打字的生物统计分析来确定是否有人物理劫持了他们的工作站，尽管更常见的是，插件可能只是提供一些日志或票务软件的连接。

展望未来，Reese 表示，One Identity 将进一步利用这一插件架构，将其与特权分析产品的[安全措施相集成，在接下来的三到四个月内，Sudo 用户将能够“将他们的 Sudo 审计数据发送到我们的集中审计产品，然后我们将能够为他们提供一个非常好的仪表板，显示不同的审计日志、不同的用户、他们在做什么，并能够针对这些内容添加行为分析。”](https://www.oneidentity.com/products/one-identity-safeguard-for-privileged-analytics/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>