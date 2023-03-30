# 采用 Trident 的 Kubernetes 中的状态工作负载 NetApp 之道

> 原文：<https://thenewstack.io/stateful-workloads-in-kubernetes-with-trident-the-netapp-way/>

NetApp 赞助了该播客。

管理企业工作负载的人可能会想到一个问题:什么是 [Trident](https://netapp.io/persistent-storage-provisioner-for-kubernetes/) ？这是 NetApp 开放生态系统产品管理总监 [George Tehrani](https://www.linkedin.com/in/tehrani/) 在 TNS 创始人兼主编 Alex Williams 主持的最新一期 New Stack Makers 播客中回答的话题。

“总的来说，任何对企业重要的工作负载都需要某种持久性。Trident 是一款开源存储协调器，由 NetApp 开发并继续维护。它极大地简化了 Kubernetes 以及其他 Kubernetes 主要发行版(如 OpenShift)中企业工作负载的持久存储的创建、管理和使用。”

[NetApp 的 Trident 如何帮助 Kubernetes 处理有状态工作负载](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads)

“看待 Trident 最常见的方式是将其视为 NetApp 提供的各种存储平台以及容器编排器之间的集成，”Tehrani 说，并补充说 Trident 是用“Kubernetes 的语言”Go 编写的 Tehrani 接着补充说，作为控制对象，Trident 不在数据路径中，因此不会对存储生态系统的性能产生负面影响。

德黑兰尼重申三叉戟背后的前提是简化。在后端设置 Trident 时，有多种平台可供开发者选择。“简化意味着一款基础架构软件能够了解如何与 ONTAP、Element、Santricity 以及 NetApp 云卷服务进行交流，”他说。

Tehrani 后来指出，Trident 是 Kubernetes 的第一个外部存储供应引擎。Tehrani 说，NetApp 的经验“为这一领域带来了非常丰富的存储遗产”，并补充说，“竞争优势一部分是技术，一部分是我们带来的专业知识，一部分是真正使技术对客户友好，并使其易于消费和采用。”

### 在这个版本中:

[1:11:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=1:11) 什么是三叉戟？
[1:12:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=11:12) 三叉戟的与众不同之处:实际部署的过程。
[15:07:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=15:07) 在后端配置 Trident 时，开发者有了不同平台的选择。
[20:15:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=20:15) 三叉戟架构。
[28:47:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=28:47) 三叉戟如何在 Kubernetes、CSI、Docker Enterprise、CNCF、红帽 OpenShift
[33:25:](https://thenewstack.simplecast.com/episodes/how-netapps-trident-helps-kubernetes-with-stateful-workloads?t=33:25) 三叉戟走向何方。

来自 Pixabay 的 enriquelopezgarre 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>