# HashiCorp Vault 如何与 Kubernetes Secrets 一起工作？

> 原文：<https://thenewstack.io/how-does-hashicorp-vault-work-with-kubernetes-secrets/>

[](https://uk.linkedin.com/in/vnicolas)

[Nicolas ver mande](https://uk.linkedin.com/in/vnicolas)

[Nicolas 是 Ondat 的首席开发顾问。他是一名经验丰富的实践型技术专家，在过去的 17 年里，他一直在云原生技术、开源软件、虚拟化和数据中心网络等领域工作。你会经常看到他在全球科技会议和在线活动上发表演讲。](https://uk.linkedin.com/in/vnicolas)

[](https://uk.linkedin.com/in/vnicolas)[](https://uk.linkedin.com/in/vnicolas)

Kubernetes Secrets 最大的问题？它们既不秘密也不安全。

当用户想要在 Kubernetes 中存储敏感数据，如认证令牌、安全外壳协议(SSH)密钥、密码等，他们使用开源平台的[秘密对象](https://kubernetes.io/docs/concepts/configuration/secret/)。不幸的是，一旦信息被存储在一个秘密对象中，Kubernetes 几乎没有采取任何措施来保护这些信息。事实上，存储在 Secret 对象中的数据仅仅是用 Base64 编码的，这很容易解码和编码，根本没有加密。

另一种方法可能是在加密配置文件中添加静态加密密钥。但是，由于该文件通常托管在控制平面节点上，任何有权访问这些节点的人都可以解密所有机密。

那么，我们实际上如何保护 Kubernetes 中的敏感信息呢？

我们使用密钥管理服务(KMS)提供商，如 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) Vault。

## 哈希公司金库概述

HashiCorp Vault 有多种安全应用，但最常用于:

*   **基于身份的访问**:使用基于角色的访问控制(RBAC)，Vault 授权或限制秘密创建或其他用户的访问。Vault 还支持生成临时机密，以根据需要在有限的基础上为机器或用户提供对机密或服务器的访问，确保没有任何不必要的许可访问权限可供利用。
*   **加密** : Vault 提供传输中和静态加密，这是我们在保护 Kubernetes 机密时感兴趣的主要服务之一。在传输中，Vault 使用 TLS 加密，而在静止时，它使用 AES 256 位 CBC 加密。
*   **机密管理**:与 Kubernetes 相关的主要 Vault 用例是其机密管理功能。Vault 可以存储 API 密钥、数据库凭证、环境变量等等。

虽然 Vault 为其用户提供的加密和秘密管理功能对 Kubernetes 用例很有吸引力，但 HashiCorp Vault 如何与 Kubernetes Secrets 配合使用仍有问题。事实上，这种挑战是大多数(如果不是全部的话)KMS 服务所共有的:它们不是库伯内特本地的。

## Kubernetes 秘密管理的挑战

默认情况下，Kubernetes 将 Secrets 对象存储在 etcd 数据库中。然而，像 Vault 这样的 KMS 服务提供商倾向于在默认情况下将秘密存储在他们自己的系统中。

从第三方 KMS 供应商的角度来看，这是有意义的。通过将机密存储在 Kubernetes etcd 数据库之外，他们可以利用这些机密做更多事情，并围绕外部存储支持的更全面的机密管理功能构建产品路线图。

这对于供应商来说是件好事——它迫使开发人员和基础设施经理在他们的工具上花费更多的时间，他们变得更加依赖他们的客户，更多的用户被迫发展他们解决方案所有特性的能力。精通一个优秀的解决方案并没有错，但是大多数开发人员和基础设施经理更喜欢限制他们使用的工具数量。

理想情况下，用户可以执行基础设施和开发相关的任务，如测试、数据保护、确保故障转移和可用性等，同时执行安全相关的任务，如机密管理，也就是说，在 Kubernetes 中。

将尽可能多的工作流保留在 Kubernetes 中可以提高效率，增加自动化步骤的数量，并限制额外培训和维护的负担。至关重要的是，Kubernetes 的功能也是一样的，不管你使用哪个(些)云提供商。相比之下，在 HashiCorp Vault 中管理机密对于每个云提供商来说都是不同的，需要特定于云的技能，并且越来越复杂。说到安全，简单的工作流比复杂的工作流产生的风险要小得多。

呆在 Kubernetes 中可以让你对公共云提供商变得不可知。Kubernetes 是事实上的云操作系统，无论使用何种云，都可以使用相同的技术和模式作为构建现代应用程序和基础架构的标准。因此，您可以专注于 Kubernetes 技能，所需的特定于云的技能是有限的。这使得客户能够构建强大的多云战略。

## 如何使用 Kube-Native Secrets Management 在 Kubernetes 上运行 Vault

幸运的是，Vault 至少为我们提供了一种开始使用 Kube-native 方法进行秘密管理的方法。

金库有各种不同的**秘密引擎**。本质上，这些是存储、生成和加密数据的不同方法。这些引擎可能专注于连接到特定的服务，如亚马逊网络服务或谷歌云，简单地存储和读取数据，提供特定形式的加密等等。

我们的兴趣在于运输秘密引擎。

Transit 的功能相当于一个加密即服务秘密引擎——它不存储发送给它的引擎的数据，而只是对传输中的数据进行加密或解密。

这允许我们以一种库伯人特有的方式处理秘密。因为 Kubernetes 希望并且是围绕在 etcd 中存储数据而设计的，所以我们需要做的就是在任何需要[Kubernetes Secrets management](https://www.ondat.io/blog/how-to-keep-a-secret-secret-within-kubernetes)的时候，通过 Transit Secrets 引擎向 Vault 请求加密服务。

## 以 Kube-Native 方式使用 Vault 创建秘密

Vault 不是为 Kube-native 应用程序设计的，Kubernetes 只提供了一个高级通用 API，将加密/解密任务卸载给外部 KMS 提供商。因此，DevOps 专业人员需要做一些工作来集成这两个解决方案。为了尽可能加快整合速度，Ondat 正在赞助一个名为 Trousseau 的开源项目。

Trousseau 充当 Kubernetes 和 Vault(或任何其他 KMS 供应商)之间的代理。使用 Trousseau，用户和工作负载可以使用本地 Kubernetes API 和 kubectl CLI 管理 Kubernetes 机密，以访问来自 KMS 提供商的加密即服务。在我们今天讨论的特定用例中，Trousseau 将使用户或工作负载能够使用 kubectl CLI 向 Vault 的 Transit Secrets 引擎请求加密。

Trousseau 起作用是因为 Kubernetes 已经[提供了一个插件来支持 KMS 提供商](https://kubernetes.io/docs/tasks/administer-cluster/kms-provider/)。使用这个插件实现 Trousseau 使用户能够快速连接到任何 KMS 提供商，并使用您的团队已经精通的 Kube-native 工具和实践来加密秘密。

一旦在 Kubernetes 中创建了一个秘密，Kube API 就会调用 Trousseau，然后 Trousseau 会将加密请求发送给一个 KMS 提供商(本例中为 Vault)。那么 KMS 提供者执行加密而不存储相关数据。相反，它会将其发送回 Trousseau，Trousseau 然后将数据发送到 Kube API，Kube API 依次将加密的资源存储在 etcd 中。

结果是更快的上市时间、更高的安全性和降低的与培训您的团队使用新工具和实践相关的成本。您可以[在这里](https://www.ondat.io/trousseau)了解更多关于 Trousseau 项目的信息，以及通过 Vault 和 Kubernetes 引导您设置 Trousseau 的实践实验室，并接收有关如何加入开源项目的信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>