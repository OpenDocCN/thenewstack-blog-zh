# PHP 供应链攻击显示了开源的优点和缺点

> 原文：<https://thenewstack.io/php-supply-chain-attack-shows-open-sources-virtues-and-vices/>

那可不好玩。3 月 28 日，“两个[恶意提交被推送到 php-src repo](https://news-web.php.net/php.internals/113838) ”如果你不知道的话，这个库就是 [PHP](https://www.php.net/) 语言的主软件代码存储站点。顺便说一下，根据网络技术调查统计，PHP 被[几乎 80%的网站](https://w3techs.com/technologies/details/pl-php)使用。

好消息是什么？这些行为几乎立刻就被发现了。坏消息呢？恶意的行为是从一开始就有的。

在 PHP 创始人拉斯马斯·勒德尔夫和知名 PHP 开发者和维护者尼基塔·波波夫的伪装下，[攻击者假装在做小的打字错误修复](https://github.com/php/php-src/commit/c730aa26bd52829a49f2ad284b181b7e82a68d7d#r48801076)。事实上，他们正在设置一个后门。这将使攻击者能够在任何使用这个被黑客攻击的 PHP 版本运行软件的人身上运行远程程序。

能说不好吗？我知道你可以。

幸运的是，正如 Popov 告诉[哔哔作响的计算机](https://www.bleepingcomputer.com/):“第一次提交是在提交后几个小时发现的，这是常规提交后代码审查的一部分。这些改变显然是恶意的，而且马上就恢复了。”

如果他们侥幸逃脱，太阳风攻击看起来就像是脚本小子做的事情。幸运的是，由于 PHP 是开源的，这个问题在它有机会毁掉任何人之前就被发现了。

我们可以预见这种袭击会继续发生。例如，在 [Git](https://git-scm.com/) 中，每个人[最喜欢的源代码版本控制系统](https://thenewstack.io/git-at-15-how-git-changed-the-way-we-code/)，伪装成另一个本地 Git 用户然后上传和签署一个伪造的提交到远程 Git 服务器[非常容易。](https://stackoverflow.com/questions/47918679/git-how-to-commit-as-someone-else/47919156#47919156)

这一事件也揭示了包括开源程序在内的任何程序的更高层次的安全问题。正如谷歌开源安全团队软件工程师丹·洛伦克(Dan Lorenc)对新堆栈说的那样，“像这样的妥协表明，我们软件供应链的攻击面比看起来要广泛得多。像构建系统、源代码管理工具和工件存储库这样的组件都需要被视为关键的生产环境，因为它们确实如此。事实是，这一事件可能会产生深远的后果，但 PHP 团队在早期发现这一点并防止受损代码到达最终用户方面做得很好。”

洛伦茨说得很对。[Linux 基金会](https://www.linuxfoundation.org/)一直致力于与[开源安全基金会(OpenSSF)](https://openssf.org/) 一起武装开源软件链。这个跨行业的组织通过构建一个更广泛的安全社区，将开源领导者聚集在一起。它结合了来自[核心基础设施计划(CII)](https://www.coreinfrastructure.org/) 、 [GitHub 的开源安全联盟](https://github.com/Open-Source-Security-Coalition/Open-Source-Security-Coalition)以及其他开源安全公司的努力，如 GitHub、GitLab、Google、IBM、Microsoft、NCC Group、OWASP Foundation、Red Hat 和 VMware。

最近，Linux 基金会与[红帽](https://www.redhat.com/en)、[谷歌](https://www.google.com/)、[普渡大学](https://www.purdue.edu/)一起创建了 [sigstore 项目](https://sigstore.dev/)。这将[提高软件供应链的安全性](https://thenewstack.io/linux-foundations-sigstore-aims-to-more-easily-secure-software-supply-chains/),使透明日志技术支持的加密软件签名易于采用。它将通过授权开发人员安全地签署软件工件(如发布文件、容器映像和二进制文件)来做到这一点。这些签名记录将保存在防篡改的公共日志中。这项服务将免费供所有开发者和软件提供商使用。sigstore 社区仍在开发 sigstore 代码和操作工具。

这项技术仍在研发中，离投入生产还差得很远。与此同时，您需要尽您所能来保护您自己的代码库。

Popov 写道，PHP 已经决定，虽然“我们还不知道这到底是怎么发生的，但一切都指向 git.php.net 服务器的妥协(而不是个人 git 帐户的妥协)。”

既然是这样，Popov 继续说，“我们已经决定维护我们自己的 git 基础设施是不必要的安全风险，我们将停止 git.php.net 服务器。相反，以前只是镜像的 GitHub 上的存储库将变得规范。这意味着更改应该直接推送到 GitHub，而不是 git.php.net。”

如果你正在运行你自己的 git 库，并且你没有掌握你的安全，你可能也想考虑这样一个迁移，或者一些其他值得信赖的 git 站点，比如 [GitLab](https://about.gitlab.com/) 。

要访问新的规范知识库，您需要联系 Popov。在 GitHub 上，您还需要使用双因素认证(2FA)。是的，许多[开发者认为 2FA 是一个痛苦的](https://thenewstack.io/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication/)，但它也将大大有助于防止这个问题的发生。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>