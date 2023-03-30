# 需要签署您的代码，没有一个线索？Sigstore 可以提供帮助

> 原文：<https://thenewstack.io/need-to-sign-your-code-and-havent-a-clue-sigstore-can-help/>

开源软件签名服务 Sigstore 现在对所有需要向客户证明他们的代码是什么的人开放。顺便说一下，这个星球上几乎所有的商业软件开发者都是如此。

T2 的 Log4j 漏洞和 T4 的网络安全管理软件产品灾难带来了一些好消息。不，说真的。这迫使我们意识到我们必须真正保护我们的软件源代码，供应链安全。现在[开源安全基金会(OpenSSF)](https://openssf.org/) 的 [Sigstore](https://thenewstack.io/kubernetes-adopts-sigstore-for-supply-chain-security/) 服务可供每一个需要它的程序员使用。那是我们所有人。

## 政府干预

你看，拜登政府已经发布了一个[行政命令来改善软件供应链安全](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)。你不能忽视在你的软件中构建安全性。事实上，一旦[两党安全开源软件法案通过](https://www.zdnet.com/article/whats-what-in-the-united-states-securing-open-source-software-act/)，它可能真的成为法律。

因此，由于我们中的许多人都不知道如何对我们的软件工件进行签名，Sigstore 1.0 的公开发布可谓恰逢其时。

[Sigstore 是一个免费的开源软件签名服务](https://thenewstack.io/linux-foundations-sigstore-aims-to-more-easily-secure-software-supply-chains/)。它通过简化对发布文件、容器映像和二进制文件的加密签名，提高了软件供应链的安全性。签名后，签名记录保存在防篡改的公共日志中。这给了软件工件一个更安全的监管链，可以保护和追溯到它们的来源。

## 关键特征

它还有许多其他有用的功能。其中包括:

*   Sigstore 的无密钥签名为开发人员提供了良好的体验，并且消除了痛苦的密钥管理需求。
*   [Sigstore 的公共透明日志(Rekor)](https://github.com/sigstore/rekor) 和 API 意味着消费者可以轻松验证签名的工件。
*   由于 Sigstore 使用了标准，例如支持任何开放容器倡议(OCI)工件(包括容器、掌舵图、配置文件和策略包)和 OpenID Connect (OIDC)，它可以与其他工具和服务无缝集成。

## 可用服务

Sigstore 还宣布了 Rekor 透明日志和 [Fulcio 认证中心](https://github.com/sigstore/fulcio)公共福利服务的全面上市。据 Sigstore 技术指导委员会成员 [Priya Wadhwa](https://www.linkedin.com/in/priya-wadhwa-693893b5) 称，[Rekor 和 Fulcio APIs 都是稳定的](https://blog.sigstore.dev/sigstore-ga-ddd6ba67894d)，将得到长期支持。

Wadhwa 继续说道:“Sigstore 还建立了一个状态页面,用户可以在这里查看这些服务的可用性。该社区将继续以 99.5%正常运行时间服务水平目标(SLO)和全天候寻呼机支持来运营该服务。这要感谢专门的多厂商 Sigstore 开源社区，他们在过去的几个月里修复了两个服务中的主要错误并添加了关键功能。还进行了第三方[安全审计](https://openssf.org/blog/2022/07/18/results-of-sigstore-and-slf4j-security-audits/)，以捕捉任何潜在的漏洞，所有发现都已得到解决。

## 专为开发者打造

在底特律 KubeCon North America 的一次采访中， [Chainguard](https://www.chainguard.dev/) 首席执行官兼 Sigstore 联合创始人 [Dan Lorenc](https://www.linkedin.com/in/danlorenc/) 解释说，在实践中，虽然“存在速率限制，主要是为了防止拒绝服务攻击之类的事情，但它们相当慷慨。”换句话说，开发人员使用 Sigstore 应该不会有问题。

即使在测试阶段，Sigstore 也已经证明了它的价值。到目前为止，已经有超过 400 万个签名通过 Sigstore 登录。世界上最大的两个开源社区， [Kubernetes](https://thenewstack.io/kubernetes-adopts-sigstore-for-supply-chain-security/) 和 [Python](https://kushaldas.in/posts/using-sigstore-python-to-sign-and-verify-your-software-release.html) ，通过与 Sigstore 签署他们的产品发布，已经采用了 Sigstore 的真实性蜡封。最近， [npm 一直在积极地集成 Sigstore](https://thenewstack.io/npm-to-adopt-sigstore-for-software-supply-chain-security/) ，

因为 Sigstore，OpenSSF 的总经理布莱恩·贝伦多夫说:

“软件组件上的签名是保护全球软件供应链的重要组成部分。在 Sigstore 之前，只有消费者的最后一英里得到了很好的保护。现在，我们可以通过一个易于使用的工具包和服务来确保我们所依赖的上游组件的完整性。Sigstore 的开发者、倡导者和其他贡献者不仅实现了 1.0，而且已经得到了广泛的实施和影响，这值得称赞。”

结果呢？Wadhwa 声称，“Sigstore 已经迅速成为签名、验证和保护软件的标准，因此在软件供应链安全比以往任何时候都更重要的时候，宣布普遍可用以消除更广泛采用的最后一个障碍是一件好事。”

我同意她的观点。Sigstore 正在成为签名标准。事实上，它是开源的，可以作为服务使用，这只会让它更有吸引力。在一个迫切需要安全软件的世界里，Sigstrore 1.0 来的正是时候。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>