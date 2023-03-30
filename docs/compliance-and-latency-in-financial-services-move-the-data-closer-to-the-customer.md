# 金融服务中的法规遵从性和延迟:让数据离客户更近

> 原文：<https://thenewstack.io/compliance-and-latency-in-financial-services-move-the-data-closer-to-the-customer/>

[](https://www.linkedin.com/in/jessica-edwards-33746a20/)

 [杰西卡·爱德华兹

杰西卡是蟑螂实验室的内容营销总监，蟑螂数据库的开发者。她对开源软件充满热情，已经向开发者推销了 10 多年。](https://www.linkedin.com/in/jessica-edwards-33746a20/) [](https://www.linkedin.com/in/jessica-edwards-33746a20/)

随着脸书、谷歌以及 Betterment 和 Robinhood 等新一代金融科技应用推动消费者期待功能丰富的应用，每个企业都需要关注性能。虽然这仍然是金融服务组织的首要任务，但银行业特有的另一个组件也是重中之重，即保持较低的延迟。对于银行来说，云原生应用程序的另一个显著优势是，它们可以以低延迟支持非常大的交易量。

传统上，减少延迟的主要驱动因素是加快交易速度和增加收入，或者最大限度地减少潜在的收入损失。在 2012 年的[速度福音](https://www.thinkwithgoogle.com/intl/en-gb/future-of-marketing/digital-transformation/the-google-gospel-of-speed-urs-hoelzle/)中，谷歌透露，搜索页面生成延迟 400 毫秒导致搜索流量下降 0.44%。现在，每次谷歌搜索，你都会看到返回结果需要多少毫秒。大约在同一时间，在一名员工工程师的演示中，[亚马逊透露](https://www.gigaspaces.com/blog/amazon-found-every-100ms-of-latency-cost-them-1-in-sales/)每 100 毫秒的延迟会损失其 1%的销售额。还有无数其他公司因延迟或停机而面临收入损失的例子。

在金融服务中，低延迟通常与高频金融交易联系在一起；或者是完全自动化和优化的交易，以利用不断变化的市场价格。这些应用程序每毫秒做出数百万个决策，因此比竞争对手的系统快几分之一秒接收数据就相当于数百万美元。大多数其他行业没有这些要求，尤其是在严格的合规指导原则和法规下。

但是，低延迟应该是每个金融服务组织都关心的问题。最近[的一项研究](https://www.computerweekly.com/news/252495737/Latency-higher-priority-than-speed-as-IT-leaders-look-to-gain-edge)发现，近 90%的商业领袖需要 10ms 或更短的低延迟来确保他们的应用程序成功。金融服务组织还必须考虑延迟对新用例的影响，如加密货币、边缘计算、人工智能(AI)和机器学习(ML)。通过利用低延迟，数据科学家可以做出明智的实时商业智能决策。此外，银行可以使用人工智能进行实时欺诈检测。

## **多区域部署和地理分区**

大多数数据通过公共网络在分布式应用程序的元素之间移动。这意味着，如果一个架构完美的应用程序必须与数千英里之外的数据库通信，它也会经历延迟。由于大多数银行的业务跨越地区、国家甚至全球，他们需要考虑这些分散的应用程序或客户来做出基础架构决策。理论上，解决方案很简单:将数据放在离应用程序或客户更近的地方。让数据更接近用户的一种方法是通过多区域部署。

对于一家为其客户身份访问管理(CIAM)寻求新数据库解决方案的[美国金融软件公司](https://resources.cockroachlabs.com/case-study/financial-services)，多区域部署是实现高性能和一致性的解决方案。CIAM 层最初构建在 Oracle 上，使用 GoldenGate 进行多区域复制。然而，该公司很快发现这种配置不能提供所需的速度或随时可用的登录体验。客户在创建账户*、*后会经历认证延迟，导致用户体验不佳。该团队决定在美国的三个 AWS 地区部署 CockroachDB，它通过复制数据和分发副本来最大限度地提高地理多样性，从而带来了弹性。

然而，对于具有分布式数据库的组织来说，多区域部署可能是复杂的，因为管理一组机器的状态从来都不是简单的。组织需要确定收益是否超过成本，因为使用单区域部署不利于速度和可用性。这就是数据地理分区的用武之地。[地理分区](https://www.cockroachlabs.com/blog/geo-partitioning/)提供行级复制控制，这意味着组织可以将数据附加到特定位置。

例如，一家[全球金融数据公司](https://www.cockroachlabs.com/blog/global-financial-data-firm-migrates-off-oracle-to-cockroachdb/)部署了 CockroachDB，通过创建一个混合的地理分区部署来减少四个 GCP 地区和两个本地数据中心的延迟。该公司已经无法满足其昂贵且过时的 Oracle 数据库体系结构的需求。它选择 CockroachDB 来迁移其身份访问管理微服务，因为地理分区功能提供了一种用于认证实体的解决方案，即使在与特定地理区域紧密相关的情况下也是如此。

即使客户移动或旅行，地理分区也可以工作，这对支付应用程序至关重要。

## **不要忘记规定**

除了在多个地区运营的银行的速度复杂性之外，金融机构还需要考虑数据法规。

数据隐私是一个热点问题，每年都有新的法律法规生效。

2020 年初，[120 多个国家](https://www.endpointprotector.com/blog/data-protection-legislation-around-the-world-in-2020/)制定了 200 多项保护数据和消费者隐私的法律。这些法规从较新的全州范围的要求，如 2018 年[加州消费者隐私法](https://oag.ca.gov/privacy/ccpa) (CCPA)，让消费者对企业收集的个人信息有更多的控制权，到全面的法规，如[欧盟通用数据保护法规](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-constitutes-data-processing_en) (GDPR) *、*，涵盖了从数据收集和共享到数据存储、擦除、销毁等所有内容。

在扩大区域或全球客户群时，组织需要牢记这些法规的最重要方面，即它们通常禁止在特定边界之外存储特定数据。例如，这可能意味着一家在欧洲拥有客户的美国银行可能需要将这些客户的数据存储在欧盟内部。让数据更靠近应用程序或客户提供了地理分区的另一个重要好处。将数据锁定到特定位置的能力有助于确保要求将数据存储在境内的国家或地区的合规性。

通过使用为多区域部署提供[地理分区的数据库解决方案](https://www.cockroachlabs.com/blog/5-reasons-to-build-multi-region-application-architecture/)，银行和金融服务机构的开发人员可以在数据库、表和行级别指定数据的存储位置。有了它，组织可以以尽可能低的延迟交付其应用程序，同时遵守最新的数据保护和隐私法规。

***下载电子书“** [**金融服务公司如何成功地将关键应用迁移到云上**](https://resources.cockroachlabs.com/guides/banking-guide-to-the-cloud) **”了解更多信息。***

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>