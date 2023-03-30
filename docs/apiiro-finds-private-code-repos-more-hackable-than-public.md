# Apiiro 发现私有代码回购比公共代码回购更容易被黑客攻击

> 原文：<https://thenewstack.io/apiiro-finds-private-code-repos-more-hackable-than-public/>

不，那不是错误。[云原生应用安全公司 Apiiro](https://apiiro.com/) 发现，私有存储库中[暴露的秘密](https://thenewstack.io/the-top-5-secrets-management-mistakes-and-how-to-avoid-them/)数量是公共存储库中的 8 倍。人，人，私密不代表安全。从来没有，也不会有。

Apiiro 的安全研究团队和外部专家强调了这样一个基本事实，即晦涩难懂的安全根本就不是安全，他们发现，私人存储库中的所有秘密中有超过一半(50.67%)是攻击者可以立即访问的暴露秘密。更糟糕的是，每 1000 个有秘密的仓库中，就有 7 个暴露在互联网上

呸！

### 寻找秘密

在你的软件供应链被黑的所有方式中，暴露秘密肯定是最尴尬的一种。我的意思是，我们都知道不应该在代码中放入密码、API 密匙和令牌之类的秘密？对吗？对！？

嗯，我想不是！Apiiro 的安全研究团队和朋友们分析了从小型到大型组织的 25，000 多个存储库，包括软件供应链中的 1，900，000 多个提交和 820，000 多个拉请求，发现赤裸裸的秘密是最常见的风险。平均而言，他们在每个储存库中发现了 3.28 个秘密。当他们关注有秘密的储存库时，平均每个储存库发现 29.64 个秘密。

太多了。其中 42.55%的暴露秘密是——惊喜！—纯文本密码。大多数秘密，79%，都藏在 JSON 和 YAML 的文件中。

那么，这些是从哪里来的？结果是一小部分开发者，6%的人要对所有放错地方的秘密负责。其中，仅仅 0.57%的开发者拥有超过一半的秘密，即 56.6%。简而言之，有极少数的程序员需要安全补救培训。

### 寻求帮助

或者，同样重要的是，即使聪明的开发人员有时也会犯愚蠢的错误，使用程序和服务，如 [Portainer](https://thenewstack.io/container-security-manage-secrets-with-portainer/) 、 [Doppler](https://thenewstack.io/doppler-a-platform-for-managing-secrets-everywhere/) 和 [Amazon CodeGuru Reviewer](https://thenewstack.io/find-annoying-secrets-in-your-aws-java-and-python-programs/) 来为你寻找和管理秘密。

你必须解决这个问题。它比我们想象的要大。正如 Apiiro 的安全研究副总裁 Moshe Zioni 所说，“有史以来第一次对组织内部存储库的上下文分析揭示了代码中秘密的真实程度。"

如果不加以解决，Apiiro 发现平均修复时间(MTTR)为 90 天。那太长了。这些秘密在源代码库中潜伏了几个月，是等待爆炸的炸弹。你不想那样。没人想这样。

你可以在 Apiiro 的[Secrets Insights Across the Software Supply Chain](http://apiiro.com/secrets-insights-2022)报告中了解更多相关信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>