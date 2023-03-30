# 将 Kubernetes 安全最佳实践应用于舵图

> 原文：<https://thenewstack.io/applying-kubernetes-security-best-practices-to-helm-charts/>

[](https://www.linkedin.com/in/taylorbsmith/)

 [泰勒史密斯

泰勒是 Prisma Cloud bridge crew 的高级产品营销经理，负责从构建时到运行时的全生命周期云原生基础设施和应用安全。此前，他曾在 Gremlin、Cisco 和 NetApp 担任产品营销和战略职位。](https://www.linkedin.com/in/taylorbsmith/) [](https://www.linkedin.com/in/taylorbsmith/)

Helm charts 是一种在 Kubernetes 上打包、版本化和部署应用程序的简单方法。它们可以用来部署应用服务，甚至是 Kubernetes 组件和工具。

它们使得内部和外部的扩展部署更加容易，因为 Kubernetes 清单和命令与预先审核的默认值捆绑在一起。作为一个 Helm 的用户，开源包，也就是所谓的图表，在诸如 [Artifact Hub](https://artifacthub.io) 这样的存储库中随时可供您使用。Artifact Hub 于 2019 年推出，拥有数千张图表，可快速将数据库等预配置服务部署到您的集群中。

然而，我们最近的研究发现，Artifact Hub 中超过 [70%的掌舵图包含错误配置，例如没有设置资源限制和运行根容器，这违反了](https://bridgecrew.io/blog/open-source-helm-security-research/) [CIS Kubernetes 基准](https://www.cisecurity.org/benchmark/kubernetes/)。即使是最流行的依赖关系图 PostgreSQL，[也包含了多个错误的配置](https://bridgecrew.io/blog/open-source-helm-security-research-part-3/)，比如忘记添加`allowPrivilegeEscalation = false`，如果忽略，默认为`true`。

部分问题是，保护舵图不像保护 Kubernetes 货单那样简单。

## 什么是舵图？

我们应该从探索舵图的工作原理开始。如果没有 Helm charts，您将编写多个 Kubernetes 清单(YAML 文件)来获取一个应用程序(如容器映像)，将其部署到您的集群，并管理该映像的附加设置以及 Kubernetes 如何管理容器。

例如:如果您想要一个入口网关，您可能需要部署具有一定数量副本的 NGINX 代理，将它设置为入口网关，并配置应用程序与之接口。仅这一项就可能是三个不同的清单，它们都有默认值。

相反，Helm 将这些清单捆绑在一起，[包括监控工具之类的依赖项，](https://bridgecrew.io/blog/open-source-helm-security-research-part-2/)并包括一个用于默认但可配置的值的中央位置(`values.yaml`)。如果你来自 Terraform 世界，就把这个当做你的`vars.tf`文件。

在部署之前，`helm install`将构建 Kubernetes 清单并为您部署它们，就像`kubectl apply`一样。

## Kubernetes 安全性如何应用？

你可能已经注意到了，但是当 Kubernetes 看到舵图的时候，它看起来就像是另一份清单。这就是为什么 Kubernetes 清单的大多数错误配置(我们将在后面讨论例外)仍然与舵图相关。Helm 仍然可以设置为以 root 或 PID 1 的身份部署容器。

然而，这并不像扫描 Kubernetes 清单那样简单。例如，CIS Kubernetes Benchmarks 5.2.6 要求“尽可能减少具有附加功能的容器的准入”就算有`allowedCapabilities`的 YAML 线，看起来也可能是:

```
allowedCapabilities:  {{-  toYaml  .Values.speaker.securityContext.capabilities.add  |  nindent  2  }}.

```

我们必须深入研究 values.yaml 以找到正确的行:

```
speaker:
  securityContext:
  capabilities:
  add:
                -  NET_ADMIN
                -  NET_RAW

```

然后，我们会发现舵轮图授予额外的能力来执行网络任务，这可能是不应该的。

开源工具 [Checkov](http://checkov.io) 通过识别舵图并首先使用`helm template`命令将它们转换成 Kubernetes 清单来解决这个问题。像任何其他 Kubernetes YAML 文件一样，可以检查生成的清单中的错误配置。

也有例外。例如，Helm 将 pod 部署到名称空间的方式使得检查部署到默认名称空间变得无关紧要，这违反了 CIS Kubernetes Benchmark 5.7.4。此外，在 Helm v3 之后，Kubernetes 的政策是不在任何 Kubernetes 清单中包含 Tiller，因为它的特权过高。然而，舵柄不太可能出现在舵轮图中，所以它不是舵轮图的必要检查。

## 如何以自动化的方式加强头盔的安全性

Helm 简化了我们在 Kubernetes 中部署和管理服务的方式。它提供了一种通过打包依赖项和基于最佳实践的默认设置来扩展部署的方法。这还可以通过确保默认设置不包含错误配置来扩展这些服务的安全性。

然而，今天大多数图表在默认情况下都是不安全的。这使得开发人员在将舵图部署到他们的生产环境之前承担起保护舵图的责任变得非常重要。

最好的解决方案是尽早并经常检查图表中的错误配置。首先检查你下载的舵图是否有错误配置。修复不符合您要求的问题，并随着时间的推移解决剩余的错误配置。如果安全补丁破坏了部署，Helm 可以通过版本控制和回滚来简化这一过程。

在 Helm charts 中保留所有的错误配置修复增强了它们的可伸缩性，因此下一个为他们的用例部署服务的团队将拥有安全的默认值。结果是 Kubernetes 应用程序的受攻击面更低。

为了使我们的研究具有动态性和可重复性，我们构建并开源了一个轻量级的[头盔扫描仪](https://github.com/bridgecrewio/helm-scanner)，你可以利用它来扫描你自己的头盔图表。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>