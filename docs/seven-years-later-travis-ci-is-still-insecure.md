# 七年过去了，崔维斯·CI 仍然没有安全感

> 原文：<https://thenewstack.io/seven-years-later-travis-ci-is-still-insecure/>

说真的，你为什么还在用特拉维斯 CI？是的，我知道他们是第一批持续集成(CI)项目之一。那是当时。这就是现在。从那以后，先是在 2015 年，然后在 2019 年，然后在 2021 年再次[，现在——是的，现在——](https://arstechnica.com/information-technology/2021/09/travis-ci-flaw-exposed-secrets-for-thousands-of-open-source-projects/)[Travis CI 日志再次被披露，使其程序员面临攻击](https://blog.aquasec.com/travis-ci-security)。

你们这些人是怎么了！？

是的，特拉维斯·CI 是罪魁祸首。在其研究中， [Aqua Security](https://www.aquasec.com/?utm_content=inline-mention) 发现，成千上万的用户令牌仍然通过 Travis CI 应用程序编程接口(API)暴露。通过这些，您可以获得历史明文日志。此外，有了 7.7 亿自由层用户的日志，为 GitHub、 [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) (AWS)和 Docker Hub 用户复制和粘贴令牌、秘密和其他凭证就变得轻而易举了。

需要我给你解释一下吗？有了这些敏感数据，攻击者就可以发动大规模的网络攻击，进行跨云的横向攻击。

## 设计上的脆弱性

你知道这一切最讨厌的是什么吗？根本漏洞是由设计造成的。

我引用文档中的话:“当您运行构建时， [Travis CI 将您的 GitHub 存储库](https://docs.travis-ci.com/user/for-beginners/#ci-builds-and-automation-building-testing-deploying)克隆到一个全新的虚拟环境中，并执行一系列任务来构建和测试您的代码。”现在，这还不算太糟。但它也复制了你所有的秘密。这可不酷。

Aqua 告诉 Travis CI，问题还在。而 Travis CI 回答，本质上，他们还是不在乎的。问题在于“设计”

没错。那好吧。

## Aqua 推荐

特拉维斯·CI 已经采取了一些措施。他们引入了 API 自适应速率限制来防止黑客的暴力攻击。特拉维斯 CI 还混淆了秘密和令牌。但是正如 Aqua 指出的，这还不够，

Aqua 建议您立即更改您的秘密。我建议你去别处寻找你的 CI 服务。

撇开你不应该在你的代码中有秘密不谈，可悲的事实是它们经常在那里，Travis CI 让它变得太容易了。

云提供商和开发者网站对此越来越重视。有些已经为他们的用户启动了密钥轮换。这还不够，但总比没有强。

Aqua 进行了一些实验，发现通过 Travis API 可以挖掘 CI 日志。多少根木头？潜在的大约 7.7 亿个日志。

是啊，太多了。一旦你从中提取了秘密——因为人们倾向于反复使用相同的秘密——你就可以从任何地方撬开当前的项目。(说到安全，我们真是白痴。)具体来说，Aqua 的研究人员发现了与 GitHub、AWS 和 Docker Hub 相关的秘密。

## 降低风险

有了 Aqua 自己的 [Trivy 开源](https://aquasecurity.github.io/trivy/v0.27.0/docs/secret/scanning/)，扫描硬编码的秘密就变得微不足道了。 [Trivy 扫描任何容器映像、文件系统或 Git 存储库，寻找暴露的密码](https://thenewstack.io/aqua-securitys-trivy-security-scanner-can-scan-anything-now/)、API 密匙或令牌。

这些秘密中最流行的包括 GitHub 访问令牌；AWS 访问密钥、电子邮件/用户名和密码组合；和 Docker 集线器密码。人们，人们不再把你的秘密放进你的代码里。

Aqua 有自己的建议列表，可以帮助您降低风险并保护 CI 环境:

*   为密钥、令牌和其他机密建立轮换策略。
*   在适用的情况下，对密钥和令牌应用最小特权原则。
*   不要在日志中打印机密、令牌或凭证。
*   定期扫描你的藏物寻找秘密。
*   使用一个[云安全态势管理(CSPM)](https://www.aquasec.com/products/cspm/) 解决方案，指示轮换密钥的最佳时间。您可以扫描您的帐户，检查循环频率，并查看您是否应用了最低权限策略。
*   使用供应链安全解决方案(如 [Argon](https://www.argon.io/) )扫描您的 [CI/CD 环境](https://thenewstack.io/category/ci-cd/)，以找到暴露的秘密、令牌和凭证，并确保您的帐户配置符合最佳实践。

我对特拉维斯. CI 很苛刻。但是你知道吗，我们都需要在安全实践方面做得更好。如果你不把高价值的秘密放在你的代码中，没有人会关心你的日志。如果我们都努力工作，把 Aqua 的建议作为一个好的起点，我们都会有更安全的代码。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>