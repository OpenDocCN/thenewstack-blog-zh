# T-Mobile 如何部署 Portworx 实现灵活存储

> 原文：<https://thenewstack.io/how-t-mobile-deployed-portworx-for-flexible-storage/>

波特沃克斯赞助了这个播客。

[T-Mobile Web 后端:Kubernetes、Cloud Foundry、灵活存储的 Portworx . MP3](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3)

T-Mobile 对流量波动如何给电子商务网站带来压力略知一二。它的网站每年至少有两次被顾客和潜在顾客淹没——一次是在新手机发布的 10 月份，另一次是在 12 月份，这一次是在节日礼物购买季。

T-Mobile 依靠容器平台管理其网站已经有几年了，Kubernetes 已被证明有助于帮助该公司扩大网站规模以满足这些峰值需求，T-Mobile 云铸造平台架构师 [James Webb](https://www.linkedin.com/in/jameswebb/) 在上个月西雅图的 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/) 录制的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中说道。

Webb 是一个运营团队的成员，该团队使公司内的其他业务部门可以轻松获得 IT 资源，因此他们可以促进自己的 DevOps 风格的实践，以快速更新和迭代面向客户的工具。Webb 说，Cloud Foundry 和 Kubernetes 在建立这些自助服务方面非常有用。

Portworx 也是如此，它有助于将这些云原生工具与后端存储资源连接起来。Portworx 工程副总裁 Venkat Ramakrishnan 加入了 Webb 的播客，向他解释了云原生存储的更多细微差别。他说，Portworx“允许你为你的容器协调器提供这些高可用性的服务”。

例如，一个 pod 被安排在一个节点上。并且[如果]由于某种原因节点关闭，调度程序将重新调度该节点。Portworx 自动管理 Kubernetes 集群上任何其他节点中该 pod 的数据可用性，”他解释道。同时，它为客户提供了一个抽象级别，因此他们可以指定他们想要的存储类型的特征

[https://www.youtube.com/embed/jQBY_wWMLnw?feature=oembed](https://www.youtube.com/embed/jQBY_wWMLnw?feature=oembed)

视频

### 在这个版本中:

[3:25:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=3:25) 这么说，您在内部负责 Kubernetes 的部署？当初让你选择 Kubernetes 的痛点是什么？
[5:10:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=5:10) 您是否不得不改变开发应用程序的方式？
[10:51:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=10:51) 你用容器承载了那份坚持吗？
[14:08:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=14:08) 你能谈谈你的缩放机制吗？
[20:02:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=20:02) 您实际上用什么来保存数据？
[27:55:](https://thenewstack.simplecast.com/episodes/t-mobile-web-backend-kubernetes-cloud-foundry-and-portworx-for-flexible-storage-mp3?t=27:55) 你 2019 年的目标是什么？

Cloud Foundry Foundation 和 KubeCon + CloudNativeCon 是新堆栈的赞助商。

专题图片:詹姆斯·韦伯(右)，文卡特·拉马克里希南。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>