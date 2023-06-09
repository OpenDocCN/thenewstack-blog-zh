# 数据库即服务:敏捷增长的关键技术

> 原文：<https://thenewstack.io/database-as-a-service-a-key-technology-for-agile-growth/>

[](https://www.linkedin.com/in/jdmintz/)

[Josh Mintz](https://www.linkedin.com/in/jdmintz/)

[Josh 是 IBM Cloud 的 IBM 云数据库产品主管。他专门研究数据和分析策略、云原生应用程序设计和分布式云。](https://www.linkedin.com/in/jdmintz/)

[](https://www.linkedin.com/in/jdmintz/)[](https://www.linkedin.com/in/jdmintz/)

数据库即服务(DBaaS)是一种[云计算](https://www.ibm.com/cloud/learn/cloud-computing)服务，允许用户访问和使用云数据库系统，而无需安装或管理他们自己的数据库软件。相反，云服务提供商为客户处理安装和设置以及持续维护。

分布式云使公共云服务(包括 DBaaS)在不同的环境中广泛可用，包括内部环境、云平台和边缘位置。分布式云提供商在维护底层软件的同时，支持客户在其选择的地点灵活使用云服务。

在本文中，我们将讨论 DBaaS 及其在分布式云架构环境中的核心优势。

## 为什么要使用数据库即服务？

企业可以从采用数据库即服务中获益，原因如下:

*   经济学
*   弹性
*   灵活
*   安全性
*   公开

### 经济学

 [蒂姆·文森特

Tim 是 IBM Systems 云数据服务的副总裁和 IBM 研究员。他是一位拥有 30 多年经验的知名软件技术高管。他负责推动 IBM 分析技术的整体战略，重点是与世界各地的 CxO 级高管进行客户咨询。](https://www.linkedin.com/in/tim-vincent-479632/) 

数据库即服务减轻了团队安装、部署、配置高可用性、管理安全补丁和使用数据库的其他生命周期方面的负担。由于云提供商维护数据库系统并确保可用性和安全性，DBaaS 的用户可以受益于站点可靠性工程(SRE)的专业知识，而无需雇佣或培训高价人才。

通过分布式云提供商(如 [IBM Cloud Satellite](https://www.ibm.com/cloud/satellite) )在本地使用云数据库，将 DBaaS 的内置 SRE 专业知识扩展到您的数据中心的四面墙上，无论是在提供商的基础设施上还是在您的基础设施上。

在云平台上，使用数据库即服务是 IT 从资本支出模式向运营支出模式战略转变的一部分。这对许多企业来说是一个重要的好处。通过这种转变，公司可以为客户实现应用开发工具、实践和应用体验的现代化。

无论是在内部使用还是在云平台上使用，DBaaS 的维护成本都更低，尤其是在雇佣开源和云数据库专家很困难或很昂贵的地区。在这两种环境中，DBaaS 的使用都有不同的计费方式:每小时的虚拟处理器核心数、每秒的请求数、扫描的数据量、每小时使用的 RAM 或磁盘容量。

### 弹性

云服务提供商拥有几乎无限的基础设施，这在以前是大多数组织通过资本支出在自己的内部数据中心无法实现的。这意味着使用分布式云和 DBaaS，只需在 web 控制台中按一下按钮，就可以实现全球范围内的纵向扩展和横向扩展。向新的市场和地区推出产品变得相对容易。例如，在日本启动应用程序并不需要在日本拥有数据中心。

有了 IBM Cloud Satellite 这样的分布式云服务，弹性就延伸到了云平台之间。Satellite 使您能够在另一个供应商云上提供数据库即服务，其中您将基础架构设置为卫星位置。通过单一控制台视图监控和管理所有位置的调配服务。

DBaaS 在敏捷应用开发工作的流水线阶段非常有用。云的原生理想——编写一次应用程序代码并将其部署到任何地方——通常假设每个管道阶段都有一个或多个数据库来保存和修改应用程序数据。在分布式云架构中，当应用程序代码准备好用于生产时，团队可以创建一种机制(可能使用 Terraform 脚本),用于在需要运行的任何地方部署应用程序及其数据库。持续集成/持续交付(CI/CD)管道中的生产目标可能涉及 IBM Cloud、AWS 或 Azure compute，或者位于内部的基础设施。DBaaS 为 CI/CD 增加了自动化使用多个环境的便利性和灵活性。灵活地将应用程序部署到不同的生产环境中可以节省成本，例如，云客户可以利用与特定提供商的现有关系来获得基础架构折扣。

### 灵活

除了降低运营成本和保护可用性，使用云数据库服务还可以加速应用创新。因为开发人员可以轻松地请求将数据库作为端点，所以为新的应用程序功能进行概念验证的成本就消失了。

云供应商作为服务提供的数据库越多，企业团队就越容易实施业务现代化计划来提升和转移工作负载，开发新的云原生应用程序，并适应未来用例成为业务优先事项。如果团队已经选择了数据库，灵活的云平台将帮助他们轻松地迁移数据。这也有助于团队为新工作负载选择最佳数据库。例如，IBM Cloud 提供了这八个专门构建的数据库作为服务，不久还会有更多:

*   DB2
*   Cloudant
*   一种数据库系统
*   MongoDB
*   雷迪斯
*   数据税
*   弹性搜索
*   etcd

这一系列的功能即服务——缓存、全文搜索、在线交易、非结构化数据——允许应用程序开发团队通过 IBM Cloud Satellite 快速移动，达到一定的范围和规模。 [IBM Garage](https://www.ibm.com/garage) 客户服务报告称，即使开发团队是使用云服务的新手，并且正在学习云原生技能和实践，上市时间也减少了 70%(与开发传统应用相比)。

通过云提供商管理数据库，开发团队可以更加专注于提供更好的跨地域用户体验和商业价值。分布式云跨环境提供的 DBaaS 一致性提高了开发灵活性和速度。

### 安全性

DBaaS 融入了最佳安全实践:使用 TLS 强制加密、锁定端口、IP 允许列表、要求强管理员密码等。这些功能可以防止 skunkworks 团队在组织的最佳实践之外构建数据库。在团队提供数据库实例时，一致的安全配置文件会自动限制风险。对于运行良好的 DBaaS 计划，所有内部团队都必须遵循组织政策。

因为当团队在不同的平台上运行时，治理的差距通常会显现出来，所以数据库一致性在使用多个云的组织中尤其重要。例如，不同的云供应商通过不同的生命周期 API 提供 PostgreSQL 数据库，使用不同的最佳实践将数据库集成到日志记录、监控、加密和密钥管理服务中。真正的分布式云即服务通过统一的治理层消除了 IT 产业中的盲点，使您能够通过单一控制台视图在内部或选定的云平台上配置、监控和管理 PostgreSQL 和其他数据库的所有实例。这种一致的观点也减轻了运营团队学习不同供应商平台上云服务的所有细微差别的负担。

统一高可用性是分布式云环境中 DBaaS 的另一个优势。假设你有一个金融科技应用。安全策略可能要求，在区域性操作中，应用程序必须能够故障转移到另一个云提供商。在一个云供应商在整个地区出现故障的情况下，分布式云状卫星能够快速启动应用程序，并将应用程序连接到不同云供应商数据中心的数据库实例，从而避免长时间停机。

### 公开

一旦数据到达某个地方，就很难移动了。即使选择云数据库即服务也涉及到一定程度的粘性，但使用专有的云数据库会使您的数据变得更加粘滞，并使整个应用程序更难以在云之间移动。

在一个多云世界中，能够在不同的云平台上以相同的方式运行相同的数据库成为一个基本要求。开源项目为跨平台数据迁移和应用程序互操作性提供了最佳选择。然而，只有当不同的开源数据库技术提供商不把开源代码分成特殊形式时，这种情况才成立。例如，IBM Cloud 上的所有开源数据库即服务虽然注入了 SRE 的专业知识，但仍然与最稳定的开源发行版保持直接的连续性，这确保了跨平台的互操作性。

## DBaaS 和分布式云结合起来更加强大

作为分布式云解决方案的一部分，DBaaS 的优势显著增加。开发运维团队可以使用通用 API 从单一控制台视图跨多个云和本地环境调配、监控和管理数据库，从而实现更高的灵活性。一个真正的分布式云状 IBM Cloud Satellite 在任何位置跨所有部署的服务(包括 DBaaS)提供连续性、治理和安全性。提供商的 SRE 专家管理数据库，修补和更新数据库软件。在分布式云上运行 DBaaS 的企业组织获得了部署环境的多功能性、无需大型运营团队的高扩展性，以及将更多工作投入到为客户创新用户体验的能力。

[*了解更多关于 IBM 云数据库和 IBM 云卫星的*](https://www.ibm.com/cloud/blog/announcements/deploy-managed-cloud-native-databases-anywhere-with-ibm-cloud-satellite) *。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>