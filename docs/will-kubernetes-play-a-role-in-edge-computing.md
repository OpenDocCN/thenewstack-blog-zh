# Kubernetes 会在边缘计算中发挥作用吗？

> 原文：<https://thenewstack.io/will-kubernetes-play-a-role-in-edge-computing/>

[KubeCon + CloudNativeCon](https://www.cncf.io/) 赞助了这个播客。

我们有越来越多的设备连接到云，增加了云的压力。这导致了延迟和带宽浪费，更不用说[环境影响](https://thenewstack.io/tech-ethics-can-developers-save-the-earth-one-container-at-a-time/))边缘计算试图弥合设备和互联网连接之间的差距，是实现更快互联网接入的潜在解决方案。但是 Kubernetes——几乎每个人都在使用的容器编排——在边缘上也有未来吗？

《新堆栈》出版商亚历克斯·威廉姆斯在 KubeCon+CloudNativeCon 北美公司与[王史提芬](https://twitter.com/cantbewong)和[德扬·博萨纳克](https://twitter.com/dejanb)坐下来谈论这个问题。Wong 是 VMware 云计算原生业务部门的软件工程师，Bosanac 是 Red Hat 的高级软件工程师。两人都是 Kubernetes 工作组的成员，致力于解决 Kubernetes 在边缘上的局限性。

[Kubernetes 会是边缘计算的答案吗？](https://thenewstack.simplecast.com/episodes/will-kubernetes-be-the-answer-to-edge-computing)

Wong 提供了现代豪华车模型的例子，从娱乐系统到防抱死制动系统，到牵引力控制系统，甚至是电动车窗和车门，可能有多达 37 台计算机在其中运行。这些连接的对象中的每一个都是经常需要配置和更新的数据源。

他认为 Kubernetes 编排是唯一适合解决这个问题的方法——最终。

“Kubernetes 的设计师从构建这个丰富的基础开始，事实证明，这个可扩展的 API 可以通过一个 API 来控制大规模的事情，在这个 API 中，你可以陈述期望的结果:‘我希望这些事情在完美的世界中处于这种状态。’然后称为控制器的东西在后台工作，无情地驱动现实世界的状态。他们会记下你说你想要什么，衡量这件事现在是什么，并不懈地推动它朝着你的既定目标前进，”Wong 说。

Wong 接着说 Kubernetes 是“可并行化的”,这意味着你可以有成百上千个这样的驱动程序来驱动你想要的状态。这种可扩展性意味着它不仅仅局限于云中的可扩展应用程序。它甚至可以在高度分散的零售站点与边缘计算结合使用。

Bosanac 在此基础上指出，人们试图分配计算资源并不是什么新鲜事。对他来说，边缘计算只是我们基于云的世界的现实的延伸——云原生架构加上开发人员工具来构建可以在云中运行的应用程序，然后部署到边缘站点。

Bosanac 还是 Eclipse Foundation 的成员，该基金会致力于为开源物联网云平台构建基础。这是为了解决所有这些新设备收集到云的压力，而不是允许它们连接到边缘，这将导致改进的延迟和保留的带宽。

Wong 举了安全摄像机的例子，每秒钟收集 30 幅图像。当你只想收集车辆牌照或游客的面孔时，把所有视频上传到云端是没有用的。机器学习、图像识别和标记最好在边缘附近完成，那里应该有更少的错误、更少的延迟、更快的结果和节省的带宽。这一切都是为了在边缘减少它——Wong 说它有可能减少三分之二。

他继续说，边缘的机器学习实际上只是容器化的应用程序，Kubernetes 习惯于管理这些应用程序。

“在某种程度上，你可以认为边缘计算真的是云计算，你只是颠倒了这些容器化应用程序的运行位置，”Wong 说。

[https://www.youtube.com/embed/ctn9v1HbiEs?feature=oembed](https://www.youtube.com/embed/ctn9v1HbiEs?feature=oembed)

视频

云计算原生计算基金会、Red Hat OpenShift 和 VMware 是新体系的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>