# CoreOS 称 Docker“存在根本缺陷”，发布替代原型

> 原文：<https://thenewstack.io/coreos-calls-docker-fundamentally-flawed-releases-prototype-alternative/>

CoreOS 称 Docker 已经偏离了其作为容器模块化构建模块的最初愿景，并于周一在 GitHub 上发布了一款名为 Rocket 的原型替代产品。

虽然它指出 CoreOS 的联合创始人/首席技术官布兰登·菲利普斯(Brandon Philips)是 Docker 治理委员会的成员，但它不同意 Docker 的方向。

“我们认为 Docker 将成为一个我们都能认同的简单单位。不幸的是，一个简单的可重用组件并不能解决问题。Docker 现在正在开发工具来启动云服务器、集群系统和各种功能:构建映像、运行映像、上传、下载，最终甚至覆盖网络……”CoreOS 首席执行官 Alex Polvi 在[发布 Rocket](https://coreos.com/blog/rocket/) 时写道。

“我们应该停止谈论 Docker 容器，而开始谈论 Docker 平台。它不会像我们想象的那样成为简单的可组合构件。”

它要求在命令行工具上输入运行它所谓的“应用容器”，特别是它添加到元数据服务中的安全功能。

这篇文章称 Docker 过程模型——通过一个中央守护进程发送所有东西——是“有根本缺陷的”,这使得分支项目站不住脚。

“修复 Docker 本质上意味着重写项目，同时继承现有实现的所有包袱，”Polvi 写道，并补充道，“我们不能真诚地继续支持 Docker 的破碎安全模型，而不解决这些问题。此外，在过去的几周里，Docker 已经展示了它将在基本的容器管理之外加入许多设施，将它变成一个复杂的平台。我们的主要用户拥有他们想要集成容器的现有平台。我们需要填补那些只想安全、便捷地运行集装箱的公司的空白。”

CoreOS，最近被 InfoWorld 称为 Docker 的[首选发行版，计划继续支持它。同时，Rocket 不会局限于 CoreOS，可以运行任何风味的 Linux。](http://www.infoworld.com/article/2844708/linux/coreos-game-changer-data-center-cloud.html)

与此同时，在周一的一篇博客文章中，Docker 首席执行官 Ben Golub 声称“只有少数厂商”不同意 Docker 的总体方向，并质疑 CoreOS 发布的动机和时机。

“由于 Docker 是开源的，并且基于 Apache，人们可以根据自己的目的自由使用、修改或改编 Docker。他们可以自由地使用 Docker 作为单一容器格式。他们可以自由构建插入 Docker 的更高层次的服务。当然，他们可以自由地推广替代标准的概念，正如 Rocket 背后的人所选择的那样，”他写道。

“虽然我们不同意火箭宣布的一些论点和有问题的言论和时机，但我们希望我们都能继续以对用户和开发者最好的东西为指导。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>