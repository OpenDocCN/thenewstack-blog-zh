# 与 LFX 一起掌握软件供应链安全

> 原文：<https://thenewstack.io/get-a-handle-on-software-supply-chain-security-with-lfx/>

勒索软件当之无愧地成为头条新闻，但是保护[软件供应链安全](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/)同样重要。在最近的 [Linux 基金会成员峰会](https://events.linuxfoundation.org/lf-member-summit/)上， [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)执行董事吉姆·泽姆林公布了其保护我们代码的最新努力: [LFX 安全](https://security.lfx.linuxfoundation.org/#/)。

LFX 安全目前支持 JavaScript、Node.js (npm)、Java、.NET、Scala、Ruby、Python、Golang 和 PHP。它可以与任何流行的源代码控制系统(SCS)一起工作。这包括 GitHub，Bitbucket，GitLab，Azure 等等等等。

它通过 [Snyk](https://snyk.io/) 的开源安全平台自动扫描漏洞来做到这一点，现在它通过 [BluBracket](https://blubracket.com/) 的自动扫描功能来寻找代码中的秘密和非包容性语言。这是一记有力的组合拳。

正如您可能知道的那样，Snyk 通过在您的代码库中搜寻近 12，000 个已知的开源漏洞来实现这一点。这有助于您从源头清理软件供应链。

基于数据库，安全问题被分为高、中或低风险。这部分是基于共同的弱点和暴露(CVE)和共同弱点列举(CWE)记录。然后，您的项目的检测到的依赖项和许可证的清单与依赖项细节一起被映射。

由于每天都有新的安全漏洞出现，LFX 安全漏洞数据库每周都会更新。它每周检查数千个经批准的开源库漏洞数据库、漏洞奖金、安全建议以及安全文章和报告，并根据检查结果进行更新。零日仍然可以度过，但是你会远离大多数已知的错误。

Snyk 组件还会查找和报告您的许可证。它通过扫描您的项目的基于 Git 的存储库，并根据[软件包数据交换(SPDX)](https://spdx.org/licenses) 许可证列表跟踪您的依赖项的许可证来做到这一点。除了因其自身的权利而广受欢迎， [SPDX 现在是一个 ISO 标准。](https://thenewstack.io/spdx-software-supply-chain-spec-becomes-an-iso-standard/)确定哪个许可证适用于给定的依赖项可能很棘手，一般来说，通过查看软件包上声明的许可证、注册表中的元数据以及清单文件中的许可证信息来确定。

BluBracket 在提交前和提交后扫描代码中的秘密，如密码、凭证、密钥和访问令牌。秘密代码和非包容性的语言，LFX 安全。

什么样的密码秘密？BluBracket 的服务扫描密码、凭证、密钥以及提交前和提交后的访问令牌。如果这些被嵌入到您的代码中，黑客就很容易进入您的存储库和活动代码。有传言称，最近大规模的 [Twitch hack](https://www.zdnet.com/article/twitch-source-code-business-data-gamer-payouts-leaked-in-massive-hack/) 可能源于其运行代码中嵌入的秘密。

BluBracket 还可以检测项目代码中的非包容性和攻击性语言。BluBracket 正在与[包容性命名倡议](https://inclusivenaming.org/)就此功能展开合作。

不过 BluBracket 的产品有一个奇怪的地方。与 Snyk 不同，它的服务代码没有开源。事实上，在服务的条款和条件中，该公司直截了当地指出:“客户不得，也不得允许他人:(a)更改、逆向工程、反编译、反汇编、创建衍生作品，或以其他方式[寻求获取 BluBracket 平台和应用程序或其任何部分的源代码](https://blubracket.com/terms-conditions/)或 API。”这不是我期望在以 Linux 基金会名义提供的服务中发现的。

只有维护者和贡献者才能在 LFX 安全显示器上看到结果。但是，如果您的项目位于公共存储库中，任何可以看到该存储库的人都可以看到显示问题总数的漏洞摘要。

要让 LFX 安全系统发挥作用，您必须将您的项目从您的 SCS 上传到 LFX 安全系统。你在 [LFX 安全项目控制中心](https://lfx.linuxfoundation.org/tools/project-control-center/)做这件事。作为入职培训的一部分，您的 SCS 上安装了一个安全机器人。目前，该系统仍然以 GitHub 为中心。它仍然在一起，当我写这篇文章的时候，它还不可用。为了引起他们的注意，[你可以在等候名单上](https://lfx.linuxfoundation.org/#newsletter)或者使用你的 [Linux 基金会会员资格来筹集门票](https://jira.linuxfoundation.org/plugins/servlet/theme/portal/4/create/358)。但是，很快就会了。到了那一天，如果你能接受这个许可，我劝你去看看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>