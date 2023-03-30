# Kubernetes 1.22 的“少即是多”

> 原文：<https://thenewstack.io/less-is-more-with-kubernetes-1-22/>

Kubernetes 版本 1.22 已经[发布](https://kubernetes.io/blog/2021/08/04/kubernetes-1-22-release-announcement/)，随着新功能的推出，一些旧功能已经被放弃了——不仅仅是被否决了……而是被放弃了。

这个新版本有 56 个增强功能(Kubernetes 1.1 中有 50 个，1.20 中有 43 个)。在这 56 个增强功能中，有 13 个已经升级到稳定，24 个功能有了重要的改进，16 个功能是全新的。

让我们明确一点，这些不是反对，而是直接删除。因此，从版本 1.22 开始，将删除以下测试版(以支持更新、稳定的版本):

*   进入
*   IngressClass
*   租赁
*   养蜂服务
*   自定义资源定义
*   验证 WebhookConfiguration
*   变异 WebhookConfiguration
*   证书签名请求
*   令牌审查
*   主题访问检查

入口特别重要，因为这是更安全的方式，使得从 Kubernetes 集群外部访问容器成为可能。从 1.22 开始，您需要确保迁移并使用 networking.k8s.io/v1 入口 API(从 1.19 开始可用)。同样，您会想知道相关的 API IngressCLass，它是作为 Ingress 的补充而设计的。

如何在 v1 中使用 Ingress 的示例如下:

```
apiVersion:  networking.k8s.io/v1
kind:  Ingress
metadata:
  name:  example-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target:  /$1
spec:
  rules:
    -  host:  hello-world.info
      http:
        paths:
          -  path:  /
            pathType:  Prefix
            backend:
              service:
                name:  web
                port:
                  number:  8080

```

有关 Kubernetes 删除了什么以及如何找到替代功能的更多信息，请务必通读[弃用指南](https://kubernetes.io/docs/reference/using-api/deprecation-guide/#v1-22)。

## 新功能

现在，让我们来看看新版本中的一些更重要的增强。

## 服务器端应用

服务器端应用使用户和控制器更容易通过声明性配置来管理资源。这一特性最终得到了广泛应用，它是一个新的字段所有权和对象合并算法。这个特性的作用是将逻辑从`kubectl apply`命令转移到 apiserver 中。服务器端应用还跟踪用户的字段管理(而不是用户的最后应用状态。字段管理存储在对象的元数据中，使用 managedFields 字段，就像这样:

```
apiVersion:  v1
kind:  ConfigMap
metadata:
  name:  test-cm
  namespace:  default
  labels:
     test-label:  test
  managedFields:
  -  manager:  kubectl
     operation:  Apply
     apiVersion:  v1
     time:  "2010-10-10T0:00:00Z"
     fieldsType:  FieldsV1
     fieldsV1:
       f:metadata:
         f:labels:
           f:test-label:  {}
       f:data:
         f:key:  {}
data:
  key:  some value

```

## 外部凭据提供程序

外部凭据提供程序提供了一种获取外部客户端身份验证凭据(如不记名令牌或 TLS 客户端证书)的方式。这项功能从 Kubernetes 1.11 开始就处于测试阶段，最终升级到稳定版。这个特性包括改进了对插件的支持，这些插件增加了交互式登录流程和一些错误修复。要开始使用这个特性，请访问 GitHub 上的 [sample-exec-plugin 代码了解更多信息。](https://github.com/ankeesler/sample-exec-plugin)

## Etcd 现在的版本是 3.5.0

Kubernetes 后端存储机制 etcd 现在的版本是 3.5.0，其中包括许多安全性、性能和监控方面的改进。添加了结构化日志记录和日志循环。对于更昂贵的请求，增加了增强的详细跟踪，这提供了一个非常有用的信号来帮助开发人员了解跨多个 etcd 服务器组件的请求的生命周期。

## Cgroups V2 API

Kubernetes 最初使用的是 cgroups API 的版本 1，这意味着给定 Pod 的服务质量(QoS)类只适用于 CPU 资源。Kubernetes v1.22 现在包括一个 alpha 版本的 [cgroups v2 API](https://thenewstack.io/linux-cgroups-v2-brings-rootless-containers-superior-memory-management/) ，它控制内存分配和隔离。这将大大提高工作负载和节点可用性，并提高容器生命周期的可预测性。

## 节点系统交换支持

如果您曾经部署过 Kubernetes 集群，那么您知道必须做的第一件事就是禁用 swap。为此，您可以使用以下命令打开/etc/fstab 文件:

`sudo nano /etc/fstab`

并注释掉以下列开头的行:

`/swap.img`

完成后，使用以下命令禁用当前正在运行的实例:

`sudo swapoff -a`

从 Kubernetes 1.22 开始，增加了对 alpha 的支持，这样您就可以在启用交换内存的情况下运行节点。

## 无根模式容器

每个人都知道作为非根用户运行容器是安全的必须。这是显而易见的。但是在 1.22 版本中，开发人员将这一思想提升到了一个新的高度，允许管理员以非根用户的身份运行整个 Kubernetes 堆栈。最终，这将对保护 Kubernetes 大有帮助。

## 功能升级到稳定和其他更新

Kubernetes 的其他功能已经升级到“稳定”状态，这意味着它们可以随时使用，包括:

*   绑定的服务帐户令牌卷
*   CSI 服务帐户令牌
*   Windows 对 CSI 插件的支持
*   不推荐使用的 API 的警告机制
*   预算驱逐

还有其他一些杂项功能更新，包括:

*   一个新的 alpha 特性，PodSecurity admission，它取代了 PodSecurityPolicy。
*   内存管理器已经升级到测试版。
*   alpha 中增加了一个新的 API 服务器跟踪特性。
*   添加了新的 v1beta3 版本的 kubeadm 配置格式。
*   持久卷的通用数据填充器在 alpha 中。
*   Kubernetes 控制平面现在将总是使用 CronJobs v2 控制器。

要获得所有新增内容、增强功能、错误修复和删除的完整列表，请查看官方 Kubernetes 1.22 发行说明。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>