# 教程:使用 Portworx 备份和恢复有状态工作负载

> 原文：<https://thenewstack.io/tutorial-backup-and-restore-of-stateful-workloads-with-portworx/>

在本系列的最后一部分中，我们看到了如何用 [Portworx](https://portworx.com/) 配置一个高度可用的 WordPress 部署，Portworx 是 Kubernetes 的一个数据和存储管理平台。在本期文章中，我们将学习如何通过 Portworx 的本地和远程快照功能实现 PVC 的备份和恢复。

### Portworx 中的快照

Portworx 可以拍摄 PVC 的时间点[快照](https://docs.portworx.com/reference/cli/snapshots/)，这些快照可以本地存储在集群中，也可以远程存储在与亚马逊 S3 API 兼容的对象存储服务中。名为 [CloudSnaps](https://docs.portworx.com/reference/cli/cloud-snaps/) 的远程快照承诺更高的可用性，因为它们存储在集群之外。

在 Kubernetes 中将分布式数据库作为状态集运行时，拍摄与状态集的每个 pod 相关联的单个 PVC 的快照可能不会产生应用程序一致的备份。为了能够备份逻辑上属于一个应用程序的一组 PVC，Portworx 有一个名为 [3DSnaps](https://docs.portworx.com/portworx-install-with-kubernetes/storage-operations/create-snapshots/snaps-3d/) 的概念。

使用 3DSnaps 时，Portworx 允许指定在使用卷的应用程序窗格上运行的先行和后继规则。这允许用户在拍摄快照前暂停应用程序，并在拍摄快照后恢复 I/O。这些命令将在连接了正在拍摄快照的 PVC 的机架中运行。

无论是通过 3DSnap 拍摄的单个 PVC 的快照还是一组 PVC 的快照，备份过程都可以是按需的或按计划的。

让我们看看如何创建一个 CloudSnap 来将 MySQL 和 WordPress PVCs 备份到一个远程站点。为了简单起见，我们将使用运行在集群之外的机器上的 MinIO 来存储快照。由于与亚马逊 S3 API 100%兼容，Portworx 可以指向 [MinIO](https://min.io) 存储 CloudSnaps。

### 在 Docker 上运行 MinIO

在运行 Docker 的 Linux 或 macOS 机器上，创建一个目录来挂载 MinIO 的卷。

运行下面的命令启动 MinIO 容器，其中一个卷指向上面的目录。

```
docker run  -p  9000:9000  --name minio1  \
  -e  "MINIO_ACCESS_KEY=AKIAIOSFODNN7EXAMPLE"  \
  -e  "MINIO_SECRET_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"  \
  -v  /mnt/data:/data  \
  minio/minio server  /data

```

我们正在使用 MinIO 的[文档](https://docs.min.io/docs/minio-docker-quickstart-guide.html)中提到的示例访问密钥和秘密密钥。对于生产用途，用您自己的密钥替换它们。

通过访问端口 9000 上的 MinIO UI 进行验证。

![](img/c40664c7137851dcf8a20d40fded8c20.png)

使用访问密钥和保密密钥登录以访问 MinIO 浏览器。

![](img/7d9136b6919435838f2ea5c13e5790c7.png)

### 向 Portworx 注册 MinIO

在启动备份过程之前，我们需要告诉 Portworx 在哪里存储快照。这是通过使用 MinIO 的访问密钥和秘密密钥在 Portworx 中创建凭证来实现的。

让我们调用 Portworx 的 CLI， **pxctl** ，它在 *kube-system* 名称空间内的 daemonset 的一个 pod 内运行，并传递创建凭证所需的参数。

```
PX_POD=$(kubectl get pods  -l  name=portworx  -n  kube-system  -o  jsonpath='{.items[0].metadata.name}')
kubectl exec  -it  $PX_POD  -n  kube-system  --  \
    /opt/pwx/bin/pxctl credentials create  \
    --provider s3 \
    --s3-access-key AKIAIOSFODNN7EXAMPLE  \
  --s3-secret-key wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY \
    --s3-region minio  --s3-endpoint http://10.0.0.5:9000 minio_creds

```

通过使用下面的命令列出凭证来验证凭证:

```
kubectl exec  -it  $PX_POD  -n  kube-system  --  \
    /opt/pwx/bin/pxctl credentials list

```

![](img/c3060eaeb4d1510eabfe1966f97295ac.png)

有了对象存储凭据，我们就可以配置 CloudSnaps 了。

### 为 MySQL 和 WordPress 配置 Portworx CloudSnaps

如果您还记得，应用程序部署导致了两个与 MySQL 和 WordPress 相关联的 PVC。我们的目标是通过 CloudSnaps 备份这些 PVC。

![](img/61bf0ca79e4cdf0513586215e7d2a15b.png)

下面的 YAML 规范为 PVC 创建了一个 CloudSnap，由 MySQL pod 使用 db-pvc。

```
apiVersion:  volumesnapshot.external-storage.k8s.io/v1
kind:  VolumeSnapshot
metadata:
  name:  db-snapshot
  namespace:  wordpress
  annotations:
    portworx/snapshot-type:  cloud
spec:
  persistentVolumeClaimName:  db-pvc

```

```
kubectl create  -f  db-snap.yaml

```

同样，让我们为 WordPress PVC 创建一个快照。

```
apiVersion:  volumesnapshot.external-storage.k8s.io/v1
kind:  VolumeSnapshot
metadata:
  name:  wp-snapshot
  namespace:  wordpress
  annotations:
    portworx/snapshot-type:  cloud
spec:
  persistentVolumeClaimName:  wp-pvc

```

```
kubectl create  -f  wp-snap.yaml

```

使用以下命令列出并验证快照:

```
kubectl get volumesnapshots

```

![](img/fef8de160a3d95f998fad38ecb43110b.png)

```
kubectl get volumesnapshotdatas

```

![](img/4d9ea9a486c3f4dae993eddb04ce1226.png)

```
kubectl describe volumesnapshotdatas k8s-volume-snapshot-76ec8970-822f-11ea-aef1-26c54787ef6a

```

![](img/10d2c836bd5938328c8bcc118f8a5d62.png)

```
kubectl describe volumesnapshotdatas k8s-volume-snapshot-b75b3cac-822f-11ea-aef1-26c54787ef6a

```

![](img/e2e7bc50478c8c02db03c43b2b6cb61c.png)

以上输出确认快照已成功创建。

参考 Portworx [文档](https://docs.portworx.com/portworx-install-with-kubernetes/storage-operations/create-snapshots/scheduled/)了解如何安排快照以实现定期备份。

最后，如果您访问 MinIO 浏览器，您会注意到在一个 bucket 中创建了两个文件夹。这些文件夹存储来自两个 PVC 的快照。

![](img/7d9136b6919435838f2ea5c13e5790c7.png)

### 从云快照恢复

让我们从存储在 MinIO 中的快照创建新的 PVC。

下面的 YAML 规范产生了一个新的 MySQL PVC，它是原始 PVC 的克隆。

```
apiVersion:  v1
kind:  PersistentVolumeClaim
metadata:
  name:  db-pvc-clone
  annotations:
    snapshot.alpha.kubernetes.io/snapshot:  db-snapshot
spec:
  accessModes:
 -  ReadWriteOnce
  storageClassName:  stork-snapshot-sc
  resources:
    requests:
      storage:  2Gi

```

注意存储类名 stork-snapshot-sc，它特定于 Portworx 的用于 Kubernetes (STORK)的存储编排器，用于管理有状态工作负载的编排和操作。

让我们也为 WordPress 创建一个 PVC 克隆。

```
apiVersion:  v1
kind:  PersistentVolumeClaim
metadata:
  name:  wp-pvc-clone
  annotations:
    snapshot.alpha.kubernetes.io/snapshot:  wp-snapshot
spec:
  accessModes:
 -  ReadWriteOnce
  storageClassName:  stork-snapshot-sc
  resources:
    requests:
      storage:  2Gi

```

当我们应用这两个规格时，会创建几个新的 PVC。

![](img/62bb265e858d502ace66850928a320b2.png)

以“*-*clone”*结尾且存储类为***stork-snapshot-sc***的 PVC 是从快照恢复的新 PVC。

您现在可以使用原始 pods 的克隆 PVC 来创建 WordPress 和 MySQL pods。这种技术可以用于将 PVC 从一个名称空间迁移到另一个名称空间，甚至迁移到运行 Portworx 的其他集群。

在本系列的下一部分中，我们将探索如何使用 Portworx 和 Velero 将整个工作负载从一个集群迁移到另一个集群。敬请期待！

*贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。请在 http://mi2.live 注册参加即将举行的 MI2 网络研讨会*

Portworx 是新堆栈的赞助商。

来自 Pixabay 的 Paul Brennan 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>