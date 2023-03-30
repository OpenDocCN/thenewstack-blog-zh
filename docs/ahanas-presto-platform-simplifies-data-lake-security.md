# Ahana 的 Presto 平台简化了数据湖安全性

> 原文：<https://thenewstack.io/ahanas-presto-platform-simplifies-data-lake-security/>

为开源查询引擎[提供托管 SaaS 平台的 Ahana](https://prestodb.io/)Presto，使用户能够对云数据湖进行 SQL 分析，目前专注于亚马逊 S3 作为存储层。

Ahana 最近[获得了](https://www.globenewswire.com/news-release/2021/11/10/2331489/0/en/Ahana-Achieves-AWS-Data-Analytics-ISV-Competency-Status.html) AWS Data & Analytics ISV 资格认证，这是对成功引导用户在 AWS 上实现数据和分析目标的认可。作为该认证的一部分，Ahana [宣布](https://www.globenewswire.com/news-release/2021/12/09/2349150/0/en/Ahana-Cloud-for-Presto-Delivers-Deep-Integration-with-AWS-Lake-Formation-Through-Participation-in-Launch-Program.html)其平台提供与 AWS 服务的深度集成，包括[亚马逊胶水](https://aws.amazon.com/glue/)和[亚马逊湖泊形成](https://aws.amazon.com/lake-formation/)。

除了这些基本和增强的功能之外，Ahana 最近[宣布了](https://ahana.io/press-releases/ahana-announces-new-security-capabilities/)新的安全功能，分为两个主要功能。

## 新功能

第一个功能建立在前面提到的与 Amazon Lake Formation 的集成之上，利用 [Apache Ranger](https://ranger.apache.org/) 来实现跨多个 Presto 集群的集中和细粒度的访问控制。

Apache Ranger 并不新鲜，但是将它与 Ahana 集成以前需要手动安装 Apache Software Foundation 发行版，一次安装一个集群，在每个集群上使用基于文件的低级配置，这也将访问控制粒度限制到了单个表的级别。然而现在，通过一个简单的插件，用户可以通过用户友好的管理 UI 在 Presto 集群上实现 Apache Ranger，并在行或列级别配置访问。

用户还可以添加基于角色的数据访问，甚至通过 Ranger 插件的策略缓存降低查询延迟。这种集成特别有利于那些在云中实现大数据并希望使用 Ranger 这样的开源组件的用户，避免了锁定，并且仍然很容易做到。对于这样的客户，Apache Ranger 提供了一个与云无关的开源授权解决方案，具有细粒度的访问控制和 SSL，并且用于 Ranger 的 Ahana 插件使其安装和配置变得简单明了。

Ahana 的另一个主要安全特性是对用户访问控制和管理进行集中审计，以获得全面的可见性。通过此功能，用户可以查看访问请求并确定其合法性。在那里，管理员可以根据策略和人员变化更新权限级别。所有更改都通过 Apache Ranger 进行跟踪和实现，以提供全面的可见性，这对于敏感数据非常重要。

管理员可以通过 Ahana 控制台轻松管理用户，并且可以跨多个集群进行管理。因此，管理员可以向用户提供对某些集群的访问权限，并拒绝访问不在这些用户工作范围内的其他集群。

## 简化很重要

Ahana 希望为 Presto 和兼容的生态系统组件实现简单和统一。该平台还寻求跨 Presto 集群统一用户，并简化 Presto 上的身份验证流程。据 Ahana 联合创始人兼首席产品官 Dipti Borkar 称，“开源 Presto 已经具备了做多用户的能力；然而，其中一些非常复杂，因为它是基于文件的。实际上，您必须提供一个又大又长的文件，并使其与您的策略保持一致，这很快就会变得非常棘手。此外，您应该对每个集群都这样做。它不会自动移动。有了 Ahana，这一切都没了。当然，在后台，我们正在利用开源 Presto，但现在您有能力跨平台创建用户。”

许多数据湖技术一直停留在相对原始的安全功能环境中。Ahana 的新开发旨在使数据湖安全的前景更加简单和容易。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>