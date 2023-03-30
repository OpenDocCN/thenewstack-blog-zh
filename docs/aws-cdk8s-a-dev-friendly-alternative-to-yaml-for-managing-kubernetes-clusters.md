# AWS 的 cdk8s，一个对开发人员友好的管理 Kubernetes 集群的 YAML 替代方案

> 原文：<https://thenewstack.io/aws-cdk8s-a-dev-friendly-alternative-to-yaml-for-managing-kubernetes-clusters/>

云巨头[亚马逊网络服务](https://aws.amazon.com/)已经推出了一个开源框架， [cdk8s](https://cdk8s.io/) ，它为开发者提供了一种定义和管理 Kubernetes 控制的应用和资源的方法，使用熟悉的编程语言，而不是当前默认的 YAML。

类型脚本、JavaScript、Python、Java 和。NET 的支持，将来会有更多的支持。它可以与 Kubernetes 的任何上游版本一起工作。

AWS 上周在 [AWS 峰会](https://aws.amazon.com/events/summits/online/)技术会议上展示了这项技术，会议由项目首席工程师 [Elad Ben-Israel](https://hackingonstuff.net/) 和 AWS 高级产品经理 [Nathan Taber](https://www.linkedin.com/in/natetaber/) 主持。

Kubernetes 开源容器编排器依靠 YAML 配置文件来维护应用程序状态。Kubernetes 的运行副本不断地将当前运行的部署与 YAML 文件中的内容进行比较，如果两者不同步，就将应用程序返回到其 YAML 文件中指定的状态。

“我们认为 YAML 很棒。我们在任何地方都使用 YAML，”泰伯谈到 AWS 时说。作为一种声明性语言，YAML 易于管理员阅读和使用。

“它确实很好地代表了系统的理想状态，”他说。“我可以表示我的系统的期望状态，然后使用 Kubernetes 中的状态机来帮助系统达到期望状态。”

也就是说，YAML 确实有一些限制，特别是对于那些不熟悉 YAML 或一般声明性语言的开发人员来说。

一个潜在的挑战是它非常静态。这对于基本设置来说是有利的，例如对于简单的 web 应用程序。然而，随着 Kubernetes 应用程序变得越来越健壮，它们相应的 YAML 文件集合也变得越来越难以管理。泰伯说，许多组织已经采取了跨多个部署进行复制和粘贴的方法，这不是一个可扩展的解决方案。

然而，随着 Kubernetes 使用的增长，管理应用和集群的工作从运营团队转移到开发团队，管理蔓延变得不太直观。使用了大量样板文件，当没有完全理解时，这可能会导致问题。“一旦您复制或派生了配置，就没有真正建立的模型来分发源代码所做的更改，以修复错误、进行安全修补或将应用程序迁移到新版本，”

相比之下，cdk8s 允许开发人员在代码库中捕获通常部署的配置设置，可以与他人共享，并为构建最佳实践甚至 GitOps 风格的可编程基础设施操作提供基础。例如，在 GitOps 设置中，应用程序和配置都可以用相同的语言编写，使用相同的工具集和 CI/CD 管道。

Ben-Israel 表示，该项目源于 AWS 在构建内部云资源供应引擎方面的工作。想法是一样的，通过面向对象编程提供一种定义基础设施或系统的方法，这对于系统建模来说是一个非常强大的工具。

cdk8s 可通过最小命令行界面(cli)访问，它提供了所有 Kubernetes 对象作为强类型类。开发人员定义不同的资源，如容器，以及它们的属性，如可访问的端口。还可以导入自定义资源定义(CRD)，例如 Jenkins 或数据库等软件的操作符。

为了进一步简化这个过程，开发人员可以使用自己喜欢的 IDE，它可以提供自动补全和其他有用的帮助。然后，软件根据这些信息生成一个 YAML 文件。这些构造，正如它们被称为的那样，可以作为库在不同的开发人员之间共享。多语言支持来自另一个 AWS 项目，名为 [jsii](https://github.com/aws/jsii) 。

cdk8s 框架也可以在其上构建。例如， [cdk8s-debore](https://github.com/toricls/cdk8s-debore) 是一个 cdk8s 库，它只用几行代码就定义了 Kubernetes 应用程序，涵盖了 Kubernetes 的资源，如部署、服务、HorizontalPodAutoscaler、Ingress 等。

[https://www.youtube.com/embed/QcF_6ZSEd5k?start=1967&feature=oembed](https://www.youtube.com/embed/QcF_6ZSEd5k?start=1967&feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>