# CircleCI 致客户:立即更改所有机密和 API 令牌！

> 原文：<https://thenewstack.io/circleci-secrets-catastrophe/>

我们都知道在我们的代码中保守秘密，比如密码、凭证、密钥和访问令牌，是一个糟糕的安全想法。但是，感谢[带秘密的代码驱动自动化](https://blubracket.com/finding-secrets-in-code-the-devsecops-way/)和[持续集成/持续交付(CI/CD)](https://practical-tech.com/2018/07/10/continuous-integration-and-delivery-tool-basics/) 我们还是做到了。有时候，它会反咬我们一口:狠狠的。

CI/CD 公司 [CircleCI](https://circleci.com/?utm_content=inline-mention) 就是这种情况。虽然该公司还不知道“安全实例”到底出了什么问题，但 CircleCI 首席技术官 Rob Zuber 在博客中写道:你应该:

*   [立即轮换 CircleCI 中存储的任何和所有秘密。这些可能存储在项目环境变量或上下文中。](https://circleci.com/blog/january-4-2023-security-alert/)
*   从 2022 年 12 月 21 日开始到今天，即 2023 年 1 月 4 日，或者在您的机密轮换完成后，客户会查看其系统的内部日志，以查找任何未经授权的访问。

Zuber 补充道，“另外，如果你的项目使用了[项目 API 令牌](https://circleci.com/docs/managing-api-tokens/)，我们已经使它们无效，你需要替换它们。”

也就是说，Zuber 说客户仍然可以在 CircleCI 的服务上建立他们的项目。“我们有信心，我们已经消除了导致这一事件的风险，”Zuber 写道。

对于 CircleCI 的 100 多万用户来说，这是个坏消息。正如一位用户在 Reddit 上所说的那样，“[去他妈的，我这一周剩下的时间都没了](https://www.reddit.com/r/programming/comments/103nvri/comment/j30n6ew/?utm_source=reddit&utm_medium=web2x&context=3) …我的公司通过 CircleCI 部署了数百个网站，每个网站都有自己的秘密…”

CircleCI 承诺在完成调查后，会将事件告诉所有人。与此同时，照它说的做，改变你的秘密。用户可以继续使用

注意，[你不必在你的代码](https://thenewstack.io/managing-secrets-in-your-devops-pipeline/)中放入秘密。或者，如果你这样做，让他们临时和自动轮换他们每隔一个小时左右。或者，更好的是，使用环境变量来保存秘密。然后用 [Azure Key Vault](https://azure.microsoft.com/en-us/products/key-vault/) 、 [HashiCorp Vault](https://www.vaultproject.io/) 或 [AWS Systems Manager 参数存储](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html)等程序管理这些秘密。您还应该使用基于角色的访问(RBAC)，这样只有授权的人才能访问加密的秘密和变量。

CircleCI 会支持你的。例如，CI/CD 服务现在支持 [OpenID 连接身份令牌。](https://connect2id.com/learn/openid-connect)这使您的 CircleCI 作业能够向支持 OpenID Connect 的云提供商(如 AWS、Google Cloud Platform 和 Vault)进行身份验证，同时避免使用静态机密。

也就是说，你也应该注意到 CircleCI 似乎有麻烦了。2022 年 12 月，[公司裁员 17%](https://circleci.com/blog/ceo-jim-rose-email-to-circleci-employees/)。首席执行官吉姆·罗斯警告说，这意味着“一切都不同了。”潜在泄露其用户的秘密当然被认为是最糟糕的“非正常业务”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>