# 微容器:Iron.io 缩小 Docker 容器的新技术

> 原文：<https://thenewstack.io/microcontainers-iron-ios-new-hack-shrink-docker-containers/>

在仍处于开发阶段的容器世界中，似乎每次你回头时都会有新的功能发布。工程师们正试图解决如何让容器运行得更快、更智能、占用更少资源的问题。

本周的黑客来自平台即服务(PaaS)公司 [Iron.io](https://www.iron.io) 。一句话:微容器。

上周，Iron.io 的联合创始人 [Travis Reeder](https://twitter.com/treeder) [解释了如何通过使用他们称为微容器的东西来缩小 Docker 映像](https://www.iron.io/blog/2016/01/microcontainers-tiny-portable-containers.html)，这是继 12 月份关于[如何构建自己的 Docker 映像](https://www.iron.io/blog/2015/12/how-to-build-your-own-docker-images.html)的帖子之后的又一篇文章。

“微容器仅包含运行应用程序和应用程序本身所需的操作系统库和语言依赖。“仅此而已，”Iron.io 博客说道，该博客还包含明确的说明和 GitHub 页面的链接。

使用 Docker 的官方存储库作为标准容器语言会产生最小 643 MB 的节点映像。通过简化连接到节点映像的 cruft 并仅安装基本组件，他们将这些“微型便携式 Docker 容器”中的映像从 644 MB 减少到 29MB 除了这一令人印象深刻的尺寸缩减之外，还有其他好处。

一个优势是配送速度更快。由于尺寸较小，从 Docker 注册表下载图像要快得多，分发到不同的机器上也是如此。

此外，该公司声称这种设计提高了安全性。“容器中更少的代码/更少的程序意味着更少的攻击面。而且，基本操作系统可以更加安全……这些好处类似于[单核](https://en.wikipedia.org/wiki/Unikernel#Benefits_and_drawbacks)的好处，没有任何缺点，”Reeder 写道。

Iron.io 在 Docker 中有一个[基础映像库](https://github.com/iron-io/dockers)，用于 GitHub 上所有主要语言。“这些都有一些优化，使它们尽可能小，我们定期更新它们，这使得它们比自己做稍微好一点的选择，”博客声称。

使用 Iron.io 基本映像，可以使用此 Dockerfile :
构建上面用于节点应用程序的 docker file

```
FROM iron/node
WORKDIR  /app
ADD  .  /app
ENTRYPOINT  [  "node",  "server.js"  ]

```

对微型容器的最初反应似乎是阳性的。

“这似乎解决了我试图使用个人码头工人来运行微服务的最大问题之一，”_Marak_ 在黑客新闻上热情洋溢地说。“过去的实验证明，将一个微服务请求匹配到一个 Docker 实例是不可行的。每个码头的规模需要垂直扩展每个集装箱的微服务，这并不理想。”

用户 lox 指出，“当然，如果你有 ruby 或 node 应用程序，你最大的空间占用仍然是你的包。”

同样在容器新闻中，谷歌软件工程师[布兰登·伯恩斯](https://github.com/brendandburns)在 Kubernetes 博客上发布了[正在进行的容器使用调查](http://blog.kubernetes.io/2016/02/state-of-container-world-january-2016.html)的结果。不可否认，这项调查是有限的——向 Kubernetes 工程师的 twitter 粉丝发出的调查问卷只有 119 个回复者，但仍然很有趣。

绝大多数受访者(80%)将容器用于开发，但只有 50%的人将它们用于生产。这种情况将很快改变，因为 78%的人表示他们计划“很快”将集装箱投入生产

大多数受访者在笔记本电脑上部署容器(53%)，其次是私有虚拟机，再次是物理基础架构(33%)，31%在公共云虚拟机上。

但是，提供最有趣信息的是针对使用容器的挑战的自由文本答案。

除了安全性，这是一个始终关注的问题，其他自由文本答案被分为开发复杂性、不成熟性、复杂性和数据的主要类别。

谈到开发的复杂性，一位回答者写道:“掌握整个基础设施堆栈和最佳实践需要大量的知识，从部署/更新 kubernetes 到底层网络。”

受访者抱怨容器系统不够成熟，抱怨缺乏全面的不恰当标准，以及 CI 支持不佳。“许多工具仍处于早期阶段。”

另一个批评涉及系统的复杂性。“聚类还是太难了，”一位受访者写道。[据上个月](https://thenewstack.io/google-now-supports-red-hat-openshift/)报道，谷歌上个月宣布与红帽合作，部分是为了解决他们客户的复杂性问题。

最后但同样重要的是，对数据存储和持久性的抱怨。

对于使用容器的系统管理员来说，这些都不是新闻。但或许像 Iron.io 的微容器这样的新兴工具会解决这些问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>