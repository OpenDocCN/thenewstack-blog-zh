# Kubernetes 命令式命令简介

> 原文：<https://thenewstack.io/introduction-to-kubernetes-imperative-commands/>

Kubernetes 诞生于使我们的复杂应用程序在小型微服务中高度可用、可伸缩、可移植和可独立部署的需求。它还扩展了采用 DevOps 流程的能力，并帮助您建立[现代事件响应](https://www.squadcast.com/blog/traditional-vs-modern-incident-response)策略，以增强您应用程序的可靠性

## **在 Kubernetes 中运行应用**

尽管 Kubernetes 的内部架构和 API 流程复杂，但它让用户可以轻松地处理部署、服务、配置图和[机密](https://thenewstack.io/kubernetes-secrets-management-3-approaches-9-best-practices/)等对象，因为 Kubernetes 旨在抽象出管理这些对象的许多复杂性。因此，用户可以专注于运行他们的应用程序，而不必担心 Kubernetes 的内部细节。

让我们探索一下用户如何与 Kubernetes 互动。

### **库贝克特尔**

Kubectl 就像是容器编排、部署和管理的瑞士军刀。它是一个强大的命令行工具，可以用来管理 Kubernetes 部署和资源。使用它，您可以检查 Kubernetes 对象、查看日志和执行其他操作任务。Kubectl 如此强大，以至于 Kubernetes 中的每个动作都可以通过 kubectl 命令来控制。

## **命令式和声明式方法**

管理 Kubernetes 对象有两种主要方式:命令式(使用 kubectl 命令)和声明式(通过编写清单，然后使用`kubectl apply`)。每种方法都有自己的优缺点，所以最好根据您的用例选择一种方法。

命令式命令非常适合学习和交互式实验，但是它们不能让您完全访问 Kubernetes API。它们更常用于在旅途中创建 YAML 清单和对象。声明性命令对于可重复的部署和生产非常有用。它们通常用在 CI/CD 管道和[舵图](https://thenewstack.io/what-the-helm-the-tool-we-all-love-and-sometimes-hate/)中，其中 YAML 清单需要提前呈现。

### **利弊**

每种类型的命令都有优点和缺点，因此确定哪种命令最适合您的需求非常重要。下面是对每种方法的优缺点的简要概述。

## **深入探究命令式命令**

在这一节中，我们将看到如何使用 kubectl 命令与 Kubernetes 集群进行交互，并对 Kubernetes 对象进行各种操作。这对于管理 Kubernetes 集群和开发应用程序非常有用。

### **创建**

kubectl CLI 通常用于创建对象。为了创建一个对象，kubectl 的命令性命令要求用户明确地指定他们希望创建的对象的类型，以及他们希望与正在创建的对象相关联的属性。

*   kubectl 创建对象的命令性命令的语法可以总结如下:

`kubectl create <type-of-object> [<subtype-of-object>] <name-of-object> <properties>`

因为一些 Kubernetes 对象有几个子类型，所以用户也需要指定对象的子类型参数。例如，Kubernetes 服务有几个子类型，如 ClusterIP、NodePort 或 LoadBalancer。创建服务时，用户需要将服务类型指定为对象子类型参数。

*   创建`nodeport`服务的语法非常简单，可以总结如下:

`kubectl create service nodeport <name-of-service> <properties>`

*   以上语法的一个示例:

`kubectl create service nodeport my-ns --tcp=5678:8080`

另一个需要指定对象子类型参数的例子是当你创建一个秘密时。Kubernetes 内部的秘密可以是 generic、TLS 或 Docker-registry 类型。

*   创建通用秘密的语法非常简单:

`kubectl create secret generic <name-of-secret>`

*   以上语法的一个示例:

`kubectl create secret generic my-secret --from-literal=key1=supersecret`

### **例题**

熟悉与创建相关的命令会有所帮助，所以让我们看看一些额外的语法和例子。

*   示例:创建一个带有`name=squadcast`键值对的配置映射。

`kubectl create configmap <name> --from-literal=<key>=<value>`

`kubectl create configmap cm123 --from-literal=name=squadcast`

*   示例:创建一个名为 Squadcast 的部署，运行 Ubuntu 的三个副本。

`kubectl create deployment <name> --image=<image> --replicas=<replicas>`

`kubectl create deployment squadcast --image=ubuntu --replicas=2`

*   示例:创建一个名为 Squadcast 的作业，在 Ubuntu 上执行 sleep 命令。

`kubectl create job <name> --image=<image> -- <command> <argument>`

`kubectl create job squadcast --image=ubuntu -- sleep 200`

除了`create`，还有其他功能可以帮助你使用 Kubernetes，比如`expose`和`run`。让我们也来看看他们。

### **曝光**

服务对象是用户如何与 Kubernetes 中的应用程序进行交互，以及不同的微服务如何相互通信。换句话说，任何可以在 Kubernetes 上使用的应用程序都需要一个服务对象。

kubectl CLI 通常用于通过创建服务来公开应用程序。为了公开应用程序——例如，大多数情况下是部署——kubectl 的命令性命令要求用户明确指定他们希望公开的部署的名称，以及他们希望在部署对象上公开的端口号。

*   要为您的部署公开端口 80，请使用以下语法:

`kubectl expose deployment <name-of-deployment> --type=<type> --port=<port> --target-port=<target-port> --name=<name-of-svc>`

*   以上语法的一个示例:

`kubectl expose deployment nginx --type=ClusterIP --port=8080 --target-port=80 --name=nginx-clusterip-svc`

### **运行**

pod 是可由 Kubernetes 管理的容器化应用程序的最小单元。您通常使用部署对象来创建 pod，但是在许多用例中，您必须单独创建 pod。事实上，独立创建一个 Kubernetes pod 是开始管理自己的容器化应用程序的好方法。通过了解如何自己创建和管理 pods，您将很快成为 Kubernetes 专家。

Kubectl 的 CLI 通常用于创建 pod。为了创建一个 pod，kubectl 的命令性命令要求用户显式地指定将在 pod 中运行的映像。

*   运行 pod 运行`ubuntu`的语法如下:

`kubectl run <pod-name> --image=<image>`

*   以上语法的一个示例:

`kubectl run ubuntu --image=ubuntu`

除了上面讨论的命令之外，还有一些重要的参数可以帮助您更快地使用命令和 Kubernetes。让我们来看看它们。

### **解释**

Kubernetes 有很多命令，这使得用户不可能记住所有的东西。虽然文档上什么都有，但是一遍又一遍地阅读文档是没有效率的，并且会严重降低您的速度。Kubectl 以`explain`的形式给出了一个优雅的解决方案。您可以将`explain`视为可以通过 CLI 访问的迷你文档。

`Explain`提供了命令支持的参数列表，以及命令的使用案例和示例。最重要的是，它可以为您提供一个完整的 YAML，包含对象支持的所有参数。让我们仔细看看。

*   查看命令参数和描述的示例:

`kubectl explain pods`

`kubectl explain pods.spec.containers`

*   例子来看一个成熟的 YAML 的命令:

`kubectl explain pod --recursive`

## **祈使句改为陈述句**

如果您使用声明性命令，您将需要一个 YAML 清单。但是，如果您使用命令式命令，您可以生成这些文件，而无需实际创建对象。

例如，如果您将`—dry-run=client -o yaml`标志与命令性命令(如 kubectl)一起使用，您将得到一个 YAML 版本的操作(如创建对象),而不会在集群上实际应用更改。这可以节省您从头开始编写 YAML 文件的时间和精力。另外，通过将生成的清单存储在代码库中，您可以根据需要以声明方式使用它们。

`kubectl create deployment squadcast --replicas=3 --image=ubuntu **--dry-run=client -o yaml** > squadcast-deployment.yaml`

## **结论**

学习任何新技术都需要时间和努力，但是有了 Kubernetes，有几种方法可以让学习过程变得更容易。首先，熟悉 kubectl 及其文档。第二，学习一些命令性的命令，这将有助于你记住关键命令，更快地执行操作。

在本文中，我们已经涵盖了您需要了解的关于命令性命令的所有内容——它们是什么、何时使用它们以及如何正确使用它们。我们已经提供了多个高级命令的实例，因此您可以开始在自己的实验和项目中使用它们。感谢阅读！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>