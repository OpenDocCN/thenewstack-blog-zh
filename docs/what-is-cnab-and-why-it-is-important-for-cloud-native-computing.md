# 什么是 CNAB，为什么它对云本地计算很重要

> 原文：<https://thenewstack.io/what-is-cnab-and-why-it-is-important-for-cloud-native-computing/>

[云本地应用捆绑包](https://cnab.io/) (CNAB)是一个开源规范，旨在促进打包、安装和管理容器化的应用。通过这个包，用户可以定义资源，然后将这些资源部署到许多运行时环境，如 Docker、Azure、Kubernetes、Helm、automation services(如 GitOps 使用的服务)等。

CNAB 规范由多家公司制定，包括微软、哈希公司、Bitnami、英特尔、Pivotal 和 DataDog。尽管许多相关公司都提供自己的云服务，但 CNAB 是作为一个与云无关的规范而创建的，这意味着它不关心你使用什么基础设施或软件来部署。因此，不存在供应商锁定。

最近，CNAB 规范达到了 1.0 版本，这意味着它已经为生产部署做好了准备。任何 IT 专业人士，只要他们的手指深入到云/容器领域，就应该了解 CNAB。

## 多一点理解

[Docker](https://www.docker.com/) 联盟营销总监[罗伯特·杜夫纳](https://www.linkedin.com/in/robertduffner/)表示:“随着现代应用程序的复杂性不断增长，简化这些多服务、分布式应用程序的构建、共享和运行方式的需求迫在眉睫。对于任何与 Kubernetes 合作过的人来说，这是一个保守的说法，因为 Kubernetes 可以很快变得非常复杂。杜夫纳继续说，“现代应用程序由广泛的组件和服务组成——它们可以由多种云资源、托管服务、SaaS 产品、容器、配置格式(掌舵图、Kubernetes YAML 和 Docker 合成文件)、功能等组成。”

但是 CNAB 是如何发挥作用的呢？“CNAB 将这些不同的组件组合在一起，为多服务应用程序提供了一种通用的打包格式。杜夫纳说:“这些捆绑包可以作为一个不可变的组合单元来开发、管理和共享(跨 Docker Hub 这样的注册中心)，而无需强制任何特定的环境/云。

为了澄清这一点，我将话题集中在 Kubernetes 和 Docker 上(因为这是容器部署的两项前沿技术)。至于 CNAB 为 Kubernetes 和 Docker 所做的事情，杜夫纳说，“CNAB 正在帮助推进我们如何看待构建、共享和运行容器，因为它将对话提升到了应用层面。”除此之外，杜夫纳谈到 Docker App 时说:“Docker App 就是这种情况，它是我们对 CNAB 规范的实现，旨在将 Docker 映像的简单性用于构建、共享和运行跨多种配置格式的多服务应用。”

最终，CNAB 将容器和服务结合成一个无缝的整体，这非常强调标准化。CNAB 规范分为以下几章:

*   [CNAB](https://github.com/deislabs/cnab-spec/blob/master/100-CNAB.md) —解释 CNAB 核心 1.0 的基本原理。
*   [CNAB 注册管理机构](https://github.com/deislabs/cnab-spec/blob/master/200-CNAB-registries.md) —将描述如何将 CNAB 捆绑包存储在 OCI 注册管理机构内(此部分尚未完成)。
*   [CNAB 安全](https://github.com/deislabs/cnab-spec/blob/master/300-CNAB-security.md) —解释签署、验证和证明 CNAB 包的机制。
*   [CNAB 索赔](https://github.com/deislabs/cnab-spec/blob/master/400-claims.md) —描述了 CNAB 索赔系统，该系统描述了如何格式化 CNAB 装置的记录以便存储。
*   [CNAB 依赖关系](https://github.com/deislabs/cnab-spec/blob/master/500-CNAB-dependencies.md) —描述捆绑包如何定义对其他捆绑包的依赖关系。

## 什么是捆绑？

目前，有许多方法可以部署容器化的应用程序。您可以使用 Docker、Docker Compose、Kubernetes 和其他工具，每种工具都有自己的配置文件布局规范。CNAB 所做的是在一个 **bundle.json** 文件中创建一个单一的捆绑元数据。这个。json 文件被分解成:

*   架构版本。
*   顶层包信息。
*   关于调用图像的信息。
*   图像地图。
*   参数覆盖规范(引用验证模式)。
*   凭据列表。
*   自定义操作的可选描述。
*   应用程序产生的输出列表。
*   用于验证输入的一组模式定义。

捆绑包有两种格式:

*   瘦包只包含一个对象，即包描述符，并且是一个 JSON 文件(必须表示为规范的 JSON)。
*   厚包包含多个对象:包描述符、一个或多个调用映像以及零个或多个映像。厚包将包含 bundle.json 文件，该文件必须位于压缩归档文件的根目录下。

一个 **bundle.json** 类似于一个 **docker-compose.yml** 文件，因为它描述了一个复杂的映像部署配置。不同之处在于，CNAB 包非常明确地定义了它应该如何布局、编码，以及所有相关文件必须驻留在哪里。

在捆绑包的问题上，杜夫纳说，“构建、共享和运行由各种部分组成的现代分布式应用程序——从 web 组件到机器学习、功能、API 等等——是一个非常复杂的过程。”任何试图部署复杂容器的人都知道这一点。CNAB 是如何应对这种复杂性的？对此，杜夫纳补充道，“Docker 应用(CNAB 的实现)的一个好处是使用 Docker Compose 简化应用，然后部署到云上。所以，没错，一种独立不变的方法和一种部署云原生应用的标准方式非常重要。”

## 谁受益最大

毫不奇怪，CNAB 主要关注企业级部署。毕竟，一个简单的容器部署不需要像财富 500 强公司使用的服务那样复杂。关于这一点，杜夫纳说，“我们已经看到企业成为 CNAB 的大力支持者，因为许多企业拥有数百或数千个分布式应用程序，并且正在寻找更轻松地构建、管理和保护软件供应链中这些应用程序的方法。”但是 CNAB 不仅仅让企业级的企业受益。事实上，杜夫纳补充道，正在与现代应用程序部署的复杂性作斗争的开发人员和 DeOps 团队将从 CNAB 规范中受益匪浅。在 CNAB 规范的帮助下，团队将享受“更好的协作和更快的上市时间”

请务必阅读整个 CNAB 1.0 规格[在这里](https://github.com/deislabs/cnab-spec)。

哈希公司是新堆栈的赞助商。

特写图片由来自 Pixabay 的 Franck THERIAUX 提供

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>