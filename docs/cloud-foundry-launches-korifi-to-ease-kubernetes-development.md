# Cloud Foundry 推出 Korifi 以简化 Kubernetes 开发

> 原文：<https://thenewstack.io/cloud-foundry-launches-korifi-to-ease-kubernetes-development/>

[Cloud Foundry Foundation](https://www.cloudfoundry.org/foundation/) 已经发布了 [Korifi](https://github.com/cloudfoundry/korifi) 的测试版，这是一个新的平台即服务(PaaS)，旨在简化开发人员和运营商的 Kubernetes 开发和部署体验。

该基金会表示，Korifi 将 [Cloud Foundry](https://www.cloudfoundry.org/) 以开发者为中心的经验用于提供一个在 Kubernetes 上运行的兼容 Cloud Foundry 的应用平台，因为 Kubernetes 的经验对运营商和开发者来说都很复杂。

## 糖果店里的小孩

Enterprise Management Associates 的分析师 Torsten Volk 解释说:“Kubernetes 让开发人员感觉像是‘糖果店里的孩子’，因为该平台提供了一个庞大的产品生态系统，他们可以将这些产品整合到灵活、可扩展的应用程序堆栈中。“另一方面，Cloud Foundry 专注于提供一套预集成和完全企业强化的开发人员和开发运维服务。但这里没有“糖果店”，因此开发者更喜欢库伯内特的本土体验。”

Cloud Foundry 是一项开源技术，由世界上许多最大的技术公司支持，包括 IBM、SAP、VMware、HCL 和华为，正在被制造业、电信和金融服务领域的领导者使用。

## 继续降低复杂性

Cloud Foundry 吸引了企业应用开发者。

“你真的只能在非常大的企业中看到 CF，因为它非常喜欢在专用的服务器基础设施上运行，”这就是为什么它屈服于 Kubernetes，”Volk 告诉 New Stack。

Cloud Foundry Foundation 提供了其他工具来帮助使用 Kubernetes 的企业[提高开发人员的工作效率，例如](https://thenewstack.io/do-i-really-need-kubernetes/) [cf-for-k8s](https://cf-for-k8s.io/) 。Cf-for-k8s 结合了 Cloud Foundry 开发人员 API 和其他流行的开源项目，如 Kubernetes、Istio、Envoy 和 Fluentd。该项目使用定制资源定义和其他 Kubernetes 原语，在新组件上提供熟悉的开发人员体验。

与此同时，另一个努力， [KubeCF](https://kubecf.io/) ，是为 Kubernetes 发布的 Cloud Foundry 应用程序运行时。它为开发人员提供了 Cloud Foundry 的生产力方面，并允许平台运营商使用 Kubernetes 工具和 API 管理基础设施抽象。

“随着 Kubernetes 的成熟，我们的社区已经建立了几个云铸造抽象来降低 Kubernetes 的复杂性，”云铸造基金会的项目经理[克里斯·克拉克](https://www.linkedin.com/in/clarkchris1/)在一份声明中说。“经验证的 Cloud Foundry 开发人员体验通过最大限度地提高开发人员的工作效率，已经为组织节省了数百万美元。对于 Korifi，我们正在构建一个新的架构，这个架构是从以前的迭代中学习来的，比如 cf-for-k8s 和 KubeCF。Korifi 带来了与云原生技术更好的互操作性，为 Kubernetes 带来了 Cloud Foundry 应用程序开发人员体验的轻松和简单。”

## 后续产品

“在某种程度上，Korifi 是 KubeCF 和 cf-for-k8s 的后续产品，”Cloud Foundry 的首席宣传员拉姆·艾扬格(Ram Iyengar)说。

“按时间顺序，先是 KubeCF，接着是 cf-for-k8s，现在是 Korifi。这种(r)进化的每一个阶段都以库贝语惯用成分的增加为标志，”他说。“KubeCF 使用了非常少的来自云原生生态系统的组件。cf-for-k8 多利用了几个。Korifi 已经发展成为一个 API，它完全集成了 Kubernetes RBAC(基于角色的访问控制)、分层名称空间、Envoy/Contour 和其他几个本地 Kubernetes 组件。它们都是不同的、有特色的努力，每个都有不同程度的成功采用。”

KubeCF 允许运营商在 Kubernetes 上部署 Cloud Foundry 或任何其他 BOSH 版本的实例，方法是将 BOSH 清单转换为 Helm 图表。这种方法是在 Kubernetes 上运行完整 CF 环境的快速方法，但即使采取下一步措施直接在 Kubernetes 上运行应用程序容器也是一个挑战，更不用说进一步发展系统了。

Cf-for-k8s 是 Cloud Foundry 社区以 Kubernetes 本地方式提供 Cf 的最初尝试。它将 Kubernetes 和 Istio 与 CF API 和其他 Cloud Foundry 组件结合在一起。虽然这是成功的，但是这种方法的一些架构限制变得很明显。

“你可以说 Korifi 是 cf-for-k8s 的迭代，尽管它是一个完全不同的实现，并且它走得更远，”Clark 说。

Cloud Foundry 基于容器的架构在各种云平台上运行用任何语言编写的应用程序，如亚马逊网络服务(AWS)、谷歌云平台(GCP)、IBM Cloud、微软 Azure 和 OpenStack 等。

“成千上万的开发人员每天都在使用 Cloud Foundry 作为一个简单、可靠的平台来部署和管理他们的任务关键型应用程序，”Cloud Foundry 董事会主席兼 VMware 研发副总裁 [Craig McLuckie](https://www.linkedin.com/in/craigmcluckie/) 在一份声明中说。“他们的团队依靠它的稳定性和自动化来支持这些开发人员和应用程序。我们认为 Korifi 是一个机会，可以确保 Cloud Foundry 与其他云原生技术和部署实践的不断增长的生态系统良好地互操作。”

McLuckie 也是 Kubernetes 的联合创始人，这表明 Cloud Foundry Foundation 更加关注为 Kubernetes 工作的开发人员抽象出复杂性。然而，该基金会表示，Korifi 并不意味着云铸造已经完成。

“传统的基于虚拟机的云铸造架构不会有任何发展，”克拉克告诉新的堆栈。“从现在起，它将继续得到发展和维护；SAP 和 VMware 都对现有 CF 用户群做出了明确承诺。”

有许多大型部署继续使用 Cloud Foundry 来支持虚拟机，例如 [BOSH](https://bosh.io/docs/) 项目。

“我们相信，这两种工具将并存，继续服务于略有不同的需求，”艾扬格说。“他们在开发人员体验方面有着共同的目标，但会针对不同的云基础架构进行专门构建。首先，Korifi 的目标是那些想要迁移到 Kubernetes 的工程团队。没有任何东西阻止人们在绿地项目中采用它，并开始将它用作内部开发平台。”

Volk 说，Korifi 以微服务的形式将最初基于虚拟机的云铸造架构带到了 Kubernetes，这些微服务可以通过标准的 Kubernetes 工具进行管理，并可以通过 kubectl 进行访问。

## 成功的两个因素？

然而，有两个因素是这个项目成功的关键，他指出。一个是能够为用户提供至少一些最受欢迎的云原生产品类别的选择，用于联网、服务网格、安全性、编排、可观察性、管道管理、数据库等。另一个因素是，Cloud Foundry 应用程序和其他 Kubernetes 应用程序必须能够并行运行，而不会对后者产生任何负面影响。

“这两项任务都不简单，我目前在 GitHub 上只看到大约十几个 Korifi 的贡献者，但考虑到项目支持者的 Kubernetes 经验，我认为有成功的机会，”Volk 说无论哪种方式，Korifi 似乎都是 Cloud Foundry 成功的唯一、也可能是最后的机会，而不是逐渐消失。"

同时，对于系统集成商和服务提供商来说，Korifi 是一种为他们的云代工客户实现云原生转型的方式，也是一种引入新的基于云的产品的方式。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>