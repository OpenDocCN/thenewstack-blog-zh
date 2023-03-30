# 桑给巴尔实现 SpiceDB 是开源的

> 原文：<https://thenewstack.io/zanzibar-implementation-spicedb-is-open-source/>

总部位于纽约的创业公司 [Authzed](https://authzed.com/?gclid=CjwKCAjw4qCKBhAVEiwAkTYsPKXCrFW_-qakzrZ7AvNhESNQrEX32Xgx4h1YP-lv9aEsqGAaYIb4oBoC59EQAvD_BwE) 发布了谷歌[桑给巴尔](https://www.usenix.org/system/files/atc19-pang.pdf)的开源版本，一致的全球授权系统。

Zanzibar 提供了统一的数据模型和配置语言，以从数百个客户端服务中实施广泛的访问控制策略。谷歌在包括云、驱动、日历、地图、YouTube 和照片在内的服务中使用它。

Authzed 是 Zanzibar 的一个商业实现，作为一个许可即服务公司出现。它的版本叫做 [SpiceDB](https://github.com/authzed/spicedb) ，是桑给巴尔的开源实现，就像[cocroach db](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)是 [Spanner](https://thenewstack.io/google-cloud-spanner-view-field/) 的开源实现一样。

[桑给巴尔](https://jacace.wordpress.com/2021/05/10/case-study-zanzibar-googles-consistent-global-authorization-system/)基于访问控制列表的统一存储和基于远程过程调用(RPC)的 API，旨在实现高可用性和低延迟。

联合创始人 [Jake Moshenko](https://www.linkedin.com/in/jacob-moshenko-381161b/) 说:“集中并快速获得权限是面向服务的架构和功能即服务的核心，因为你不能再依赖整体中的一段代码来评估存储在数据库中的权限。

他、[乔伊·肖尔](https://www.linkedin.com/in/joseph-s-4324904/)和[吉米·泽林斯基](https://www.linkedin.com/in/jzelinskie/)来自科瑞奥斯码头和[红帽](https://www.openshift.com/try?utm_content=inline-mention)。他们称之为“谷歌之外最完整的桑给巴尔实现”，莫申科和肖尔之前也曾在这里工作过。

莫申科说，作为 Quay 的联合创始人，他和朔尔很早就发现了这个问题。

“作为构建 Docker 注册表的一部分，我们需要检查复杂的权限。我们选择这样做的方式，与今天许多开发人员所做的非常相似，即在他们的数据库中存储关系，然后使用他们的源代码解释这些关系，”他说。

“……当我们有递归关系时，我们最终会遇到问题。比如组是组的一部分，或者名称空间是其他名称空间的一部分。我们实际上无法模拟这些东西。我们不得不取消这些功能，仅仅是因为建立权限的难度。”

Zanzibar 以及 SpiceDB 将所有这些关系保存在一个有向图中。

## 大多数通用用例

“它基本上将问题设定为图遍历。如果你能在对象和用户试图拥有的访问权限以及用户本身之间找到一个有效的遍历，那么这就被认为是一个成功的权限检查，用户被允许执行该操作，”他说。“因此，很容易看出，您可以让组成为其他组的一部分，让用户成为这些组的成员，只需向图中添加边和节点，就可以非常容易地与许多组共享一个文档。”

Authzed 专注于桑给巴尔最常见的用例，而用户，如 [Airbnb](https://medium.com/airbnb-engineering/himeji-a-scalable-centralized-system-for-authorization-at-airbnb-341664924574) 和资本化表管理初创公司 [Carta](https://medium.com/building-carta/authz-cartas-highly-scalable-permissions-system-782a7f2c840f) 已经定制了桑给巴尔，以满足他们自己的特定需求。他说，例如，Airbnb 的姬路版本在桑给巴尔岛论文最初描述的一致性和更高的可用性之间进行了权衡。

他说，在努力为尽可能多的用例构建解决方案的过程中，它不会做出这样的权衡。

“我们的桑给巴尔实现让你自己模拟用户，”他说。“你可以从不同的用户来源引入不同的用户。例如，如果您使用多个身份提供者。例如，您可以将 Auth0 和 Google OAuth 结合使用，并讨论不同的异构用户集。这在桑给巴尔岛的报纸上是不可能的。

“所以我们不得不退一步说，‘如果没有谷歌基础设施给实施带来的一些假设和限制，桑给巴尔岛会是什么样子？’"

在[的博客文章](https://authzed.com/blog/spicedb-is-open-source/)中，莫申科解释了用户为什么会选择 SpiceDB:

“SpiceDB 是可扩展的，支持全局复制后端，并且在许可的 [Apache 2](https://www.apache.org/licenses/LICENSE-2.0) 许可下可用。我们通过实现桑给巴尔文章中的最佳伸缩概念来实现可伸缩性，比如分布式缓存和并行执行。有了对[cocroach db](https://github.com/cockroachdb/cockroach)的支持，你的存储后端就有了一个[扳手](https://research.google/pubs/pub39966/)等价物，为你提供具有 ACID 语义的全球分布数据。”

它还具有多个数据后端，包括用于持久存储的 Postgres 和 CockroachDB，以及用于测试和开发的内存数据存储。

## 提高采用率

它是用 Go 编写的，尽管一些授权的商业组件是用 Python 和 JavaScript 开发的。

在商业产品中，该公司将提供一个托管版本，它希望这将使中小型公司更容易获得该技术。

“我们计划在全球范围内运行这项服务，作为一个全球部署的许可数据库。对于我们大多数较小的采用者来说，这将是成本过高的。但因为我们可以与每个人共享单个集群，并联合成更小的块，他们可以获得全球部署的好处，而不必支付成本，”莫申科说。

基本上，用户只需要告诉 SpiceDB 在他们的网站上建立的关系。

“因此，每次他们与用户共享文档，或者每次他们向 RBAC 系统中的角色添加用户时，他们都会添加新的关系。然后，基于这些现有关系和一个非常简单的模式进行查询，就可以非常简单地确定相关用户是否拥有权限。”

莫申科说，该公司开源 SpiceDB 的动机是增加该技术的采用，并鼓励所有开源项目的贡献者。这家早期创业公司在 4 月份的种子轮融资中筹集了 390 万美元。

他们之前的初创公司 Quay.io 是一家专门托管私人 Docker 仓库的服务公司，于 2014 年出售给了 CoreOS。红帽然后[在 2018 年收购了 CoreOS](https://thenewstack.io/docker-acquiring-coreos-red-hat-aims-kubernetes-company/) ，同年 [IBM](https://www.ibm.com/cloud?utm_content=inline-mention) 收购了红帽。第二年,[开源项目 Quay](https://www.redhat.com/en/blog/red-hat-introduces-open-source-project-quay-container-registry?sc_cid=701f2000000tyBjAAI) container registry 启动。

开放政策代理的联合创始人兼 Styra 的首席技术官 Tim Hinrichs 最近写道，[需要重新考虑云原生堆栈的授权](https://thenewstack.io/why-we-need-to-rethink-authorization-for-cloud-native/)。Mary Branscombe 概述了认证和授权之间的[差异](https://thenewstack.io/how-do-authentication-and-authorization-differ/)。

谷歌的桑给巴尔[论文](https://research.google/pubs/pub48190/)发表于 2019 年，然而最近对它又有了一点新的兴趣。

它的最初创造者之一 Lea Kissner 最近在推特上发布了关于桑给巴尔“反向索引”的属性，它允许你查找一个人可以访问什么，而不是通过对象的名称来查找访问控制规则。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>