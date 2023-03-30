# 容器编制器 SDK 的兴起

> 原文：<https://thenewstack.io/the-rise-of-the-container-orchestrator-sdks/>

[](https://www.appdynamics.com/)

 [拉维·拉赫曼

拉维是 AppDynamics 的一名布道者，专注于云计算和 DevOps 领域。在加入 AppDynamics 之前，Ravi 曾在 Mesosphere、Red Hat 和 IBM 工作，帮助企业和联邦部门设计下一代分布式平台。当不帮助推进技术社区时，Ravi 喜欢周游世界，尤其是带着他的胃。](https://www.appdynamics.com/) [](https://www.appdynamics.com/)

AppDynamics 赞助了这篇文章。

让我们回到 10 到 15 年前软件发行的镀金时代。如果你正在构建一个分布式平台，比如门户网站或电子商务网站，它很可能是用 Java 编写的——谢谢，“一次编写，随处运行”(WORA)。二进制发行版的打包将由一个或几个 ear(企业归档)、WARs (web 归档)和/或 JARs (Java 归档)组成。对于不同的应用服务器会有特定的说明。从产品管理的角度来看，考虑到应用服务器之间的差异，您应该发布不同的 web.xml 文件。

多么美好的时光。

快进到今天。有一系列的包装和分销机制来使你的产品被采用。客户和最终用户希望选择在哪里以及如何安装您的产品。这要求产品经理不仅要做出创建原始二进制文件的决策，还要做出包含基础设施即代码、特定于云提供商的自动化和容器编排格式的决策。对于日益复杂的分布式平台，诸如仲裁或会话集群等应用程序基础设施需求很难简单地用这些新的分布格式来描述。

## 你有码头工人吗？

当我在容器繁荣时期为几家公司担任解决方案架构师时，客户经常会问我，我们是否有产品/平台的 Dockerized 版本。每当我问为什么时，他们都会说他们遵循公司的指令，要求他们的工作负载转向容器格式，因为企业正在采用容器编排策略。他们的最终目标是什么？容器天堂，中间件(或系统)工程团队将只管理容器编排。

## 没那么快

平台本身很少是完全无状态的。一个典型的平台可能有几十个需要编排的无状态和有状态服务。某些零件或应用程序无法装箱。随着系统以不同的速度发展，马丁·福勒的扼杀者模式开始变得非常真实。对于复杂的分布式基础架构(如消息传递),需要管理特定的容差和基础架构要求。

假设您正在处理一个故障或就地升级。例如，一个健壮的安装可能不容易用容器编排器来配置，因为集群机制需要特定的指标来做出反应。阻力最小的方法是把平台硬塞进管弦乐队。你能装箱吗？是的。您能从有状态工作负载的故障中恢复吗？不需要，因为这些步骤可能涉及工作流，如 orchestrator 本身无法执行的重放或重试。

## 马拉松 vs. Kubernetes:这还在继续吗？

纵观 container orchestrator 领域，两个占主导地位的平台是 Marathon 和 Kubernetes，后者已经成为 800 磅的大猩猩。对于大多数正在经历容器化之旅的组织来说，最初的障碍是以两种格式之一描述他们的应用程序:marathon.json 或 kubernetes.yaml。

当然，每个管弦乐队都有其优点和缺点。马拉松和 Kubernetes 之间的特征差距似乎总是会给两个社区带来快速的变化。对于更复杂的分布式平台，一般的 Kubernetes YAML 可能没有足够的粒度来描述操作步骤，例如，围绕初始化的 orchestrator 的普通安装/实现。

## 为什么你好，SDK

之前潜伏在指挥者阴影下的是软件开发包(SDK)，比如中间层 [DC/OS SDK](https://github.com/mesosphere/dcos-commons) 。在 CoreOS 与 Kubernetes 的[运营商的合作下，RedHat/CoreOS 最近推出了](https://coreos.com/blog/introducing-operators.html)[运营商框架](https://github.com/operator-framework)。

现在，不是用部署描述符来描述您的应用程序或平台，而是将您的应用程序或平台构建到 SDK 中。想象一下，在 Kubernetes 中扩展[自定义资源定义](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRD)和控制器，将伴随 CRD——基本上，在 go 中编写一个控制器来定义什么需要被监视以及如何对状态变化做出反应。

我们无畏的产品经理要考虑的另一个决定是:从重新描述原始包装(例如，包括一个[木偶](https://www.digitalocean.com/community/tutorials/getting-started-with-puppet-code-manifests-and-modules)或厨师脚本)转变为创建一个新的 orchestrator SDKs 版本/可部署版本。

通过构建 orchestrator SDKs 之一，产品的最终消费者可以管理和扩展 orchestrator 接口之一的实现；中间层 CLI / [KubeCTL](https://kubernetes.io/docs/tasks/tools/install-kubectl/) 。一个 orchestrator 接口混淆了集群产品或重放/重试工作流的复杂连线。

## 牵引力有多大？

GitHub 提供了一个建立在 Kubernetes 运营商基础上的[良好平台列表](https://github.com/operator-framework/awesome-operators)。这份名单会定期更新。对于 DC/OS SDK 来说，要判断 SDK 实际包含了什么有点困难，因为 SDK 的使用在 [DC/OS 宇宙](https://universe.dcos.io/#/)中没有被调用。项目[有这个结构](https://github.com/mesosphere/dcos-commons/tree/master/frameworks)。

## 最后的想法

在混合云与 Mesosphere 的[DC/操作系统](https://mesosphere.com/blog/dcos-1_11-hybrid/)和 Kubernetes 的联邦之后，我相信 SDK 的重要性排在第二位，并将带来更复杂的工作负载，这些工作负载已经不容易用 orchestrator/资源管理器来描述。部署 SDK 可能会改变编排框架的常规安装，因为需要将定制/内部内容写入编排器以支持附加功能。截至 2018 年 6 月下旬，DCOS SDK 处于 alpha 版本，运营商框架 SDK 处于 pre-alpha 版本。当然，在快速发展的空间里，这些快速发展的项目会带来很多变化。

AppDynamics 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>