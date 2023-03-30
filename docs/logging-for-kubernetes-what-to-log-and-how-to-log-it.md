# Kubernetes 的日志记录:记录什么以及如何记录

> 原文：<https://thenewstack.io/logging-for-kubernetes-what-to-log-and-how-to-log-it/>

[](https://www.linkedin.com/in/franciss-espenido-1bb84725/)

[Francis Espenido](https://www.linkedin.com/in/franciss-espenido-1bb84725/)

[Francis 是 LogDNA 的一名合作伙伴项目经理，在那里他主要负责 IBM Cloud 上的可观测性产品的技术支持。他曾担任该公司的技术支持工程师，在那里他对现代日志实践和开发人员工作流程中的挑战有了深入的了解。](https://www.linkedin.com/in/franciss-espenido-1bb84725/)

[](https://www.linkedin.com/in/franciss-espenido-1bb84725/)[](https://www.linkedin.com/in/franciss-espenido-1bb84725/)

无论您的 Kubernetes 环境[看起来如何，日志记录和监控都是您开始 Kubernetes 之旅时需要解决的首要挑战。无论您是在 PC 上本地运行单节点集群、托管开发环境的小型节点集合，还是托管生产应用的大规模多主控集群，能够访问监控数据和日志以解决问题和优化性能都至关重要。](https://thenewstack.io/category/kubernetes/)

鉴于 Kubernetes 由如此多的不同部分组成，知道在哪里寻找数据以及如何解释数据可能会很棘手。事实上，Kubernetes 日志记录和监控需要使用多种数据源和多种工具，因为 Kubernetes 以多种方式生成日志。

本文概述了 Kubernetes 的日志记录。它涵盖了 Kubernetes 中可用的日志数据类型以及如何访问这些数据。正如我们将看到的，大多数类型的 Kubernetes 日志数据都有多种访问方法。本文解释了如何评估您的日志记录需求并设计适合它们的日志记录策略。

下面的大部分信息适用于任何类型的 Kubernetes 环境。然而，为了奠定讨论的基础，我们将引用相关的[IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/container-service/)(IKS)来解释我们讨论的工具和实践如何应用于现实世界的生产 Kubernetes 服务。

## **什么是 Kubernetes？**

如果你正在阅读这篇关于 Kubernetes 日志的文章，你可能已经知道 Kubernetes 是什么了。但是，简要说明它的作用是值得的，因为理解 Kubernetes 能做什么和不能做什么是扩展日志策略以支持它的第一步。

Kubernetes 提供了几种关键类型的功能:

*   **应用托管** : Kubernetes 的首要特性是托管应用。通常，这些应用程序托管在容器中，尽管使用 Kubernetes 也可以运行其他类型的工作负载(如虚拟机)。
*   **负载平衡** : Kubernetes 自动在不同的应用程序实例之间分配流量，以优化性能和可用性。
*   **存储管理** : Kubernetes 可以管理对应用程序用来存储有状态数据的存储池的访问。
*   **自我修复**:当出现问题时，比如应用程序失败，Kubernetes 会尝试自动修复。然而，它并不总是成功的，这也是 Kubernetes 日志如此重要的原因之一。

Kubernetes 也做其他事情，但这些是它提供的核心功能领域。

## **Kubernetes 和 Logging:很复杂**

您会注意到日志记录和监控并不在 Kubernetes 的核心特性列表中。这并不是因为 Kubernetes 不提供任何日志和监控功能。是的，但是很复杂。

一方面，Kubernetes 通过 kubectl 提供了一些非常基本的功能，用于检查集群中对象的状态，我们将在下面讨论。它还为某些类型的数据创建日志，并公开其他类型的数据，以便通过第三方日志记录工具进行收集。

另一方面，Kubernetes 没有提供成熟的本地日志解决方案。不像亚马逊网络服务，它有一个内置的 CloudWatch 形式的日志解决方案；或者 OpenStack，有自己全面的日志解决方案；stock Kubernetes 没有完整的原生日志服务，甚至没有首选的第三方日志方法。相反，它希望您使用外部工具来收集和解释日志数据。

也就是说，某些 Kubernetes 发行版确实带有基于第三方工具的内置日志扩展，或者至少是它们支持的首选日志方法。例如，正如我们将在下面看到的，IBM Cloud Kubernetes Service (IKS)集成了 IBM Log Analysis with LogDNA 来收集 Kubernetes 日志数据，并使用 LogDNA 实现实时分析和日志管理。

在大多数情况下，可以使用另一种日志记录方法，即使是在 Kubernetes 发行版上，它也有一个首选的或本地集成的日志记录解决方案。然而，供应商支持的方法通常更容易实现。

## **在 Kubernetes 上登录什么**

无论您选择哪种日志选项，Kubernetes 中都有几种可以收集的日志数据类型。

### **应用日志**

首先也是最重要的是来自 Kubernetes 上运行的应用程序的日志。存储在这些日志中的数据由应用程序运行时输出的信息组成。通常，这些数据被写入运行应用程序的容器中的 stdout。

我们将在下面的“查看应用程序日志”一节中研究如何访问这些数据。

### **Kubernetes 集群日志**

构成 Kubernetes 本身的几个组件会生成自己的日志:

*   Kube-apiserver
*   kube-调度程序
*   Etcd
*   Kube 代理
*   库伯莱

这些日志通常存储在运行服务的服务器的/var/log 目录下的文件中。对于大多数服务，该服务器是 Kubernetes 主节点。然而，Kubelet 运行在 worker 节点上。

如果您遇到了集群级别的问题(与只影响某个容器或 pod 的问题相反)，这些日志是寻找洞察力的好地方。例如，如果您的应用程序在访问配置数据时遇到问题，您可以查看 Etcd 日志，看看问题是否出在 Etcd 上。如果一个工作节点未能按预期上线，它的 Kubelet 日志可以提供洞察。

### **Kubernetes 事件**

Kubernetes 跟踪它所称的“事件”，这些事件可以是集群中对象状态的正常变化(比如容器被创建或启动)或错误(比如资源耗尽)。

事件仅提供有限的上下文和可见性。他们告诉你一些事情发生了，但是没有告诉你为什么会发生。它们仍然是快速获取集群中各种对象状态信息的有用方法。

### **Kubernetes 审计日志**

Kubernetes 可以配置为记录对 Kube-apiserver 的请求。这些请求包括人类发出的请求(比如请求运行的 pod 列表)和 Kubernetes 资源发出的请求(比如请求访问存储的容器)。

审计日志记录了谁或什么发出了请求、请求是为了什么以及结果。如果您需要解决与 API 请求相关的问题，审计日志提供了大量的可见性。通过查找不寻常的请求，它们对于检测不寻常的行为也很有用，例如用户访问群集中不同资源的重复失败尝试，这可能表示正在查找不正确保护的资源的人试图滥用资源。(这也可能反映了您的身份验证配置或证书有问题。)

## **如何访问 Kubernetes 日志数据**

上述各种类型的日志数据可以以不同的方式访问。

### **查看应用程序日志**

与应用程序日志数据交互有两种主要方式。第一种方法是运行如下命令

`kubectl logs pod-name`

其中“pod-name”是托管您要访问其日志的应用程序的 pod 的名称。

kubectl 方法对于快速查看日志数据非常有用。假设您想要持久地存储日志并系统地分析它们。在这种情况下，最好使用外部日志工具，如 IBM Log Analysis with LogDNA，来收集和解释日志。最简单的方法是运行一个所谓的 sidecar 容器，它与应用程序一起运行，收集应用程序的日志，并将它们提供给外部日志记录工具。在 IKS 上，您可以从命令行或者通过在 IKS Web 控制台中执行一些步骤，设置一个 LogDNA 实例来为应用程序日志(以及与 Kubernetes 本身相关联的日志)执行这个功能。要获得完整的说明，请查看 [IBM Cloud 文档](https://cloud.ibm.com/docs/containers?topic=containers-health#app_logdna)。

### **查看集群日志**

查看集群日志有多种方式。您可以简单地登录到托管您想要查看的日志的服务器(如上所述，在大多数情况下这是 Kubernetes 主节点服务器),并直接在文本编辑器、less、cat 或您喜欢的任何命令行工具中打开各个日志文件。或者，可以使用 journalctl 来检索和显示给定类型的日志。

最用户友好的解决方案还是使用外部日志工具，比如 IBM Log Analysis with LogDNA。如上所述，IBM Cloud 的[与 LogDNA](https://cloud.ibm.com/docs/containers?topic=containers-health#app_logdna) 的集成使得收集 Kubernetes 集群日志和应用程序日志并通过一个集中的界面进行分析变得容易，而不必担心通过命令行从每个节点收集单独日志的繁琐过程。

### **查看事件**

您可以使用类似下面的命令通过 kubectl 查看 Kubernetes 事件数据

`kubectl get events -n default`

其中“-n flag”指定要查看其事件的名称空间(在上面的示例中为默认值)。命令

`kubectl describe my-pod`

将显示特定 pod 的事件数据。

因为事件数据的上下文是有限的，所以您可能会发现记录所有事件不是很有用。但是，您总是可以将 kubectl 的 CLI 输出重定向到一个日志文件中，然后使用日志分析工具对其进行分析。

### **查看审计日志**

与其他类型的 Kubernetes 日志数据相比，您查看和管理审计日志的方式会有很大的不同，这取决于您使用的 Kubernetes 发行版和您希望用来收集这些日志的日志收集器。没有直接从 kubectl 收集审计日志的通用和直接的方法。

在 IKS 上，审计事件被路由到一个 webhook URL。从那里，您可以通过遵循这些[指令](https://cloud.ibm.com/docs/containers?topic=containers-health#webhook_logdna)来收集 IKS 本地 LogDNA 集成的日志数据。

## **如何构建 Kubernetes 日志解决方案**

正如我们在上面看到的，Kubernetes 中有多种类型的日志数据可用，但是也有多种访问它的方法。设计最适合您的 Kubernetes 日志记录策略和工具集需要权衡几个因素:

*   **你需要收集哪种库伯内特原木？**某些类型的数据对您来说或多或少都很重要。例如，如果您运行不生成有意义的监控数据的简单应用程序，那么应用程序日志可能没有 Kubernetes 集群日志重要。
*   你的日志目标是什么？如果您只想快速查看日志文件，kubectl(或者在某些情况下，journalctl)可以完成这项工作。但是，如果您需要长期的日志管理，您将需要一个外部日志收集器。
*   你需要可视化吗？当您访问 Kubernetes 日志文件时，您是否只是在寻找特定的信息，比如 API 请求的来源？或者，您希望能够可视化数据以识别趋势或比较日志吗？在后一种情况下，需要提供日志收集和可视化的外部工具或工具组合。
*   **是否需要聚合日志？**您的目标是访问单个日志文件，还是希望将多个日志聚集在一起并进行综合分析？您需要外部工具来完成后者。
*   **您需要将日志保留多长时间？**存储在 Kubernetes 中的大多数日志数据会在一段时间后被删除，这取决于日志类型和您的日志记录配置。因此，如果您想长期保存历史日志数据，您需要将它导出到外部日志平台。

## **结论**

在 Kubernetes，围绕伐木有许多细微差别。尽管 Kubernetes 提供了一些基本的内置日志和监控功能，但它离成熟的日志解决方案还很远。为了充分利用 Kubernetes 日志记录，您需要一个外部日志收集、分析和管理工具，如 log DNA——如上所述，它很容易在 Kubernetes 发行版(如 IKS)上设置，它是官方支持的日志记录解决方案之一。

*这篇文章是探索 Kubernetes 日志记录和 Red Hat OpenShift 日志记录之间差异的更大系列文章的一部分。下载完整电子书* [*这里*](http://go.logdna.com/openshift-vs-kubernetes) *。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>