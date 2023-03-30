# 为什么在云和容器环境中保护机密非常重要，以及如何做到这一点

> 原文：<https://thenewstack.io/why-securing-secrets-in-cloud-and-container-environments-is-important-and-how-to-do-it/>

[Cloud Native Computing Foundation](http://cncf.io/)赞助了这篇文章，期待虚拟 [KubeCon + CloudNativeCon 北美 2020–虚拟](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)，11 月 17-20 日。

 [Gary Duan

Gary 是 NeuVector 的首席技术官，neu vector 是一家集装箱安全公司，从管道到生产全程保护 Kubernetes。](https://www.linkedin.com/in/garyduan/) 

需要基于密钥的“秘密”来授权跨所有云应用和服务的访问和通信，包括对容器化应用的登录访问。从 AWS IAM 访问密钥，到 Google API 访问令牌、脸书访问令牌、OAuth 客户端秘密，以及无数其他秘密，秘密被用来保护无数面向公众的服务和内部或外部 REST APIs。

考虑到机密的可访问性，其安全存储和管理对于整体数据和系统安全是绝对必要的。服务自然需要访问敏感数据；因此，如果机密暴露，即使是最精心配置的环境也无法完全保护敏感数据。秘密落入坏人之手的后果可能是毁灭性的，允许攻击者通过读取数据库记录来制造数据泄露；并通过删除文件或添加他们自己的文件进行破坏。

## 泄露机密的高昂代价

秘密曝光的危险是真实的，并继续成为头条新闻。以优步的一名工程师为例，他不小心在 GitHub 存储库中留下了一个秘密，允许访问优步亚马逊的网络服务器。一名攻击者开始从服务器上下载文件，其中包括一个包含 5000 万优步客户数据记录的敏感备份文件。袭击者索要 10 万美元赎金，优步支付了赎金。当这个故事后来公开时，[优步也为数据泄露支付了 1 . 48 亿美元的和解金](https://www.usatoday.com/story/tech/news/2018/09/26/uber-pay-148-million-over-undisclosed-data-breach-ex-ceo-paid-hackers-keep-quiet/1432335002/)，并同意今后对公司的所有运营进行全面的安全合规性审计。这一影响还包括优步 IPO 的推迟——这一切都源于一个管理不善的秘密。

在另一个攻击者利用泄露的秘密制造恶作剧的例子中，DXC 的开发人员犯了硬编码密钥的错误——这允许访问项目中的亚马逊网络服务资源。然后，一名团队成员使用不安全的 GitHub 存储库共享了该项目。攻击者利用这些(并非如此)私钥在四天内启动了 244 台 AWS 虚拟机，[花费了该公司 64，000 美元](https://www.theregister.com/2017/11/14/dxc_github_aws_keys_leaked/)。

## 机密管理解决方案

有多种工具可用于管理机密安全，包括几个强大的开源选项。

AWSLabs 的开源 git-secrets 保护组织免受上述情况的影响，防止开发人员将密码和其他敏感信息提交给 git 存储库。

工具 [detect-secrets](https://github.com/Yelp/detect-secrets) 被设计用来检测和防止秘密进入代码库。它还检测其预防规则是否被绕过，并提供需要迁移到安全存储的任何机密的清单。

[HashiCorp 的 Vault](https://www.vaultproject.io/) 工具利用 UI、CLI 或 HTTP API 为机密和其他敏感数据提供安全存储和访问控制。

在其容器环境中使用 Kubernetes 的组织可以利用 [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) ，这是 orchestrator 的内置秘密管理解决方案。Kubernetes Secrets 方便了密码、OAuth 令牌、SSH 密钥和其他敏感信息的存储和管理；实现了更高的安全性和灵活性(与将机密存储在 Pod 定义或容器映像中相比)。

另一个流行的企业级容器平台 Red Hat OpenShift ，也具有内置的秘密管理功能。

## 秘密审计解决方案和深度防御

在容器化的环境中，秘密审计工具使得识别源代码存储库、容器映像、跨 CI/CD 管道等等中秘密的存在成为可能。部署容器服务将激活平台和 orchestrator 安全措施，分发、加密和正确管理机密。默认情况下，秘密被保存在系统容器或服务中——这种保护在大多数用例中已经足够了。

然而，对于特别敏感的工作负载——优步的客户数据库后端服务是一个很好的例子，任何数据加密或标准图像扫描用例也是如此——仅仅依靠传统的保密存储安全和保密分发是不够的。这些敏感的使用案例需要更强大的深度防护。在容器环境中，深度防御实施利用深度数据包检测(DPI)和数据泄漏防护(DLP)来监控正在使用的*秘密。任何通过网络数据包的秘密传输都可以被识别、标记并在不适当的情况下被阻止。通过这种方式，最敏感的数据可以在整个容器生命周期中得到有效保护，并且由于这一额外的安全层，可以阻止可能导致违规事件的攻击。*

## 保护云和容器应用程序的秘密比以往任何时候都更加重要

新冠肺炎疫情极大地增加了远程访问工作应用程序的使用。因此，对这些应用程序安全性的挑战正在增加。通过实施有效的机密管理和审计工具，以及深度防御来保护最敏感的工作负载，组织可以实现成功的安全性并保守秘密。

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 11 月 17 日至 20 日在 T4 举行的 [KubeCon + CloudNativeCon 北美 2020 大会。](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)*

亚马逊网络服务、云计算原生计算基金会、HashiCorp 和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>