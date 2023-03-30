# SaaS 备份中的 API 瓶颈

> 原文：<https://thenewstack.io/the-api-bottleneck-in-saas-backup/>

[](https://www.linkedin.com/in/flopitaux/)

[Francois Lopitaux](https://www.linkedin.com/in/flopitaux/)

[Francois Lopitaux 是 Odaseva 的首席产品官，该公司为 Salesforce 提供企业数据平台。他为 Odaseva 带来了超过 17 年的构建企业产品和云服务的经验，从概念到超过 4 亿美元的收入。在 Odaseva 之前，Lopitaux 先生在 Salesforce 工作了十多年，担任过许多产品管理职位，包括 Einstein Analytics 产品的产品管理副总裁。](https://www.linkedin.com/in/flopitaux/)

[](https://www.linkedin.com/in/flopitaux/)[](https://www.linkedin.com/in/flopitaux/)

企业 IT 已经跨过了一个门槛，现在大多数组织都意识到他们需要保护他们的 SaaS 数据。在分析公司 ESG 的 [2021 年数据保护云战略的演变](https://www.esg-global.com/hubfs/ESG-Infographic-DP-Cloud-Strategies.pdf)报告中，64%的受访 IT 决策者表示，他们对备份 SaaS 应用程序中的数据负有部分或全部责任。

当然，还有超过三分之一(35%)的人表示，他们完全依赖 SaaS 供应商来保护他们组织的数据，这一比例太高了。因为尽管 SaaS 供应商确实非常注意保护他们的基础架构，但他们通常不会备份客户数据，因此如果数据被意外或恶意删除，客户很可能会倒霉。

此外，即使是著名的服务，也确实会发生大量的 SaaS 停机。就在最近，[atlassian 在 4 月遭遇了一次中断](https://www.atlassian.com/engineering/april-2022-outage-update)，两个星期都没有完全解决。没有备份，这些数据是完全不可访问的。

然而，备份 SaaS 数据与传统的内部数据保护完全不同，特别是因为 SaaS 备份依赖于有限的资源:API。显然，IT 无法完全控制应用程序或数据，因为数据位于 IT 团队无法管理的设备上的异地服务中。

因此，要获得这些数据，任何 SaaS 备份系统都需要通过 API 访问数据。问题是，API 调用是有上限的，这意味着 IT 团队必须确保他们为这项工作选择了正确的 API，更复杂的是，API 会随着时间而变化。这种复杂性意味着企业 IT 团队必须仔细考虑 API 的使用和管理策略。

## 硬性 API 上限

大多数 SaaS 应用程序在多租户的基础上运行，因此多个客户共享相同的资源，包括 API。因此，SaaS 提供商通常会限制单个客户在 24 小时内可以进行的 API 调用次数，以确保每个人都有足够的资源可用，并且单个客户不会消耗过多的资源。

结果是，IT 部门对每个 API 在备份中的使用量设置了硬性上限。这是一个重要的考虑因素，因为这些 API 不是备份专用的，它们也用于与其他应用程序共享信息，这些应用程序已经与 SaaS 应用程序集成在一起。尤其是在核心 SaaS 应用程序的情况下，如 Salesforce 或 ERP，将会有大量其他应用程序和服务依赖于这些 API。

为要备份或恢复的数据选择 API 以优化速度至关重要。例如，在 Salesforce 中，REST API 每小时可以移动一百万条记录，而 BULK API 每小时可以移动一千万条记录。如果它进行并行 API 调用以从 Salesforce 中多路传输数据，REST 每小时最多可以实现 1000 万条记录，而 BULK 最多可以达到 3 亿条，这取决于对象的复杂性和大小。

要点是 API 的选择会对组织的恢复点目标(RPO)产生巨大影响。您执行备份的速度越快，一天中可以完成的备份就越多。

但这并不意味着一个组织可以只依赖批量 API。为了及时提取和恢复企业的所有数据，备份系统必须充分利用所有可用的 API，比如 REST、批量、批量 V2 和 SOAP。毕竟，有些类型的对象不能被批量 API 访问，比如 share 对象，这就需要使用 REST API。

此外，批量 API 对于 IT 组织来说非常珍贵，因为他们几乎肯定会有其他使用批量 API 的系统，并且很容易遇到这种硬性限制。因此，它需要平衡 API 的使用，并管理每个 API 的使用量。

## 依赖单一 API 的问题

此外，仅仅因为 API 可以读取数据，并不意味着它可以写入数据，这对于恢复有着巨大的影响。某些对象可能可以使用另一种类型的 API 进行恢复，但不幸的是，由于 SaaS 应用程序本身的架构限制，很可能有一些数据无法恢复。

然而，仅仅因为对每个 API 的使用量有限制，并不意味着它们是一成不变的。实际的 API 限制基于客户与提供商的许可协议。因此，重要的是要模拟出使用每个 API 需要多少时间。不要忘记恢复大量数据的 API 需求。恢复真的会耗尽 API 资源，没有人希望在关键恢复期间达到 API 上限，而业务经理迫不及待地回到他们的应用程序中工作。

最后，API 会发生变化。SaaS 备份系统必须适应这些变化，这给本已复杂的管理和优化数据保护 API 的方案增加了额外的复杂性。

虽然组织肯定会理解在 SaaS 服务中备份其数据的需求，但他们可能没有意识到构建一个以满足其 RTOs 的方式保护所有数据的 SaaS 备份系统是多么复杂。仔细考虑 API 的使用并开发管理它们的策略是构建任何 SaaS 备份解决方案的关键部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>