# 企业为什么需要管理平面

> 原文：<https://thenewstack.io/why-enterprises-need-a-management-plane/>

这是三部曲系列的第三部。阅读[第一部分](https://thenewstack.io/data-control-management-three-planes-different-altitudes/)和[第二部分](https://thenewstack.io/why-developers-need-a-management-plane/)。

在[云原生](https://www.nginx.com/resources/glossary/cloud-native-app-delivery/)基础设施的控制平面上工作并不适合胆小的人。

 [埃里克·布劳恩

Eric 是 F5 NGINX 产品管理和商业战略副总裁。Eric 在 SaaS、PaaS 和 IaaS 领域工作了 20 年，在公有云、私有云(系统软件)和混合云领域拥有 10 年的经验，任职于 Joyent、三星、甲骨文和德国电信的 MobiledgeX(已被 Google 收购)。Eric 是社区和生态系统的架构师，拥有开发人员体验领域的专业知识，以及云与电信和新兴 AI、ML、XR 和其他用例及互联设备的交叉。](https://www.linkedin.com/in/ebraun/) 

菜单很少，配置文件很多，控制平面很容易出错，尤其是当一个没有经验的管理员试图设置流量控制、安全或访问控制策略时。

在某种程度上，这是因为应用程序的传统控制平面是在角色和专业产品较少的时候出现的——您的企业可能只有少量的负载平衡器、几个应用交付控制器(ADC)实例、全局防火墙和 web 应用防火墙(WAF)。

如今，拥有大型云原生应用的企业可能需要数万个[负载平衡器](https://www.nginx.com/resources/glossary/load-balancing/)，每个都有自己的 [WAF](https://www.nginx.com/resources/glossary/what-is-a-waf/) 。这些分布式网络和流量管理元素位于分布式且不断移动的[容器](https://www.nginx.com/resources/glossary/container/)的前面。即使对于最精明的 DevOps、NetOps 或 DevSecOps 团队来说，通过脚本而不是抽象来管理整个舰队也是一项巨大的成就。

但是云原生的全部意义在于让更多的人能够自给自足，并把能力转移到左边。与此同时，我们需要让人类能够以机器的速度管理这个不断变化的计算万花筒。

在这个大规模计算和容器的时代，在各种控制平面之上需要一个抽象层来设置和实施策略，以提供企业范围的可观察性，并提供跨一切的安全层。

这个新层就是管理平面，它是云运营中最新的基本工具。管理平面是支持云原生系统为整个企业大规模交付承诺的效率和功能的关键。

## 什么是管理平面？

在大型组织的网络系统和架构中，我们长期以来从两个层面考虑管理:

*   粗略地说，**数据平面**是数据生活、移动和活动的地方。网络系统——[负载平衡器](https://www.nginx.com/resources/glossary/cloud-load-balancing)、[防火墙](https://www.nginx.com/resources/glossary/what-is-a-waf/)、 [API 网关](https://www.nginx.com/learn/api-gateway/)、i [网络控制器](https://www.nginx.com/resources/glossary/kubernetes-ingress-controller/)、[缓存系统](https://www.nginx.com/resources/glossary/caching/)在这里检查入站和出站数据包，并决定如何处理它们。
*   **控制平面**是位于数据平面之上的策略层，在这里管理和配置控制数据平面行为方式的规则。

![](img/e76c900f346b256de582c607748f5959.png)NGINX 产品设计的一个长期坚持的原则是，为了使您的架构具有可伸缩性并且与系统和架构无关，这两个层面必须完全分离。

随着云原生、左移和现代应用的兴起，我们看到了对更深一层抽象的新需求:管理平面。管理平面是控制平面之上的一层，它降低了控制平面上的管理复杂性，并使企业内部的不同角色更容易管理应用程序、网络和计算资源。

[平台运营团队](https://thenewstack.io/platform-ops-the-next-frontier-for-operations-teams/)设计和配置管理平面。管理平面的用户可能包括通常的嫌疑人:应用程序开发团队、DevOps、SecDevOps、SecOps 和 NetOps 团队。

除了这些核心网络、应用管理和安全团队之外，许多其他团队可以使用管理平面更轻松地完成工作，同时保持在旨在安全提供可扩展性、安全性、弹性和可观察性的架构护栏内。

管理平面的其他受益者包括 IT 团队、采购团队、API 管理团队、基础设施管理团队甚至营销团队。换句话说，管理平面变成了一个广泛的产品，它给用户带来的好处远远超出了传统的网络、安全和应用程序开发团队。

## 有了原生云，每个人都是基础架构工程师

随着我们过渡到面向云原生时代的现代应用，集中控制和角色专业化的整个概念已经被颠覆。考虑构建微服务的普通开发人员。过去，他们主要担心应用程序代码的质量。

但是有了现代应用，开发者有了更多的责任。为了确保他们的微服务运行和扩展，他们需要设置理想的流量管理策略和负载平衡规则，为 [WAF](https://www.nginx.com/learn/waf-web-application-firewall/) 配置防火墙规则，设置 API 速率限制和重试策略——这只是在流量级别！在很大程度上，执行这些任务需要控制平面和数据平面的详细知识，并结合 mad 脚本印章。

营销技术专家也是如此，这是一个更新但发展迅速的角色。他们需要根据市场营销的需要上下扩展他们的系统，并且通常比应用程序开发人员高一层。但是，在保证营销体系基础设施的安全性、弹性和可观察性方面，他们有着相同的顾虑和需求。

将此应用到 NetOps 体验中，他们现在的任务不仅是管理使用一套全球设备的全球网络的网络安全性和可靠性，还包括跨不同云、供应商等的多种类型的网络实例。

这不是网络团队的初衷，也是不可持续的。即使是从一个主要系统发展到两个系统，也意味着复杂性呈天文数字增长。再加上 [Kubernetes](https://www.nginx.com/resources/glossary/kubernetes) ，事情变得更加复杂；混合的[第 7 层](https://www.nginx.com/resources/glossary/layer-7-load-balancing/)和[第 4 层](https://www.nginx.com/resources/glossary/layer-4-load-balancing/)流量以及新的数据路由和控制方法使网络看起来和感觉完全不同。

## 管理平面降低了复杂性，增强了控制力，并支持扩展

仅仅向新的利益相关者公开控制平面管理工具是不够的；这更有可能增加他们工作的复杂性和范围。这就是为什么企业必须考虑拥抱管理平面。让我们看看管理平面如何帮助特定的团队。

*   **开发人员:**管理平面提供了一个单一界面，微服务所有者可以从一个基本的设置和配置列表中选择应用所需的所有基础设施，包括负载平衡器或入口控制器、API 网关、WAF 等。服务所有者可以从配置和策略的精选列表中进行选择，允许他们为自己的应用程序运行时、网络和安全性设置参数。这使得左移，敏捷性和速度，同时最大限度地减少认知负荷和专业知识的要求。
*   **网络运营团队:**管理平面支持跨所有网络应用的快速更改和策略检查，而无需网络运营团队学习多种编码语言，如 NGINX conf 脚本、 [YAML](https://yaml.org) 和 [Terraform 的脚本语言](https://www.terraform.io/language)。管理平面还允许他们将所有网络系统的可观测性和遥测数据导出到集中的可定制仪表板和报告中。
*   **业务线工程师:**使用管理平台采购实例来扩展他们的系统，确信这些实例已经具有所有正确配置的安全、流量和重启设置。

在所有这些团队中，管理平面解决了一个共同的问题:需要考虑的事情太多。为了确保 shift left 有效，并确保组织可以转换到云原生并快速运行以构建现代应用程序，所有团队都需要学会用更多资源做更多事情。NGINX 认为,[针对生产力、弹性和安全性进行调整的管理平面层](https://www.nginx.com/blog/connect-scale-secure-apps-apis-with-f5-nginx-management-suite/)消除了控制平面和数据平面的复杂性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>