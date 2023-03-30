# Twistlock 增强了对 Multicloud、Istio、Kubernetes 的可见性

> 原文：<https://thenewstack.io/twistlock-enhances-visibility-into-multicloud-istio-kubernetes/>

云发现(Cloud Discovery)是云原生安全厂商 [Twistlock](https://www.twistlock.com/) 几周前发布的开源工具，这只是其最新安全平台版本 18.11 的新功能之一。

“随着人们开始采用所有这些云原生服务(容器、无服务器),并且我们接触的大多数组织都有意采用多云，他们的物品所在位置的潜在变化可能是巨大的。这些平台中的每一个都有几十个区域，每个区域都有几个或更多不同的服务，不同的团队可能有不同的帐户。所以很难(真正知道)那里有什么，”Twistlock 首席技术官[约翰·莫雷罗](https://www.linkedin.com/in/john-morello/)说。

它被称为云平台合规性，允许客户在雷达仪表板上以可视化方式集中发现 AWS、微软 Azure 和谷歌云平台(GCP)上使用的所有云原生服务。

它将该工具集成到其企业产品中，具有持续监控功能，并增加了警报集成，因此您可以向 JIRA、Slack 和 PagerDuty 等网站发送警报。

它还增强了 Istio 服务网格中服务间互连性的可见性。Morello 将于周四在 kube con+CloudNativeCon North America 上发表关于 Istio 作为防火墙的演讲。

“在 18.11 中，与 Istio 的集成主要集中在两个方面:您可以自动发现 Istio 网状拓扑。我们在所谓的雷达图中展示了这一点。这有点像你的环境的谷歌地图…他说:“你可以看到你用 Istio 管理的所有 pod，你可以看到它们之间的所有互联性、服务角色、允许的 HTTP 方法，并可视化和了解你的 Istio 拓扑结构实际上是什么样子，以及组件如何相互交互。

第二部分与合规有关。其研究团队研究了 Istio 的所有可能风险，该公司为 Istio 建立了十几项具体的合规检查。它为 Twistlock 库添加了 300 多项针对 Kubernetes、Docker 和 Linux 的合规性检查，使用户能够查找和执行安全策略。

“它本身并不是在寻找漏洞，”他说，“但对于任何技术，你可以配置得很好，也可以配置得很差。对于一项新技术，很多时候人们不知道什么是好的，什么是坏的。我们努力确保他们知道什么是最佳实践，并能够自动监控。”

它还增加了 Kubernetes 服务帐户监控和可视化功能，并与其雷达仪表板相集成。 **"** 我们将这一点与服务客户认知相结合。您可以在您的群集中看到哪些帐户、…哪些 pod 拥有哪些服务令牌、授予他们哪些权限、如果他们被过度授权，他们的权限提升了多少。就像 Istio 一样，这是一种想象和理解你的环境的能力，这是你以前无法做到的。在你看几十份 YAML 档案之前。对于不关注 DevOps 工件的安全人员来说，这样做真的很难知道环境是什么，”Morello 说。

与 Prometheus、AWS 安全中心、IBM 安全顾问的集成。与 AWS Fargate 配合使用的云原生应用防火墙。对 Lambda 层的支持，这是一种在运行时将可重用组件动态组合到函数中的方式。

它还增加了对 Pivotal Cloud Foundry PAS (Pivotal 应用服务)的支持，以及与 [Prometheus](https://prometheus.io/) monitoring、 [AWS Security Hub](https://aws.amazon.com/security-hub/) 和 [IBM Cloud Security Advisor](https://console.bluemix.net/docs/services/security-advisor/about.html#about) 的集成。

451 Research security 分析师 Fernando Montenegro 指出，容器安全市场[正变得越来越拥挤，但他也提到了 Twistlock 对新技术的支持，如无服务器和受管理的无服务器环境。](http://go.451research.com/Twistlock-looks-beyond-basics-container-security.html)

“虽然 Kubernetes 和云原生技术在生产工作负载中的采用呈指数级增长，但安全性和合规性仍然是大规模生产部署的主要障碍，”Montenegro 说。“Twistlock 已经显示出云提供商、ISV 和开源工具推动云原生运动的势头。我们相信，在未来的一年里，我们将看到对容器和云原生应用安全性的重视程度超过以往任何时候。”

作为一家相对较小的公司，它在大型类别中与 Aqua Security、Google 和 Red Hat 等竞争，这些大型类别是每年类别收入超过 1000 万美元的云安全供应商，Forrester 的第四季度容器安全报告显示了这一点。

早在 8 月份，Twistlock 宣布了一个云原生应用防火墙，它可以与 [Fargate](https://thenewstack.io/aws-fargate-the-beginning-of-the-end-for-infrastructure-management/) 、AWS 容器即服务产品和 AWS [Lambda Layers](https://www.twistlock.com/2018/11/29/introducing-lambda-layers/) 一起工作，这提供了一种在运行时将可重用组件动态组合到您的功能中的方法。它的防御者保护就是其中的一层。

俄勒冈州波特兰市。这家总部位于美国的公司在 8 月份的 C 轮融资中又融资 3300 万美元，使其融资总额达到 6300 万美元。

Twistlock 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>