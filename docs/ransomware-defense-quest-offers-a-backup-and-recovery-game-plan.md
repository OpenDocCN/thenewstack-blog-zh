# 勒索软件防御:Quest 提供备份和恢复策略

> 原文：<https://thenewstack.io/ransomware-defense-quest-offers-a-backup-and-recovery-game-plan/>

现在有理由假设大多数组织已经或将遭受勒索软件攻击。虽然统计数据已经令人清醒，但最近的数据指向了一个更加不祥的威胁前景。Quest 软件公司对此有一个答案。

根据 CyberEdge 第八次年度[网络威胁防御报告](https://cyber-edge.com/cdr/):

*   去年，创纪录的 86%的组织遭受了成功的网络攻击。
*   创纪录的 69%的组织受到勒索软件的危害。
*   57%的勒索软件受害者去年支付了赎金，但其中四分之一(28%)的受害者未能恢复其数据。

可以理解的是，对于许多组织来说，重点已经发生了变化。虽然寻求防止勒索软件和总体安全攻击仍然至关重要，但考虑到组织的运营通常会在勒索软件攻击得到解决之前停止，因此在勒索软件攻击发生时如何做已经成为一项重要举措。

为此，一个潜在的解决方案是数据库、系统和安全软件提供商 Quest Software 的用于活动目录灾难恢复版(RMAD DRE)的[恢复管理器 10.2](https://www.globenewswire.com/news-release/2021/08/17/2281768/0/en/Quest-Disaster-Recovery-Innovation-Protects-Active-Directory-Backups-from-Malware-Infection-Minimizing-Ransomware-Destruction.html) 存储，旨在保护[微软活动目录](https://azure.microsoft.com/en-us/services/active-directory/)备份免受恶意软件的攻击，并将勒索软件攻击的影响降至最低。

认证信息系统安全专家(CISSP)和 Quest Software 顾问 Bryan Patton[“不仅要定期对活动目录进行可靠备份，还要将它们保存在空隙存储中，这一点非常重要。“这意味着他们处于离线状态——与互联网和内部网络断开连接且无法访问。”](https://www.linkedin.com/in/bjpatton)

## 数据存储

针对勒索软件攻击的最明显的第一道防线之一是维护备份，一旦数据存档，就无法通过网络连接访问这些备份。过去，这一过程通常包括在磁带上制作备份，并定期将磁带运送到安全的异地位置。但是，除了每小时左右(或根据行业的不同以更短的时间增量)将存档数据运送到异地以外，这在很大程度上是不可行的。

“老派的解决方案是将备份写入磁带，并将其发送到铁山等异地存储设施，”Patton 说。“然而，这种方法不仅麻烦而且昂贵；它还会大大降低恢复速度，因为检索、运输、装载和读取磁带必然会花费大量时间。”

此外，备份的数据很可能包含漏洞，这些漏洞首先成为攻击的攻击点。此外，一旦发生攻击，组织必须有一个非常有效的数据恢复过程，一旦创建，如果没有经过适当的测试，往往会导致令人沮丧的失败。

由于大多数组织使用 Microsoft Active Directory (AD)来管理身份并提供对业务资源(如数据库、文件、应用程序和端点)的访问，因此在 AD 备份并运行之前，无法恢复任何内容。

“如果您的备份已经损坏，您就无法从备份中恢复，”Patton 说。“如今的勒索软件攻击会寻找并破坏任何联网的备份，以最大限度地增加您支付赎金来恢复数据的机会。”

RMAD DRE 10.2 版有可能加快恢复过程，活动目录继续作为“整个企业的中枢神经系统”，巴顿说。巴顿解释说，RMAD·DRE 10.2 支持恢复工作，以便:

*   备份团队提供备份并执行恢复。
*   存储团队确保您有足够的存储来从备份中恢复服务器。
*   网络团队确保正在恢复的服务器已经过沙箱保护，并且域控制器(DC)可以通信。
*   服务器团队验证恢复是否正确和完整，并安装所需的任何其他防病毒或防恶意软件软件。
*   安全团队验证勒索软件不在恢复的服务器上。
*   应用程序团队验证应用程序正在运行。
*   需要协调和管理外部各方，如微软、备份和恢复供应商以及云存储提供商。

Patton 说，恢复过程包括确定哪些应用程序对业务运营最重要，以便 DevOps 团队可以首先专注于恢复它们。接下来是确定哪些域控制器(DC)对于这些应用程序是必不可少的，并首先恢复它们，“尽快启用登录和业务关键功能，”Patton 解释道。

“通常，关键的域控制器是在数据中心，而不是在远程办公室，”巴顿说。一旦您恢复了它们，应用程序团队、数据库团队和其他人就可以开始他们的恢复过程，而 Active Directory 团队则继续恢复不太重要的数据中心

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>