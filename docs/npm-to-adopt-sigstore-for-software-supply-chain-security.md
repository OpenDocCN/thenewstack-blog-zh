# Npm 将采用 Sigstore 实现软件供应链安全

> 原文：<https://thenewstack.io/npm-to-adopt-sigstore-for-software-supply-chain-security/>

实话实说吧。 [npm](https://www.npmjs.com/) ，JavaScript 包管理器和 JavaScript 运行时环境 [Node.js](https://nodejs.org/) 的默认包管理器，需要它能得到的所有安全帮助。领先的开源安全提供商 [Mend](https://www.mend.io/) ，最近声称 [npm 是恶意行为者的游乐场](https://thenewstack.io/is-npm-a-hotbed-of-malware/)。WhiteSource 说得有道理。现在，[贾斯汀·休金斯](https://www.linkedin.com/in/hutchingsjustin)， [GitHub](https://github.com/) 的产品管理安全总监想要解决这个问题。

Npm 是 GitHub 的子公司，所以当休金斯发言时，npm 会倾听。虽然 Hutching 没有命令 npm 采用 Linux Foundation 和[开源安全基金会(OpenSSF)](https://openssf.org/) 的 [Sigstore](https://www.sigstore.dev/) 来签署源代码，但他强烈鼓励这样做。

## Sigstore 的优势

通过 Sigstore，开发人员可以使用 Sigstore 客户端为他们的软件生成临时密钥对。Sigstore 公钥基础设施(PKI)随后提供签名证书，该证书记录在证书透明性日志中。然后，这将用于向用户的 OpenID 帐户引入可信根。完成后，蜉蝣密钥可以被丢弃，软件代码有了信任证书。

Sigstore 的签名与 npm 的其他安全改进相结合，如[要求双因素身份验证](https://github.blog/2022-05-10-enhanced-2fa-experience-for-your-npm-account/)、[简化登录和增强工件签名](https://github.blog/2022-07-26-introducing-even-more-security-enhancements-to-npm/)，有助于保护 npm 免受软件供应链攻击。

具体来说，休金斯解释说，他们正在开放一个[新的征求意见稿(RFC)](https://github.com/npm/rfcs/pull/626) ，讨论将一个包与其源代码库和构建环境链接起来。“当包维护者选择加入该系统时，他们的包的消费者可以更有信心包的内容与链接的存储库的内容相匹配。”

从历史上看，这是一个痛苦，所以没有人这样做。它要求单个项目注册并管理他们自己的密钥。如果被采用，开发者就不用担心这个问题了。相反，通过使用 Sigstore 添加对 npm 包端到端签名的支持，该过程是自动化的。休金斯补充说，“这个过程将包括生成关于在何处，何时，以及如何制作软件包的证明，以便以后可以验证它。”

Sigstore 的策展人丹·洛伦茨(Dan Lorenc)和 [Chainguard](https://thenewstack.io/chainguard-a-zero-trust-supply-chain-security-company/) 的首席执行官兼联合创始人在一封电子邮件中告诉我，Sigstore 已经成为“历史上被采用最快的开源技术之一，因为它对开发者来说是一种签名、验证和保护软件的友好方法。”

## Sigstore 采用

Npm 不是唯一一个采用 Sigstore 来使其代码更安全的公司。 [Kubernetes](https://thenewstack.io/kubernetes-adopts-sigstore-for-supply-chain-security/) 、 [Python](https://kushaldas.in/posts/using-sigstore-python-to-sign-and-verify-your-software-release.html) 、 [Rust 开发者都在与 Sigstore](https://github.com/sigstore/sigstore-rs) 合作

Lorenc 声称，“数以千万计的开发者正在使用 Sigstore 签名的软件，这对所有软件的完整性产生了巨大的影响。”天知道 npm 需要这个。如今，开发人员在考虑 npm 时，脑海中不会出现“值得信赖”这个词。

然而，正如休金斯总结的那样，这只是一步。“保护软件供应链是我们行业目前面临的最大安全挑战之一。该提案是重要的下一步，但真正解决这一挑战需要整个社区的承诺和投资。我们很高兴听到[您的反馈](https://github.com/npm/rfcs/pull/626)，并期待一起踏上这一旅程！”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>