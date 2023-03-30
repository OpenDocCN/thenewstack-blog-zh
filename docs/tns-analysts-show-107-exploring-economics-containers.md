# 新堆栈分析师:探索集装箱经济学

> 原文：<https://thenewstack.io/tns-analysts-show-107-exploring-economics-containers/>

在这一集的 [The New Stack Analysts](/tag/the-new-stack-analysts/) 中，我们深入讨论了从亚马逊 EC2 到容器的迁移，向基于容器的基础设施的转变，以及 [Joyent](https://www.joyent.com/) 如何帮助逆向物流平台 [Optoro](http://www.optoro.com/) 实现自己的 API 驱动的基础设施，同时保持在本地。New Stack 创始人 Alex Williams 和联合主持人技术编辑 Benjamin Ball 与 Optoro 的 DevOps 总监 Zach Dunn 进行了深入的讨论。

[#115:探索集装箱的经济学](https://thenewstack.simplecast.com/episodes/115-exploring-the-economics-of-containers)

Optoro 开始从亚马逊迁移到容器化服务的原因很简单。“我们意识到那袋屎已经满了，我们再也装不下了。当我们开始走服务路线时，我们偶然发现集装箱在这里非常有价值，”邓恩说。最初运行 400 个 EC2 实例的设置，Dunn 继续解释说，Optoro 的服务很快开始膨胀，因为更多的层被添加到单个服务中，以便登台将类似于生产。随着每个暂存层添加的虚拟机数量持续攀升，Dunn 注意到 Optoro 开始注意到每次推出新服务时都会有 10%的增长。“当我们向系统中添加越来越多的负载时，这就成了问题。”

[https://www.youtube.com/embed/DzlNyWBmIdQ?feature=oembed](https://www.youtube.com/embed/DzlNyWBmIdQ?feature=oembed)

视频

因此，该公司决定迁移到本地，从 EC2 迁移到主要基于容器的基础设施。随着最近围绕 Docker Fork 可能性的讨论，Williams 后来询问如果这种事情成为现实，Optoro 会受到怎样的影响。“我们已经被孤立了。Dunn 说，后来他补充说，Joyent 的 Triton 上的 Docker 的操作可靠性是他决定采用 Docker 的关键。

他后来继续解释说，对于当今的许多企业来说，转向基于容器的基础设施通常是“直截了当的经济效益”，并指出 Optoro 通过在内部安装和运行自己的解决方案节省了大量运营成本。虽然效率惊人，但有些事情容器并不适合。在这种情况下，邓恩指出，Optoro 不会很快运行完全基于容器的基础设施。“这实际上是我们最终没有使用一些 Docker 框架的原因之一，它们对我们来说有点太‘一切都需要成为容器’。MySQL 并不完全是为了摆脱容器而构建的。”

当对话接近尾声时，Dunn 详细介绍了 Joyent 如何让 Optoro 灵活地在内部迁移，同时又不会失去在云中工作的好处。“人们似乎认为只有在云中才能拥有 API 驱动的基础设施。事实是，您可以在自己的内部拥有一个 API 驱动的基础架构。我们选择 Triton 的一个决策是，我现在可以使用 Joyent 的公共云。如果我需要额外的容量，我只需开始在 Joyent 中旋转东西。”

[Docker](https://www.mirantis.com/software/docker/kubernetes/) 和 [Joyent](https://www.joyent.com/) 是新堆栈的赞助商。

专题图片:[特伦顿·凯利](https://www.flickr.com/photos/trentenkelleyphotography/ "Go to Trenten Kelley's photostream")创作的:[纽约大都会艺术博物馆喷泉](https://www.flickr.com/photos/trentenkelleyphotography/12761083963/)获得 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>