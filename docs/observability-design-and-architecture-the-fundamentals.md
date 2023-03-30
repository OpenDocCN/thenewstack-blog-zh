# 可观察性设计和架构:基础

> 原文：<https://thenewstack.io/observability-design-and-architecture-the-fundamentals/>

[](https://www.linkedin.com/in/baileyedward/)

 [Ed Bailey

Ed 是一位热情的工程倡导者，在为各种应用、操作系统和硬件提供操作和安全观察方面拥有 20 多年的经验。](https://www.linkedin.com/in/baileyedward/) [](https://www.linkedin.com/in/baileyedward/)

*这是关于可观察性设计和架构如何需要从基础开始的两部分系列的第 1 部分:将人和过程放在一切的中心。[第二部分](https://thenewstack.io/technology-decisions-for-a-successful-observability-strategy/)是关于技术方面的。*

在现代 IT 环境中获得[可观察性](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/)是越来越多的企业发现难以克服的挑战。复杂的数据、高数据量和速度、云计算的兴起以及 Kubernetes 等快速变化的应用平台，使得在没有合适的人员、流程和技术的情况下，很难从可观察性管道中创造和获取价值。复杂性从未如此之高。企业将如何架构和设计他们的可观察性工具来克服这些挑战，并在现代企业中获得可观察性？

## **一切还是从人和流程开始**

作为一名[技术人员](https://cribl.io/blog/introducing-cribl-developer-evangelist-ed-bailey/?utm_campaign=thewnewstackreferral&utm_medium=sponsoredarticle&utm_source=thenewstack&utm_content=hyperlinktexttechnologyperson)，我原本认为工具应该解决一切，但我发现人员和流程仍然是任何 IT 职能实现重大变革的基础。我痛苦地认识到，我本应该花更多的时间来实施可持续的流程，以支持长期的成功。从我的错误中吸取教训，花尽可能多的时间在人员和流程上，就像花在正确的硬件和网络设计上一样。

让我们讨论将可观测性团队置于成功位置的通用基础步骤。

### **人**

成功的日志记录需要的不仅仅是可观察性团队。它需要一个数据/记录治理团队、一个架构团队、一个法律支持团队和一个安全团队向足够高的领导层汇报，以便在高级领导层解决问题。当开发团队因为工作量太大而关闭日志记录时，高层领导必须参与进来，与开发领导一起解决问题。可观察性是一个战略目标，需要在整个企业中如此对待。可观察性团队还需要治理支持，以跟上在美国和世界各地如何管理数据的不断变化的规则。[数据隐私法规](https://cribl.io/resources/using-cribl-logstream-to-support-data-governance/?utm_campaign=thewnewstackreferral&utm_medium=sponsoredarticle&utm_source=thenewstack&utm_content=hyperlinktextdataprivacyregulation)的兴起几乎势不可挡，因此可观察性团队需要与了解问题并优先解决问题和消除障碍的专业人士合作。

### **流程**

该过程从数据治理开始，并且是任何大中型企业成功进行日志记录所必需的。日志团队无法亲自与每个开发人员、操作系统所有者、工具所有者或任何生成日志的人合作。企业需要明确的规则来:

1.  数据格式。
2.  数据格式是如何改变的。
3.  如何将新设备添加到日志记录中。
4.  伐木业的资金来源。
5.  记录数据后如何管理数据。
6.  如何与测井团队共享数据规则和规定。
7.  问责制。

度量、事件、日志和跟踪(MELT)是大多数企业中最不稳定的数据，如果没有明确的规则，数据问题很快就会失控。拥有强大治理团队的质量过程可以从混乱中带来秩序。

## **关于人员和流程重要性的例子**

### **格式管理**

企业可能有数百种日志格式需要跨每个设备、装置以及内部和第三方应用程序进行管理。每种格式都会增加人员、流程和技术的开销，并使数据法规合规性变得更加困难，用户搜索也更加困难。

### **我们来谈谈 Syslog…**

许多应用程序和设备使用 [syslog](https://cribl.io/resources/replacing-your-syslog-server-with-logstream/?utm_campaign=thewnewstackreferral&utm_medium=sponsoredarticle&utm_source=thenewstack&utm_content=hyperlinktextsyslog) 作为默认的日志格式。不幸的是，许多供应商习惯性地给猪涂上口红，并称之为“系统日志”

*   通过 UDP 推送结构化数据不是 syslog。
*   TCP 上连续的随机数据流不是系统日志。
*   通过 UDP/TCP 推送随机数据不是 syslog！

Syslog 有定义明确的标准，如果遵循这些标准，在日志记录工具中会发挥神奇的作用。对于所有正在阅读这篇文章的供应商:请为了对日志的热爱，遵循下面的 syslog 标准！

https://datatracker.ietf.org/doc/html/rfc3164**RFC 3164**–[](https://datatracker.ietf.org/doc/html/rfc3164)

**RFC 5424**–[https://datatracker.ietf.org/doc/html/rfc5424](https://datatracker.ietf.org/doc/html/rfc5424)

最后，不要让我从时间戳开始。没有毫秒精度的时间戳会有后果。

### **数据隐私条例**

由于距离和不断扩大的数据隐私法规，例如欧盟的《一般数据保护条例》(GDPR)、新加坡的《个人数据保护法》(PDPA)和日本的《个人信息保护法》(APPI)，跨国企业的复杂性正在增加。数据隐私法可能会对违规行为处以重罚。拥有一个能够接触法律的强大的治理团队对于了解规则以及如何保持企业的合规性是至关重要的。犯错是很容易的。

例如:假设您正在使用几个小国家的消费者个人身份信息(PII)处理交易，而该过程实际上发生在另一个国家。每个提供 PII 数据的国家都有权要求该公司和所有有权访问 PII 数据的外国人遵守一项数据共享协议，该协议列出了有权访问的任何人的国籍。

因此，协议是与公司、处理交易的业务部门和有数据隐私法规的国家达成的。你以为你的法规已经涵盖在内了，但是唉，你忘了你在印度的 L1 服务台。该国对该公司的罚款超过了其去年在该国的收入，并威胁说，如果再次发生这种情况，将禁止该公司今后开展业务。

小错误越积越多，数据隐私法规是可观察性团队无法独自管理的重点领域。要在快速变化和日益复杂的监管环境中取得成功，需要来自治理团队的支持。

### **应用复杂性**

随着企业采用像 Kubernetes 这样的平台，应用程序的复杂性正在激增。企业需要能够同时管理遗留日志和下一代应用平台，如 Kubernetes。在过渡到现代云原生平台时，需要规划和强大的工具集来保持传统工具的运行。

根据 [Kubernetes 和云原生运营报告](https://juju.is/cloud-native-kubernetes-usage-report-2021)，45.6%的受访者在生产中使用 Kubernetes，尽管只有 15.7%的受访者专门使用 Kubernetes。

考虑到这项调查是为对 Kubernetes 感兴趣的前瞻性企业自行选择的，这是一个很好的数据。这种转变正在发生，但速度缓慢。企业必须选择构建或购买合适的软件来帮助管理这一过渡。您的企业和应用程序架构师应该在 Kubernetes 之旅的早期就让 observability 团队参与进来。

Kubernetes 日志有许多方面，包括安全性、应用程序和操作日志。您的 Kubernetes 平台也必须考虑在内。AWS 上的 Kubernetes，Azure 等。，都有点不同，所以这些细节都要考虑进去。我不能强调与您的安全团队合作以确保您有良好的覆盖面是多么重要。Kubernetes 是一个功能强大的平台，它正在改变应用程序的管理方式，但它的许多层、一般复杂性和快速发展的工具造成了潜在的安全缺口，企业需要制定计划来解决这些缺口。

## **底线**

在你的可观察性实践的长期成功中，最重要的因素是人和过程。组织基础仍然是你成功的基础。你必须承担协调内部利益相关者的重任，以建立长期成功的组织。

在[第 2 部分](https://thenewstack.io/technology-decisions-for-a-successful-observability-strategy/)中，我们将讨论如何构建基础设施来支持可观测性。我们将探讨如何扩展您的容量，为失败做准备，并避免被容量管理谬论所困。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>