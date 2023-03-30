# HashiCorp 对其开源遗产的反思

> 原文：<https://thenewstack.io/hashicorp-defines-enterprise-sweet-spot-path-forward/>

在去年八月任命[大卫·麦克詹尼特](https://twitter.com/davidmcj?lang=en)为首席执行官后，哈希公司在过去的一年进行了大量的反省。McJannet 是 VMware、GitHub 和 Hortonworks 的校友，最近在 Greylock Partners 担任常驻执行官。在交接过程中，联合创始人[艾蒙·达德加尔](https://github.com/armon)和[米切尔·桥本](https://github.com/mitchellh)成为联合首席技术官。

“从某种意义上说，这对公司来说是一段有趣的时光，”Dadgar 说。“对于公司的商业使命到底是什么，我们有很多悬而未决的问题。

“[它]是，好，我们有这六个开源项目，它们拥有庞大而繁荣的社区，但如何转化为商业上可行的 HashiCorp 和一个可以继续投资这些工具并增长的项目？”

该公司提供[vagger](https://www.vagrantup.com/)来管理开发环境， [Packer](https://www.packer.io/) 来构建映像， [Terraform](https://www.terraform.io/) 来提供映像，[consult](https://www.consul.io/)来连接和监控应用程序， [Nomad](https://www.nomadproject.io/) 来部署应用程序，以及 [Vault](https://www.vaultproject.io/) 来保护应用程序和基础设施。

然而，这家总部位于旧金山的公司已经寻求超越创建开发者工具，整合[工作流](https://thenewstack.io/hashicorp-drives-to-expand-the-scope-beyond-developer-tools/)，这需要开发者、运营和安全团队作为应用交付流程的一部分共同工作。

McJannet 之前与 New Stack 谈论了其统一产品的工作，以帮助大型组织向基于云的架构转移。

Dadgar 说，它已经确定了开源方面的“甜蜜点”或核心任务是解决从业者的挑战。但它也有一个财富 2000 强的客户群，像家得宝，塔吉特和威瑞森这些客户有着不同的问题。这促使了向企业版的巨大转变。

最近更新的 [Vault](https://www.hashicorp.com/blog/vault-0-8-1/) 就是一个例子，对开源和企业版都进行了改进。

Vault 开源版本整合了机密管理、加密即服务和特权访问管理。企业版还包括协作和操作功能、治理功能以及跨多个数据中心扩展保险存储的能力。

今年早些时候的 0.7 版本增加了对多数据中心复制的支持，但用户希望每个数据中心都有一个本地保险库，以防丢失主保险库。

[Enterprise 0.8](https://www.hashicorp.com/blog/vault-0-8/) 增加了灾难恢复复制模式，允许复制令牌和租用凭据以及机密和策略，并优先考虑从停机状态快速恢复的能力，而不必为访问机密的应用程序/用户重新生成令牌。

它还包括装载筛选复制。

“这些跨国公司中有很多都有数据治理法——哪些数据实际上可以复制到哪里。我们最初的实现是要么全有要么全无。你的整个数据集要么被复制到每个数据中心，要么根本不被复制，”Dadgar 说。“现在你有了这些细粒度的旋钮，‘好吧，这些数据可以去这些国家。这些数据可以传到这些地区。像欧盟通用数据保护条例(GDPR)这样的法规即将出台，而大多数公司还没有做好准备。“这是一个围绕跳马的话题，”达德加尔说。

新的多因素认证子系统允许在 Vault 内的认证路径上的任何操作都需要[双推](https://duo.com/product/trusted-users/two-factor-authentication/authentication-methods/duo-push)、 [Okta 推](https://support.okta.com/help/blogdetail?id=a67F0000000L2MpIAK)、[pinid 推](https://www.pingidentity.com/en/platform/multi-factor-authentication.html)和基于时间的一次性密码(TOTP)方法。

0.8 版本还在开源端增加了对安全插件的支持。

“我们的核心问题之一是，我们如何提供一种中央服务，为我们基础设施的所有部分提供中央访问，”他说。

“无论是数据库、亚马逊云凭据还是加密密钥，目标都是集中管理。安全团队只需在一个地方制定策略，只需在一个地方进行审核，只需在一个地方提供访问权限。”

为此，它增加了对一系列系统的支持——couch base、MySQL、Postgres、HANA、Oracle DB 等等。

“我们传统上所做的，比如说它是一个 Oracle 数据库，就是说我们希望它在 Vault 中得到本机支持，整个社区都可以从中受益，”他说。“面临的挑战是，一些公司拥有这种特定的本土系统，并希望通过 Vault 代理对它的访问。但这是这家公司独有的，对整个社区没有好处，我们承担了维护它的负担。

“安全插件为我们提供了一条出路。我们可以与您合作开发一个插件，让您管理自己开发的系统，并且您可以维护这个独一无二的系统。因此，它有助于我们支持我们的核心使命，即如何支持所有这些异构终端。我们正在通过合作伙伴关系、插件和附加集成的组合来解决这个问题。”

Vault 0.8.1 还包括 Google 云平台身份和访问管理( [IAM)认证后端](https://opensource.googleblog.com/2017/08/hashicorp-vault-and-google-cloud-iam.html)和 Oracle 数据库 Secret 后端。

[https://www.youtube.com/embed/CLgqDgsrn3M?feature=oembed](https://www.youtube.com/embed/CLgqDgsrn3M?feature=oembed)

视频

该公司正在进一步支持谷歌云，最近宣布了与微软的多年[合作伙伴关系，以进一步整合其跨 Azure 云服务的 Terraform 基础设施供应工具。](http://www.crn.com/news/cloud/300090771/microsoft-commits-to-long-term-development-plan-with-hashicorp.htm)

Adobe 将是 9 月 18 日至 20 日在德克萨斯州奥斯汀举行的[hashi conf ' 17](https://www.hashiconf.com/)上谈论其体验的客户之一。

专题图片:由[高尔夫度假村 Achental 团队](https://www.flickr.com/photos/chiemseehotel/)制作的“来自高尔夫度假村 Achental 的甜蜜——糕点”，获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>