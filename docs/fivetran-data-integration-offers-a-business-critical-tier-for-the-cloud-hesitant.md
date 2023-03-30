# Fivetran 数据集成为犹豫不决的云提供了“业务关键”层

> 原文：<https://thenewstack.io/fivetran-data-integration-offers-a-business-critical-tier-for-the-cloud-hesitant/>

基于云的全面管理的数据集成服务 Fivetran 正在推出 Fivetran Business Critical (FBC)，这是一套新的安全相关功能，适用于迄今为止认为有必要避免公共云的企业。

Fivetran 的产品副总裁 [Fraser Harris](https://www.linkedin.com/in/fraserharris/) 告诉新堆栈，敏感数据安全是他们的客户在使用云平台时最大的担忧之一。与 FBC 合作，该公司旨在解决这一问题。Harris 说，FBC“为企业的敏感数据提供了最高级别的保护。它使他们能够创建更安全、更现代化的数据堆栈，满足内部和法规要求。

在此之前，使用像 Fivetran 这样的云服务，您无法达到某些组织所需的安全级别。"

## 向下钻取

让我们打开包装。当然，基于云的数据平台越来越受欢迎，因为它们具有处理大量数据的弹性和能力。然而，云中敏感数据的安全性和各种法规遵从性要求阻碍了金融和医疗保健等受到严格监管的行业的客户采用云技术。这正是 Fivetran 试图与 FBC 解决的问题。

据该公司称，FBC 层最初将在亚马逊网络服务(AWS)上提供，随后是微软 Azure(T10)。FBC 的主要优势是它能够与 AWS 的 [PrivateLink](https://aws.amazon.com/privatelink/) 私有云互联服务集成。运行在 AWS 云上的数据仓库平台，如[雪花](https://www.snowflake.com/?utm_content=inline-mention)和亚马逊自己的[红移](https://aws.amazon.com/redshift/)，也是 PrivateLink 兼容的，允许 Fivetran 管道处理内部数据，将管道的输出推入仓库，同时保持数据远离公共互联网。

此外，客户能够使用 [AWS 密钥管理服务](https://aws.amazon.com/kms/) (KMS)管理他们自己的加密密钥。由于 Fivetran 提供单租户流程，每个数据管道在加密和处理方面都是独立运行的，从而确保数据安全。因此，Fivetran 表示，它现在可以保证其平台符合数据保护法规，如 GDPR 和[CCPA](https://oag.ca.gov/privacy/ccpa)；以及 HIPAA 和 PCI DSS 级验证等行业认证。Fivetran 表示，这是唯一符合该标准的 ELT 软件即服务(SaaS)产品。

## **为什么重要** 

借助 Fivetran Business Critical，需要遵守严格安全标准的行业现在可以获得内部/私有云安全优势，同时使用可扩展的云环境并利用其通常卓越的基础架构管理功能。此外，由于数据不通过公共互联网路由，用户可以从数据集成管道的更高吞吐率中受益。除了增强的安全性和法规遵从性之外，这种降低的延迟以及一些数据出口费用的免除是 FBC 的两项额外好处。出于控制和安全原因，希望留在本地环境中的企业可以保留这些功能，同时利用 Fivetran 的 SaaS 数据管道平台。

*披露:帖子作者 Andrew Brust 和 Esin Alpturk 就职于 [Blue Badge Insights](https://www.bluebadgeinsights.com/) 、*一家研究、战略和咨询公司，服务于数据和分析软件公司、解决方案提供商和客户*。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>