# 安全性必须是容器部署的重中之重

> 原文：<https://thenewstack.io/tns-analysts-show-97-departing-container-island-joyent/>

开发者开始拥抱容器，无论是 Docker 容器、Kubernetes pods 还是 Amazon EC2 实例。因此，容器安全性是企业在考虑容器是否适合其堆栈时最关心的问题之一。

 [Joyent 首席技术官 Bryan Cantrill

Bryan Cantrill 是 Joyent 的首席技术官，负责监管 Triton Elastic Container 服务以及 SmartOS、SmartDataCenter 和 Node.js 平台的全球开发。在加入 Joyent 之前，Bryan 在 Sun Microsystems 担任杰出的工程师，在那里他从事了十多年的系统软件工作。特别是，他参与设计并实现了 DTrace，这是一种用于生产系统动态检测的工具。Bryan 还参与创建了 Sun 的 Fishworks group，在那里他为 Sun Storage 7000 系列设备设计并实现了基于 DTrace 的分析工具。](https://www.joyent.com/) 

对于首席技术官和 IT 管理团队来说，重点是确保这些容器在部署到生产就绪系统上时既可见又安全。将容器的灵活性引入今天的企业一直是像 [Joyent](https://www.joyent.com/) 这样专注于云的组织平台的长期目标。

在这一集的[中，新的堆栈分析师](https://thenewstack.io/podcasts/)嵌入在下面，我们深入讨论了大规模容器的安全性，硬件可视化如何影响容器安全性，以及 Joyent 如何促进容器在生产中的持续使用。New Stack 创始人 [Alex Williams](https://twitter.com/alexwilliams) 与共同主持人和[电子书](https://thenewstack.io/ebookseries/)编辑 [Benjamin Ball](https://twitter.com/benballjr) 一起与 Joyent 首席技术官 [Bryan Cantrill](https://twitter.com/bcantrill) 交谈，听听他对这些问题和更多问题的想法。

在今年早些时候的 Twitter 民意调查中，Joyent 发现，对于超过 50%的技术行业来说，将容器投入生产的最大障碍是安全性。简而言之:企业如何确保他们的容器是安全的，同时他们的开发人员和 IT 团队成员能够以这样一种方式连接它们，即服务仍然可以通过他们的基础设施被发现。

对于每一个关于安全性的担忧，Cantrill 指出，过去和现在都有更紧迫的问题:“如果你担心安全性，你可能不知道这些堆栈的容器网络带来的灾难。安全性是您需要首先解决的事情之一，尽管有许多不同的关注点。这很难，因为当你建立一个系统时，(安全)需要在约束中设计。很难改造，”坎特里尔说。

[#97:安全必须是集装箱部署的重中之重](https://thenewstack.simplecast.com/episodes/97-security-must-be-a-top-priority-with-container-deployments)

Joyent 采用了多租户方法来实现容器安全。因此，两个容器可以作为一个堆栈中面向互联网的部分协同工作，而不会对其他容器或系统产生负面影响。所有的 Joyent 容器都可以在网络上被发现，这意味着相对于将容器隔离在它们自己的虚拟机孤岛上，整体挫败感更少。

“有时，您会看到容器在硬件虚拟化层中被分隔开，这可以防止容器相互干扰。通过这样做，您已经创建了容器旨在解决的问题。Cantrill 继续解释道:“如果您的容器位于虚拟机孤岛上，或者依赖于硬件虚拟化，就会重现所有这些问题。

[https://www.youtube.com/embed/sw8a7BW-66g?feature=oembed](https://www.youtube.com/embed/sw8a7BW-66g?feature=oembed)

视频

在匆忙部署代码的过程中，开发人员可能会发现自己不得不回到他们的代码中，以加强其安全性或解决安全问题。对坎特里尔来说，这是错误的方法。“那可能是进行这种思考过程的错误时间；你需要在一开始就具备这一点，”他说。为了解决这个问题，Joyent 已经实施了一个容器命名服务，它允许在本地运行的同时发现和提供容器。Cantrill 指出，在本地运行具有本地容器和安全基础设施的容器，对于开发人员有能力转移和解决其他问题是至关重要的。

“这不仅仅是安全，而是建立一个安全系统允许你做的所有事情，”Cantrill 说。

Docker 和 Joyent 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>