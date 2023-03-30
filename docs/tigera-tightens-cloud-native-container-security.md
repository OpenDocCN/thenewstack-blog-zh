# Tigera 加强了云原生容器安全性

> 原文：<https://thenewstack.io/tigera-tightens-cloud-native-container-security/>

[Tigera](https://www.tigera.io/) 声称，通过为其 [Calico 云](https://www.tigera.io/tigera-products/calico-cloud/)开发的新云本地应用程序保护平台(CNAPP ),您可以对您的容器安全性小睡片刻。如果这个名字听起来很熟悉，那是有原因的。 [Gartner](https://www.gartner.com/en) 将 [CNAPP 定义为一个新兴的安全程序类别](https://start.paloaltonetworks.com/gartner-report-cloud-native-application-protection.html)。它的目的是从开发到生产保护云原生应用。Tigera 并不是唯一一家采用这种方法的公司。Tigera 带给这群打盹的猫的是[零信任](https://thenewstack.io/zero-trust-security-and-the-software-development-lifecycle/)。

根据 Gartner 的说法，“将[云工作负载保护平台(CWPP)](https://www.gartner.com/reviews/market/cloud-workload-protection-platforms?utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 和[云安全态势管理(CSPM)](https://www.gartner.com/en/documents/3899373/innovation-insight-for-cloud-security-posture-management) 功能结合在一起会产生协同效应，多家供应商正在推行这一战略。这种结合将创造一种新的云本机应用程序保护(CNAPs)类别，它可以扫描开发中的工作负载和配置，并在运行时保护工作负载和配置。”具体来说，CNAPPs 捆绑了集装箱扫描等多个安全功能；基础设施代码(IaC)扫描；和云运行时工作负载保护。

## 什么都不能相信

对此，Tigera 的零信任抛弃了传统的系统有“边界”的安全概念，取而代之的是你不能相信任何人或任何事。因此，身份验证是基于每个请求来处理的。每一个动作要么被授权，要么被限制，默认是一切都被限制。这大大减少了您的云原生程序的攻击面。

除了这个基本概念，Tigera 还增加了机器学习(ML)来应对已知和零日威胁的运行时安全风险。这有助于实现持续的合规性，通过安全策略的改变来确定漏洞和攻击的优先级并降低风险。

这一切都与 Tigera 的印花云(T1)相呼应。除了为 [OpenStack](https://www.openstack.org/) 和 [Kubernetes](https://kubernetes.io/) ， [Calico 已经在软件即服务(SaaS)模式中增加了网络安全保护](https://thenewstack.io/project-calico-kubernetes-security-as-saas/)。

## 祭

这是 Tigera 现在通过其 CNAPP 和 Calico 云的配对提供的内容。

### **具有映像保证的构建时安全性:**

Calico Cloud 引入了一种新的扫描引擎来持续评估图像的漏洞和错误配置。它还提供了 Kubernetes 集群中运行的映像及其潜在风险的实时视图。

利用准入控制器在构建和部署期间提供主动安全性，该控制器可以自动阻止部署包含高严重性漏洞的 pod。

### **改进映像、工作负载和 Kubernetes 的配置管理:**

Calico Cloud 使用 [CIS 基准](https://www.cisecurity.org/cis-benchmarks/)根据通用配置安全标准持续监控映像、工作负载和 Kubernetes 基础设施，并提供详细的评估报告。应用程序和基础架构所有者可以将这些报告集成到他们的 CI/CD 管道或事件响应工作流中，以实现主动缓解。

### **云原生应用的零信任原则:**

Calico Cloud 使用零信任原则，通过实现零信任工作负载访问控制、身份识别微分段以及与防火墙和安全信息和事件管理(SIEM)工具的集成来减少攻击面。

Calico Cloud 增加了已知的零日运行时威胁防御

### **针对容器化工作负载的全面运行时威胁防御:**

Calico Cloud 具有内置的探测器，可以收集网络流量、文件系统、进程、系统调用、二进制文件等方面的工作负载活动数据。威胁防御引擎近乎实时地将来自这些探测器的数据与已知的恶意攻击进行比较。它使用机器学习来创建工作负载的行为基准，以及 Tigera 自己基于历史攻击的策划规则集，来提供针对零日威胁的全面威胁防御解决方案。它还提供工作负载级别的入侵检测和预防、深度数据包检测(DPI)、分布式拒绝服务(DDoS)攻击预防以及带有 web 应用程序防火墙(WAF)的应用程序级保护。

### **通过动态服务和威胁图提高可观察性:**

Calico Cloud 的动态服务和威胁图提供了服务、名称空间和工作负载之间通信的实时可视化，从而实现了更快的故障排除。安全差距和漏洞与微服务之间的性能问题和通信故障一起显示。很容易深入到可视化中执行故障排除，并显著减少查明和排除容器或连接问题所需的时间和步骤。

### **集成安全策略引擎降低暴露风险:**

Calico Cloud 建立在 [Calico 开源](https://www.tigera.io/project-calico/)之上，这是业界应用最广泛的容器网络和安全技术。凭借其集成的策略引擎，Calico 通过将纠正性安全策略部署为可以发出警报、暂停、隔离或终止 pod 的代码来降低暴露风险。

## 措施组合

Tigera 总裁兼首席执行官 [Ratan Tipirneni](https://www.linkedin.com/in/ratantipirneni/) 表示:“在构建、部署和运行云原生应用的整个生命周期中，从未提供过如此高的安全性。“这不仅仅是找到最多的漏洞；它是关于在零信任的情况下减少广泛的攻击面，并通过预防措施的组合主动降低风险，将行为基准和已知威胁知识相结合以检测运行时的异常活动，并能够实时降低风险。”

它是否为您的云原生设置提供了合适的安全性？只有你能决定，但快速一瞥，它肯定看起来值得一试。

[Calico 云和企业版现已上市](https://www.tigera.io/tigera-products/calico-cloud-pricing/)。您还可以报名参加 Calico Cloud[14 天免费试用版的动手测试。](https://www.calicocloud.io/home)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>