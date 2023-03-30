# 海港，“库伯内特的最佳注册地”

> 原文：<https://thenewstack.io/harbor-the-best-registry-for-kubernetes/>

[开源开发者如何让 Harbor 成为“Kubernetes 的最佳注册中心”](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes)

如今，跟踪和管理容器会给组织带来明显的挑战。但是随着容器和 Kubernetes 的加入，考虑到容器的多孔性，任务变得更加困难。

后起之秀 [Harbor](https://goharbor.io/) 开源容器映像管理注册表是一种据称用于存储和扫描容器映像以发现漏洞的方法。

Harbor 如何以及为什么能够帮助解决云原生部署的安全问题，以及它是如何开发的，是 New Stack 创始人兼主编 Alex Williams 最近在上海举办的[kube con+CloudNativeCon 2018](https://www.cncf.io/kubecon-cloudnativecon-events/)播客中的讨论主题。与他一起的还有[开源港云原生应用首席架构师张卫彝](https://www.linkedin.com/in/henryxnzhang/)，以及[VMware 云原生应用产品管理副总裁保罗·杜尔](https://www.linkedin.com/in/pauldul)。

“关键是安全性，”张说，并补充说，Harbor 提供诸如访问、控制和复制以及漏洞扫描等功能。

Harbor 的设计也使注册表位于防火墙之后。“假设你要去一个 Docker hub 或一个公共托管的注册表，那么你就能够拥有一个位于防火墙后的管理图像的管理注册表，”杜尔说，“所以，你对它有更多的控制权。”

如上所述，Harbor 是开源的，适合云原生部署。“由于 Harbor 是开源的，这是一个很大的优势，它在开源社区得到了很好的接待，”Dul 说。“它真正关注的是 Kubernetes，而其他一些注册管理机构可能会有更广泛的关注。”

Harbor 的起源可以追溯到大约四年前，当时张注意到缺乏管理集装箱图像的工具。“当我那时参加聚会或会议时，我经常看到人们用他们自己的方式管理容器映像，有各种各样的黑客和变通办法，”张说。“所以，在那个时候，我们认为我们可能能够做点什么来创造一个供人们使用的通用工具。”

然后，张和他的团队在中国的 VMware 中心创建了一个用于管理容器映像的原型解决方案。在收集反馈以逐步改进软件后，该项目被开源。

Dul 描述了 VMware 如何帮助客户能够更好地控制他们的容器映像。感兴趣的关键点之一是 Harbor 如何从一开始就作为一个开源的替代方案，作为一个私有的而不是公共的注册中心。第二个主要属性是它的漏洞扫描能力。Dul 说，虽然存在许多开源的漏洞扫描器，但真正重要的是“这些扫描器的集成”。

张说，Harbor 团队最近为那些在 Kubernetes 上运行 Helm 的人增加了 Helm 图表，以提高“利用 Kubernetes 的能力来管理 Harbor”。“所以，这是一个循环的方式，取决于他们的需要，”张说。

张说，以前，开发人员必须使用 Helm 来部署他们的应用程序，而 Helm 图表由“磁盘上的一堆文件”组成。Zhang 说，通过将舵图与集装箱图像集成，以便在 Harbor 内形成一致的管理系统，用户可以在部署到 Kubernetes 集群之前一起检查他们的舵图和集装箱图像。

事实上，赫尔姆越来越受欢迎，“我们从我们的用户那里发现，他们真的希望看到对赫尔姆图表的支持，”杜尔说。“此外，我们还在围绕可扩展性和高可用性开发其他功能。”

张说，Harbor 开发团队的目标是继续改进注册表，以获得更好的用户体验。“我想我们也想让它对 Kubernetes 的用户更可靠、更有用，”张说。

[https://www.youtube.com/embed/MIpTEsRoWyE?feature=oembed](https://www.youtube.com/embed/MIpTEsRoWyE?feature=oembed)

视频

### 在这个版本中:

[1:40:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=1:40) 什么是港湾，为什么现在重要？
[7:04:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=7:04) 探索 Helm 的模板管理功能
[11:30:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=11:30) 告诉我在底层发生的监控，以及您正在使用哪些工具进行监控？
[16:32:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=16:32) Dul 关于 CI/CD 管道如何工作的理念
[20:47:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=20:47) 现在，您希望在社区内填补 Harbor 技术中的哪些空白？
[26:25:](https://thenewstack.simplecast.com/episodes/how-open-source-developers-wanted-to-make-harbor-the-best-registry-for-kubernetes?t=26:25) 这与我们听到的 VMware 的大故事有什么关系？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>