# 云原生开源有什么新特性？

> 原文：<https://thenewstack.io/whats-new-in-cloud-native-open-source/>

[Cloud Native Computing Foundation](http://cncf.io/)赞助了这篇文章，期待虚拟 [KubeCon + CloudNativeCon 北美 2020–虚拟](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)，11 月 17-20 日。

 [乔纳·科瓦尔

Jonah Kowall 是 Logz.io 的首席技术官。他在安全和运营领域的初创公司和企业中拥有超过 15 年的最终用户经验。2011 年，他加入 Gartner，担任研究副总裁，专注于可观察性研究，并为 IT 领导者和首席信息官提供建议。2015 年加入 AppDynamics 领先产品战略。思科收购 AppDynamics 后，Jonah 加入 Kentik 担任首席技术官，负责制定和执行产品愿景和战略。2020 年，Jonah 加入 Logz.io，担任首席技术官，负责推动其基于开源的 SaaS 平台的战略和生态系统。](https://www.linkedin.com/in/jkowall/) 

作为一个使用、关注和贡献开源生态系统的人，跟踪新兴项目是一个挑战。开源的速度一直在加快。因此，随着新技术或工具变得越来越相关，倾听社区是跟踪对他人有用的内容的重要部分。

云计算原生计算基金会(CNCF)生态系统扩展如此之快，很难跟上最新的发展。有这么多新项目进入社区。在 CNCF，随着项目的成熟和社区的建立，这些项目也有不同的阶段。通过初始需求后，CNCF 接受项目进入沙箱——在那里项目成熟和成长。一旦他们通过了[特定的里程碑](https://github.com/cncf/toc/blob/master/process/project_proposals.adoc)，他们就进入孵化过程。最后，他们继续成长，毕业后成为 CNCF 社区的正式成员。

值得注意的是，基金会最近增加的一些成员在 2020 年 6 月至 2020 年 9 月中旬期间进入了 CNCF 的沙盒状态。虽然有很多，但我还是试着挑选了几个有趣的项目，我们特别期待它们的成长。

## Kubernetes 特定项目

有几个项目在 Kubernetes 的基础上扩展或提供新的发行版。由于 Kubernetes 是 CNCF 的核心项目，这是有意义的。新的孵化项目包括非常流行的 [**K3S**](https://k3s.io/) ，这是一个为 IoT 和 Edge 设计的轻量级 Kubernetes 发行版。它是由牧场主捐赠的。类似地，阿里巴巴贡献的 **OpenYurt** 也是基于 Kubernetes 构建的——但不是发行版，而是通过附加组件实现的，这使得该方法不同于 K3S。

由 Upbound 创建的 [**Crossplane**](https://crossplane.io/) 作为其核心业务的一部分，正在基于开源项目构建一个商业产品。这个项目是对 CNCF 生态系统的有趣补充。Crossplane 就像 Terraform，几乎是管理现代基础设施的事实标准。基本的区别在于 Crossplane 对基础设施和服务(应用程序)都使用 Kubernetes 资源模型，并且它提供了一个使用 Kubernetes 风格的 API 的控制平面。这些 API 在创建 Terraform 时并不存在，这使得 Crossplane 特别适合 Kubernetes 的本地架构。

Kubernetes 部署中最关键的组件之一是服务网格。流行的 [**特使**](https://www.envoyproxy.io/) 代理已经是一个毕业的 CNCF 项目，并且是许多——如果不是大多数——Kubernetes 部署的核心组件。 [**开放服务网格**](https://openservicemesh.io/) 扩展了 Envoy 并实现了服务网格接口 API，使 Kubernetes 管理在服务网格产品的大型生态系统中更加标准化。感谢 Microsoft Azure 团队为此项目做出的贡献。

对于我们这些使用或构建 Kubernetes 的人来说，缺少的一件事是一个简单的软件包管理器来安装组件。正如 Node.js NPM 事件所显示的，运行一个公共存储库并不是一项实质性的业务，但对用户来说却是必不可少的。 [**Artifact Hub**](https://artifacthub.io/) 是 Kubernetes 的公共存储库——类似于 Node.js 的 NPM，或者 Python 的 pip。拥有一个 Kubernetes 包的公共目录是非常有用的，但是很难保持所有的元数据都是最新的。随着它的发展，我们将对此进行监控，因为它是当今生态系统中的一个缺口。

## 其他值得注意的项目

[**后台**](https://backstage.io/) 是 Spotify 之外的一个有趣的开源软件项目；它用于构建服务目录和开发人员门户。该门户有许多插件来集成各种工具和技术，并提供大量有用的功能，如文档、与监控工具集成以提供健康状况、构建和集成状态、发布信息、打开拉取请求等。随着它的成熟，这将对我们的团队非常有用。

CNCF 沙盒的另一个独特参与者是 Dynatrace 创建的 [**Keptn**](https://keptn.sh/) 项目。Dynatrace 将该项目设计为控制平台，以解决运营的持续部署和其他自动化需求。Dynatrace 主要是为了自己的运营需求而构建的，类似于 Logz.io 为什么要构建 [**阿波罗**](https://github.com/logzio/apollo) 开源项目。Keptn 围绕 Kubernetes 构建，并使用 Helm 来定义服务。Keptn 有一个有趣的事件驱动系统，有无数的用例，应该是一个值得监控的有趣项目。还有另外一个 CNCF 项目， [**Argo**](https://argoproj.github.io/) ，有一些相似之处；但是 Argo 的成熟度更高，因为它是一个毕业项目。

最近 CNCF 接受的其他项目还有很多，包括[](https://www.tremor.rs/)**[**metal 3-io**](https://metal3.io/)[**波特**](https://porter.sh/)[**工藤**](https://kudo.dev/)[**CNI-精灵**](https://github.com/cni-genie/CNI-Genie)[**云护法**](https://cloudcustodian.io/)[**Dex**我们将密切关注所有这些项目，因为它们经常解决由其他流行的开源项目解决的问题。在一个繁忙且不断发展的社区中，差异化对这些项目来说将是一个挑战。祝贺这些项目在 CNCF 受到欢迎。](https://github.com/dexidp/dex)**

 ***如有问题或评论，请在 Twitter [@jkowall](https://twitter.com/jkowall?lang=en) 联系我。*

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 11 月 17 日至 20 日举行的 [KubeCon + CloudNativeCon 北美 2020](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 虚拟大会。*

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**