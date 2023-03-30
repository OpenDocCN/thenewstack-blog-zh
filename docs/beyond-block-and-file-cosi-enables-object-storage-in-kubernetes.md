# 超越块和文件:COSI 支持 Kubernetes 中的对象存储

> 原文：<https://thenewstack.io/beyond-block-and-file-cosi-enables-object-storage-in-kubernetes/>

Kubernetes 在开发当今的应用程序方面发挥了不可估量的作用。容器编排系统还有其他选择，但是 Kubernetes 被认为是最流行和最成熟的选择之一。现在让我们来看看这个系统的强大之处，它的局限性以及让它变得更加有用和有益的创新。

## **Kubernetes:快速概述**

 [达里娅·古罗娃

Daria 是 Scality 的技术社区经理。她是最终用户和技术团队之间的联络人。](https://www.scality.com/) 

对于那些不熟悉 [Kubernetes](https://www.scality.com/solved/our-experiences-learnings-directions-with-kubernetes/) 的人来说，这是一个用于部署和管理容器化应用的编排系统。在集群中，Kubernetes 确保运行状态始终符合应用程序开发人员提供的规范。

系统使用抽象的“对象”来定义 API。对象是开发人员可以用来运行他们的应用程序的资源(如容器和负载平衡器)，需要多少个实例，以及允许应用程序在集群中的什么位置运行，等等。这些抽象允许开发人员关注他们的应用程序，而不是它将运行的环境。它还鼓励非常便携、可伸缩和有弹性的应用程序架构。

## **库伯内特的局限**

 [尼古拉斯·特兰格斯

Nicolas 是 Scality 的首席架构师，专注于下一代技术。他精通多种编程语言，偶尔会在会议上发言，有开放源代码的思想，还是一名初创企业爱好者。](https://www.linkedin.com/in/nicolastrangez/) 

在这一点上它会变得令人困惑。Kubernetes 的工作负载通常非常动态，尤其是在微服务架构中，应用程序由许多短暂的无状态服务组成。服务容器部署在 pod 中，通常分布在一个机器集群上。豆荚可以被破坏、重新创建和复制——资源可以从系统中任何可用的地方获取。例如，如果服务失败，Kubernetes 将再次启动它，但不一定是在集群中的同一台机器上。

可以轻描淡写地说，对于持久存储来说，这并不理想。然而，几乎每个生产应用都包含有状态服务，即需要保存其状态并在以后访问的工作负载。为了保证数据安全，并确保数据在 Kubernetes 集群中的任何地方都可用，生产应用程序使用远离应用程序运行的 Kubernetes 集群的远程存储。

持久卷(PV)是 Kubernetes 向用户公开永久存储的概念。整个集群都可以使用一个 PV 资源，将它从 pod 的生命周期中分离出来。永久卷通常由附加的外部存储器支持。Kubernetes 使用控制平面接口与外部存储连接，存储供应商必须开发与 Kubernetes 兼容的卷插件。有一段时间，这些卷插件不得不用 Kubernetes 代码库开发和发布。它们通常被称为树内卷插件。

对于存储供应商和 Kubernetes 开发者来说，这些插件带来了问题。如果供应商想要为 Kubernetes 提供他们的解决方案，特定于供应商的代码必须作为 Kubernetes 的一部分进行编译和发布。这将交付更新的集成代码的能力与 Kubernetes 发布周期联系起来；同时，这使得 Kubernetes 社区很难测试他们发布的软件。此外，从 Kubernetes 用户的角度来看，存储供应商和类型的选择仅限于少数在存储库中有插件的供应商。

## **支持数据块和文件存储，那么对象呢？**

Kubernetes 社区在 2017 年引入了容器存储接口(CSI ),以克服树内存储插件带来的限制。CSI 支持在 Kubernetes 1.13 中获得 GA 状态。CSI 是一种标准，用于将任意块和文件存储系统暴露给在 Kubernetes(或任何其他使用 CSI 的容器编制器)上运行的容器化工作负载。它使 Kubernetes 卷层真正可扩展。借助 CSI，第三方存储提供商可以创建和部署卷插件，向 Kubernetes 公开他们的系统，而无需接触 Kubernetes 代码库。

但是还有第三种存储选择:对象。因为今天产生了前所未有的大量非结构化数据，所以对象存储正迅速且理所当然地越来越受欢迎。今天，生产中的应用程序经常选择对象存储来持久化它们的数据。有各种各样的原因，但一些主要的原因是它的成本效益和极大的可扩展性，它支持粒度访问权限，并且可以通过网络 API 轻松访问。

## **COSI 为物品储存搭建舞台**

直到最近，Kubernetes 的持久存储机制只处理块和文件存储。然而，鉴于对象存储的流行，Kubernetes 社区继续定义了一个新标准:[容器对象存储接口](https://github.com/kubernetes/enhancements/tree/master/keps/sig-storage/1979-object-storage-support#provisionergetinfo) (COSI)。这一新标准包含一组对象存储供应和管理的抽象，旨在成为多家供应商的通用层。该设计模仿 CSI，并得到各种[开源和商业存储系统开发者的支持。](https://techfieldday.com/video/scality-kubernetes-experiences-learnings-and-future/)

这是 COSI 定义的两个控制平面 API:

*   供应商用来实现其存储系统插件以充当 COSI 后端的 API。
*   用于存储桶供应和访问的面向用户的 API。

这项技术是厂商中立的，因为 COSI 标准没有实现任何特定的对象存储协议或 API。

## **COSI 的桶 API**

对象存储不能使用 CSI 中使用的块和文件存储原语。对象存储中的资源调配单位是一个存储桶(不是卷),存储桶是不挂载的。相反，它们是通过网络访问的。此外，对象存储允许更细粒度的访问控制。

COSI 引入了一组新的资源来使用存储桶实现对象存储抽象:

*   ***bucket class*****:**群集范围的资源，包含定义置备程序的字段和用于配置新存储桶的参数集。
*   ***bucket request:***一个命名空间资源，表示对一个新的后端存储桶或访问一个现有存储桶的请求。
*   ***Bucket*****:**Bucket request 引用的集群范围的资源，包含后端 Bucket 的连接信息和元数据。
*   ***bucket accessclass:***集群范围的资源，包含指定可用于访问存储桶的策略的字段。
*   ***bucket accessrequest:***一种命名空间资源，表示对现有存储桶的访问请求。
*   ***bucket access:***授予 bucket 访问权限的集群范围的资源。

此外，COSI 定义了一个名为“provisioner”的服务(见图 1)。供应器必须由供应商实施，以便与 COSI 通信并提供与标准兼容的存储解决方案。你可以在 COSI GitHub 库上找到 [gRPC 规范。](https://github.com/kubernetes/enhancements/tree/master/keps/sig-storage/1979-object-storage-support#provisionergetinfo)

## **COSI 力挽狂澜**

CSI 克服了最初的集装箱存储障碍，但这还不够。虽然 CSI 中的现有原语不适用于对象存储，但 COSI 为供应和管理对象存储桶的生命周期提供了一个通用抽象层。通过 COSI，Kubernetes 集群用户能够以一种标准化的本地方式管理对象存储。存储供应商能够通过 COSI 公开他们的对象存储解决方案，而无需接触 Kubernetes 代码。存储能够满足当前需求，这是一个双赢的局面。

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 5 月 4 日至 7 日在[T2 举行的 kube con+CloudNativeCon Europe 2021 虚拟大会。](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>