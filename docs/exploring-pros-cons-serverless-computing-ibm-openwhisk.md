# 是什么让 IBM OpenWhisk 与众不同？公开

> 原文：<https://thenewstack.io/exploring-pros-cons-serverless-computing-ibm-openwhisk/>

随着这么多无服务器计算提供商的出现，是什么让 IBM OpenWhisk 与众不同呢？首先，IBM 的 OpenWhisk 作业可以由外部事件触发，而不仅仅是那些来自云提供商自己的基础设施的事件。

“我们有一个开放的活动提供商生态系统。其他大多数平台都不允许你引入自己的活动提供商。IBM 首席架构师和杰出的工程师 [Michael Behrendt](https://www.linkedin.com/in/michael-behrendt-a8548a6) 解释道:“如果你有一个自己构建的或者你想使用的事件提供者，你就不能把它们插入其他平台，而有了 OpenWhisk，你就可以了。

Behrendt 是在最新一期的《新堆栈制造商》播客《T4》中说这番话的。IBM 技术项目经理[Andreas Nauerz](https://de.linkedin.com/in/nauerz)博士参加了在德国法兰克福[云铸造峰会](https://thenewstack.io/?s=cloud+foundry+europe+summit+2016)上举行的采访。

[探索使用 IBM OpenWhisk 进行无服务器计算的利弊](https://thenewstack.simplecast.com/episodes/exploring-the-pros-and-cons-of-serverless-computing-with-ibm-openwhisk)

Behrendt 解释说，就像 AWS Lambda 一样，OpenWhisk 在被某种事件触发时会执行一个功能，比如新文件被添加到存储服务中。然而，与 Lambda 不同，OpenWhisk 可以由任何外部 API 驱动的事件触发，[比如出现在 RSS 提要中的新项目](https://github.com/openwhisk/openwhisk/blob/master/docs/feeds.md)。

与 Lambda 不同的是，除了 IBM Bluemix 上的托管版本之外，OpenWhisk 还以开源软件的形式提供。开源版本允许组织建立他们自己的无服务器平台，如果他们想走这条路的话。

Nauerz 指出，认知工作负载、照片识别、文本识别和视频识别是无服务器架构处理得很好的例子。

部署在无服务器架构上的许多工作负载都是短期进程。“如果您需要大量控制，通常会选择虚拟机。如果您不需要这种级别的控制，您可以选择无服务器模式，在这种模式下，您不必担心操作系统缓存、监控基础架构或扩展。在我看来，这不是一个好或坏的场景，而是理解利弊以及在控制和抽象之间进行权衡，”Behrendt 说。

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

Cloud Foundry 和 IBM 是新堆栈的赞助商。

专题图片:Andreas Nauerz 博士(左)，Michael Behrendt。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>