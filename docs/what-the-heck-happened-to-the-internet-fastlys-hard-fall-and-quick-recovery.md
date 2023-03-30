# 互联网怎么了？法斯特丽的艰难摔倒和快速恢复

> 原文：<https://thenewstack.io/what-the-heck-happened-to-the-internet-fastlys-hard-fall-and-quick-recovery/>

那不是很有趣吗？2021 年 6 月 8 日，许多互联网用户前往他们常用的网站，如亚马逊、Reddit、CNN 或纽约时报，除了“错误 503 服务不可用”和不祥的“连接失败”通知外，什么也没找到。发生了什么事？内容分发网络(CDN)迅速崩溃:非常严重。

一家只有 ISP 管理员知道的公司的服务故障是如何造成如此大的破坏的？简单。

当互联网以 ARPANet 的名字出现时，它的任务是提供容错和健壮的连接，即使发生了核战争。当它在 1993 年由于网络和[商业互联网交换(CIX)](https://www.hpe.com/us/en/insights/articles/the-real-history-of-the-modern-internet-1801.html) 而变得商业化时，其他特征变得重要起来。特别是，每个人都开始要求更快的性能和更低的延迟。

解决办法？CDNs。这些公司，除了 Fastly 以外，还包括市场领导者 Akamai 和 [Cloudflare](https://www.cloudflare.com/) ，都使用相同的基本技术来加快网络速度。他们从热门网站获取数据，并将其存储在靠近消费者的分布式缓存中。

如果这听起来对您来说很熟悉，即使您是云原生开发人员而不是网络管理员，这是有充分理由的。cdn 是最早依赖于边缘计算模型的商业模式之一。

这通常很有效。事实上，如今超过一半的互联网流量都是通过 cdn 传输的。当你现在访问一个网站时，你很可能不是直接从该网站获取数据，而是从最近的、受支持的 CDN PoP 获取数据。技术已经成熟，也很好理解。

那么，Fastly 到底哪里出了问题？

Fastly 工程和基础设施高级副总裁 [Nick Rockwell](https://www.linkedin.com/in/nickrockwell/) 解释道:“5 月 12 日，我们开始了一项[软件部署，该部署引入了一个 bug](https://www.fastly.com/blog/summary-of-june-8-outage) ，该 bug 可能由特定环境下的特定客户配置触发。”然后在“6 月 8 日早些时候，一位客户推送了一个有效的配置更改，其中包括触发该错误的特定情况，这导致我们 85%的网络返回错误。”

哎哟！

该公司在不到一小时的时间内通过紧急修复恢复了服务。但是，对于数以亿计的用户来说，这些仍然是太多分钟的死气沉沉。当天晚些时候，Fastly 开始部署一个永久性的错误修复。

快速，因为它继续部署其修复其网络的持久性有机污染物并没有说到底是什么问题。然而，我们知道，该公司正在“对我们在此次事件中遵循的流程和实践进行全面的事后检查；找出“为什么我们在软件质量保证和测试过程中没有发现 bug 以及“缩短补救时间的方法”

快速前瞻将对其底层基础设施进行根本性的安全改进。他们将通过使用 WebAssembly 和 Compute@Edge 的“隔离[功能来从头开始构建更大的弹性。”具体怎么做？罗克韦尔承诺，“随着我们朝着这个目标前进，我们将继续更新我们的社区。”](https://www.fastly.com/press/press-releases/fastly-expands-webassembly-investment)

这并不是 CDN 第一次崩溃并带走许多网站。2020 年，Cloudflare [出现了半小时的停电，覆盖了欧洲和美洲的大部分地区](https://www.zdnet.com/article/why-the-internet-went-haywire-last-week/)。那次停机是因为对一个物理问题的糟糕的一行修复。结果是连锁反应，最终导致全球近 20 家公司倒闭。

这不会是最后一次。cdn 已经悄然成为现代互联网的重要组成部分。正如最近的两个案例所显示的，它们是脆弱的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>