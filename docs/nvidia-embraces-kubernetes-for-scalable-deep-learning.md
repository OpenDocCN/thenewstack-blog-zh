# 英伟达采用 Kubernetes 进行可扩展的深度学习

> 原文：<https://thenewstack.io/nvidia-embraces-kubernetes-for-scalable-deep-learning/>

GPU 制造商 [Nvidia](http://www.nvidia.com/page/home.html) 已经将开源的 Kubernetes 容器编排引擎置于其将机器学习引入企业的战略中心。

在舞台上，Nvidia 的 [GPU 技术会议](https://www.nvidia.com/en-us/gtc/)，本周在加州圣何塞举行。[英伟达首席执行官/创始人黄仁勋](https://nvidianews.nvidia.com/bios/jensen-huang)鼓吹一套新的优化方法来及时执行大型机器学习作业——例如最新版本的 [TensorRT](https://developer.nvidia.com/tensorrt) 库——这将使 ML 作业加速 100 倍。他还推出了"[世界上最大的 CPU](https://twitter.com/thenewstack/status/978683446242435072) ，它能够执行通常需要六天才能完成的神经网络工作[只需 18 分钟](https://twitter.com/thenewstack/status/978684582999420928)。但是，在大规模运营中，一个组织如何管理和充分利用所有这些跨越云和数据中心的快速技术呢？

“事实证明，有一种叫做 Kubernetes 的东西，”黄说。“Nvidia GPUs 上的 Kubernetes 将带来如此多的欢乐。太开心了。”

黄指出，这种兴奋的原因是 Kubernetes 最近对 GPU 的支持，随着 1.8 版本的发布引入了测试版。黄说，对于全球最大的 GPU 制造商 Nvidia 来说，Kubernetes 现在是“GPU 感知型”的，这是一个好消息。

在一次演示中，黄展示了 Kubernetes 如何扩大工作负载。他从该公司的标准演示开始，演示如何使用单个 GPU 扫描一组包含花朵的照片，并几乎立即识别出它们是什么类型的花。为了增加工作量，黄的工程师叫来了 Kubernetes，为这个基本程序增加了四个副本，这样一来，屏幕上能识别的花的数量立刻增加了许多倍。

[https://www.youtube.com/embed/P3BjB5-Y4JM?start=1421&feature=oembed](https://www.youtube.com/embed/P3BjB5-Y4JM?start=1421&feature=oembed)

视频

“Kubernetes 可以在一个 GPU 上、一台服务器上的多个 GPU 上、多台服务器上的多个 GPU 上分配 pod，这是一种基本的服务，可以容纳大量容器。您还可以跨数据中心分配它。所以你可以把一部分放在云中，一部分放在数据中心，”黄告诉听众。“所有这些事情都是在完全看不见的情况下发生的，因为我们让 Kubernetes 能够感知 GPU。”

演示还展示了 Kubernetes 提供的弹性。黄的工程师杀死了四个 GPU，以展示 Kubernetes 如何自动找到四个替换单元，尽管 K8s 在这个演示中找到替换单元的速度如此之快，观众甚至没有注意到所有照片识别的速度变慢。

## 在幕后

据该公司称，从 4 月份开始，任何 Kubernetes 托管服务都可以提供 GPU 即服务。该公司特别吹捧亚马逊网络服务和谷歌云平台，但不包括仍在接受英伟达认证的微软 Azure。

在幕后，Nvidia 计划向 Kubernetes 项目贡献 GPU 支持代码，该项目由[云原生计算基金会管理。Nvidia 加速计算软件总监](https://www.cncf.io/)[卡莉·布里斯基](https://www.linkedin.com/in/karibriski/)解释道:该公司首先在内部开发技术，然后将其提供给上游社区的其他人采用。

容器支持背后的想法是 Kubernetes 将识别系统中的 GPU，并能够为它们分配工作负载。Nvidia 已经通过 [Nvidia 容器运行时](https://github.com/NVIDIA/nvidia-container-runtime)支持基于容器的操作，这是一个识别 GPU 的 [runc](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/) 的修改版本。

Kubernetes 首先在 1.7 版本中开始实验性地支持 GPU，尽管它需要手动安装 pod 规范中的卷，并且它不提供任何监控或健康检查。从 Kubernetes 版本 1.8 开始，用户可以通过使用 Nvidia 容器运行时，为 Kubernetes 使用 alpha [Nvidia 插件，Nvidia GPU 云计算软件总监 Viraj Chavan](https://github.com/NVIDIA/k8s-device-plugin) 在一次技术会议上解释了更多关于 Kubernetes 的工作。这个插件在本周被升级为测试版。

Chavan 说，该插件“将 GPU 作为一级资源暴露给栈顶的其他软件组件”。

Chavan 说，现在该公司正在努力进一步完善这种支持。它希望看到适当的 GPU 运行状况检查和监控，以及对拓扑感知和不同类型 GPU 的支持，以便用户可以通过特定的 GPU 类型指定工作负载。愿望清单上的另一项是允许用户切换到不同的容器运行时间，比如 [CRI-O](https://thenewstack.io/cri-o-project-run-containers-without-docker-reaches-1-0/) 。

“我们希望增加这些功能，这样您就可以根据这些限制来安排您的工作。例如，你可以选择说‘我的应用需要这种 GPU 和这种内存’”，Chavan 说。

尽管如此，现代企业在使用 GPU 进行生产规模的工作时，仍然面临着其他挑战。一个是将技术与持续集成和部署实践相协调。Nvidia 应用工程解决方案经理 [Michael Wendt](https://github.com/mike-wendt) 在会议的另一场技术会议上指出，基于云的 CI/CD 系统，如 [Travis CI](https://travis-ci.org/) 和 [CircleCI](https://circleci.com/) 还不支持 GPU。Wendt 自己正在开发一个支持 Docker 容器运行时的 Jenkins 插件。他说，它适用于 Docker Swarm，但还不支持 Kubernetes。

CircleCI 和 Cloud Native Computing Foundation 是这个新堆栈的赞助商。

专题图片:英伟达首席执行官黄仁勋，在 GTC 2018 的舞台上，演示用于机器学习工作的 Kubernetes。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>