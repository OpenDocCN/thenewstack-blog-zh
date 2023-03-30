# Docker 变通方法:Bricks 是如何获利的

> 原文：<https://thenewstack.io/the-docker-workaround-how-profitbricks-did-it/>

新赞助商 ProfitBricks 在这里有一个故事，讲述了搭建 Docker 托管平台的复杂性。这是一项正在进行的工作，但可能值得一看。他们为新的 Stack 阅读器提供了独家的早期访问邀请码，以尝试这项服务

**. **

使用代码

**5cb2xw**

到

[deploy your Docker containers](https://www.profitbricks.com/docker)

并免费获得 2500 个 CPU 核心小时。让我们知道你的想法。谢谢，亚历克斯。

码头工人。这就好像你无法逃避阅读这个名字或听到集装箱的奇迹。在基础设施托管领域，这个问题变得越来越普遍，需求也越来越迫切:在部署和管理 Docker 环境时，用户可以轻松利用哪些解决方案？

## 2015 年 Docker 生态系统的野生世界

在评估如何构建 Docker 交付和集群平台时，我们面临的一些早期问题包括查看市场上的各种竞争技术:Apache Mesos、Google Kubernetes 和 Docker 本身的各种组件。过去是，现在仍然是，很难将这些技术划分为代表其核心功能的领域和可能被认为是边缘的领域，并且很难确定哪些领域有重叠，哪些领域没有重叠。同样明显的是，许多项目太新，例如 Kubernetes 而其他项目，比如 Mesos，最近才开始支持 Docker (Mesos 0.20.1)。

您想简单地启动一个 Docker 环境，跨机器，部署容器，管理卷和扩展。为了确保我们能够满足这一需求，我们剥离了除了 [ProfitBricks](https://www.profitbricks.com/) 基础设施、其 RESTful API、Docker 和配套组件之外的所有东西:[机器](https://docs.docker.com/machine/)和 [Swarm](https://docs.docker.com/swarm/) 。当我们构建 Docker 托管平台时，我们不想在开发和学习阶段过早引入太多的复杂性。

> 虽然使用 pure Docker 降低了复杂性，但它增加了我们在开发过程中处理的问题的数量，并且在我们积极解决自己的错误时仍然需要应对。

没有什么比重构或燃烧来自其他活动项目的问题更令人沮丧的了。但是，这也是我们签约的目的:我们需要建立一个平台，让客户能够加速、管理和跨越他们的容器。

## 每个人房间里的大象:码头保安

安全性是一个普遍且绝对的需求，所以当我们配置 Docker 守护进程时，我们会为它绑定一个证书；然而，我们也有一个常见的场景，我们必须撤销相同的自签名证书。我们遇到的问题是，为了让您撤销证书并让 Docker 守护进程遵守该撤销，您需要在 localhost 上重新配置并重启守护进程，这并不理想。此外，没有用于这些类型的管理任务的 API，需要我们自动进入系统进行更改，然后退出。目前，还没有解决方法——至少，我们无法找到一个能够以我们希望的方式解决这个问题的方法。这给我们留下了一个特别的过程，外壳，重新配置和重新启动。

## Docker 图片——不像我们希望的那样清晰

我们遇到的一个问题是，我们只能想象其他人遇到过的问题，即预先存在的映像的相对不透明性，以及容器对其成功运行的要求。我们的应用程序的一个方面是从 DockerHub 中提取图像及其相应标签的列表。然后，我们将配置预加载到界面中。

我们开始遇到这种情况，一些容器需要在运行时创建环境变量、链接或卷，但是这些需求的信息很少(除非在 docker 文件中，如果存在的话)，并且没有真正的方法自动吸收它们。虽然这不是一个直接的 Docker 问题，但它确实会引起头痛，有时会令人困惑，为什么一个容器就是不旋转，或者继承了一个我们期望为空的环境变量。我们还发现了一些问题，一些预构建的容器——甚至是来自 MySQL 等官方存储库的容器——为容器中的可选环境变量设置了默认值，但用户并不知道哪些是可选的，哪些是必需的，以及哪些预定义值可能需要更改，例如 MySQL 中的密码处理。

## 自动扩展和持久卷—现在可用于 Docker 容器

为了克服 Docker 中自动伸缩的不足，我们开发了自己的系统来监控底层主机系统的健康状况，以确定它是否接近资源耗尽。当容器密度增加时，我们会增加内核和内存。当存储需求增加时，我们会调整卷的大小。设置限制，代理会遵守这些限制。如此等等，确保你总是有一个健康的码头环境。

我们发现构建 Docker 平台的另一个挑战是如何处理持久卷。Docker 本质上是短暂的，但是应用程序(如数据库)通常需要数据在系统重启后保持不变。当然，让我们丢失状态，但是我不想丢失我的 PostgreSQL 数据。同样，在这里我们组合了功能，并允许用户添加多达 8 个容量高达 2TB 的卷。这些卷也可以在主机之间移动。

## Docker 主机世界的下一步是什么？

我们仍在努力解决多个问题——包括我们自己的问题和我们所依赖的不同 Docker 项目强加给我们的问题——但我们看好 Docker 在容器生态系统和云计算领域的变革性力量，并为此做好了准备。随着我们不断改进平台，添加 Swarm 等功能，我们将继续在社区中与 Docker 分享我们的成长烦恼和成功。 [](https://thenewstack.io/wp-content/uploads/2015/05/achim_weiss-1.jpeg)

[![profitbricks-achimweiss](img/f1066307e078df7396c90de128196692.png)](https://thenewstack.io/wp-content/uploads/2015/05/profitbricks-achimweiss.jpg) 阿奇姆·维斯是 ProfitBricks 的首席执行官和联合创始人。1995 年，阿齐姆·韦斯中断学业，与人合伙创办了网络托管公司“Schlund+Partner”。“Schlund+Partner”公司后来成为第一个虚拟主机产品线。从 1995 年到 2008 年，他担任多个项目的技术总监:世界上最大的 web 托管平台、第二大 DSL 平台、视频点播交付网络、欧洲最大的电子邮件后端以及通用计费系统。2010 年，他与人共同创立了云计算 IaaS 提供商 ProfitBricks，该公司如今是领先的提供商之一。ProfitBricks 为所有 IT 用户提供了无痛苦的云体验，无需学习曲线，并拥有灵活的云服务器和网络，用于可视化控制云的集成数据中心设计工具，以及最佳的性价比。

ProfitBricks 是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/elpadawan/8505316460/in/photolist-dXzYgf-4hAHcM-7v53AU-bF4pSB-boZDaK-6XWdi6-8J2JZX-atXxSw-4hEGFS-7vh6ca-4hEH4L-7mhfz-dpeLbo-85rnJg-5JaiGa-dpeKKC-sT4TwA-4hAC5n-ego2LR-5Je4mS-dpeAJB-fZwb7n-fpYMmd-bH1KXT-rKPbLg-dPhf8x-82TPWp-5J9Moa-hbcHhU-6fJMZt-9sF9uw-7Eu8sy-5JaiE6-7v25ZK-a6HdYw-btt1TY-a7ictd-qBKtNb-adXFps-7vjWih-5Je4k9-73vgJm-9m269C-5Je4xU-a8BTwM-6ATFb5-fjLhMa-b9K1xx-dFCSDn-7v1eQ2)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>