# CircleCI 的技术架构是为可伸缩性而构建的

> 原文：<https://thenewstack.io/circieci-technical-architecture-build-for-scale/>

[CircleCI 的技术架构是为可扩展性而打造的](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability)

像许多创业公司一样， [CircleCI](https://circleci.com/) 一开始是一个整体，运行在亚马逊网络服务(AWS)上。但是，当到 2015 年公司的成功需要更大的可扩展性时，要保持这个庞然大物的运行，能做的就只有这么多了。在新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 中，TNS 创始人 [Alex Williams](https://twitter.com/alexwilliams) 与 CircleCI 的首席技术官 [Rob Zuber](https://www.linkedin.com/in/robzuber) 进行了一场直播讨论，以深入挖掘该组织背后的架构工作。

CircleCI 在 2011 年建立了自己的作业调度程序，因为市场上没有符合他们需要的东西。然而，到 2015 年，该公司有意识地决定使用第三方工具，而不是构建自己的工具，包括[云本地计算基金会的](https://www.cncf.io/) Kubernetes 容器编排器、Docker 容器、AWS 和 HashiCorp 的 [Nomad](https://www.nomadproject.io/) 调度器。在 AWS 上管理 Kubernetes 时，Zuber 指出，CircleCI 面临一些问题，因为 Kubernetes 没有得到 AWS 的官方支持，但总体经验是积极的。

“就管理我们自己的基础设施而言，对我们来说重要的是生态系统，”他说。“Kubernetes 是一个调度程序，但它是人们用来帮助我们完成工作的所有工具。很明显，就获得的支持数量而言，Kubernetes 是一个领导者。”

[https://www.youtube.com/embed/eNoB6gohAY8?feature=oembed](https://www.youtube.com/embed/eNoB6gohAY8?feature=oembed)

视频

### 在这个版本中:

[1:40:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=1:40) 探索 CircleCI 背后的技术架构和基础设施。
[6:23:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=6:23)circle ci 如何实现从单一基础设施的转型。
[11:12:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=11:12) CircleCI 在其基础设施中使用游牧民和 Kubernetes。
[18:07:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=18:07)circle ci 如何在 AWS 上管理其 Kubernetes 基础设施。
[21:35:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=21:35)circle ci 用来管理其基础设施的附加工具。
[23:14:](https://thenewstack.simplecast.com/episodes/circlecis-technical-architecture-is-built-for-scalability?t=23:14) 探索 CircleCI 2.0 平台的发展方向。

云本地计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>