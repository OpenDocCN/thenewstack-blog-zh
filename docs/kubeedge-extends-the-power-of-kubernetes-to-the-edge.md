# KubeEdge 将 Kubernetes 的力量延伸到了边缘

> 原文：<https://thenewstack.io/kubeedge-extends-the-power-of-kubernetes-to-the-edge/>

云原生计算和边缘计算代表了现代基础设施的两个独立但重要的方面。云原生计算是云计算的第二波浪潮，它提供了最佳的云投资回报。边缘计算充当云和物联网(IoT)设备之间的管道，为数百万联网设备和应用提供自主和智能计算。

AI 的崛起让边缘计算变得更加重要。在云中训练的复杂模型部署在边缘进行推理。

Kubernetes 已经成为编排在数据中心和公共云中运行的容器化工作负载的黄金标准。在很短的时间内，云原生生态系统增加了多种功能，使 Kubernetes 成为一个强大而可靠的平台，可以运行 web 级应用程序和企业业务线应用程序。

投资物联网平台的公共云供应商正在将其产品扩展到边缘。物联网应用的设备注册、通信、部署和管理主要在云中运行，并对边缘提供扩展支持。这些供应商现在正在连接物联网、ML 和 AI 平台上的点，以无缝地将 ML 模型从云推到边缘。 [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) 、 [AWS Greengrass](https://aws.amazon.com/greengrass/) 和 [Google Cloud IoT Edge](https://cloud.google.com/solutions/iot/) 都是扩展公共云的边缘平台的例子。像 [FogHorn](https://www.foghorn.io/) 、 [Swim.ai](https://www.swim.ai/) 和 [Rigado](https://www.rigado.com/) 这样的初创公司正在构建多云、多路访问的边缘计算平台。

Kubernetes 正在迅速成为调度和管理容器之外的资源的通用调度器。Kubernetes 的控制平面旨在处理跨越数百个节点运行的数万个容器。这种架构非常适合管理可扩展的分布式边缘部署。每个边缘计算设备可以被视为一个节点，而一个或多个连接的设备可以被映射到 pod。开发者和运营商可以使用熟悉的 kubectl 工具或 Helm charts 来推动在一个或多个边缘设备上运行的容器化物联网应用。这种方法使 Kubernetes 不仅成为容器的控制平面，也成为通过自主边缘计算层管理的数百万设备的控制平面。

> 一艘大船可能运行多个边缘计算节点，这些节点在获得连接之前不会与控制平面对话。这种模式与 Kubernetes 主节点和工作节点的原始设计非常不同。

云原生社区一直在探索将 Kubernetes 用于物联网和边缘计算。微软[试图通过虚拟 Kubelet 的方法来实现这一点。华为基于 Kubernetes 构建了智能边缘结构。2018 年 6 月，谷歌、华为、红帽和 VMware 启动了](https://thenewstack.io/tutorial-kubernetes-for-orchestrating-iot-edge-deployments/)[物联网边缘工作组](https://blogs.eclipse.org/post/mike-milinkovich/k8s-edge-%E2%80%93-some-context-new-kubernetes-iot-working-group)来正式确定这些努力。在西雅图举行的 KubeCon+CloudNativeCon 2018 上，华为展示了 [KubeEdge](https://kubeedge.io/en/) ，这是一个将 Kubernetes 的力量推向边缘的官方项目。

KubeEdge 基于华为的[智能边缘架构](https://www.huawei.com/en/press-events/news/2019/3/huawei-ai-fabric-lossless-data-center-network-tolly-test)(IEF)——基于华为物联网 PaaS 的商用物联网边缘平台。IEF 的很大一部分已经被修改并为 KubeEdge 开源。KubeEdge 在 v0.2 版本中可用，稳定且完整，可解决与物联网和边缘相关的关键用例。它可以安装在受支持的 Linux 发行版和像 Raspberry Pi 这样的 ARM 设备上。

作为 Kubernetes 的粉丝和物联网爱好者，我对 KubeEdge 的设计和建筑非常着迷。与 Kubernetes 集群的节点不同，边缘节点必须在完全断开的模式下工作。一艘大船可能运行多个边缘计算节点，这些节点在获得连接之前不会与控制平面对话。这种模式与 Kubernetes 主节点和工作节点的原始设计非常不同。

KubeEdge 巧妙地解决了这个问题，它将消息总线和数据存储结合起来，使边缘节点自治和独立。存储在控制平面中的期望配置与边缘设备的本地数据存储同步，该数据存储在下一次握手之前被缓存。持久存储在边缘设备的数据存储中的设备的当前状态也是如此。

KubeEdge 利用了 Kubernetes 原语，如控制器和自定义资源定义。像复制控制器和 StatefulSet 控制器一样，控制平面中有一个边缘控制器，它与部署在设备中的边缘运行时进行对话。这种设计使得使用 kubectl 管理边缘部署成为可能。

对于边缘和控制平面之间的机器对机器通信和双工通信，KubeEdge 依赖于 Mosquitto，这是 Eclipse Foundation 的一个流行的开源 MQTT 代理。该平台还支持 device twin 来维护物联网设备的状态。SQLite 用作数据存储区来保存设备双状态以及从边缘到控制平面来回流动的消息。WebSockets 用于实现边缘节点和主节点之间的通信。

KubeEdge 是使 Kubernetes 成为边缘计算统一控制平台的第一步。它的成功很大程度上取决于主流云提供商的采用，包括亚马逊、谷歌和微软。

*贾纳基拉姆·MSV 的网络研讨会系列，“* [【机器智能和现代基础设施(MI2)](https://mi2.janakiram.com/) *”提供了涵盖前沿技术的信息丰富、见解深刻的会议。* [注册](https://mi2.janakiram.com/) *参加即将举行的 MI2 网络研讨会，了解如何使用 Azure IoT Edge。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>