# 数据 2023 展望:重新思考现代数据堆栈

> 原文：<https://thenewstack.io/data-2023-outlook-rethink-the-modern-data-stack-1/>

随着我们进入本世纪 20 年代的第四年，全球经济继续动荡已不是什么秘密。会不会出现衰退？这是任何人的猜测，这种不确定性对像 [Snowflake](https://finance.yahoo.com/quote/SNOW/) 这样的热门增长技术成长股产生了影响，同时为像 [IBM](https://www.cnbc.com/2022/12/27/ibm-stock-outperformed-technology-sector-in-2022.html) 和 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 这样不太性感的老牌支柱提供了喘息的机会。

这一惊人的增长主要是在云中。自疫情诞生以来，故事一直围绕着 COVID 加速云应用增长的现有长期趋势展开。展望未来，通常的怀疑仍然是预测 2023 年云支出的增长，但雪花的[下调了第四季度的指导](https://www.cnbc.com/2022/11/30/snowflake-snow-earnings-q3-2023.html)指出了一种可能的说法，即“无论出现什么，都必须(在某个时候)下降”，或至少放缓。

在本帖中，我们就云数据平台和分析的运营方面发表了我们的预测。明天，我们将在后续文章中关注数据管理方面的发展。但首先，让我们了解一下这种情况发生的原因。

这不会是网络泡沫 2.0。

总体情况是这样的:尽管或因为经济的不确定性，云的采用将继续推进。

毫无疑问，云不再是将成本从资本转移到运营预算的财务预算策略；这使得整体采用率对整体经济的峰值相当有弹性。它是业务转型的推动者和加速器，因为它消除了启动新应用程序和业务服务的许多障碍，并提供了比系统更容易改变的灵活性，在数据中心内运行自己的专用基础架构。

经济不确定性只会增加企业转型的压力。所以，不，这不会是互联网泡沫破灭的重演。即使像亚马逊、T2、Meta、甚至谷歌这样的互联网巨头可能会裁员，主流经济中的企业也会乐意吸收他们能找到的所有云基础设施、网络安全、数据科学、人工智能专业知识。

虽然我们不会看到云采用的缩减，但我们会看到对云支出的更多审查。虽然云计算和存储可能很便宜，但很多便宜最终会变得昂贵。更重要的是，聚光灯会以更多的方式展现自己，而不仅仅是武断的预算上限；相反，我们预计它还将出现在平台选择中，并希望简化他们的现代数据堆栈，直到最近，云一直在分解这些堆栈。云本该让它变得简单，在接下来的一年里，企业将让超大规模者的脚在火上燃烧，以实现这一承诺。

当然，优化云支出有多种攻击方式。有一个完善且多样的解决方案生态系统，从超大规模的监控工具(如 AWS CloudWatch)到供应商，如 [BMC](https://www.bmc.com/?utm_content=inline-mention) 、 [CloudBolt](https://www.cloudbolt.io/) 、 [Datadog](https://www.datadoghq.com/) 、[dyna trace](https://www.flexera.com/)、【Flexera】、 [Micro Focus](https://www.microfocus.com/en-us/home) 、 [ServiceNow](https://www.servicenow.com/) 、VMware、 [Yotascale](https://yotascale.com/) 、 [Zerto](https://www.zerto.com/) 和这些解决方案中有许多可以深入到 SaaS 服务、应用程序和部门组织的精细消费报告。将这些工具视为传统 IT 服务管理和 IT 计费解决方案的现代云表现形式。

这枚硬币的另一面超越了传统的玻璃窗格，这就是服务的交付方式。[例如，AWS](https://aws.amazon.com/?utm_content=inline-mention) 提供数百种服务，涵盖从分析到应用集成、容器中心、容器、数据库、游戏、物联网、机器学习、量子计算、安全、存储等各个方面。试图从充裕的角度进行优化已经足够具有挑战性了。回到我们的核心观点，即复杂性是效率的敌人，复杂性增加了成本。由于数据是我们生活的车道，我们将把焦点放在那里。在数据领域，我们有一个非常诱人的目标:现代数据堆栈。

由于数据是我们参与的领域，让我们将目光集中在如何使数据管理合理化上。是时候切入正题了。

## 简化面向云的现代数据堆栈

如果你想更聪明地使用云，复杂性就是你的敌人。去年，我们在自己的帖子[中对此大肆宣扬，云什么时候会变得更简单](https://www.zdnet.com/article/data-2022-outlook-part-i-will-data-clouds-get-easier-and-streaming-get-off-its-own-island/)？

我们期待看到所谓的“现代数据堆栈”的重构，正如各种提供商所描述的那样，如 [Fivetran](https://www.fivetran.com/blog/what-is-the-modern-data-stack) 和 [MongoDB](https://www.mongodb.com/basics/data-stack) 。该堆栈通常包含用于获取、转换和接收数据的数据管道(ETL 工具的现代继承者)、数据仓库以及用于获得洞察力的各种可视化和分析工具。除此之外，我们还要添加操作或事务数据库，它通常是这些数据的主要来源。

是什么让数据栈变得现代？嗯，它是在云中托管和[交付的](https://thenewstack.io/how-mongodbs-atlas-helped-amadeus-reengineer-a-crucial-app/)，它利用了云的弹性。好了，这是一个开始；客户不再需要担心补丁程序和升级的配置或日常管理，而且由于许多现代数据堆栈服务都是无服务器的，因此前期的麻烦少了很多，灵活性也大了很多。

但这还不够。现代数据堆栈拥有几乎过于丰富的数据和分析 SaaS 服务，虽然每个 SaaS 服务都单独使其自己的流程更简单，便于客户启动和管理，但他们仍然需要集成它们。我们有没有忘记提到，这些工具链会变得非常复杂？

我们已经呼吁数据库和分析 SaaS 提供商，从字面上来说，得到它在一起。让顾客的生活更简单。越简单越经济，越简单越聪明。客户浪费的周期和费用更少，提供商消耗的增值服务更多。每个人都应该赢。在过去的一年中，我们看到一些提供商开始感受到您的痛苦，这是我们预计在 2023 年看到更多积极回应的地方。

## 寻找捆绑

这个唾手可得的果实是为了提供经常一起使用的服务组合。这在内部解决方案领域已经是一种由来已久的模式。在这里，我们对今年在哪些领域会出现更多联系做出了一些预测和建议。

捆绑销售为超大规模客户将其合作伙伴计划提升至新的白金级提供了绝佳机会。它将涉及通过预集成、捆绑和促销定价流行的第三方服务来扩展核心数据库和分析服务，并通过幕后编排将它们缝合在一起。我们的目标是减轻客户的负担，与您最受欢迎的合作伙伴合作，并对这些组合进行有吸引力的定价，以刺激采用。

我们来举几个例子。向事务数据库中添加轻量级分析，对于更“严重”的用例(您不希望通过分析降低事务处理的速度)，将变更馈送预打包到数据仓库服务中，您可以在其中执行 ELT。至于英语教学，在目标中有现成的集成。这就是竞争机会的来源。AWS Glue、Azure Data Factory、Google Cloud Data Fusion 将分别凭借 Redshift、Synapse Analytics 和 BigQuery 获得主场优势。但是开发者不会放弃他们自己的最爱，比如 dbt 或者 Fivetran。这就是您的合作伙伴计划开始捆绑预集成堆栈的原因。顺便说一下，这同样适用于分析和 AutoML 服务。

数据库内机器学习已经成为云数据仓库服务的一个复选框功能，尽管数据必须移动的程度仍然因提供商而异。将轻量级运营分析融入交易数据库的工作也已经开始。谷歌和[甲骨文](https://www.oracle.com/mysql/heatwave/)引入了 MySQL 和 PostgreSQL 的 API 兼容实现，结合了三大优势:事务处理、分析和数据库内自动建模。与此同时， [SingleStore](https://www.singlestore.com/resources/whitepaper-introduction-to-singlestore/) 重新发明了分层存储和索引。甚至雪花也已经开始尝试用 Unistore 进行轻量级事务处理。

当然，所谓的(取决于你用的是 Gartner 的还是 Forrester 的术语)[增强分析](https://www.gartner.com/en/information-technology/glossary/augmented-analytics)或者 [translytical](https://www.singlestore.com/resources/industry-report-the-forrester-wavetm-translytical-data-platforms-q4-2022/) 数据库并不新鲜。添加列和行存储的做法可以追溯到十多年前的 IBM BLU、Oracle 数据库内存、MariaDB SkySQL 等等。

但是如上所述，我们不要止步于此。融入英语教学。AWS 至少通过预建的 [Zero ETL](https://aws.amazon.com/about-aws/whats-new/2022/11/amazon-aurora-zero-etl-integration-redshift/) 变更数据捕获馈送简化了 Aurora 到红移的数据管道。谷歌已经在 BigQuery 中内置了变更数据捕获支持，而 Azure Synapse Analytics 则预集成了 Azure Data Factory。对于几乎每一个分析平台，都有大量的机会融入流以及与数据流管道和 Kafka PubSub feeds 的集成。客户不必自己单独配置这些集成，也不必支付照单定价。

交易数据库和数据仓库的独立平台不会消失，最终用户也不会放弃他们的可视化或报告工具。但我们预计超大规模和第三方 SaaS 服务在混合、捆绑和定价方面会更有创意。这里有一个潜在的例子。在 Google Cloud 中，几个数据库(例如 AlloyDB、BigQuery、Dataproc)共享公共存储。借助 Google 的 Dataplex 数据结构提供的统一治理，数据可以由选择的引擎有选择地呈现，并按使用付费。

## 无服务器起辅助作用

迈向更智能的云消费的另一个趋势是无服务器的增长。它提供了一种明显的简化形式，客户不再需要担心资源调配或容量调整。临界质量的超大规模数据库已经提供了它；例如，通过 OpenSearch，AWS 刚刚解决了其分析产品组合中缺少无服务器的最后一个缺口。我们希望看到新的条目，如 Oracle MySQL Heatwave 和 Google AlloyDB 也提供无服务器选项。当然，无服务器并不是万能的，因为如果您的工作负载是稳定的和/或可预测的，那么保留实例显然是更好的选择。但对于新的工作负载，无服务器消除了摩擦，更不用说过度配置的成本，这应该会鼓励更多的开发。无服务器可以是新工作负载的入门级阶段，随着吸收的成熟，可以转移到保留的实例。

虽然无服务器已经在云数据仓库、分析和机器学习服务方面站稳了脚跟，但我们预计今年会有更多的交易和运营服务加入这一选项。

## 多云呢？

关于云生活的一个核心事实已经写了太多的废话:大多数组织将使用不止一个云。我们一直抱怨管理多个云会带来管理开销。但是就像板块构造一样，没有回头的现实选择，此外，出于竞争的原因，任何组织都应该把自己的命运绑在一朵云上吗？

我们认为，多云是关于云的自由:在您选择的云上运行工作负载的自由。考虑到延迟、不同的安全性和访问管理结构以及超大规模环境之间的基础架构差异，我们[并不十分相信](https://www.zdnet.com/article/the-myths-and-truths-about-multi-cloud/)在多个公共云中运行相同的工作负载或数据库。当然，大自然厌恶真空，当然，这就是各种第三方介入的地方。关于数据服务，云自由在来自 [Databricks](https://thenewstack.io/databricks-brings-data-pipeline-service-to-ga/) 、Snowflake、MongoDB 等公司的消息中非常突出。他们承诺，无论每个超大规模服务器的基础架构和管理差异如何，在操作上，无论您在哪个云中运行，他们的数据库服务看起来都是一样的。

然而，多云是简化的下一个前沿。我们将向 Silicon Angle 大声疾呼，以确定云生态系统的新兴层，他们称之为[超级云](https://siliconangle.com/2022/05/21/supercloud-becoming-thing/)。但与此同时，超大型企业将忙于简化自己后院的老鼠窝。

明天，我们将看看【2023 年对数据迷们来说意味着什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>