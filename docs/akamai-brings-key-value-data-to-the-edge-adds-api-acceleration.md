# Akamai 将关键值数据带到边缘，增加 API 加速

> 原文：<https://thenewstack.io/akamai-brings-key-value-data-to-the-edge-adds-api-acceleration/>

内容交付网络(CDN)服务提供商 Akamai 扩展了其边缘无服务器计算平台 [EdgeWorkers](https://developer.akamai.com/akamai-edgeworkers-overview) ，随着本周推出其 [EdgeKV](https://developer.akamai.com/edgekv) 键值存储，增加了边缘的数据。

今年早些时候发布到[测试版](https://blogs.akamai.com/2021/03/serverless-storage-at-the-edge-edgekv-beta.html?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+TheAkamaiBlog+%28The+Akamai+Blog%29)，EdgeKV 现在已经普遍可用，并允许开发者在边缘访问轻量级数据库，而不是在数据中心。在对其产品的最新[更新](https://blogs.akamai.com/2021/06/platform-update-akamai-boosts-edge-application-power-expanding-possibilities-for-developers.html)中，Akamai 还推出了 API 加速，将专用硬件与优化的 API 路由和 GraphQL 缓存相结合，以大规模提高可靠性和性能。

Akamai 的边缘计算高级产品经理 CJ 阿内森说，EdgeKV 是对 Akamai 的边缘计算的补充，该公司以前以预定功能的形式提供了边缘计算，但最近更新了 EdgeWorkers 的无服务器模型，允许用户在边缘运行 JavaScript。

“能够在边缘运行 JavaScript 很棒，你可以执行一些代码，但所有这些都必须在内存中运行，它必须独立运行，”阿内森说。“我们需要为此添加一个数据存储，这样客户就可以在边缘写入或读取数据，从而减少到达原点的延迟。拥有边缘计算固然很好，但其中一部分是访问数据，甚至是写入数据。这让我们可以在边缘做更多的重活。”

键值存储是一种无模式数据库，旨在存储非结构化或半结构化数据。没有复杂的查询语言，相反，用户查找一个键，然后返回一个值。值可以是任何东西，从简单的字符串到嵌套的 JSON 到 base64 编码的二进制文件，但是与关系数据库相比，它的简单性减少了延迟。阿内森解释说，在边缘增加一个键值存储意味着公司可以更快地为用户提供更个性化的体验。

“如今的数字体验非常强劲。品牌希望给每个用户最好的体验，个性化的体验，来吸引他们，让他们参与进来，”他说。“EdgeKV 可以存储有关用户、地区或您想要的任何内容的基本值，然后 EdgeWorkers 可以调用这些数据，实时重写网页，进行动态内容组装，并为该用户定制页面。这真正将基于原点的个性化计算的能力带到了边缘，减少了您过去在个性化方面的所有损失。”

阿内森进一步解释说，EdgeKV 可以被认为是“一个全局写入和一个本地读取”，Akamai 提供 10 秒的服务级别协议(SLA)的全局数据同步。“你需要的数据总是在你的边缘服务器上，但我们继续在全球范围内同步和写入，”他说。

除了 EdgeKV，Akamai 还推出了 API 加速，Akamai 的高级产品营销经理亚历克斯·巴尔福德(Alex Balford)将其描述为对最近 API 请求同比增长 30%的回应，这使得 Akamai 的流量在 2020 年超过 300 万亿个 API 请求。

“API 已经存在很长时间了，但随着组织继续进行数字化转型，他们正在从整体服务转向微服务，”Balford 说。“他们正在他们的云基础架构中部署微服务，他们还在边缘部署更多。所有这些都通过 API 进行通信。我们有许多使用 API 的大客户，他们需要出色的性能和高可靠性来满足流量需求。”

虽然 API 请求可能是小事务，但 Balford 解释说，它们通常是高度计算密集型的——在很短的时间内建立和拆除传输层安全会话。因此，他们可以受益于 Akamai 通过其 API 加速为他们提供的专用硬件、预留容量和优先路由。

展望未来，Balford 表示 Akamai 不仅希望帮助客户发现 API，还希望将 Akamai 的 API 解决方案与其安全产品相集成。至于 EdgeKV，阿内森表示，Akamai 将寻求通过增加一个“更强大，或更传统的边缘数据库”来增强其边缘产品

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>