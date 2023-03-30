# 在你的 AWS Java 和 Python 程序中寻找恼人的秘密

> 原文：<https://thenewstack.io/find-annoying-secrets-in-your-aws-java-and-python-programs/>

有时候好事伴随着不好的副作用。获取我们代码中的秘密，比如密码、凭证、密钥和访问令牌。曾几何时，我们从未将这些放在代码中。但是随后出现了[代码驱动的自动化，秘密](https://blubracket.com/finding-secrets-in-code-the-devsecops-way/)经常意外地，有时是有意地，检查到我们的程序中。然后，软件即服务(SaaS)和基础设施即服务(IaaS)带来了调用其他服务的令牌的激增。怎么办？当然，在恶意黑客发现和使用它们之前，找到并清除它们！这就是[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)更新[亚马逊代码大师](https://aws.amazon.com/codeguru/)的用武之地。

亚马逊 CodeGuru 是一款人工智能/机器学习(AI/ML)开发者工具。它的核心工作是提高代码质量，识别程序中最昂贵的代码行。它的 CodeGuru Reviewer 组件在应用程序开发过程中识别关键问题、安全漏洞和难以发现的错误，并提供代码质量建议。

## 自动化代码审查

[CodeGuru Reviewer 有了一个新特性](https://aws.amazon.com/blogs/aws/codeguru-reviewer-secrets-detector-identify-hardcoded-secrets/)。上个月在 AWS 的年度 re:Invent 用户大会上推出，这种自动化代码审查扫描并分析您的 Java 和 Python 应用程序的硬编码秘密。

具体来说，这个自动化工具检测源代码或配置文件中的秘密，如密码、API 密钥、SSH 密钥和访问令牌。

它使用[机器学习](https://thenewstack.io/category/machine-learning/)在你的代码审查过程中发现硬编码的秘密。当然，目标是确保您的新 Java 和 Python 代码在被合并和部署之前不包含硬编码的秘密。除了您的代码之外，这个新函数还扫描配置和文档文件中的秘密。

一旦扫描完你的最新代码，程序会建议补救措施来保护你的秘密。当然，最明智的做法是在提交之前删除秘密。硬编码的秘密可以用来自秘密管理器的秘密替换，或者在需要时用配置变量替换。

## 秘密经理

程序的默认建议是使用 [AWS 秘密管理器](https://aws.amazon.com/secrets-manager/)。这种托管服务使您能够安全、自动地存储、轮换、管理和检索凭证、API 密钥和几乎任何其他类型的秘密。

一旦秘密被存储在 AWS Secrets Manager 中，它会给你代码片段，使用[AWS SDK](https://aws.amazon.com/tools/)将你的秘密提取到许多编程语言中。这使您不必手动插入必要的 SDK 调用。

这一新功能是 CodeGuru Reviewer 服务的一部分，无需额外费用。它支持最常见的 API 提供者。除了 AWS，它还支持 Atlassian、Datadog、Databricks、GitHub、Hubspot、Mailchimp、Salesforce、SendGrid、Shopify、Slack、Stripe、Tableau、Telegram 和 Twilio。[你可以在这里查看完整的名单](https://docs.aws.amazon.com/codeguru/latest/reviewer-ug/recommendations.html#secrets-detection)。

我强烈建议，如果你在 AWS 上用 Java 和 Python 编程，你应该使用这个新功能。当你在最后期限时，很容易找到秘密的捷径，并向自己保证你会记得在推进代码之前把它们取出来。这听起来不错，但是几小时、几天或几周后，当你发现一个被遗忘的秘密正在被利用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>