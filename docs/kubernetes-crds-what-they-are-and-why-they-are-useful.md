# Kubernetes CRDs:它们是什么，为什么有用

> 原文：<https://thenewstack.io/kubernetes-crds-what-they-are-and-why-they-are-useful/>

Kubernetes 如此受欢迎的一个主要原因是它非常灵活。当我们提到 Kubernetes 时，我们通常会想到部署和管理容器。虽然这实际上是 Kubernetes 的主要工作，但它实际上可以做得更多。多亏了被称为自定义资源定义(简称 CRDs)的东西，这才成为可能。在这篇文章中，你将学习什么是 CRD 以及你可以用它们做什么。我们还将看看如何创建它们。

> 但是通过观察 Kubernetes 的内部，您可以看到 Kubernetes 的主要组件是一个 API 服务器和 etcd 数据存储。

## **Kubernetes API**

 [达维德·齐奥尔科夫斯基

Dawid 有 10 年的经验，最初是网络/系统工程师，中间是 DevOps，最近是云原生工程师。他曾在一家 IT 外包公司、一家研究机构、电信公司、一家托管公司和一家咨询公司工作过，因此他从不同的角度收集了很多知识。如今，他正在帮助公司迁移到云和/或重新设计他们的基础设施，以实现更加云本地化的方法。](https://twitter.com/DavidZisky) 

在我们深入定制资源定义之前，让我们先从总体上谈谈 Kubernetes。如果我问你，“Kubernetes 是什么？”那么你可能会回答，“Kubernetes 是一个容器管弦乐队。”当然，这是一个正确的答案。

但是通过观察 Kubernetes 的内部，您可以看到 Kubernetes 的主要组件是一个 API 服务器和 etcd 数据存储。此外，还有其他更重要的组件，如 kube-scheduler、kube-controller-manager 和 cloud-controller-manager，但几乎所有集群上的操作都需要通过 API 服务器。

这个 API 有一些它能理解的内置对象。您可能熟悉的东西，如 pod、名称空间、配置图、服务或节点都是 API 对象。这就是为什么每当您执行`kubectl get pods<`或`kubectl get nodes`时，您会得到一个 pod 或节点的列表。但是，如果您试图获取 Kubernetes API 中不存在的对象的列表，例如，`kubectl get biscuits`，您将会得到类似如下的响应:

`error: the server doesn't have a resource type "biscuits"`

这是因为 Kubernetes API 中没有定义“饼干”这种东西。很符合逻辑，对吧？那么，如果我告诉你，你可以添加一个饼干定义到你的 Kubernetes 集群？事实上，您可以用任何您喜欢的定制对象来扩展您的 Kubernetes API。这正是自定义资源定义的用途。

## **为什么选择 CRDs？**

那么，向 Kubernetes 集群添加饼干定义有什么意义呢？还记得我之前提到的 Kubernetes 的成功来自于它的灵活性吗？用自定义资源定义扩展 Kubernetes API 的能力是一个非常棒的特性，可以让您做一些神奇的事情。它允许您指示 Kubernetes 管理不仅仅是容器。

为什么这是一件如此伟大的事情？因为 CRDs 和 Kubernetes 算子一起给了你几乎无限的可能性。您可以调整 Kubernetes，使其能够处理您的基础设施中较旧的部分。如果你做得对，你将能够避免瓶颈，轻松地使通常需要长时间和昂贵的重新设计的东西现代化。

## **集群上的 CRDs】**

在我们开始创建自己的 CRD 之前，你需要知道两件事。

首先，创建自定义资源定义是一个高级主题。许多公司甚至不需要创建任何 CRD。Kubernetes 社区一直在为常见问题寻找有趣的解决方案，很可能您遇到的任何用例都已经有了您可以使用的 CRD。如果你还是 Kubernetes 的新手，在你很好地理解基础知识之前，你绝对不应该跳入 CRDs。

第二，正如已经提到的，如果你觉得没有必要，你不需要自己创建任何 CRD。然而，许多 Kubernetes 工具会安装它们自己的 CRD，所以即使您自己没有创建任何 CRD，您也可能会在您的集群上安装一些。

一个例子是 [cert-manager](https://cert-manager.io) ，一个非常流行的用于管理证书的 Kubernetes 工具。它在您的集群上安装一些 CRD 来完成它的工作。如果您在安装 cert-manager 之前执行`kubectl get clusterissuers`,您的集群将不会知道什么是集群颁发者:

`error: the server doesn't have a resource type "clusterissuers"`

但是如果您在 cert-manager 安装之后执行相同的命令，您将获得您的集群上的 ClusterIssuers 列表。

事实上，您可以通过执行`kubectl get crd` :
列出集群上安装的所有定制资源定义

```
$  kubectl get crd

NAME CREATED AT

addons.k3s.cattle.io  2022-01-23T12:48:31Z

helmcharts.helm.cattle.io  2022-01-23T12:48:31Z

helmchartconfigs.helm.cattle.io  2022-01-23T12:48:31Z

serverstransports.traefik.containo.us  2022-01-23T12:49:48Z

tlsoptions.traefik.containo.us  2022-01-23T12:49:48Z

ingressroutetcps.traefik.containo.us  2022-01-23T12:49:48Z

ingressroutes.traefik.containo.us  2022-01-23T12:49:48Z

tlsstores.traefik.containo.us  2022-01-23T12:49:48Z

middlewares.traefik.containo.us  2022-01-23T12:49:48Z

traefikservices.traefik.containo.us  2022-01-23T12:49:48Z

middlewaretcps.traefik.containo.us  2022-01-23T12:49:48Z

ingressrouteudps.traefik.containo.us  2022-01-23T12:49:48Z

```

上面的输出以`<object>.<group>`的形式出现，告诉我可以执行`kubectl get addons`、`kubectl get helmcharts`或`kubectl get middlewares`这样的命令。它们都没有在 vanilla Kubernetes 中定义，之所以存在是因为它们被定义为自定义资源定义。

## **如何创建 CRD**

好吧，别提饼干了。让我们来看看一些更现实的例子。假设您希望 Kubernetes 以某种方式管理您数据中心中的定制路由器。为此，您可以创建一个类似于下面的自定义资源定义:

```
apiVersion:  apiextensions.k8s.io/v1

kind:  CustomResourceDefinition

metadata:

# Name of your CRD. Must match the spec block below, and be in the form: <plural>.<group>

name:  routers.example.com

spec:

# Group name to use for REST API: /apis/<group>/<version>

group:  example.com

names:

# Plural name to be used in the URL: /apis/<group>/<version>/<plural>

plural:  routers

# Singular name to be used as an alias on the CLI and for display

singular:  router

# Kind is normally the CamelCased singular type. Your resource manifests use this.

kind:  Router

# ShortNames allow shorter string to match your resource on the CLI

shortNames:

-  rt

# Scope can be either Namespaced or Cluster-wide

scope:  Cluster

versions:

-  name:  v1

# Each version can be enabled/disabled by Served flag.

served:  true

# One and only one version must be marked as the storage version.

storage:  true

schema:

openAPIV3Schema:

type:  object

properties:

spec:

type:  object

properties:

dataCenter:

type:  string

rack:

type:  integer

type:

type:  string

enum:

-  f5

-  virtual

required:  ["dataCenter",  "rack",  "type"]

required:  ["spec"]

```

您可以通过执行`kubectl apply -f router-CRD.yaml`将上述 CRD 应用于集群。一旦你这样做了，你的 Kubernetes 集群就已经知道什么是“路由器”。因此，您将能够执行`kubectl get routers`。当然，我们只是应用了资源定义，而不是资源本身。所以`kubectl get routers`会返回以下内容:

`No resources found.`

但是你可以看到，它没有返回这个:

`error: the server doesn't have a resource type "routers"`

这意味着我们成功地向 Kubernetes API 添加了一个新对象。要添加一个实际的路由器资源，您可以像使用任何其他对象一样构造一个 YAML 定义文件:

```
apiVersion:  example.com/v1

kind:  Router

metadata:

name:  example-router

spec:

dataCenter:  eu-1

rack:  3

type:  virtual

```

现在，您可以通过执行`kubectl apply - f example-router.yaml`在您的集群上创建一个新的路由器，如果您尝试使用`kubectl get routers`再次获得路由器列表，您现在应该会看到一个:

```
$  kubectl get routers

NAME AGE

example-router  4s

Congratulations!  You just extended the Kubernetes API.

```

> 在目前的形式下，我们的 CRD 除了被 Kubernetes API 处理和存储之外没有做任何事情。

## **如何处理 CRDs**

你可能在想，“好的，太好了，但是那个路由器什么也不做！”是的，没错。在目前的形式下，我们的 CRD 除了被 Kubernetes API 处理和存储之外没有做任何事情。虽然有这样就足够了的用例，但通常 CRD 与定制控制器相结合。

定制控制器是 Kubernetes 中的另一个概念，它允许您实际使用定制资源做一些事情。在我们的案例中，我们希望在数据中心实际创建或配置路由器。因此，我们必须编写一个定制控制器，并指示它监听 Kubernetes API，等待对我们的定制路由器对象的任何更改。

幕后的自定义控制器只是用您选择的编程语言编写的应用程序或脚本。它们作为 pod 部署在集群上，它们的工作是监听 Kubernetes API 并根据定义的逻辑执行一些操作。

## **CRD vs. ConfigMap**

最后但同样重要的是，通过查看 CRDs，您可能会发现它与 Kubernetes 内置对象 ConfigMap 有一些相似之处。如果您使用没有定制控制器的 CRD，它们实际上可以达到类似的目的。它们都可以用来存储定制配置。然而，它们之间有明显的差异。

首先，ConfigMaps 的设计意图是为您的 pod 提供配置。它们可以作为文件或环境变量安装到 pod 中。如果您有定义良好的配置文件，例如 Apache 或 MySQL 配置文件，它们就能很好地工作。

豆荚也可以食用 CRDs，但只能通过接触 Kubernetes API。它们只是有不同于配置图的目的。它们不是用来为您的 pods 提供配置的，而是用来扩展 Kubernetes API 以构建定制的自动化。

## **总结**

当然，Kubernetes 的灵活性是它如此成功的原因之一。现在，您可以通过创建自己的 Kubernetes 对象来利用这种灵活性。可能性几乎是无限的，如何利用 CRDs 取决于你自己。

回来我们这里看更多的 Kubernetes 文章。[这里是](https://releasehub.com/blog/kubernetes-daemonset-tutorial)[发布的](https://releasehub.com/)文章，解释另一个 Kubernetes 对象 DaemonSets。此外，请随意查看我们的产品。我们通过提供[环境即服务来简化开发过程。](https://releasehub.com/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>