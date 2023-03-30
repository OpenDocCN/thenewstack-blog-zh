# Red Hat，Google 工程师正在为 Kubernetes 开发一种不用 Docker 就能运行容器的方法

> 原文：<https://thenewstack.io/oci-building-way-kubernetes-run-containers-without-docker/>

2015 年，当[开放容器倡议](https://thenewstack.io/docker-donates-container-format-and-runtime-code-joins-coreos-to-form-standards-group/) (OCI)启动以创建围绕容器的行业标准时，它使用 Docker 的容器运行时和图像格式作为基础。但现在许多公司正在进行一个项目，将 OCI 堆栈从 Docker 中分离出来，优先于谷歌的开源容器编排引擎 [Kubernetes](/category/kubernetes/) 。

这个新项目是为 Kubernetes 设计的。它将直接与 Kubernetes 豆荚接口。它将使 Kubernetes——而不是 Docker——能够大规模启动和管理容器。

“我们想要的是一个守护进程，可以被 Kubernetes 用来运行存储在 Docker 注册表上的容器图像，”长期负责 SELinux 项目的顾问工程师[丹·沃什](https://people.redhat.com/dwalsh/)在谈到新的堆栈时说。红帽公司和谷歌的开发人员在这个项目中处于领先地位，目前，这个项目被简称为 [OCID](https://github.com/kubernetes-incubator/ocid) (OCI 守护进程)。“为了做到这一点，”沃尔什继续说道，“我们希望建立一系列库，以便能够方便地运行这些容器映像。”

该项目的维护者断言，OCID 不是一个“Docker fork”，尽管该项目是容器生态系统分裂的证据，特别是当 Kubernetes 继续在容器市场获得自己的牵引力时。

今年早些时候，Docker，Inc .制作了自己的编排引擎 Docker Swarm，[作为其 Docker 引擎 1.12 版本的一部分。因此，Docker Engine 现在允许用户管理复杂的容器化应用程序，而无需额外的软件。Docker 编排功能是可选的；它们必须由用户激活，尽管许多人担心不选择可能会导致向后兼容问题。](https://thenewstack.io/docker-engine-1-12-will-come-built-orchestration-capabilities/)

Docker 将 Swarm 添加到 Docker 引擎的举动给一个已经不和的社区增加了摩擦。八月下旬，在与供应商和用户的讨论中，出现了对分叉 Docker 的兴趣。在公开场合，开发人员对 Docker 激进的发布时间表以及它如何让第三方系统提供商与他们自己的客户群发生冲突颇有微词。

目前，红帽的工程师[正牵头](https://www.redhat.com/en/about/blog/running-production-applications-containers-introducing-ocid)OCID 项目，该项目于今年 6 月启动。它是作为 [Kubernetes 孵化器项目](https://github.com/kubernetes-incubator)的一部分开发的，该项目支持反过来支持 Kubernetes 的项目。它的主要维护者是谷歌的 [Vishnu Kannan](https://twitter.com/vishnukanan) 和红帽的 [Mrunal Patel](https://twitter.com/mrunalp) 。

“我们真的不需要任何容器运行时，无论是 Docker 还是[CoreOS ']rkt-他们需要做的很少，”谷歌的员工开发人员倡导者凯尔西·海塔尔说，“主要是给我们一个内核 API。所以这不仅仅是关于 Linux。我们可以在 Windows 系统上…如果这是社区想要的方向，来支持这些想法。因为在这一点上它比 Docker 公司大。这是关于，你如何运行一个容器化的应用程序？"

## 在(或进入)最重要位置

如果 OCID(发音为 O-C-I-D)真的像一些人建议的那样成为容器引擎的参考实现，它将为大规模运行 OCI 容器提供免费的*和*开源选项。它将包括 [**runc**](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/) ，基于 **libcontainer** 的容器运行时，Docker 将其捐赠给 OCI 作为免费标准使用。它还将包括将图像推送到容器注册中心托管的存储库中以及从存储库中取出图像所需的代码。它将支持 CoreOS 构建的[容器网络接口](https://thenewstack.io/container-networking-landscape-cni-coreos-cnm-docker/)，用于独立于托管容器的引擎对插件进行建模。

然而，作为 OCID*存在理由*的组件被称为 **oci-runtime** 。正如其在 GitHub 上的项目页面所描述的，“这是 Kubernetes 容器运行时接口(CRI)的一个实现，将允许 Kubernetes 直接启动和管理开放容器倡议(OCI)容器。”

> Kelsey Hightower 解释说，OCI 不仅需要指定如何运行容器，还需要指定如何下载和联网容器，给人们一些他们可以实际使用的东西。

在 Kubernetes 环境中，有一个名为 *kubelet* 的组件，它的工作是管理 pod——通常构成一个应用程序的容器集群。kubelet 能够充当独立的守护进程，是其 pod 中容器的一种本地霸主。OCID 的关键项目 **oci-runtime** ，将在 kubelets 和 Kubernetes 之间实现一个新的接口类，使编排器能够有效地管理整个容器生命周期。

“我们现在想做的是重构 kubelet 代码库，”谷歌的 Hightower 评论道，“这样我们与 Docker、 **rkt** 以及现在的 OCID 整合的方式就更加干净和一致了。我们希望提供一个定义良好的接口，也就是说，为了让容器运行时引擎与 Kubernetes 兼容，我们将拥有一个容器运行时接口。CRI 将是你的容器运行时需要支持的 API 抽象，以便我们证明它可以在 Kubernetes 下运行。”

## 填补空白

如果 OCID 听起来像一个全新的、功能完整的容器引擎，它不是。不管迄今为止它是如何被描述的，有一个非常重要的遗漏。

“现在，在这一点上，OCID 还没有实施，以建立一个 OCI 的形象，”红帽的沃尔什说。“你首先就没有能力创建图像……你仍然需要一个像 Docker 这样的工具来构建 OCI 图像—[*基本上是一个 Docker 图像。”*

 *“我们的目标——我认为也是业界的目标——是拥有一个容器运行时的标准实现，以及一个如何构建容器映像的标准格式, [Joe Fernandes](https://twitter.com/joefern1?lang=en) 评论道，他是 Red Hat 负责 [OpenShift](https://www.openshift.com/) (Red Hat 的商业编排引擎，基于 Kubernetes)的产品管理高级总监。“这样，不同的供应商可以在此基础上构建不同的解决方案，生态系统也可以发展壮大。”

费尔南德斯解释说，Docker 图像格式为开发生态系统建立了共同基础。他认为发布这种格式的标准是 OCI 工作的一部分。

“一旦你有了格式，接下来就是运行时间了，”他说。“有些人认为，当 Docker 贡献了**lib container**——后来变成了**runc**——那就是运行时。这是运行时的*部分*——最低的部分。但是这些其他模块也组成了运行时。因此，我们在这里所做的是为这些模块创建标准实现。”

去年 12 月，这似乎是真的，在[演示幻灯片显示 OCI 的重点将被限制在容器运行时( **runc** )和容器图像格式上之后](https://thenewstack.io/oci-reveals-governance-structure-amid-debate-focus/)似乎已经被坚定地决定了。

但是 Red Hat 的开发者在 Google 开发者的帮助下，可以说是扩展了“容器运行时”的定义。Fernandes 将其解释为更广泛的实现的基础层。Hightower 解释说，根据定义，它包括一个 orchestrator 组件的接口——目前是 Kubernetes，但理论上不限于 Kubernetes，假设任何其他 orchestrator 都想使用相同的 API 并运行它。

“OCID 实际上是 OCI 的自然发展，”海塔尔解释说。“他们的目标是围绕 Docker 开创的东西制定一些标准:我们可以将应用程序打包成图像格式，放在存储库中，并与任何人共享。一旦它们被共享，就可以下载、提取并以非常一致的方式运行它们。”

Hightower 解释说，为了做到这一点，OCI 不仅需要指定如何运行容器，还需要指定如何下载和联网容器，给人们一些他们可以实际使用的东西。

“如果它们将是一堆文档和库，让我们给人们一些东西，我想在许多方面，可以与 Docker 本身相媲美，”他继续说道，“只专注于我刚才提到的那些部分。这样，OCI 是什么就不那么神秘了；现在，您将拥有一个完全指定的、集成的东西，您可以在其中一些项目中实际使用它。”

OCID 的主要组件之一是 [**skopeo** ，这是一个用于从 Docker 存储库中验证和获取容器图像的工具](https://github.com/projectatomic/skopeo)，它现在是 Red Hat 对 Docker 本身的主要贡献之一。

Walsh 解释说, **skopeo** 最初是作为一种检查集装箱图像的工具开发的，并生成一个可以用作其清单的 JSON 文件。该工具后来被用于从 Docker 注册表中提取和推送图像。Red Hat 随后将其注册为其 Project Atomic 的一部分，基于 Go 库的衍生产品[现在在 GitHub 上以 **containers/image**](https://github.com/containers/image) 的名称提供。

Walsh 说，除了 skopeo 之外，OCID 项目还包括一个基于 Docker 组件的写时复制文件系统，这个 Docker 组件被称为图形驱动程序。

“我们几个月前就开始工作了，”他告诉我们，“分离出写时复制文件系统，这样除了 Docker 之外的其他工具就可以共享[*it*]。实际上，我们发现很难继续在 Docker 下工作，将它作为一个独立的模块，所以我们决定将它拔出来，集中精力让模块完全正确。希望在某个时候，我们可以打开一个拉取请求，将它放回 Docker。”

与此同时，他说，库的当前形式[在 GitHub 上也显示为**容器/存储**](https://github.com/containers/storage) 。Walsh 指出，虽然 Docker 有自己的写时复制文件系统，但它完全运行在自己的专用内存中。

“我们使用的共享图书馆和 OCID 使用的一样，”他说。“我们希望看到这些库中的一些进入未来版本的 **rkt** ，我们实际上希望看到它们回到 Docker……我们希望对**存储**做的是将文件系统存储的锁定转移到*文件锁*，以便多个应用程序可以同时共享存储。我们很想在某个时候把它放回 Docker 守护进程中。”

## 动机

作为一个发展中的项目，OCID 今天可能是某些东西，但它在未来将不复存在，反之亦然。令人惊讶的是，至少在今天，OCID 没有的东西之一是专门运行 OCI 集装箱的机制。帕特尔说，OCID 也不属于 OCI 项目的范围，因为该项目证明集装箱符合 OCI 标准。[Patel 和 Kannan 共同撰写的文档](https://github.com/mrunalp/kubernetes/blob/dce95c8a7564a973d5699fc7386c39dc417bfd8d/docs/proposals/kubelet-oci-runtime.md)明确要求容器格式支持的灵活性，包括随着 OCI 的发展继续支持 Docker，以及支持日常的 TAR 文件。

正如 Joe Fernandes 提醒我们的那样，Docker 最初是作为一个完整的容器系统存在的，在之前的几个月里(它还是一个非常年轻的产品)变得更加模块化了— **runc** 就是其中的一个模块。虽然 **runc** 的前身被设计成拉进 Docker 引擎，但是 **runc** 今天也可以同样轻松地拉进 CoreOS 的 **rkt** 。

“你可以沿着这条线看 OCID，”费尔南德斯解释道。“这里还有其他模块，我们希望将其划分出来并使之成为标准……我们希望与 Docker 社区合作，他们可以将这些模块拉回来，因为它们是标准接口——而不是拥有一种将所有模块融合在一起的整体。这是整个 UNIX 哲学，“做好一件事。”我们创建了 OCID 项目来完成这项工作——测试这些想法，并提出标准实现，然后可以推回到 OCI，然后最终引入不同的实现，Docker 是显而易见的一个。"

正如 Fernandes 和 Walsh 对我们说的，省略“引擎”组件作为 OCID 容器图像的创建者是有意的。他们一致认为，这是一个引擎，Red Hat、Docker、CoreOS 和 VMware 等供应商可以利用它来实现各自的“增值”，并在价值和服务方面相互竞争。

然而，在撰写本文时，GitHub 上的开源文档中仍有两个措辞非常奇怪的元素(当然，其整体仍在不断审查中)。

首先，在 kubelet 接口的项目页面上有这样的描述:“对于第一个版本， **oci-runtime** 将继续使用 **docker-engine** 来管理映像。映像管理功能将从运行时功能中分离出来，因此每个功能都可以有不同的实现，这些实现可能会被切换。一旦 OCI 图像规范达到 1.0 版，它将非常适合支持图像。”

该描述可以解释为运行时组件将依赖 Docker 代码来支持，至少在最初几轮中是这样，但它也为 OCID 使用其他引擎奠定了基础，减少了对 Docker 引擎本身的依赖。

第二个同样奇怪的短语是 OCID 文档中把 OCID 和谷歌联系在一起的钩子:具体来说，[明确自我声明](https://github.com/kubernetes-incubator/ocid)是 Kubernetes 环境的一部分。首先，OCID 声明其生活的目的是为 Kubernetes 的成员提供管理——这一声明优先于其对容器的管理。

Google 的 Hightower 认为 Kubernetes 在容器社区中赢得了一个位置，或许可以被描述为公平的仲裁者。

“这更多的是为了公平竞争，”他说。“现在，Docker 是最受支持的容器运行时，因为我们在谷歌和社区已经完成了使 Docker 作为一流运行时工作的大部分工作。但是现在我们看到人们想要选择，并且我们的愿景一直是支持多容器运行时，那么做的一个步骤就是创建这个容器运行时接口。作为其中的一部分，我们将重构当前的代码库，以实现[CRI]。”

## 奇异

然而，为了让 CRI 像 Hightower 解释的那样工作，将需要某种组件来打击围绕 Docker 爆发的第一场争论的核心:具体来说，一个能够自我启动的*系统容器*。这样一个组件有效地将 systemd，Linux 现在首选的应用程序初始化机制**，**从地毯下踢了出来。

“我们希望以容器的形式运送所有东西，所以我们需要一个不使用编排的容器运行时，”Red Hat 的 Walsh 解释说，“因为编排需要它。所以我们面临着先有鸡还是先有蛋的局面。通过使用系统容器，我们能够使用**容器/映像**库提取映像，我们能够将它存储在**容器/存储**中，然后我们将执行 **runc** ，但在这种情况下，我们将把它作为**系统和**的一部分运行。”

沃尔什认为，这是一种方式，一个集装箱化的环境可以有效地在生产中启动自己，进而启动 Kubernetes。

毫无疑问，OCI 的活动范围在第一年就扩大了。一开始有人说，一旦容器格式规范发布，OCI 的工作就完成了。现在，我们看到它的两个最突出的成员正在推动一个开放的写时复制文件系统库、一个开放的注册表维护库、一个联网方案和一个依赖于 Docker 宁愿保留的架构特性的引导机制。容器安全库还会远吗？

至关重要的组件——容器引擎本身——将留给每个数据中心自己解决。在这种情况下，Docker 可能拥有先发优势，因为它首先创造了市场。但它可能会发现自己在与 OpenShift 进行一对一的竞争，条件是红帽帮助创造的。

“我想说 OCID 将会被库伯内特公司使用。在 OpenShift 环境中，我们的目标是让 Kubernetes 使用 OCID 作为其容器运行时环境。然后 OpenShift 会使用 Kubernetes，这样我们就能得到 OCID 的优势。”

所以如果你将来要用 Kubernetes，你会有 OCID，这个决定会为你做出。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*