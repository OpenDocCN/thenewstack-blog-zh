# 复制，而不是整合:应用的前进之路

> 原文：<https://thenewstack.io/duplication-not-consolidation-the-path-forward-for-apps/>

[](https://www.linkedin.com/in/jenngile/)

[Jenn Gile](https://www.linkedin.com/in/jenngile/)

[Jenn 是 F5 旗下 NGINX 的产品营销经理，专门从事使用云原生技术(包括 Kubernetes 和微服务)的现代应用开发和安全性。她来自俄勒冈州，现在住在西雅图。](https://www.linkedin.com/in/jenngile/)

[](https://www.linkedin.com/in/jenngile/)[](https://www.linkedin.com/in/jenngile/)

随着微服务的兴起和远离单片架构，IT 和 [DevOps](https://www.nginx.com/resources/glossary/devops/) 团队专注于将基础架构中的一切整合到越来越小的平台和技术集合中。大胆的设想是每个人都在同一个“上帝平台”上，有一个管理平面、一个数据平面和一个简单的参考点。 [Kubernetes](https://kubernetes.io/) 、[云原生](https://www.nginx.com/resources/glossary/cloud-native-app-delivery/)和[微服务](https://www.nginx.com/resources/webinars/fundamentals-microservices/)将成为这一愿景的载体。每个人都在同一个页面上，使用相同的指标，使用相同的语言。网络和开发团队会突然精神融合，喜悦随之而来。

问题是，现实和关键绩效指标阻碍了发展。NetOps、SecOps 和 DevOps 团队需要非常不同的能力和指标，以至于将所有团队都塞在一个平台上并迫使他们共享一切会给各方带来真正的痛苦。

当今大多数大型企业的现实是，他们必须生活在两个世界中:云原生世界和更古老但仍然相关的整体世界。

## 现实:团队需要不同的东西

例如，NetOps 和 DevOps 对流量管理的期望不一致。NetOps 希望维护安全性和正常运行时间，主要目标是网络稳定性和一致性。网络运营团队必须保持整个公司正常运行，包括财务、人力资源、营销等领域的应用程序。所以，不，一些想要尝试新的基于 Clojure 的微服务的热情开发人员本周无法进行蓝绿展示。开罚单然后排队，哟。这种保守的观点使得 NetOps 不愿意也不能改变防火墙、负载平衡器和其他关键的网络平台。NetOps 的谨慎颠覆了快速迭代、持续测试和快照部署的整个前提，而这些正是敏捷开发运维的关键。

另一方面，DevOps，尤其是在构建云原生和基于微服务的应用时，需要能够快速地对安全规则和路由表进行更改，以现代 CI/CD 管道的速度进行测试和迭代。按照设计，服务和云原生应用程序是松散耦合的，只有当开发人员对部署有更大程度的自主权和控制权时，它们才会成功。与此同时，现代应用被分解为如此多的不同服务，以至于缺乏粒度级别的控制，这可能会显著降低开发运维的能力，以至于客户可能会注意到这一点。对于 DevOps 团队来说，由他人控制他们的部署的想法感觉就像回到了 20 世纪 90 年代，当时他们必须等待一个月才能获得服务器。

对于 SecOps 而言，微服务和 Kubernetes 带来的安全挑战无法仅通过传统方法(如隔离安全)来解决。虽然 SecOps 能够在 Kubernetes 集群之外执行策略，但他们的工具不适合轻量级的容器化应用程序。由于安全性不足，Kubernetes 团队的配置错误会导致数据泄露。当 SecOps 通过延迟或停止生产中的容器化应用程序部署来保护组织免受风险时，他们就成了罪魁祸首。开发人员认为这是他们快速交付应用能力的主要限制，影子 IT 成为常态，安全性经常以速度的名义被牺牲。

## 原生云迫使整合成为问题

随着各种规模的组织纷纷转向云原生和采用微服务，截然不同的世界观发生了碰撞。结果并不理想:要么 DevOps 在 NetOps 两周的变更周期中陷入不耐烦的等待，要么 NetOps 紧张地试图以 DevOps 的疯狂速度工作，并不断担心一个团队请求的防火墙或负载平衡规则变更会导致整个应用程序基础架构崩溃，使数百个应用程序一下子离线。对于 SecOps 来说，他们经常陷入两个世界之间:试图弄清楚一个全球 WAF 如何在外围环境下处理 Kubernetes 集群的规则，同时还实施微服务级别的安全性。

整合的级联效应也迫使 DevOps、SecOps 和 NetOps 在不同的观察和管理工具集、不同的安全原则以及对应用程序行为的不同期望之间做出选择。例如，对于 NetOps 来说，平均数据包丢弃率是一个关键的 KPI，而对于 DevOps 来说，它与理解用户体验几乎无关。

## 解决方案:复制，而不是整合

解决方案既违反直觉，又显而易见。停止争斗，让整合发挥作用。相反，接受基础设施和工具的复制。允许网络运营通过基本的安全徽章和相当静态的规则和管理来控制前门。允许每个开发运维团队平衡负载，并将自己的应用配置为高容量设备或虚拟机后面的一组辅助网络活动，这些设备或虚拟机位于前端，由 NetOps 管理。

需要说明的是，我们并不提倡所有开发人员都可以选择自己的负载平衡器和工具，而让网络运营部门来收拾残局。相反，我们谈论的是基于维护重复功能的用户组的受控整合——如双轨——以便每一方都有一些可行的东西。这是生产力和幸福的金凤花配方。

我们一次又一次地看到，一旦公司接受了这个新的现实，他们实际上能够在不降低安全性或稳定性的情况下加快代码速度和应用程序迭代。每个团队都可以愉快地关注自己的 KPI。同样重要的是，双基础设施使 NetOps、SecOps 和 DevOps 能够协同工作，而不是纠结于选择和控制一个解决方案。举两个例子，您的开发人员不需要一直学习 Nagios，这是他们真正不关心的事情，您的 NetOps 团队不需要学习如何配置和调优 Prometheus。

下面是我们看到的聪明的组织如何处理这种重复的趋势，如何使它更容易，以及他们在哪里获得最大的杠杆作用，细分为特定的领域。

## 交通管理:大处着眼，小处着眼

前门的哨兵还在那里，而且可能会呆上一段时间。还有，坦白说，这是必要的。对于既想要性能又想要控制并保护自己免受 DDoS 和其他威胁的公司来说，由 NetOps 团队控制的经过测试的、稳定的、企业范围的负载平衡器是非常有意义的。网络操作可以像前门安全一样工作，确保每个人都有一个进入大门的通行证。借助精心制定的策略，NetOps 可以给予开发运维团队所需的回旋余地，使他们能够在外围负载平衡器后部署自己的轻量级网络基础设施，如 Kubernetes。

DevOps 使用一个专门的负载平衡器，一个[入口控制器，](https://github.com/nginxinc/kubernetes-ingress)然后在他们自己的沙箱中运行，而不会用一连串的请求来打扰 NetOps。DevOps 可以迭代。网络运营可以稳定下来。SecOps 可以维护防火墙的全局安全基础设施，同时与 DevOps(更有可能是 DevSecOps)合作，创建一个零信任框架，在服务级别跨应用程序分配安全性，并使 DevOps 团队能够满足其特定应用程序或服务需求的安全性。

## 监测和绩效:两套优先事项和衡量标准

因为对于这两个团队来说，重要的指标是如此不同，所以 NetOps 和 DevOps 需要各自挑选自己的分析堆栈。当每个团队决定使用工具时，这样做效果最好，但是通过在没有替代方案的情况下在双栈上标准化来限制蔓延。然后，NetOps 可以使用 Nagios、Zabbix、ThousandEyes 或任何其他常用于网络分析的工具来监控数据包丢失、一般吞吐量和流量。DevOps 可以选择像 [Prometheus](https://youtu.be/hJoH7J0un5U) 这样的工具进行服务监控，也可以选择 NewRelic 或 AppDynamics 这样的工具以足够的粒度进行特定应用程序的性能监控。

近年来，运行并行分析堆栈实际上变得更加容易，因为 Grafana 和 Kibana 等集成仪表板可以接受来自 NetOps 和 DevOps 监控堆栈的分析，同时为不同的团队维护不同的角色。

SecOps 主要监视异常行为，这与 NetOps 或 DevOps 并不完全不兼容。这两种类型的监控都显示在一个统一的控制面板上，该控制面板提供警报并与 SIEM 等安全平台集成，因此安全部门实际上可以更好地了解现场情况。对于首席技术官、首席信息官和 CISO 来说，有一个单一的地方看到发生了什么是一个重大的奖励。

## 安全基础设施:保持围栏并向左转

双层安全结构对成功的流量管理同样重要。当 NetOps 和 SecOps 能够继续依靠稳定的外围安全时，他们可以高枕无忧，例如他们的 web 级应用程序防火墙、数字丢失防护以及全球政策级别强制要求的所有终端保护要求。

使用 Kubernetes 和 ingress 控制器、 [Kubernetes-native WAF](https://youtu.be/BwOUpmv3HgQ) 和 [service mesh](https://www.nginx.com/resources/webinars/are-you-service-mesh-ready-moving-from-consideration-to-implementation/) 的 DevOps 团队可以管理应用和服务特定的安全规则，这些规则考虑了快速应用迭代过程中产生的独特风险，这些风险只有开发人员才能很好地理解。更快的安全规则版本使 DevOps 能够保持代码速度和快速的特性引入，而不会给企业带来风险。划分风险还意味着企业皇冠上的明珠— ERP、财务—可以享受更严格的安全标准，而不会中断快速开发周期。

## 部署工具:整合不同的管道设置

虽然“基础设施即代码”听起来很棒，但实际上，基础设施的运行速度取决于您所关注的内容。这就是为什么一些云原生应用程序公司可以一天发布几次新版本，而拥有广泛应用程序组合的大型企业在进行新部署时要慢得多的原因之一。与监控和负载平衡一样，如果需要，成熟的部署工具可以轻松支持重复的 CI/CD 平台。在这种情况下，您可能希望建立两个管道:一个管道用于配置更改、全局网络系统和防火墙上的补丁和规则更改，另一个管道用于单独的代码团队。您可以对两者应用相同的 CI/CD 原则和检查点或过程，或者根据需要进行定制。例如，您可以向 [DevOps 管道](https://www.nginx.com/resources/library/build-test-deploy-docker/)添加静态代码分析或单元测试，同时跳过 NetOps 管道中的这些步骤。SecOps 团队可以在 CI/CD 环境中建立他们自己的要求，包括代码审查、测试和试运行或沙箱化新应用程序，以便在实际部署之前测试运行时的行为。

## 结论:必要的妥协

这两个世界说不同的语言，工作速度不同，喜欢不同类型的工具。你不能命令一个世界的居民突然改变他们所知道和喜欢的一切，而不会大规模破坏组织的生产力，或者在网络运营的情况下，会危及你的整个应用程序组合的全球稳定性。对于 SecOps，您希望保持前门安全坚如磐石，同时允许 DevOps 团队在不牺牲敏捷性的情况下适当地保护自己的应用程序。开发运维团队只需加快速度，他们使用的许多平台并不完全符合网络运维模式。

从这个角度来看，复制是不可避免的，也是可取的，这是工具和整合战争的积极结果，这些战争耗费了无数的时间和大量的精力来追求并不存在的中庸之道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>