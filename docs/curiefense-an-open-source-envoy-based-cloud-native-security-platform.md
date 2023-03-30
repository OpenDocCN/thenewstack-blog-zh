# Curiefense，一个开源的、基于特使的云本地安全平台

> 原文：<https://thenewstack.io/curiefense-an-open-source-envoy-based-cloud-native-security-platform/>

以色列云原生托管应用安全解决方案提供商 Reblaze 发布了云原生计算基金会(CNCF)沙盒安全项目[Curie fence](https://www.curiefense.io/)的商业版。它的工作是保护云原生应用和 API 免受 SQL 注入、跨站脚本(XSS)、应用层分布式拒绝服务(DDoS)和 API 滥用等威胁。

怎么会？通过建立在 Lyft 的开源[特使](https://www.envoyproxy.io/)高性能 C++分布式代理之上。

Envoy 是一个开源的 edge 代理，旨在与云原生应用一起使用。Envoy 还可以用作大型微服务[服务网状架构](https://thenewstack.io/part-3-the-best-way-to-select-a-proxy-architecture-for-microservices-application-delivery/)的通信总线和通用数据平面。Curiefense 在此基础上作为特使过滤器工作。您可以在任何有 Envoy 运行的地方使用它，无论是作为入口网关、边车或反向代理、负载平衡器还是其他情况。Curiefense 直接连接到 Envoy，可以立即开始保护您的平台。

Curifense 本身是在 Apache 2.0 许可下授权的。但是，虽然它仍然在 CNCF 的沙盒中，Reblaze 感觉它的生产准备就绪。

除了构建在 Envoy 之上，它还使用了 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 和对 [Kubernetes](https://kubernetes.io/) 和 [Istio](https://istio.io/) 等服务网格的本地安全支持。它的程序员声称 Curifense 是一个 API 优先的安全平台，是“开发者的，开发者的”。:Curiefense 完整规格包括:

*   支持开发运维/基础架构代码/gitop
*   可由 UI、cURL 和 Swagger 驱动
*   配置在 JSON/YAML 中导入/导出
*   Git 中的所有数据和配置版本
*   支持分支环境(例如生产/开发运维/质量保证)
*   实时分析/指标，与 Prometheus/Grafana 和 ELK stack 集成
*   内置自动威胁源+自带威胁源
*   高级机器人检测/生物特征人体验证
*   高级服务，包括基于机器学习的自动化安全配置和全天候支持

该程序也是平台不可知的。它可以在云虚拟机上运行，并作为一个特使插件。你的部署选项包括 Docker Compose，Helm chart，Terraform，还有更多方法。

Curifense 收集的所有数据和分析都保存在您的系统中。它不会导出到任何第三方网站或数据库。

Envoy Proxy 的创建者 Matt Klein 在一份声明中说:“现代云原生部署需要复杂的边缘网络安全，而从历史上看，开放解决方案在这一领域一直缺乏。“Curiefense 对一个古老的问题采取了一种新的开放方法，我很高兴看到这种独特的解决方案上市。特使社区期待着与 Curiefense 团队合作，在这一关键举措上进行迭代和协作。”

您当然可以按原样使用 Curiefense。除了开源之外，它还有一个完整的 API。但 Reblaze 将提供自己的商业自动化层，使其易于部署、维护和使用。这个版本的程序也将更频繁地更新。

Reblaze 还将提供完全托管和管理的 SaaS cure fence 产品。该版本将在大多数流行的公共云上提供。这将包括[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)、Azure、数字海洋和谷歌云平台。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>