# 教程:使用 MiniKube 在 Kubernetes 中动态提供持久存储

> 原文：<https://thenewstack.io/tutorial-dynamic-provisioning-of-persistent-storage-in-kubernetes-with-minikube/>

在……里

[previous article](/kubernetes-storage-dynamic-volumes-and-the-container-storage-interface)

，平台 9 Kubernetes 工程师 Jay Vyas 深入研究了 Kubernetes 存储的构造，以及不同类型的存储有什么好处。我们讨论了动态配置、存储类别和 CSI 外部存储。在本文中，我们使用 MiniKube 建立了一个简单的私有沙箱，在这里我们可以观察和破解 Kubernetes 存储的内部工作方式。

当我最近意识到 [MiniKube](https://kubernetes.io/docs/setup/minikube/) 发布了自己的动态供应器，它使用*gasp*、 *hostPath、*时，我很高兴。现在，我终于可以与任何能够以一种可理解的方式从根本上说明并再现 Kubernetes 存储模型的微妙之处的人共享一个环境了。

## 你能用 MiniKube 回答什么样的现实问题？

 [杰伊·维亚斯

Jay Vyas 是 Kubernetes platform 9 的工程师，Kubernetes 的核心贡献者，ASF 成员和委员。除了在 Kubernetes core 成立(在 Red Hat)以来的几年时间里致力于其多个方面的工作之外，Jay 还在 Synopsys (Blackduck)担任云原生产品线的工程主管，为全球数百家客户带来了基于 Kubernetes 的大规模解决方案。在大数据、横向扩展存储和云原生技术的交叉领域工作过。Jay 深信，微服务的核心附加值体现在企业工程创新周期的去风险化和民主化。](https://platform9.com/) 

以下是客户遇到的一些与储物相关的问题，可以在 MiniKube 中轻松演示和回答:

*   一旦索赔和 pod 被删除，回收量索赔会发生什么情况？技巧问题:回收不再是一件事了——动态置备程序允许您以自己选择的任何方式定制逻辑。
*   有没有一种方法可以强制存储在装载卷之前/之后更改卷的权限？
    是的，看看外部存储库中的各种例子(稍后会详细介绍)。
*   如果目录尚不存在，主机路径卷会发生什么情况？
    它是由库伯莱特创造的。
*   kubelet 可以为我修改卷权限吗？
*   我需要什么样的安全上下文设置才能使用主机网络端口(经常需要 glusterFS)？
*   有没有完全容器化的分布式文件系统，我可以快速运行？(是的，NFS，它在 MiniKube 经营 OOTB)
*   如果我在一个 IP 地址上有一个可用的 NAS，我是否可以将子目录放在我的默认存储类别下？
    当然，只要 IP 可路由，您就可以将其安装在笔记本电脑上。

## 为什么是 MiniKube？

在推理 Kubernetes 的功能和系统行为时，MiniKube 仍然是 Kubernetes 工具箱中最重要的工具。

尽管很多人使用 MiniKube 来测试 YAML 格式和基本的 kubectl 命令语法，但是很少有 MiniKube 的例子来说明如何深入更复杂的 Kubernetes 结构的内部——比如存储。因此，不幸的是，许多人第一次调试 StorageClass 或 CSI 问题的经历都发生在一个实际的生产集群中。

在深入研究了 MiniKube 存储模型的各个方面之后，我意识到我们中的许多人每天都在使用持久卷，却从来没有机会真正了解 Kubernetes 存储是如何在一个适合玩、黑客和学习的简单环境中实现的。因此，我想我应该写一篇关于我最喜欢的动态存储模型的内部结构的博文:MiniKube(是的，MiniKube)！

## 欢迎来到 MiniKube 大学

当人们听到我说“MiniKube”时，他们说的第一句话通常是“哦，那不是真的，我需要一个真正的集群。”但是“真正的”集群经常会误导您分布式系统问题和与 Kubernetes 内部无关的特定于供应商的功能。使用 MiniKube，我们可以快速迭代 kubelet 配置、存储配置，并实际了解其整体，一个完整的端到端动态预配置系统。

所以，如果你想深入了解 Kubernetes 供应是如何工作的，请继续阅读…无论你有多少技术才能，MiniKube 总能带你去学校。

### 为什么用于存储建模的沙盒很重要

在 Kubernetes 部署的所有旋钮和滑块中，存储仍然是 Kubernetes 集群的唯一核心方面，对于该集群，没有任何 80/20 解决方案能够开箱即用地处理大多数工作负载(我稍后将证明这一点)。因此，重要的存储策略最终将成为集群的重要组成部分。

在这篇文章中，我们将采用一些容易理解的东西，MiniKube，并将其作为一个跳板，在一个云和平台中立的环境中深入了解 Kubernetes 存储模型的内部。在下一期文章中，我们将继续扩展这个模型来实现 CSI(容器存储接口)特性，这些特性现在已经在 Kubernetes 1.13 中发布。

## 让我们开始吧:

理解动态预配置含义的最佳方式是观察它是如何工作的*而不要有任何流行词汇在周围浮动。没有时髦的分布式文件系统项目，没有 GCP 或 EBS 卷类型，只有*纯*动态预配置。*

我们将使用本地安装的 MiniKube 来设置动态配置—不需要公共云或 CSI。

除了作为一个学习 Kubernetes 内部如何工作的好环境，MiniKube(with*–VM-driver = none*)还可以用于直接在裸机上测试 Kubernetes 存储的性能。这些将云基础设施从容器中分离出来的独立实验可以告诉您很多关于性能瓶颈的信息。

在沙盒 Kubernetes 集群中测试您的存储模型是一种强大的方法，可以确定您是否在基线上获得了正确的存储模型。大型 JVM 应用程序可能会由于[传统上大量的磁盘或 GC 相关的 I/O](https://engineering.linkedin.com/blog/2016/02/eliminating-large-jvm-gc-pauses-caused-by-background-io-traffic) 而遭受长时间的启动，这在分布式文件系统中可能是致命的。类似地，数据库中高水平的 I/O——使用任何一种基于磁盘的行锁定或顺序扫描的密集型应用程序都会使[应用程序崩溃](https://wiki.postgresql.org/wiki/Shared_Storage)。最糟糕的是，一些文件系统根本不支持[持久容器](https://bugzilla.redhat.com/show_bug.cgi?id=1512691)所需的文件操作语义。

好了，让我们开始黑这东西吧！

### 一步一步:在本地模式下可黑客攻击的 MiniKube

有两种方法可以在没有设备的情况下以可重现的方式快速运行 Kubernetes:

*   hack/local-up-cluster.sh，
*   minikube–虚拟机驱动程序=无

在本教程中，我们将讨论后者，因为 VirtualBox 虚拟机可能无法用于存储测试(即，您的数据中心或云中的真实存储阵列可能无法安装在您的笔记本电脑上)。*注:*如果没有真正的 Linux 盒子，可以使用 vm-driver=virtualbox。

请注意，您无法在所有平台上完整地进行这些卷和动态预配置实验。MiniKube 的独特之处在于，它是唯一一个可以在任何硬件上几乎立即启动的 Kubernetes 发行版，具有完全透明和可访问的模型，可以访问所有组件并实时修改它们。云提供商通常只保证 Kubernetes API 可用，并且会混淆主组件的内部。

例如，在谷歌 Kubernetes 引擎(GKE)上，你甚至无法直接访问你的主人，甚至无法查看其相应的 etcd 配置。虽然您可以在 GKE 修改 kubelet 选项并重新启动它们，但是这些修改可能不受支持，并且不能在运行主节点的同一节点上完成(因为主节点不可访问)。因此，尽管任何 kube 环境都允许您探索存储类的某些方面，但您无法看到它们是如何在所有平台上被修改和实现的。

## 第 1 部分:设置可黑客攻击的 MiniKube 环境

注意:如果您没有实际测试需要分配大量 CPU 或内存的实际应用程序，可以跳到第 2 部分。

### 关于入侵 Kubernetes 主组件部署的快速说明:

您可以轻松修改控制器管理器记录控制平面事件的内部方式，这在研究内部通用卷绑定、连接和分离逻辑时非常有用。这些事件由典型的动态卷供应器响应，它将注意到已经创建了 PVC，并通过最终基于存储类的配置方式在幕后创建 PV 来响应这些事件。如果您想深入了解这些内部细节(注意，您不需要这样做，但这样做特别有趣，因为“航天飞机”风格的[登录卷控制器](https://github.com/kubernetes/kubernetes/blob/master/pkg/controller/volume/persistentvolume/pv_controller.go))您可以打开/etc/kubernetes/manifests/kube-controller-manager . YAML 并修改其启动设置，特别是通过向 KCM 容器添加“-v=5”选项。

### 黑客 MiniKube 核心服务:静态吊舱。

如何破解 MiniKube 中的主组件的最佳示例可以在控制器管理器的 ku bealet 清单中找到，它由 ku bealet 持续监控*，如果它发生变化，与之相关的静态 pod 会*重新启动。*它由 kubelet 而不是复制控制器实现的原因是，复制控制器假定控制器管理器已经在运行，而静态 pod 却不是这样。类似地，api 服务器和其他“初始”组件也有静态 pod。你可以在/etc/kubernetes/manifest 下看到它们。具体来说，我们将研究一个有助于研究存储如何工作的修改，这是本文的主题:)。* 

```
vi  /etc/kubernetes/manifests/kube-controller-manager.yaml

```

现在，在 kube-controller-manager (KCM)中，在记录部分的末尾进行修改:

```
   -  command:
-  kube-controller-manager
-  --address=127.0.0.1
-  --authentication-kubeconfig=/etc/kubernetes/controller-manager.conf
-  --authorization-kubeconfig=/etc/kubernetes/controller-manager.conf
-  --client-ca-file=/var/lib/minikube/certs/ca.crt
-  --cluster-signing-cert-file=/var/lib/minikube/certs/ca.crt
-  --cluster-signing-key-file=/var/lib/minikube/certs/ca.key
-  --controllers=*,bootstrapsigner,tokencleaner
-  --kubeconfig=/etc/kubernetes/controller-manager.conf
-  --leader-elect=<strong>true</strong>
-  --requestheader-client-ca-file=/var/lib/minikube/certs/front-proxy-ca.crt
-  --root-ca-file=/var/lib/minikube/certs/ca.crt
-  --service-account-private-key-file=/var/lib/minikube/certs/sa.key
-  --use-service-account-credentials=true# Add verbosity here …
-  <strong>-v=5</strong>

```

如果您想了解 Kubernetes 如何在 Kubernetes 的内部*工作(即从 PVC 如何绑定和解除绑定的角度，以及卷控制器本身如何管理触发您的存储供应器的通信事件的角度)，您只需这样做。)*

现在，回到这篇文章的出发点:揭示集群中存储模型的内部细节。

### 破解 MiniKube Docker 或 CRI 版本，让它在你的云中运行。

以本地模式在 VM 之外运行 MiniKube，在运行其他东西的同一硬件上，是 A/B 测试 Kubernetes 发行版的行为与已知常数的最佳方式。此外，如果您的工作负载使用 GPU、SSD 或其他对性能敏感的设备，而这些设备不能直接转换到您的虚拟机管理程序中，那么这可能是必要的，您希望测试、修改和入侵虚拟机管理程序，而不需要修改由某种自动化控制的重量级 K8s 集群(您通常无法访问)。

在这种情况下，有一个警告:**你要确保你安装了一个稳定的 Docker 版本**。MiniKube 对 Docker 版本要求严格，在任何情况下都不会接受最新版本。所以你需要确保你有正确的 Docker 版本(这可能需要在你的 Linux 机器上卸载默认的 Docker 版本)。对于 MiniKube 0.33，docker-ce-17 工作得很好，所以下面是如何做到这一点。

```
sudo yum remove docker docker-common docker-selinux docker-engine
sudo yum install autoconf
sudo yum remove containerd.io
sudo yum remove  -y  docker-ce-cli
sudo yum install  --setopt=obsoletes=0   docker-ce-17.03.2.ce-1.el7.centos.x86_64

```

完成后，运行 **systemctl start docker** 来启动并运行您的稳定 docker 守护进程。

假设你已经从某个地方安装了 MiniKube(很简单，只需从 github 上的发布页面获取)，你可以运行**MiniKube start—VM-driver = none。**

## 第 2 部分:尝试动态预配置模型

### 创建应用程序

此时，您已经运行了 MiniKube，并且它已经为您设置了存储类。我们一会儿就知道怎么做了。

现在，您可以创建一个 pod，任何依赖于某种存储的 pod。由于每个人总是使用 NGINX 进行这种类型的烟雾测试，我们将做同样的事情——结合完全通用的 PVC。真正重要的是 pod 中的卷挂载引用了名为“ **my-pv-claim，**”的 PVC，就像这样:

```
kind:  PersistentVolumeClaim
apiVersion:  v1
metadata:
name:  my-pv-claim
spec:
accessModes:
-  ReadWriteOnce
resources:
requests:
storage:  1Gi
---
kind:  Pod
apiVersion:  v1
metadata:
name:  task-pv-pod
spec:
volumes:
-  name:  my-pv-storage
persistentVolumeClaim:
claimName:  my-pv-claim
containers:
-  name:  task-pv-container
image:  nginx
ports:
-  containerPort:  80
name:  "http-server"
volumeMounts:
-  mountPath:  "/usr/share/nginx/html"
name:  my-pv-storage

```

现在您已经有了一个在单节点集群中运行的 pod。因为您从未设置过任何类型的存储卷供应，所以您的第一个问题是“这个 pod 是如何神奇地实现其 PVC 的？”

答案是: **StorageClasses** 。存储类是动态资源调配的核心。通过声明性地请求存储类型，您的动态供应器可以决定如何在运行时实现该存储。这使得你的应用可以在 MiniKube 上运行，就像在其他云或容器管理平台上一样(比如 Platform9 自己的[管理的 Kubernetes](https://platform9.com/managed-kubernetes/) )。)

但是，我相信你已经知道了。您可能不知道的是，MiniKube 可以开箱即用地使用动态预配置。它的工作方式实际上是通过定义一个置备程序。

### 现在，让我们来看看 PVC 是如何实现的

首先，在你的名称空间中运行 kubectl get PVC，确保一切正常:

```
➜   csi-hacking kubectl get pvc
NAME          STATUS    VOLUME                                      CAPACITY    ACCESS MODES    STORAGECLASS    AGE
my-pv-claim    Bound     pvc-ada22e4b-2351-11e9-b86b-fa163ef9a3a4    1Gi         RWO             standard        45h

```

我们可以看到，我们声称的 PVC 确实达到了我们要求的 1Gi 的容量，其访问模式是读写一次。然而，有趣的是，它的 STORAGECLASS 被设置了——但是我们没有设置存储类，不是吗？

你说得对，我们没有。

这越来越奇怪了。我们的 PVC 规范(不是它的状态)被修改了，实际上是请求“标准”存储类。这是由运行在我们集群中的 AdmissionController 完成的，它拦截我们对 Kubernetes API 服务器的请求并修改传入的对象。如果我们提供了一个存储类，接纳控制器就不会注入这个。

但这里仍有未解之谜。除了没有在我们的 Nginx pod 上要求一个特定的存储类之外，我们也从来没有创建一个存储类！这是怎么回事？

```
➜   csi-exp kubectl get sc
<strong>NAME</strong>                  PROVISIONER                 AGE
standard  (<strong>default</strong>)    k8s.io/minikube-hostpath    2d&lt;

```

### 黑掉存储类

原来当你启动 MiniKube 本身的时候，*一个 StorageClass 就为你创建了。*您可以轻松地将这个存储类*修改为 Kubernetes 对象*，而不是文件。原因是*它是在你的 MiniKube 安装上为你*引导的。所以你可以阅读它的内容，但是你只能在 Kubernetes 内部修改它，使用“kubectl edit sc standard”

例如，我们可以完全禁用默认存储类，如下所示:运行编辑命令后，将 storageclass.beta.kubernetes.io/is-default-class:“true”注释值修改为值“false”

```
➜   csi-exp kubectl get sc
NAME        PROVISIONER                 AGE
standard    k8s.io/minikube-hostpath    22d➜   csi-hacking cat  /etc/kubernetes/addons/storageclass.yaml
kind:  StorageClass
apiVersion:  storage.k8s.io/v1
metadata:
namespace:  kube-system
name:  standard
annotations:
storageclass.beta.kubernetes.io/is-default-class:"true"
labels:
addonmanager.kubernetes.io/mode:  Reconcileprovisioner:  k8s.io/minikube-hostpath

```

所以存储类并不神奇。但是你已经知道了。现在，撤消您的更改，使您的集群再次正常运行。

让我们看看存储类的内部细节:

```
➜   csi-hacking kubectl get sc
NAME                  PROVISIONER                 AGE
standard  (default)    k8s.io/minikube-hostpath    21d
➜   csi-hacking kubectl get sc  -o  yaml
apiVersion:  v1
items:
-  apiVersion:  storage.k8s.io/v1
kind:  StorageClass
metadata:
annotations:
kubectl.kubernetes.io/last-applied-configuration:  |
{"apiVersion":"storage.k8s.io/v1","kind":"StorageClass","metadata":{"annotations":{"storageclass.beta.kubernetes.io/is-default-class":"true"},"labels":{"addonmanager.kubernetes.io/mode":"Reconcile"},"name":"standard","namespace":""},"provisioner":"k8s.io/minikube-hostpath"}
storageclass.beta.kubernetes.io/is-default-class:  "true"
creationTimestamp:  "2019-01-08T03:56:44Z"
labels:
addonmanager.kubernetes.io/mode:  Reconcile
name:  standard
resourceVersion:  "424"
selfLink:  /apis/storage.k8s.io/v1/storageclasses/standard
uid:  69f175d0-12f9-11e9-a834-fa163ef9a3a4
provisioner:  k8s.io/minikube-hostpath
reclaimPolicy:  Delete
volumeBindingMode:  Immediate
kind:  List
metadata:
resourceVersion:  ""
selfLink:  ""

```

这里需要注意的是注释中有一个置备者:k8s.io/minikube-hostpath.，那到底是什么？查看 MiniKube 代码库中现有的 Provisioner 控制器，可以看到这个键映射到它的常量 provisionerName 键:

```
<strong>const</strong>  provisionerName  =  "k8s.io/minikube-hostpath"

```

同时，“volumeβkubernetes . io/storage-provisioner”是一个标准注释，任何 Kubernetes 观察者都可以下拉它。检查了 provisioner 的值后，如果您确实是“主机路径”资源调配者，那么从逻辑上讲，您将继续为该声明调配卷。

当然，由于截取和创建卷很容易，现在是做出“您不应该信任在您的集群上运行的任何卷控制器”这一强制性声明的好时机，但这是不言而喻的。因为卷控制器可以拦截任何和所有的存储请求，并安装恶意的东西到你的豆荚里。请注意,“provisioner”现在已经退出测试，并且也是 StorageClass 对象中的一级字段。

## 第 3 部分:现在，让我们深入研究 minikube-hostpath 的内部工作原理

现在您已经了解了置备程序的工作原理，让我们看看如何构建我们自己的动态置备程序。这实际上并不难，而且你可以借用一些实用工具。同样，这里需要注意的关键点是，您不需要编写自定义卷，甚至不需要构建 CSI 驱动程序来创建自己的动态置备程序。

### 外部存储:CSI 的开端

Kubernetes 社区目前正在从“外部存储”存储库(依赖于编译到 Kubernetes 中的存储驱动程序)过渡到两个分离的存储库，这将允许单个存储实现(基于 CSI)管理注册存储驱动程序和实现存储特定逻辑。在那一点上([这个库大部分将被弃用](https://github.com/kubernetes-incubator/external-storage/))，它有一些[通用功能将存在](https://github.com/kubernetes-sigs/sig-storage-lib-external-provisioner)，而主要的外部存储工作发生在[接口级](https://github.com/kubernetes-csi/external-provisioner)。在本系列的下一篇文章中，我们将深入探讨基于 CSI 的外部供应器如何工作的细节。

目前，理解外部存储如何工作仍然很重要，因为您将使用的大多数 Kubernetes 集群可能正在某个地方实现某种树内存储，并且这种情况至少会持续一年(或者永远——请记住 hostPath 和 emptyDir 本身也是树内驱动程序，并将在很长一段时间内成为 Kubernetes 核心的一部分)。

最终，作为 minikube 动态供应器的一部分运行的 minikube-hostpath 程序是一个模型，您可以使用它来管理您自己的集群中的存储，它也是 CSI PV 实现将遵循的同一模型。要了解如何在后 CSI 环境中实现相同的插件，您可以查看外部供应器存储库中的进度，该存储库将 hostPath 实现为 CSI 驱动程序(而不是自定义控制器)。

从上面 storage_provisioner.go 实现的简单性中得到的启示是，实现动态存储可以非常简单，并且您不一定需要 Kubernetes 或 CSI 或任何其他方面的博士学位。只需从 watch 中抓取一个字段，然后，如果您喜欢 provisioner 值，则提供一个相应的卷——如果您正在使用上面的外部存储包装库，则返回 volume 对象(就像 MiniKube 一样),或者进行自己的实现。****

## 第 4 部分:动态存储+ CSI:它们如何影响您的开发工作流

现在，您已经了解了动态存储，让我们深入了解一下我们在上面讨论的动态供应器与动态存储平面的区别:CSI。

这两个实体为您提供了一个 Kubernete 集群的四种不同**类型**存储模型的矩阵。通常，出于安全考虑，并且为了能够将您的应用程序商品化，您会想要知道您的应用程序的默认存储模型是什么(理想情况下，它将是动态的，至少在配置级别是如此)。最终，您的存储开发工作流将取决于您选择四种存储模式中的哪一种(一般来说，CSI provisioned+dynamic 是两者中最好的)。

1.  **提供 CSI，非动态**
2.  **CSI 预配，动态**
3.  **非 CSI 供应(在树中)，动态**
4.  **非 CSI 供应(在树中)，非动态**

如您所见，有动态资源调配，也有 CSI 卷资源调配。支持这两者的 Kubernetes 集群在用户端和存储端都是动态的，可以处理任何事情。但是，您可以在没有动态供应器的情况下实现 CSI，反之亦然。

**CSI provisioned，非动态** :
示例:您编写一个 golang 或终端程序，它直接调用 CSI machinery，而不使用任何动态预配置。在这种情况下，您可以使用类似于 [GoCSI](https://github.com/rexray/gocsi) 的东西作为客户端，与您正在运行的 CSI 服务实现进行通信。

**CSI provisioned，dynamic** :
示例:当您为 Kubernetes 现有树内文件系统之外的供应商创建 PVC 时，MiniKube 为您动态创建的文件系统。在这种情况下，你会在某个时候使用以下 YAML 对象:作为存储类的 CSI 驱动程序，以及一个 PersistentVolumeClaim，而**对 CSI 驱动程序一无所知。当您创建 PVC 时，它最终将由 StorageClass 来完成，storage class 最终依赖 CSI provisioner 来创建相应的卷。** 

```
kind:  PersistentVolumeClaim apiVersion:  v1 metadata:  name:  task-pv-claim spec:  accessModes:  -  ReadWriteOnce resources:  requests:  storage:  3Gi  ---  apiVersion:  storage.k8s.io/v1 kind:  StorageClass metadata:  name:  csi-my-vendor annotations:  storageclass.kubernetes.io/is-default-class:  "true"  provisioner:  csi-my-vendor

```

**非 CSI 配置(在树中)，动态**:如前所述，您可以在没有 CSI 的情况下拥有完全动态的存储:您只是受限于 Kubernetes 支持的文件系统类型或 flexVolume 实现。使用绑定的 persistentVolumeClaim(就像我们对 MiniKube 所做的那样)，或者甚至实现类似 emptyDir 的东西，演示了如何在有(或没有)PVC 的情况下动态(即时)供应卷。

```
spec:
containers:
-  image:  my-app:1.0
name:  testing
volumeMounts:
-  mountPath:  /data-shared-with-another-container
name:  mounted-scratch
volumes:
-  name:  mounted-scratch
emptyDir:  {}

```

**非 CSI 配置(在树中)，非动态**:您在数据中心手动创建的 NFS 共享，您已将其硬编码为持久卷。然后，创建一个指向该卷的 PVC。在这种情况下，pod 本身声明了卷(而不是指向 PVC 抽象)。例如，在您的 pod 定义之外，您将有一个这样的代码片段，请注意，我们在卷定义内定义了 NFS，专门创建了一个没有任何间接性的卷。

```
volumes:
-  name:  nfs-volume
nfs:
server:  192.100.200.212
path:  /data

```

现在，您已经了解了动态预配置 CSI 框架之间的区别，并且希望知道在您的生产环境中是需要一个还是两个都需要。

## 总结:Kubernetes 储物的四个象限

总之，如果您正在为您的云原生环境开发存储解决方案，您会有四个象限:CSI 从供应商的角度使您的存储平面具有声明性，动态预配置从用户的角度使存储具有声明性。CSI 和动态配置意味着开发人员不需要配置存储，Kubernetes 也不需要了解存储。

当然，理想的情况是既有基于 CSI 的卷，又有动态预配置。

从半空的角度来看，如果您没有动态存储，您的开发人员必须知道他们应用程序的持久卷类型，并在制定 pod 规范时明确声明和引用它。如果您没有 CSI 实现，这通常意味着您必须在 Kubernetes 节点中定制 yum/apt 安装存储驱动程序，以使存储库完全按照 Kubernetes 树希望的方式工作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*