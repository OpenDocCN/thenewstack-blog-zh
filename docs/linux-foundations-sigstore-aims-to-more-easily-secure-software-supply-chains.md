# Linux 基金会的 Sigstore 旨在保护软件供应链

> 原文：<https://thenewstack.io/linux-foundations-sigstore-aims-to-more-easily-secure-software-supply-chains/>

到目前为止，安全软件供应链还没有标准化。更糟糕的是，大多数加密签名工具都没有被使用，因为它们要么太麻烦，要么太混乱。开发人员的工作已经够有挑战性了。如果没有易于使用的工具来对他们的代码进行数字签名，很少有开发人员会去费心。

在红帽、[、谷歌](https://security.googleblog.com/2021/03/introducing-sigstore-easy-code-signing.html)和[普渡大学](https://www.purdue.edu/)的帮助下，Linux 基金会启动了一个名为 [sigstore](https://sigstore.dev) 的数字签名项目，该项目可能会消除许多源于必须保护开源代码的问题。

通过这项服务，开发人员可以对发布文件、容器图像和二进制文件进行数字签名。一旦工件被签名，签名记录就被保留在防篡改的公共日志中。sigstore 将免费供所有开发者和软件提供商使用。

sigstore 项目“使所有开源社区能够签署他们的软件，并将出处、完整性和可发现性结合起来，以创建一个透明和可审计的软件供应链，”首席技术官办公室的红帽安全工程负责人卢克·哈里斯在一份声明中说。

一旦 sigstore 就位，它可以有效地消除开放源码软件进入的任何与安全相关的障碍。有了该服务签署的软件，首席运营官和首席技术官可以相信他们正在部署的软件不会导致另一场[太阳风灾难](https://thenewstack.io/solarwinds-hack-reveals-3-overlooked-steps-to-securing-a-software-supply-chain/)。

想想其中的含义。

## 它是如何工作的

这个新的(免费的)服务就像[让我们加密](https://letsencrypt.org/)(另一个 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)项目)，但是用于代码签名。sigstore 将提供免费的证书和必要的工具来自动化和验证源代码的签名。这项新服务是这样工作的:

*   开发人员使用 sigstore 客户端为他们的软件生成临时密钥对。
*   sigstore PKI 提供签名证书(在成功的 OpenID 连接授权时)。
*   证书被记录在证书透明度日志中。
*   透明日志为用户的 OpenID 帐户引入了信任根。
*   签名完成后，可以丢弃短期密钥。

此时，有一个与该软件相关联的信任证书。

在第一个版本中，sigstore 的目标是通用的发布工件，比如 tarballs、二进制文件和容器映像。在以后的版本中，sigstore 将探索其他类型的工件，如 jar、清单和软件材料清单(SBOM)。

使用 sigstore 所需的唯一个人信息是一个 [OpenID Connect](https://openid.net/connect/) 授权(仅包括用户的电子邮件地址)；因此，sigstore 不会访问您的联系人、云驱动器、日历或任何其他信息。

Sigstore 用户可以使用该服务，甚至可以在内部部署一个“rekor”服务器(它管理一个“防篡改账本”)(我们将在后面的教程中介绍这一点)，它有一个可插拔的 PKI，目前支持:

有了 [rekor 服务器](https://github.com/sigstore/rekor)，您可以定制清单模式，这样您就可以让 rekor 处理几乎任何您需要的值(了解更多关于 rekor [可插拔类型](https://sigstore.dev/docs/plugable_types/))。

请在四月初回来查看关于如何设置 rekor 服务器的教程。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>