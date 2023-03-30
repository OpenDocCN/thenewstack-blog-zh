# Argo 连续发送程序中的安全问题

> 原文：<https://thenewstack.io/security-trouble-in-argo-continuous-delivery-program/>

也许有一天会有一天，我们没有一个严重的安全问题要担心，但那一天不是今天。在我们最近的头痛中，云原生安全公司 [Apiiro](https://apiiro.com/) 的安全研究团队揭露了一个[令人讨厌的软件供应链零日漏洞](https://apiiro.com/blog/malicious-kubernetes-helm-charts-can-be-used-to-steal-sensitive-information-from-argo-cd-deployments/)、 [CVE-2022-24348](https://nvd.nist.gov/vuln/detail/CVE-2022-24348) ，在 [Argo CD](https://argoproj.github.io/cd/) ，流行的开源 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) [连续交付(CD)](https://thenewstack.io/how-continuous-integration-and-continuous-delivery-ci-cd-enhances-devops/) 平台。

这是一个老掉牙的问题，但是令人讨厌的[路径遍历错误](https://owasp.org/www-community/attacks/Path_Traversal)。当被滥用时，它使任意值文件被[舵](https://helm.sh/)图表消耗。雪上加霜的是，攻击者可以编制恶意的 Helm chart 包，其中包含实际上是符号链接的值文件，指向存储库根目录以外的任意文件。

## 认真对待这个洞

如果你是安全专家，你应该已经知道这一点都不好。如果你对它的严重性有任何疑问，它的 CVE 通用漏洞评分系统(CVSS)得分 7.7，高，告诉你它必须认真对待这个漏洞。

例如，能够创建或更新应用程序，并且知道或能够猜出包含有效 [YAML](https://yaml.org/) 的文件的完整路径的攻击者，可以创建恶意的 Helm chart。然后，这种 Helm 恶意软件可以用来访问私人数据。这包括包含敏感或机密数据的加密值文件(例如，使用带有 git-crypt 或 sop 的插件)。这些秘密可以在舵图绘制之前被解密。

哦，因为来自 helm 模板的详细错误消息被传回给用户，所以攻击者可以很好地了解存储库服务器的文件系统中有什么。是的，这意味着恶意参与者可以从他们的应用程序生态系统“跳到”用户范围之外的其他应用程序的数据。

## 一点都不好玩

这不是我认为的乐趣。

这种撬开攻击可以在 Argo CD 2 . 1 . 9 之前和 2.2.4 之前的 2.2.x 上使用。

具有讽刺意味的是，Argo CD 的开发者看到了这种[类型的利用将在 2019 年](https://github.com/argoproj/argo-cd/issues/2715)到来，并建立了一种机制来阻止这种攻击。不幸的是，他们的修复不够好。

所发生的是[代码搜索一个模式化的字符串，该字符串将适合作为其输入值的 URI 的模型。](https://github.com/argoproj/argo-cd/blob/96f95ca1c1048c37f935f6f72ff54be641d92b60/reposerver/repository/repository.go#L588)它通过 ParseRequestURI 函数来实现这一点。但是您可以欺骗这个函数接受一个本地文件路径作为 URI，并跳过现有的 URI 清理和反路径遍历机制检查。

## 坏消息和好消息

很抱歉，一旦你知道怎么做就太容易了。正如 Apiiro 团队所说，“简单地说:如果列出的值文件看起来像一个 URI，它将被视为一个，跳过所有其他检查，并将其视为一个合法的 URL。”

哎呦。

这是个坏消息。好消息是。 [Argo CD 和 Apiiro 立即着手解决这个问题](https://blog.argoproj.io/?p=86e8fb158e8f)。针对以下 Argo CD 版本的此漏洞的修补程序:v 2 . 3 . 0；v2.2.4 和 v2.1.9 已经发布。现在修补一下，一切都会好的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>