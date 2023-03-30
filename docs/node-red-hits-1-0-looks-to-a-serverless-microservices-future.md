# Node-RED 发布 1.0，展望无服务器、微服务的未来

> 原文：<https://thenewstack.io/node-red-hits-1-0-looks-to-a-serverless-microservices-future/>

经过六年的开发， [Node-RED](https://nodered.org/) 低代码、事件驱动的编程平台终于发布了 1.0 版本，此次发布为其用户带来了几个关键的新功能，以及更新的外观和更统一的白色标签实现的级联样式表(CSS)实现。

根据[的说法，Node-RED 项目负责人 Nick O'Leary](https://www.linkedin.com/in/nickoleary) 表示，达到 1.0 版本在一定程度上是一个象征性的信号，表明该工具不仅仅是一个玩具，而是可以投入生产了。

“尽管我们不是 1.0，但已经有很多公司在自己的产品和服务中采用 Node-RED。它在生产中被广泛使用。这其中很大一部分是为了反映项目的成熟度而达到 1.0，”O'Leary 告诉 New Stack。“Node-RED 性能稳定，适合生产。这不仅仅是一个你拿起五分钟就扔掉的玩具项目，而是一个提高工作效率的合适工具。”

Node-RED Node.js 发行版于 2013 年推出，专为物联网(IoT)而设计。作为一个经常发现自己成为定制硬件和软件的聚集地的空间，它需要某种类型的专业知识，消除要求硬件专家也是软件专家的痛苦似乎是一个显而易见的解决方案。因此，物联网领域的 Node-RED 可以提供可视化编程环境，并使硬件与软件的连接更加容易。在成立后不久，Node-RED 被 IBM 采用并开源，然后转移到 JavaScript foundation，最后是今天驻留的 [OpenJS Foundation](https://openjsf.org/) 。

虽然 Node-RED 最初是一个专注于物联网的工具，但 O'Leary 现在表示，用例已经扩展，其中有微服务的可能性，尽管可能需要一些变化来完全实现这个梦想。例如，现在，Node-RED 运行时和基于 web 的可视化编辑器打包在一起，甚至作为默认安装在 Raspberry Pi 操作系统上，但这可能需要改变，以真正拥抱[微服务](/tag/microservices)。尽管如此，Node-RED 1.0 的一个主要变化可以为未来的版本铺平道路。

根据 O'Leary 的说法，默认情况下向异步流(程序执行的线性运动)的转变不仅为开发人员提供了他们的应用程序将如何运行的确定性，而且还为未来的功能打开了新的大门。

“它在我们的路线图中实现了一些令人兴奋的新功能。通过完全异步，我们能够在节点之间做更多的工作。我们在路线图中即将推出的一个重要功能是，当消息在节点之间传递时，允许在运行时插入自定义代码，”O'Leary 说。例如，您可以创建一个分布式节点红色流，在编辑器中，您按照自己的逻辑想法绘制流，但在部署时，系统可以意识到这部分流在此设备上运行，但后一半流需要在另一台设备或云中运行

除了默认情况下的异步迁移，Node-RED 1.0 还带来了一个新的 Docker 容器映像。虽然该项目已经提供了一段时间的 Docker 图像，但 O'Leary 表示，它已经“略有衰退”，并与不同的东西不合拍，包括 Raspberry Pi 架构，新图像现在完全是最新的。

除了功能性之外，Node-RED 还具有新的外观，针对白标实现进行了彻底的 CSS，以及重新设计的 Node-RED 流库，其中包含 2200 多个可用于任何流的第三方插件。在时间节点——RED 已经面世，已经被下载了两百万次，但奥利里指出，达到第一个一百万用了五年时间，第二个一百万就发生在去年。

展望未来，O'Leary 表示，他可以看到 Node-RED 与 Knative 集成的一些可能性，Knative 是一个在无服务器环境中运行容器化工作负载的项目。目前，Node-RED 可以在任何你可以运行 Node.js 的地方运行，但他认为 Node-RED 有可能在 Knative 的不太短暂的无服务器环境中运行。他还说，他可以看到编辑器也用于其他用例，无服务器环境再次成为一个主要机会。

“我们拓宽了视野，因为我们认识到，作为一个工具，它适用于更广泛的开发人员、场景和行业，适用于任何类型的事件驱动应用程序，”O'Leary 说。“你可以用它轻松创建微服务。”

[https://www.youtube.com/embed/vYreeoCoQPI?feature=oembed](https://www.youtube.com/embed/vYreeoCoQPI?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>