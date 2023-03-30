# Red Hat 用块和对象存储来填充其云原生存储包

> 原文：<https://thenewstack.io/red-hat-fills-cloud-native-storage-package-block-object-storage/>

Red Hat 推出了容器原生存储 3.6，作为其提供全面容器堆栈的努力的一部分，这是继 8 月份发布的 [Red Hat OpenShift 容器平台 3.6](https://www.redhat.com/en/about/press-releases/red-hat-enhances-cloud-native-security-application-consistency-latest-version-red-hat-openshift-container-platform) 之后的又一次努力。

这种集装箱存储包建立在其 [Gluster](https://www.redhat.com/en/technologies/storage/gluster) 存储技术之上，并与 [OpenShift](https://www.openshift.com/) 平台集成。

“我们试图用容器原生存储解决的关键问题是让存储最终变得不可见。我们希望开发人员对存储有足够的控制，而不是等待存储管理员为他们的应用程序分配存储。他们能够动态、自动地请求和供应存储，”Red Hat 产品营销高级经理[伊尔沙德·雷汉](https://www.linkedin.com/in/irshadraihan/)说。

据该公司称，容器原生存储 3.6 特别适合混合云环境，因为它可以部署在内部和公共云中，完整的容器堆栈提供了单一控制平面，节省了成本，并提供了更简化的体验。它还增强了应用程序的可移植性。

新特性包括:

*   支持文件、块和对象接口。块存储的增加(通过 iSCSI)为分布式数据库和其他低延迟工作负载(如 Elasticsearch)提供了支持。对象存储是一种技术预览。面向寻求类似 AWS 体验的客户。
*   对核心容器平台组件的支持:注册表、日志和指标。存储管理员不需要多个存储系统；单一的集成平台提供了简化的管理、采购和支持。
*   在单个存储集群上部署的应用和微服务的数量增加了持久卷密度。

Raihan 说，在向越来越小的微服务转移的过程中，开发人员不希望必须处理性能瓶颈、降级和类似的问题。因此，每个集群支持大约 1，000 个持久卷，这为开发人员提供了更大的灵活性，使他们可以无缝扩展，而不会遇到性能瓶颈。

Red Hat 还在 OpenShift 容器平台上为客户提供容器原生存储的[测试。使用在云中运行的多节点集群，客户可以探索旨在让他们接触不同管理和操作任务的实验室练习。](https://www.redhat.com/en/engage/openshift-storage-testdrive-20170718)

存储的动态供应是 Red Hat 在容器原生存储中首先提供的东西之一。Raihan 说，OpenShift 管理员可以根据工作负载、延迟类型和其他因素来定义服务层，从而为开发人员创建易于翻译的存储类。

## 未来的存储

尽管有不同的说法，[持久存储在可预见的未来仍将是容器的拦路虎](https://thenewstack.io/containers-storage-arent-yet/),[IBM 容器传道者 James Bottomley](https://twitter.com/jejb_) 在今年早些时候的 Linux Foundation Vault storage 会议上告诉与会者。

他说，问题在于 Linux [用户名称空间](http://rhelblog.redhat.com/2015/07/07/whats-next-for-containers-user-namespaces/)的工作方式，以及协调外部存储系统使用的文件系统用户 ID (fsuid)和容器内创建的用户 fsuid)的难度。

[对象存储](https://thenewstack.io/forget-file-system-future-scalable-cloud-storage-will-objects/)将是云原生应用的未来，[新西兰开源系统提供商](https://www.linkedin.com/in/aboag) [Catalyst IT Limited](https://catalyst.net.nz/) 的董事总经理 Andrew Boag 在去年巴塞罗那 OpenStack 峰会上关于集群文件系统的[演讲](https://youtu.be/KVRAc56Js8Q)中预测。

当在当前设置中无法有效管理数据量时，一种方法是通过集群或分布式文件系统将数据分布在单个名称空间内的多个服务器上。

根据 Raihan 的说法，这是 GlusterFS、 [CephFS](http://docs.ceph.com/docs/master/cephfs/) 、Hadoop 的 [HDFS](https://hortonworks.com/apache/hdfs/) 、Lustre 以及 Oracle 集群文件系统和 OpenShift 使用的方法。

“您将建立一个单一的名称空间；可能是多卷。您也可以设置一个多集群环境。您将在 OpenShift 集群本身的单个名称空间内操作。您可以拥有作为存储和应用的 OpenShift pods，您可以拥有从作为应用的相同 pod 提供存储的 pod。

“这是我们前进的方向，存储即服务——它看起来只是位于 Linux 命名空间之上的另一个应用程序，”他说。

然而，他说，客户一直在要求对象存储。尚未确定对象存储正式上市的日期。

红帽公司是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>