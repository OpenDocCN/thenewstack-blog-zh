# 如何锁定和保护 Kubernetes 持久卷

> 原文：<https://thenewstack.io/how-to-lockdown-and-secure-kubernetes-persistent-volumes/>

[NetApp](https://www.netapp.com/us/solutions/devops/index.aspx) 赞助了这篇文章。

 [安德鲁·苏利文

Andrew 在信息技术行业工作了 10 多年，拥有丰富的数据库开发历史、开发运维经验和虚拟化经验。作为 NetApp 的技术营销工程师，他目前专注于存储和虚拟化自动化，并致力于简化日常工作流程。](https://www.linkedin.com/in/andrew-sullivan-a77b7173/) 

确保只有授权的应用程序和用户才能访问由 [NetApp Trident](https://netapp.io/2016/12/23/introducing-trident-dynamic-persistent-volume-provisioner-kubernetes/) 调配的 Kubernetes 卷，这显然是一个最重要的问题，也是我们倾向于与任何计划部署的人进行的第一次深入对话之一。

好消息是 Kubernetes 和 Trident 共同提供高度安全的持久性，前提是您遵循以下准则:

1.  通过创建定义信任边界的名称空间来隔离对 Kubernetes 中卷的访问。
2.  通过创建适当的 Kubernetes pod 安全策略，防止 pod 访问工作节点上的卷装载。
3.  通过 Trident 指定适用于每个后端的安全策略，将卷访问权限限制在适当的工作节点。

我们经常被问到安全问题，以下是一些最常见的问题。然而，如果你有其他人，请通过这个帖子的评论、 [Slack](https://netapp.io/slack) 或我们其他的[沟通渠道联系我们。](https://github.com/netapp/trident/issues)

### 能否将对永久卷的访问限制在一个 pod/container 中？

[Trident 管理的持久卷](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistent-volumes) (PVs)在应用程序提交[持久卷声明](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistentvolumeclaims) (PVC)时创建。这将触发 Trident 在存储系统上创建卷。然而，PVs 是全局对象，并且 PVC 属于单个名称空间。只有管理员或 Trident(由于其使用的服务帐户被授予了权限)能够管理 PVs。

为什么这很重要？名称空间是 Kubernetes 中大多数资源的逻辑边界。它们是一个安全域，假设命名空间中的所有内容都可以访问其中的所有内容。但是，用户或应用程序不能使用不同命名空间中的资源。例如，一个名称空间中的 pod 不能使用另一个名称空间中的 PVC，即使用户可以访问这两个名称空间。

此外，已经绑定到一个 PVC 的 PV 不能绑定到另一个 PVC，无论其命名空间如何。这意味着，即使用户试图创建一个声明来自不同名称空间的现有 PV 的 PVC，也将失败。使用 Trident 时，默认情况下 PV 和 PVC 同时被销毁。可以改变这种行为，以便保留 PV，但是曾经绑定到 PVC 然后解除绑定的 PV 将无法再次绑定。

所以，回答这个问题:不，一个单独的 PV/PVC 不能被限制在一个单独的 pod 中。然而，与其他资源一样，PVC 也受限于单个名称空间。

### pod 是否可以看到装载到主机上的其他卷，和/或看到阵列中提供了什么存储？

如果 pod 中的用户针对为 Kubernetes 集群提供卷的存储系统执行“ *showmount -e* 命令或[iSCSI 等效命令](https://library.netapp.com/ecmdocs/ECMP1217221/html/GUID-45DBD708-6649-4DEB-A6F5-D3F6A5B4454A.html)，他们就能够看到导出列表。但是，如上所述，他们不能从 pod 内部访问另一个卷。

为了缓解这种情况，存储系统卷访问控制策略，无论是[I group](http://docs.netapp.com/ontap-9/index.jsp?topic=%2Fcom.netapp.doc.onc-sm-help-960%2FGUID-876222DF-D8E8-4193-9564-EDC3AD19E2E2.html&resultof=%22%69%47%72%6f%75%70%73%22%20%22%69%67%72%6f%75%70%22%20)、[卷访问组](https://library.netapp.com/ecm/ecm_download_file/ECMLP2842189)还是[导出策略](http://docs.netapp.com/ontap-9/index.jsp?topic=%2Fcom.netapp.doc.cdot-famg-nfs%2FGUID-9A2B6C3E-C86A-4125-B778-6072A3A19657.html)，都应该仅限于 Kubernetes 群集中的节点。这可以防止从 Kubernetes 集群之外的主机装载卷并绕过现有的安全控制。此外，禁用 SVM 的“showmount”功能。

### 同一节点上但来自不同命名空间的 pod 是否可以访问已装入的卷？

不，有一个例外:特权容器。Kubernetes 节点上的 pod/container 中的流程不能查看系统上的资源，除非它们已经被分配了资源。这也是所有容器使用的核心 Linux 名称空间功能。用户或应用程序不会通过发出 fdisk 或 mount 命令对其他卷造成任何威胁。

### 创建具有特定 UID 和 GID 的卷有助于保护数据吗？

不，它真的不会为基于 Kubernetes 的应用程序提供额外的保护。这里假设该卷指定了 userID (uid)和 groupID(gid ), Unix 权限设置为类似“700”的值(注意:Trident 不支持设置 uid 和 GID，但允许自定义 Unix 权限)。此外，pod 正在使用一个指定匹配 uid 和 gid 值的[安全上下文](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-pod)。

从逻辑上讲，这意味着因为进程和卷的 uid/gid 都匹配，所以访问被授予。如果 uid/gid 不匹配，那么即使装载了卷，pod 也无法访问数据。Kubernetes 还允许管理员[将一个名称空间](https://kubernetes.io/docs/concepts/policy/pod-security-policy/)限制为特定的 uid 和 gid 值，以防止一个名称空间中的用户试图使用另一个名称空间的用户信息。

那么，这为什么不能保护数据呢？NFSv3 假设客户端已经完成了身份验证/授权。这些值也可以任意指定，NFSv3 服务器不会完成任何验证。这意味着任何 pod(在同一命名空间中)都可以使用与该卷相关联的 uid/gid 并获得访问权限。

Kerberos 可以解决其中的一些问题，因为 NFS 服务器参与了授权过程，从而确保只有经过有效身份验证的授权用户才能访问数据。然而，除了当[使用代理](https://kubernetes.io/docs/admin/authentication/#authentication-strategies)时的用户认证之外，Kubernetes 不支持 Kerberos。

## 安全性发生在所有层

通过任何方式将其在 Kubernetes 节点上的访问权限提升为完全根用户的用户能够以多种方式安装、操作和/或破坏资源。因此，[保护您的集群](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/)至关重要，包括 Kubernetes 本身和 Kubernetes 所在的底层主机操作系统。因此，群集的保护方式与您完成虚拟机管理程序管理控制台或其他关键系统的保护方式相同。一个好的起点总是你的操作系统的 STIG(不，不是那个 [Stig](https://en.wikipedia.org/wiki/The_Stig) )。

## 结论

使用名称空间来提供安全域之间的隔离，无论是应用程序、团队还是其他，对于许多用例来说已经“足够好”了。当主机操作系统、Kubernetes 和存储系统被配置为限制对存储设备及其可能包含的附加元数据的访问时，尤其如此。如果您想要在部署到 Kubernetes 的应用程序之间提供终极保护，那么拥有多个具有专用资源的集群可以提供最健壮的隔离。

我们知道你会对与你有关的事情有更多的疑问。我们没有涵盖所有可能的场景，可能永远也不会，所以请使用下面的评论或联系我们的 [Slack 团队](https://netapp.io/slack)、 [GitHub 问题](https://github.com/netapp/trident/issues)或[打开支持案例](https://mysupport.netapp.com/)。我们很乐意帮忙！

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>