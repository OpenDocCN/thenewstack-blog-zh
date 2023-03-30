# Kubernetes 1.23:双栈 IPv4/IPv6、CronJobs、临时卷

> 原文：<https://thenewstack.io/kubernetes-1-23-dual-stack-ipv4-ipv6-cronjobs-ephemeral-volumes/>

在云原生开发的世界里，你眨眼的那一秒，你已经错过了一些东西。事情就是这样快速发展的。以至于，似乎就在昨天 Kubernetes 1.22 才出了 1.22(实际上是在[8 月 22 日](https://kubernetes.io/blog/2021/08/04/kubernetes-1-22-release-announcement/))。

就像他们说的，那是过去，现在是现在。现在是关于 Kubernetes 1.23 GA(根据[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)今天到期)这个新版本充满了可跳舞的曲调，有超过 45 个增强(其中 11 个正在升级到稳定，15 个已经改进，19 个是全新的)。虽然这些新功能可能不会都是十大热门，但其中一些可能对 Kubernetes 的工作人员非常有帮助。然而，真正的亮点属于 1.23 中已经升级到 GA(稳定性)的特性，所以它们已经准备好投入生产了。

让我们先来看看已经升级到稳定的特性(因为这些是您想要立即开始使用的特性)。然后，我们将看看所有其他站在阴影中的进步，希望能被注意到。

打开灯，蹦迪，是时候开派对了。

## 逐渐稳定

坐在毕业列表的顶部，您会发现四个非常令人兴奋的功能:IPv4/IPv6 双栈支持、CronJobs、临时卷和 HPA API。让我们来看看每一个。

## IPv4/IPv6 双栈支持

有了 IPv6/IPv6 双栈支持，Kubernetes 现在可以在集群中本机支持双栈模式。这意味着您可以将 IPv4 和 IPv6 地址分配给任何给定的 pod 或服务。这是通过. spec.ipFamilyPolicy 字段配置的，该字段可以设置为以下值之一:

*   单栈
*   首选堆栈
*   RequireDualStack

要使用双栈支持，您需要将`.spec.ipFamilyPolicy`设置为`PreferDualStack`或`RequireDualStack`。该功能在 Kubernetes 中默认启用，并且还包括通过 IPv4 和 IPv6 地址的 pod 脱离集群出口路由。

## 克朗乔布斯

CronJobs 特性使得在 Kubernetes 集群中运行定期任务成为可能。Kubernetes CronJobs 与 Linux cron 系统非常相似。CronJobs 从 Kubernetes 1.4 开始就已经存在，自从在迭代 1.5 中达到 CRI 支持以来，已经在生产中被广泛接受。

在 YAML 文件中，CronJob 被定义为:

`kind: CronJob`

每 10 分钟打印一次“Hello Newstack”的示例 CronJob 清单可能如下所示:

```
apiVersion:  batch/v1
kind:  CronJob
metadata:
  name:  hello
spec:
  schedule:  "*/10 * * * *"
  jobTemplate:
     spec:
       template:
         spec:
           containers:
           -  name:  hello
             image:  busybox
             imagePullPolicy:  IfNotPresent
             command:
             -  /bin/sh
             -  -c
             -  date;  echo Hello Newstack
           restartPolicy:  OnFailure

```

对于那些不知道 cron 语法的人来说，是这样的:

如果你不确定如何创建一个 cronjob，我强烈推荐从 [Crontab Guru](https://crontab.guru/) 开始，它允许你将值插入到一个 cronjob 中，并确切地看到它们会生成什么。

## 短暂的卷

临时卷自 Kubernetes 1.19 以来就存在了，它允许您为特定的 pod 创建卷，然后在 pod 终止时删除这些卷。换句话说，这些是临时卷。

Kubernetes 支持四种类型的临时卷，它们是:

*   empty dir—Pod 启动时可用的空卷，它使用 kubelet 基本目录或 RAM 中的存储。
*   configMap，downwardAPI，secret —将不同种类的 Kubernetes 数据注入指定的 Pod。
*   CSI 临时卷—类似于其他类型，但由特殊的 CSI 驱动程序提供。
*   通用临时卷—由所有存储驱动程序(支持持久存储)提供

使用临时存储的样本清单可能如下所示:

```
kind:  Pod
apiVersion:  v1
metadata:
  name:  sample-storage-app
spec:
  containers:
     -  name:  storage-frontend
       image:  busybox
       volumeMounts:
       -  mountPath:  "/storage"
         name:  sample-storage-app-vol
       command:  [  "sleep",  "1000000"  ]
  volumes:
     -  name:  sample-storage-app-vol
       csi:
         driver:  inline.storage.kubernetes.io
         volumeAttributes:

```

## HPA API v2

水平 Pod 自动缩放 API 对于 Kubernetes 舞来说并不陌生。其实最早是 2016 年推出的。此功能负责自动扩展复制控制器、部署、副本集或有状态集中的 pod 数量。缩放基于以下类型的指标:

*   资源使用—当 Pod 超过内存或 CPU 使用的阈值时。这可以用原始值或百分比来表示。
*   自定义指标—这是基于 Kubernetes 报告的指标(即每秒的客户端请求率)。
*   外部指标—这基于外部应用程序或服务提供的指标。

自动应答器使用控制回路运行，周期由`--horizontal-pod-autoscaler-sync-period`标志控制。默认值为 15 秒。在控制循环期间，控制器根据在`HorizontalPodAutoscaler`定义中配置的指标查询 Pod 的资源利用率。

## 折旧和 Beta 毕业

Kubernetes 1.23 也有三个值得注意的缺点。其中包括:

*   HPA v2beta2 API
*   灵活卷
*   klog 特定标志

一些功能也升级到了测试版，包括:

*   PodSecurity —它取代了 PodSecurityPolicy 准入控制器。
*   结构化日志记录——来自 kubelet 和 kube-scheduler 的大多数日志消息都已被转换，建议用户尝试 JSON 输出。

## Alpha 中的新功能

Kubernetes 1.23 还包括一些现在在 alpha 中的新特性。其中包括:

*   CRD 的表达式语言验证—如果启用了`CustomResourceValidationExpressions` ，自定义资源将通过使用通用表达式语言的规则进行验证。
*   服务器端字段验证—如果`ServerSideFieldValidation`启用，当在请求中检测到未知或重复字段时，用户将收到来自服务器的警告。
*   OpenAPI v3 — `OpenAPIV`启用后，用户将能够请求所有 Kubernetes 类型的 OpenAPI v3 规范。

有关新版本的更多信息，请务必查看[完整版本说明](https://www.kubernetes.dev/resources/release/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>