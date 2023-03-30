# 为什么云数据出口非常昂贵

> 原文：<https://thenewstack.io/why-cloud-data-egress-is-expensive/>

众所周知，刚开始在云上运营的企业经常会因为每月账单上的意外数据传输费用而吃不消。

这些费用，通常被称为“数据出口”费用，可能会失去控制，这有许多业务和技术原因。但有办法让它们变得更可预测，这通常需要知识和资源，而大多数公司的员工都不具备这些。

花更多的时间来了解情况和调查权衡可能意味着为组织节省大量成本，并减少管理云基础架构的团队的惊喜。

## 什么是数据出口？

它们被称为出口费，因为大多数云提供商向客户收取将数据从他们的云*移出*或从一个数据中心*移出*到另一个数据中心的费用，包括在同一地区。向相反方向移动数据，或者将数据从 T4 转移到云提供商的数据中心，通常是免费的。出口是描述离开云的流量以及离开客户项目以连接各种内部云服务或可用性区域的云提供商基础架构内的内部流量的表述。

典型的客户将数据移出云有许多原因。数据可能需要由运行在另一个云中的应用程序访问，或者客户可能希望在切换到另一个提供商或他们自己的环境时[移动数据](https://thenewstack.io/even-seasoned-it-warriors-fumble-when-migrating-data-to-the-cloud/)。

数据可以从一个数据中心移动到另一个数据中心，无论谁拥有这两个数据中心中的任何一个，以便为灾难恢复进行复制。(这是一个特别尖锐的例子，因为在实际的灾难场景中，从云中获取灾难恢复数据通常会带来非常高且不可预测的数据出口[成本](https://thenewstack.io/7-ways-to-reduce-cloud-data-costs-while-continuing-to-innovate/)。)客户可能希望将已经在一个可用性区域运行的应用程序部署到另一个区域。这些只是人们将数据移出云环境的几个常见原因。

客户通常会对内部数据传输产生的数据出口费用感到惊讶。这是指在一个数据中心或可用性区域中运行的服务使用存储在相同区域但不同设施或区域中的数据。这种转换可以在云管理的服务(例如数据库)和运行在相同或不同区域的云虚拟机之间进行。

使用托管数据库之类的东西来节省资金和时间是有意义的，但是如果不了解数据出口费用，客户最终可能会支付远远超出预期的费用。如果不知道去哪里找或者如何监控运输过程，一些顾客可能直到发票到达时才知道费用。

“内部”和“外部”数据出口之间的区别是表面的。无论数据流向何处，将数据从一个区域移动到另一个区域所需的所有基础架构和流程都是相同的，并且对于客户和提供商来说,[都要花费实实在在的金钱](https://thenewstack.io/cloud-cost-management-for-devops/)。

## 数据传输的成本

确保高质量的数据传输对云提供商来说并不便宜。你是否认为他们收取的运输费用是公平的是一个不同的问题。让我们忽略数据中心设施的成本，如房地产、电力、冗余公用供电、备用发电机、冗余机械和电气设备、机架、电缆等，而只关注将数据从 A 移动到 b 的基础架构。

基础设施包括所有必要的交换机、路由器和站点之间的光纤，大规模实施可能需要数百万美元。这种基础架构需要定期管理、维护和升级，而容量必须随着更多客户增加资源而不断扩展。

> 提供商必须不断扩展这个网络。如果他们不投资扩张，那么链接的质量最终会因为饱和而受损。

云提供商必须与 IP 传输提供商建立良好的关系，同时维护 IP 空间，并拥有足够的冗余高带宽直接互联网电路，随时准备就绪。所有这些不仅在物理设备方面，而且在实施、维护和扩展网络的员工方面都付出了巨大的代价。

云提供商需要在地铁设施之间维护多条高容量链路，以确保始终有足够的空间满足客户不断增长的带宽需求。提供商必须不断扩展这个网络。如果他们不投资扩张，那么链接的质量最终会因为饱和而受损。

云提供商通过对数据出口收费或者将此成本捆绑到其他服务中，与客户共同承担构建和运营基础设施的成本。提供商如何包装其成本的运输部分，以及他们如何标记它们，因提供商而异。一些提供商收取较低的传输费用，同时通过收取较高的数据存储或计算服务费用进行补偿。

提供商并没有把所有的钱都装进自己的口袋，因为投资于进一步的开发和容量扩展对他们在市场中的成功至关重要。

## 简单是非常珍贵的

云发票的不透明性部分源于提供商试图为寻求云整体简单性的客户保持简单的账单。避免过多的数据出口费用需要一定水平的应用程序架构和基础设施专业知识。对于任何大规模的云客户来说，一个重要的问题是他们是否想投资构建内部专业知识。他们的另一个选择是支付额外费用，这样他们就可以立即投入运营，并希望自己不会被成功击垮。

没有深厚云经验的应用程序或基础架构架构师可能会设计出理论上看起来完美的架构。它可能包括多个可用性区域中的冗余系统、冗余网络连接等等。然而，当第一份云账单到来时，在本地站点之间、云服务之间，甚至是那些冗余的网络链接之间移动数据，可能会产生一些令人惊讶的费用。

> 看似完美的架构可能会被证明是成本过高，但有时只有在第一张账单到来后才变得清晰。

更实用的解决方案通常需要在设计中进行一些权衡，以降低成本，同时只解决少数关键故障点，而不是所有故障点。

许多客户看到了获得可预测但更大的云账单的足够价值，而无需构建创建最佳解决方案的内部能力。使用更高层的托管云服务，如数据库即服务，是获得这种可预测性的一种方式。在大多数情况下，数据出口的费用包含在服务报价中。出口仍然存在，但是每个 API 调用或数据库读写的成本包括使用服务所需的一切。通常，这会导致账单更容易理解，但代价是应用程序设计的灵活性和潜在的更高成本。

托管云提供商、咨询公司和系统集成商组成了一个蓬勃发展的行业，他们将有偿设计定制解决方案。无论如何，优化使用云是有成本的。成本的形式可能是托管服务提供商的费用、内部云架构师的工资或预打包云服务的溢价。

## 我们也对数据出口收费

我们的云裸机服务器产品 Equinix Metal 也对数据出口收费，这并不奇怪，这是 Equinix 的许多互连选择之一。Equinix Metal 的互联网出口是为无法创建自己的解决方案的客户提供的。它还可以包括到另一个云提供商的连接，或者在城域网之间传输。即使您在部署中的设施之间移动数据，我们也不会对在同一地铁内的金属服务器之间移动数据收费。(“[地铁](https://deploy.equinix.com/developers/docs/metal/locations/metros/)”是云可用性区域的 Equinix 等价物。它是一个大都市区域，包含我们的数据中心和设施之间的私有连接。)

我们在这里的总体方法围绕着灵活性。您可以与运营商达成协议，将 Metal 环境私下连接到您现有的网络，并使用 Fabric(Equinix 运营的[可扩展专用网络](https://deploy.equinix.com/fabric/))和您与提供商协商的任何传输速率设计统一费率的解决方案。对于南北和东西运输都可以这样做。

## 在归零的竞赛中，每个人都会输

传输计费并不简单，不同的云提供商采取不同的方法。一些公司设计了复杂的计量系统，而另一些公司可能提供单位带宽的统一费率。细节往往被抽象在统一费率或允许客户使用的最大带宽背后。如果客户预先计算错了使用量，他们可能会意外超出限额并收到超额账单。如果客户愿意了解数据出口成本的细节，还有其他选择，但这些选择都带有警告。

一些云提供商提供复杂的成本计算器，需要大量的时间、资源和专业知识才能有效应用。其他人在使运输成本看起来简单方面做得很好，但是在基础设施启动之前很难预测实际的使用需求。

更高的运输成本不仅意味着云提供商获得更多的利润，还意味着有更多的资本来确保高质量的服务。如果提供商开始竞相降低运输定价，客户可能会觉得运输有价值，但这种价值是表面的。

这种方法将是毁灭性的，因为在用户群和利用率增长的同时，几乎没有现金可用于持续扩展和改善底层网络基础设施。这可能会导致每个人的服务质量下降，或者供应商提供的其他领域的价格上涨。

随着下一代数据传输技术进入市场，它将使云提供商能够提供 1tb 的传输限制，而不是 100 的传输限制。价格可能会保持不变，但服务会好得多。无论客户使用的是哪种云，他们都需要理解云是一种不断发展和改进的业务。

出口费有助于创造一个新的数字景观，但作为用户，它有助于了解在引擎盖下发生了什么。理解传输不像插上交换机或路由器那么简单，可以引导客户找到在应用需求和预算之间取得平衡的解决方案。老话在这里依然适用:好、快、便宜……挑两个。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>