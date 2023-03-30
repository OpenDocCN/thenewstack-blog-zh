# 达到 1.0 时，HashiCorp Vault 开始发挥作用

> 原文：<https://thenewstack.io/reaching-1-0-hashicorp-vault-comes-into-its-own/>

经过近四年的开发， [HashiCorp](https://www.hashicorp.com/) 宣布其秘密管理和数据保护工具库[1.0 版](https://github.com/hashicorp/vault/blob/master/CHANGELOG.md)正式上市。

它带来了新的功能，包括开源版本的[云自动解封](https://www.vaultproject.io/docs/concepts/seal.html)，据联合创始人兼联合首席技术官 [Armon Dadgar](https://github.com/armon) 称，这是社区一直渴望的，以及批量令牌，这是一种用于大规模和短暂工作负载的新型令牌。

该公司于 10 月在旧金山举行的 2018 年 HashiConf 会议上宣布了 Vault 1.0 里程碑。这只是其产品套件中的[增强功能](https://thenewstack.io/hashicorp-aims-to-lighten-management-of-the-multicloud/)之一，旨在降低多云环境的管理复杂性。

Dadgar 解释了为什么花了这么长时间才达到 1.0，他说 Hashicorp 产品必须满足四个复选框:

*   公司了解所有主要的用例，并支持 95%到 99%的用例。
*   技术架构已经成熟。
*   而且它有足够的时间投入生产，有足够多的用户使用它，找到错误并修复它们。

[https://www.youtube.com/embed/2wI0IMSl0ZE?feature=oembed](https://www.youtube.com/embed/2wI0IMSl0ZE?feature=oembed)

视频

Dadgar 说，云自动解封的开源版本诞生于其企业产品中，是用户最需要的功能之一。

他说，过去的启封就像电影《猎杀红色十月》中的场景一样，启动一艘船意味着两个人必须同时插入钥匙并转动它们。

“如果我是一名黑客，我可以获得你的密钥，我无法单独获得数据。手动很难做到，”他谈到为所有用户存储和重新组装 Shamir 的密钥的过程。

它的解决方案是与云服务集成，如 AWS KMS、Azure Key Vault 和 GCP CKMS，以自动化 Vault 的解封过程。

“这归结于利用能够访问这些密钥的云提供商，对其进行配置，以便云提供商是唯一能够解封保险库的提供商。你有一把用途单一的钥匙，就是开启金库，仅此而已。它最终是一个非常狭窄的表面区域，你可以使用云原生许可系统，”他说。

自动解封和密封包装—由两套不同的密钥保护的加密和静态存储的数据—仍将是企业产品的一部分。

新的批处理令牌专为大数据等大规模工作负载和无服务器等短暂工作负载而设计。

“如果我要运行一个机器学习模型，或者每天晚上我要处理一堆数据，突然之间，我可能会有数百或数千台机器同时开始运转并访问凭据。您试图平衡需求，因为我的数据管道运行在许多机器上。Dadgar 解释说:“面临的挑战是大量的工作同时出现在许多许多机器上。

同时，无服务器环境会产生真正短暂的工作负载。

“因此，工作负载最终会变得非常具有突发性。您可能会从没有工作负载到有数千个请求，再回到零。

“这两种模式都有点困难。你要么有一个非常大规模的模式，要么有一个非常突发的模式。这两者都给 Vault 带来了一些挑战，因为它试图跟踪所有用户。批处理令牌就是为这两个问题而设计的。它允许 Vault 处理这两种模式，而不会使 Vault 服务器不堪重负。”

他是这样解释的:

在标准模式下，Vault 会跟踪与用户相关的所有信息。如果我登录到 Vault，它会发送一个 cookie 显示，但在内部，它会跟踪我，我可以访问的东西。所有元数据跟踪的问题是，如果有很多用户，Vault 需要处理大量元数据。如果我有一群用户，但是他们消失了，那么元数据就没用了。

与 Vault 跟踪信息本身不同，它使用批处理令牌对所有元数据进行加密，并在 cookie 中将其返回给客户端。客户不知道 Vault 给了什么，因为它是加密的。但是，当它与 Vault 交互时，Vault 解密元数据并处理请求，而不必在服务器端跟踪所有数据。

该公司警告称，这些令牌不会写入磁盘，从而降低了 Vault 内任何操作的性能成本，但也不适合在遇到故障时需要持久性或弹性的操作。

OpenAPI 标准支持 1.0 版中其他值得注意的特性，它为 API 调用提供了一种与供应商无关的描述格式。

“它可以让您自动为每种语言生成客户端库。您不必为 Javascript、PHP、Nodejs 和所有其他东西开发定制的 SDK，而是可以从开放 API 规范中自动生成一个库。它让我们有一个更一致的图书馆，也有一个更广泛的社区，”他说。

另一个是与阿里云更紧密的集成。阿里云身份验证方法现在是 Vault Agent 中自动身份验证的支持界面。

Dadgar 说，达到 1.0 并不意味着跳马完成。

“这是跳马之旅的开始，”他说。“我们将 Vault 视为一个安全平台。我们把它设计成非常基于插件的。由于客户有不同的问题，他们可以通过启用我们提供的不同插件来扩展 Vault。如果您从秘密管理开始，您希望如何解决证书管理或 SSH 代理？我们如何让您快速轻松地扩展 Vault，以提供其他功能？”他说。

在这种情况下，该公司正在寻找插件可以用核心平台解决的邻近问题。

Twistlock 是新堆栈的赞助商。

特征图片:[zeevweez](https://www.flickr.com/photos/zeevveez/)的[键入手电筒](https://www.flickr.com/photos/zeevveez/6089266689/in/photolist-ah65QH-a16qMn-mWtbXX-Nz7HE-53wBsY-2tfR44-91z4qu-53snpD-4VgjA1-e46Ube-7XPUmY-n9So12-6bhYKg-nYPhwv-dEDK6N-7JsFTQ-4keYNu-4mgwu5-g4x4e-a61r1g-pDfgN-pDh2i-kmcuS-6bn9MQ-dgMDn8-ipy2Ch-4cQmrw-a7npZp-7jTUVo-9V4hwF-d69Nk1-5k9rRK-4uVemC-91Hkk2-pDea1-7XPVnG-4qgHa7-onRjDW-adPKPd-oysvPj-Y8ZztA-oNVj9J-7fwWB6-Jzpu78-6gRie4-BN2AG-pGYcpS-8SoPRt-8GzJUt-8FWMM8)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>