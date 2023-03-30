# 不是你通常的供应链黑客:Codecov Bash 上传者的失误

> 原文：<https://thenewstack.io/not-your-usual-supply-chain-hack-the-codecov-bash-uploader-blunder/>

我们都知道网络安全管理软件产品供应链被黑的事情。但是，尽管范围较小， [Codecov](https://about.codecov.io/) 的 [Bash 上传者安全供应链失败](https://about.codecov.io/security-update/)也是一个创纪录者。而且，这不是任何人都想打破的记录。

在他们的代码被破解几个月后，Codecov 才发现了这个错误，这要感谢一个有安全意识的用户。他检查了 Github 版本的 [Codecov Bash Uploader](https://docs.codecov.io/docs/about-the-codecov-bash-uploader) 的安全哈希算法 1 (SHA-1)校验和，以及下载的 Bash Uploader 版本与 [shasum](https://linux.die.net/man/1/shasum) 的 SHA-1 校验和，发现它们不匹配。换句话说，它们不是同一个程序。

哎呦！

Codecov 是一个报告工具，它将覆盖度量直接插入到[持续集成(CI)](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/) 工作流中。它的工作是在运行测试套件时监视编码问题。它特别关注 pull 请求，在这些请求中通常会发现新的特性和错误修复，并且经常会出现新的错误和问题。

Bash Uploader 的任务是导出用户的 CI 环境数据。这包括执行 Bash Uploader 脚本时用户在 CI 运行程序中使用的任何凭证、令牌或密钥。这已经够危险的了，因为它的名字完全是描述性的。Bash Uploader 使用 Bash shell 和 [curl](https://curl.se/) 将未加密的环境数据上传到 Codecov。哦，对了，还有攻击者的服务器。

这种发送数据的方法简直是自找麻烦。正如一位 Slashdot 读者所说，“[将一个你无法控制的 URL 直接传送到 Bash 中……会有什么地方出错呢](https://it.slashdot.org/story/21/04/16/2126257/codecov-bash-uploader-compromised-in-supply-chain-hack)？”我的意思是，对于犯这种错误的人来说，确实有一个[耻辱堂网页。](https://gnu.moe/wallofshame.md)

雪上加霜的是，Bash 上传器还用于三个相关的上传器:Codecov-actions Uploader for GitHub、Codecov CircleCl Orb 和 Codecov Bitrise Step，因此如果您将 code cov 的上传器用于其中任何一个，您就会被这个问题标记。

那么你会怎么样呢？很高兴你问了。据该公司称，修改后的 Bash 上传程序脚本可能会影响:

*   当 Bash Uploader 脚本执行时，我们的客户通过他们的 CI 运行程序传递的任何凭证、令牌或密钥都是可访问的。
*   可以使用这些凭证、令牌或密钥访问的任何服务、数据存储和应用程序代码。
*   使用 Bash Uploaders 将覆盖率上传到 CI 中的 Codecov 的存储库的 git 远程信息(原始存储库的 URL)。

如果你像一位 Ycombinator 读者那样仔细思考，这意味着“黑客窃取了运行 Codecov 脚本的上下文的每个环境变量。这意味着，如果您使用 CI 来部署您的代码，[您的所有凭证都已被泄露](https://news.ycombinator.com/item?id=26825813)。

这种情况持续了多久？该公司报告称，从 2021 年 1 月 31 日开始，该公司的谷歌云存储(GCS)密钥存在周期性的未经授权的访问。这使得恶意第三方能够更改其 bash 上传程序脚本，从而在 2021 年 4 月 1 日之前将配置项导出到第三方服务器。不，这不是愚人节玩笑。

这就是我喜欢称之为“开枪吧”的时刻。比如说，现在就杀了我，而不是去管理层告诉首席信息官、首席技术官和 CISO，我们的 CI 数据被劫持了三个月。

这是怎么发生的？由于 Codecov 的 Docker 映像创建过程中的错误，攻击者不知何故(我们不知道具体是如何获得代码的)。这使得黑客能够提取修改 Bash 上传程序脚本所需的凭证。由于这种未经授权的访问，他们修改了脚本以将配置项数据导出到第三方服务器。

根据 Codecov 首席技术官 Eli Hooten 的评论，这里唯一的“好”消息是，“根据这次攻击的性质[，我不认为恶意行动是直接针对 CI 管道](https://news.ycombinator.com/item?id=26819983)执行的，我们也没有任何证据。”如果是真的，这次入侵可能是一个真正的黑客只是在戳一个系统，看看他们能发现什么，而不是一个急于赚钱的黑客。

至于你现在需要做什么，那并不重要。正如 Codecov 所说:

我们强烈建议受影响的用户立即在使用 Codecov 的 Bash Uploaders 之一的 CI 流程中重新设置位于环境变量中的所有凭证、令牌或密钥。

如果您一直在审计这些令牌在您的系统中是如何使用的，那么现在是开始扫描您的日志以发现从 1 月底到 4 月初的异常活动的好时机。

Codecov 现在说了所有关于保护他们的系统和审计他们的代码的正确的事情。但是，马已经离开了马厩，如果我是他们大约 29，000 名使用其程序来检查我的代码质量的客户中的一员，我会在信任他们使用我的 CI 数据火车之前与他们进行长时间的艰苦交谈。

我还会深入研究他们的脚本，看看是否还有其他潜在的问题。最后，很少有人费心去检查 SHA-1 和其他校验和，以发现程序所说的和实际情况之间的问题。是时候开始了。毕竟，用 shasum 和 [sha256sum](https://linux.die.net/man/1/sha256sum) 之类的程序检查这些总和可以通过在 Bash 脚本中流水线化它们来实现自动化。这将使得在 Bash Uploader 这样的脚本中使用 curl 更加安全。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>