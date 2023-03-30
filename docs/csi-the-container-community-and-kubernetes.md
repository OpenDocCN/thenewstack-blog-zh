# CSI、容器社区和 Kubernetes

> 原文：<https://thenewstack.io/csi-the-container-community-and-kubernetes/>

[【CSI】【集装箱社区】和](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes)

在最新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，我们开始了解更多关于 [Kubernetes](/category/kubernetes/) 开源容器编排引擎的存储选项，以及对[容器存储接口](https://github.com/container-storage-interface/spec)的内部改进。

回答主持人这些问题的是 TNS 创始人[亚历克斯·威廉姆斯](https://twitter.com/alexwilliams?lang=en)，技术总监 [{code}](http://web.archive.org/web/20180220231349/https://thecodeteam.com/) 柯林顿·麦显杰和[波特沃克斯](https://portworx.com/)联合创始人兼首席技术官[古瑟姆·拉奥](https://www.linkedin.com/in/gouthamrao/)。

“这是经验教训。当你丢失数据时，你的日子真的很糟糕。这就是为什么存储是我们做对的关键领域之一。麦显杰说:“我认为我们正处于《犯罪现场调查》的关键时刻。

麦显杰指出，让两个独立的组件决定如何相互通信，最好是通过远程过程调用(RPC)来实现。他接着解释说，这是一段时间以来休息的理想目标，并朝着 [gRPC](https://grpc.io/) 前进。对于 CSI，麦显杰还强调了原始数据块设备也是卷的能力。

“您可以让一些存储后端来自公共云，一些来自本地，但用户有一致的体验，并且运营商可以决定他们希望如何扩展他们的环境。我认为这就是用户所要求的，那就是控制。”饶补充道。

[https://www.youtube.com/embed/Fe3s0hsw0yc?feature=oembed](https://www.youtube.com/embed/Fe3s0hsw0yc?feature=oembed)

视频

### 在这个版本中:

[4:48:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=4:48) Kubernetes 和使用 CSI 等存储平台时的用户体验。
[6:20:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=6:20) 抽象和用户体验是 CSI 的支柱。
[13:26:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=13:26)CSI 背后的技术架构。
[16:59:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=16:59) 为什么 gRPC 在 CSI 中如此关键。
[18:57:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=18:57)CSI 的用例是如何演进的？
[24:24:](https://thenewstack.simplecast.com/episodes/csi-the-container-community-and-kubernetes?t=24:24)CNCF 的存储工作组。

云计算原生计算基金会赞助了这个播客。{code} 和 [Portworx](https://portworx.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>