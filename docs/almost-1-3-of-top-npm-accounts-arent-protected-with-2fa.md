# 几乎 1/3 的顶级 npm 客户没有受到 2FA 的保护

> 原文：<https://thenewstack.io/almost-1-3-of-top-npm-accounts-arent-protected-with-2fa/>

JavaScript 运行时环境 [Node.js](https://nodejs.org/) 的 [npm](https://www.npmjs.com/) JavaScript 包管理器和默认包管理器非常流行。它是世界上最大的软件注册中心。但是它的安全性没有什么值得大书特书的。 [Aqua Security](https://www.aquasec.com/?utm_content=inline-mention) 的团队 Nautilus 最近的一项研究发现，前 35 个 npm 包中有 [32%面临账户被接管的风险](https://blog.aquasec.com/npm-supply-chain-attack)，因为其依赖者的所有者没有正确使用[双因素认证(2FA)](https://www.idginsiderpro.com/article/3612170/can-webauthn-and-u2f-finally-give-us-safe-and-easy-two-factor-authentication.html) 。

我们需要这个就像我们需要一个脑袋上的洞。

## 很难保护

就其本质而言， [npm 是一部恐怖片。Npm 使您能够使用外部库，并支持依赖性管理。结合起来，这使得为您的项目调用第三方库和依赖项变得非常容易。此外，虽然理论上 npm 软件包包含了其功能所需的一切，但很多软件包在安装时会下载额外的资源。当然，您检查了特定程序的安全问题，但是它所有的依赖项和下载内容呢？](https://thenewstack.io/is-npm-a-hotbed-of-malware/)

你会说“[依赖地狱](https://searchitoperations.techtarget.com/definition/dependency-hell)”吗？我可以。

2019 年的一项研究发现，平均而言， [npm 包隐式信任 79 个第三方包和 39 个维护者](https://www.usenix.org/conference/usenixsecurity19/presentation/zimmerman)。此外，流行的软件包通常会影响超过 100，000 个其他软件包。这使它们成为主要的攻击目标。

### 只有 100 个项目

现在， [npm 终于为它的 100 大项目](https://github.blog/2022-02-01-top-100-npm-package-maintainers-require-2fa-additional-security/)采用了 2FA，但这远远不够。还记得那些依赖吗？如果其中只有一个受到威胁，数以千计的应用程序都可能被转化为密码矿工。那不只是杞人忧天。已经发生了。 [UA-Parser-JS](https://blog.aquasec.com/npm-library-supply-chain-attack?_ga=2.264576711.97554855.1649160330-461876756.1649160330) ，一个每周下载数百万次的 npm 包，它曾被加密挖掘和密码泄露恶意软件短暂破坏。

双因素身份验证也计划用于高影响包。也就是周下载量超过 100 万或者依赖度超过 500 的包。这是一个好的开始，但还是不够。所有 npm 帐户都需要 2FA 保护。

## 最小化攻击面

现在， [2FA 并不完美](https://thenewstack.io/multifactor-authentication-is-being-targeted-by-hackers/)。远非如此！而且，我们也知道[许多开发者讨厌使用 2FA](https://thenewstack.io/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication/) ，但是它比其他选择好得多。

考虑一下，如果你是一个黑客，攻击一个没有使用 2FA 的人的账户会容易多少？你猜怎么着？事实证明，直到最近，你还可以自动发现某人是否启用了 2FA。如果你的 npm 项目被广泛使用，你也可以背上一个靶子。

因此，Aqua Security 强烈建议开发人员尽量减少我们的攻击面，让攻击者接管帐户更具挑战性。"否则，结果会对整个社区造成损害。"特别是，“我们强烈鼓励贡献开源和创建包的开发者在他们所有的账户上启用 2FA。”

对此，我只能说，“阿门！”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>