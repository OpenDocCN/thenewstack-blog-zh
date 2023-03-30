# MariaDB 通过 AWS S3 API 实现云原生

> 原文：<https://thenewstack.io/mariadb-goes-cloud-native-with-aws-s3-api-and-introduces-smart-transactions/>

本周， [MariaDB](https://mariadb.com/) 发布了最新版本的企业开源数据库，用于大规模的混合事务/分析处理。该公司解释说 [MariaDB Platform X4](https://mariadb.com/products/mariadb-platform/) 现在是云原生的，因为它将存储从计算中分离出来，引入了对亚马逊网络服务的简单存储服务(亚马逊 S3)API 的支持。他们解释说，亚马逊 S3 便宜得多，并允许无限的存储容量，这有利于分析，并节省了使用更昂贵的块存储(如 AWS Elastic Block Store，亚马逊 EBS)进行快速交易的成本。

“在这种非聚合体系结构中，一层用于存储，一层用于计算。MariaDB 平台现在将使用块存储进行交易，我们将使用亚马逊 S3 兼容的对象存储来存储用于分析的列数据。在这方面，我们有一个云原生存储架构，因为这些不同的工作流使用不同的云存储服务，一个针对他们的特点进行了优化的云存储服务，”MariaDB 产品营销高级总监[尚恩·约翰逊](https://www.linkedin.com/in/shanekjohnson)在接受采访时解释道。“有些数据库非常适合事务处理，有些数据库非常适合分析，而 MariaDB 平台可以做到这两者——我们使用行存储进行事务处理，使用列存储进行分析。”

Johnson 进一步解释说，亚马逊 S3 对象存储的增加带来了运行“智能事务”的能力，而不是“哑事务”或上面提到的事务性的创建、读取、更新和删除(CRUD)操作。通过智能交易，Johnson 提供了一个旅游网站的例子。虽然非智能交易可能指的是基本的航班数据，如起飞时间和航班成本，但智能交易可以提供特定航班准点的概率。对于一个智能交易来说，它需要历史数据，约翰逊说这是许多开发人员根本无法获得的。

“通常，您的商业智能(BI)团队可能有一个单独的数据仓库，在该数据仓库中有所有航班的完整历史记录。使用 MariaDB 平台，你不需要维护一个单独的数据仓库，因为如果你这样做了，应用程序开发人员通常无法访问。它只面向 BI 数据分析和数据科学团队，”Johnson 说。“现在，有了 MariaDB，我们可以拥有典型的交易数据—即将到来的航班和时刻表—以及所有过去航班的完整历史记录。”

Johnson 说，由于亚马逊 S3 存储的相对便宜及其扩展能力，MariaDB 可以保留所有历史数据，以提供分析性的智能交易，同时为亚马逊 EBS 等块存储的愚蠢交易提供所需的速度。总的来说，约翰逊说，这种结合是 MariaDB 未来努力的重点。

“这代表了我们的方向和愿景。这始于 X3 的 MariaDB 平台。那是我们第一次开始将交易和分析结合在一起。Platform X4 将它们完全集成在一起，为开发人员和数据库管理员创造了一个无缝的体验，随着我们构建智能事务和有洞察力的体验的概念，您可以期待在每个后续版本中看到更多。这正是我们所看到的数据库的发展方向，”他说。

MariaDB Platform X4 现已[正式上市](https://mariadb.com/downloads/#mariadb_platform-enterprise_server)，具有用于分析处理的列存储的 MariaDB Community Server 10.5 预计将于本月晚些时候上市。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>