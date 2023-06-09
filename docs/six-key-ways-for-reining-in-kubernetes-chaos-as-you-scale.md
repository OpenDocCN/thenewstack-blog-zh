# 控制 Kubernetes 混乱的六个关键方法

> 原文：<https://thenewstack.io/six-key-ways-for-reining-in-kubernetes-chaos-as-you-scale/>

随着 Kubernetes 作为许多组织选择的 IT 战略越来越受欢迎，公司面临着越来越复杂的问题，以满足客户需求、多样化的应用程序和扩展的合规性要求。

 [克里夫·马尔姆堡

Cliff 是 Rafay Systems 的高级产品营销经理，Rafay Systems 是一家拥有超过 15 年经验的充满活力的产品营销领导者。他热衷于讲故事和将复杂的产品带入生活。](https://www.linkedin.com/in/cliffmalmborg/) 

随着这些组织增加其 Kubernetes 机群中的集群数量以保持领先于需求，他们面临着管理这种增长的挑战。

随着集群分布在内部、云和边缘位置，以及不同的配置和工具，您可以看到组织如何在保持对混乱的控制的同时不知道如何扩展。

在本文中，我们将讨论管理日益复杂的 Kubernetes 集群的一些关键方法，充分利用这些集群，并定位其 IT 组织以取得有意义的持续成功。

## **关键 1:拥抱混合和多云**

随着越来越多的公司采用远程工作，混合云和多云的受欢迎程度迅速提高。Kubernetes 本身是一个高度可移植的选项，这意味着您可以使用云进行工作负载部署，同时还可以改善客户和员工的体验。这意味着以更低的延迟和更高的性能交付应用。

也就是说，利用混合或多云可能会为您的 Kubernetes 带来更好的结果，但这也可能意味着增加 K8s 的复杂性。因此，使用正确的工具使您能够跨多个云或数据中心运行，同时保持标准化是非常重要的。

## **关键 2:关注自动化**

许多组织开始了他们的 Kubernetes 之旅，并惊讶于管理和维护几个集群是如此简单。但是随着你的业务增长，它会很快变得更加复杂。因此，尽可能地利用自动化机会是非常重要的。从自动化常见的集群或应用程序操作，到标准化和自动化测试，只要您能够减少手动工作量来扩展 K8s，就越好。

实现这一点最流行的方法之一是通过 GitOps。GitOps 将许多开发人员已经熟悉的 git 工具与基础设施管理和持续部署相结合。事实上，在 [2021 年 AWS 集装箱安全调查](https://aws.amazon.com/blogs/containers/results-of-the-2020-aws-container-security-survey/)中，64.5%的受访者表示他们使用 GitOps——这个数字只会继续增长。

GitOps 的美妙之处在于，当对 Git 存储库进行更改时，代码会被推送到生产环境中，从而使部署更快、更可靠。但是 GitOps 不是唯一的选择。[开放策略代理](https://www.openpolicyagent.org/)——或 OPA——是一个通用策略引擎，帮助在一系列 Kubernetes 相关项目(如微服务、CI/CD 管道、API 等)上实施策略。这是在您的 Kubernetes 中构建基于策略的管理的一个好方法。

## **关键 3:将安全放在首位**

我们都知道，在 2022 年，安全不仅仅是“拥有就好”，而是至关重要的。对于 Kubernetes 来说，重要的是要确保安全是真正的优先事项，并且您最重要的集群和应用程序应该具有顶级的安全性和控制。一个常见的建议是部署零信任原则来保护 Kubernetes——事实上，K8s 是以一种容易支持零信任的方式构建的。

## **关键 4:通过监控保持能见度**

你所不知道的事情会伤害你，尤其是当涉及到 Kubernetes 时。像 K8s 的其他方面一样，随着您的组织的扩展和复杂性的增加，监控变得更加困难，因为监视许多集群、应用程序和配置不一定是一件容易的任务。同时，保持可见性至关重要，那么 IT 组织应该做些什么呢？

一个常见的最佳实践是通过集中日志记录保持基本的监控水平，并为最重要的项目创建警报和可视化。这通常是用普罗米修斯和格拉夫纳来实现的。

对于对使用这些开源工具构建自己的监控平台不太感兴趣的公司，市场上有许多 SaaS 选项可以帮助您完成繁重的工作，并可以集中监控，甚至跨不同的配置和应用。

## **关键 5:利用 SaaS**

[使用 Kubernetes](https://thenewstack.io/do-i-really-need-kubernetes/) 可能意味着管理大量移动部件和复杂性。建立一个能够处理您的 K8s 环境的所有细节的团队可能是一项重要的(也许是不可持续的)投资，无论是在技能还是时间方面。为了帮助减轻这种压力，我们建议尽可能求助于服务。

K8s 服务大放异彩的一个常见领域是托管 Kubernetes。许多公共云提供商，如 AWS、Azure 和 Google Cloud，已经管理了 Kubernetes 产品，可以帮助组织扩展和管理复杂性。也有越来越多的 SaaS 工具可以帮助公司处理 K8s 管理、监控、安全等问题。

## **关键 6:你不需要单干**

许多组织，特别是当他们第一次开始使用 Kubernetes 时，试图用 K8s 引导他们的方式。这意味着建立自己的基础设施，编译上游代码，甚至开发自己的工具。但是过去的 Kubernetes 并不是今天的 Kubernetes，市场上有很多工具和服务可以让 K8s 变得更容易。通过与合适的公司合作，您可以简化运营、提高生产率，并将更多的时间用于创新，而减少管理 K8s 的时间。为什么 Kubernetes 应该比它需要的更难？

## **化繁为简**

像许多事情一样，Kubernetes 随着你的成长变得越来越复杂。但是通过关注上面的关键方法——并在您的 Kubernetes 之旅的早期考虑它们——您可以建立您的组织以取得成功，无论是近期还是长期。凭借远见卓识和与正确的合作伙伴合作，Kubernetes 可以帮助您交付出色的成果，即使您的组织在不断扩展和变化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>