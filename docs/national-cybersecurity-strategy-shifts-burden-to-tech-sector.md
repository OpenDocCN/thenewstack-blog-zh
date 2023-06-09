# 国家网络安全战略将负担转移到科技行业

> 原文：<https://thenewstack.io/national-cybersecurity-strategy-shifts-burden-to-tech-sector/>

上周，拜登-哈里斯白宫发布了一项新的国家网络安全战略，以保护国家的关键基础设施、网络和数据免受网络威胁。正如预期的那样，这个全面的计划概述了一个多管齐下的战略，以改善国家的公共和私营部门的网络安全。可能没有预料到的是，根据这项指令，网络安全的负担从最终用户转移到了科技行业。

## **这对软件提供商意味着什么？**

新的国家网络安全战略敦促对控制国家大部分数字基础设施的公司给予更多授权。它还敦促政府和国家支持的实体在帮助阻止黑客方面发挥更大的作用。虽然这个新文件本身并不是法律，但它确实为可能影响软件提供商的新立法设定了一个框架。

该计划侧重于五个关键支柱。

*   保护关键基础设施
*   破坏和消除威胁
*   塑造市场力量以推动安全性和弹性
*   投资有弹性的未来
*   建立国际伙伴关系

为什么要改变？在 [38 页的蓝图](https://www.whitehouse.gov/wp-content/uploads/2023/03/National-Cybersecurity-Strategy-2023.pdf)中，白宫承认其之前对自愿网络安全措施的依赖未能阻止勒索软件攻击的激增。这导致了数十亿美元的经济损失。该文件还指出了能源管道、食品公司、学校和医院等关键基础设施的“不充分和不一致的结果”。

## 转移网络安全负担

新框架的一个关键要素是将网络安全的负担从个人、企业和政府身上转移。相反，负担转移到了软件开发商和其他机构身上。新战略要求科技公司负责开发能够抵御恶意行为的软件。

事实上，该文件提出，新的法律将责任转移到未能采取合理预防措施来保护其产品和服务的软件制造商身上。这些法案将在国会和私营部门的协调下起草，包括“适应性安全港框架”，以保护“安全地开发和维护其软件产品和服务”的公司。

## 零信任授权

这项新战略是在改善国家网络安全的行政命令发布不到两年后出台的。在这份报告中，拜登白宫敦促联邦政府采用安全最佳实践，并向[零信任安全(ZTS)](https://thenewstack.io/what-is-zero-trust-security/) 迈进。

这个[零信任战略](https://www.solo.io/zero-trust/)包括加速安全云服务，包括软件即服务(SaaS)、基础设施即服务(IaaS)和平台即服务(PaaS)。它还要求集中和简化对网络安全数据的访问，以推动用于识别和管理网络安全风险的分析。它还敦促对技术和人员进行投资，以匹配这些现代化目标。

## API 网关如何帮助实现零信任安全

API 对于业务来说是必不可少的，这样程序就可以相互交互和协调。一个 [API 网关](https://www.solo.io/api-gateway/)，作为 API 和不同客户端或服务之间的中间人，以一种统一的方式访问数据，并以一种安全和有组织的方式维护 API 通信。它还提供了其他好处，如身份验证、分析等。

## 使用 API 和 API 网关时的最佳实践

零信任方法建议尽可能缩小任何隐式信任边界。这可以通过为每个服务使用单独的 API 网关以及区分内部和外部 API 来实现。

如果组织外的用户没有使用这些 API，就没有必要以这种方式提供它们。重要的是，网关管理具有关于外部 API 所需的认证量的全局规则，并且网关背后的环境可以确认这些规则被应用于传入流量。

为了保持安全性，有必要跟踪不再使用或过时的 API。一个 [API 网关](https://thenewstack.io/the-gateway-api-is-in-the-firing-line-of-the-service-mesh-wars/)可以用于这个目的，允许您测量和观察使用情况。如果某个特定的 API 不经常使用，或者如果它接收到异常数量的流量，那么应该对其进行密切监控。

这让我们考虑 API 网关的监控和数据分析能力。收集显示流量和请求详细信息的指标和记录有助于我们在潜在的安全问题被恶意用户利用之前识别它们。

## 服务网格如何帮助实现零信任

[服务网格](https://www.solo.io/topics/service-mesh/)提供了一种全面的方法来满足零信任模型的所有方面。

正如 [CISA](https://www.cisa.gov/zero-trust-maturity-model) 和 [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-207.pdf) 框架所建议的，服务网格促进了遵循最佳实践的能力，例如减少隐含的信任边界和为每个服务实现单独的 API 网关。此外，它还有助于优化身份、网络/环境、应用程序工作负载和数据支柱。以下是方法:

### 访问控制

在[服务网格](https://thenewstack.io/service-meshes-in-the-cloud-native-world/)中，实施了多级安全协议来限制访问并确保安全通信。这些包括网络规则、授权和根信任策略。

### 资源保护

实施服务网格中的网关和侧柜来保护连接的资产。网关在集群级别上确保 Kubernetes 集群之外的资源的安全，而 sidecars 为每个资源提供更复杂的安全级别。

### 监控和分析

为了使服务网格保持安全并实施其策略，所有网关和侧柜都必须配置为发送度量和日志。像 [Gloo Platform](https://www.solo.io/products/gloo-platform/) 这样的管理工具可以设置这种配置，当数据屏蔽被添加到组合中时，它会创建一个零信任治理系统。

### 最小特权

服务网格中的单个配置可以对工作负载之间的网络通信实施“全部拒绝”。然后，授权、网络和安全策略可用于基于身份验证有选择地开放通信。

## 企业如何准备

虽然拟议的立法似乎主要涉及科技行业的公司，但其他拥有多元化公司组合的大公司也可能受到影响。坚持零信任模式可以帮助所有组织抢先保护他们的数据免受未经授权的访问。更进一步，组织应该研究 [FIPS 认证、](https://www.solo.io/fips/)以及 [FedRAMP](https://www.solo.io/resources/webinar/how-fips-enabled-software-can-help-you-get-fedramp-certified/) 批准。

为了防止攻击的后果，无论是财务负担、对公司信誉的打击还是政府行为，组织都应该考虑立即采取行动。现在采取行动有可能让企业、消费者和国家安全受益。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>