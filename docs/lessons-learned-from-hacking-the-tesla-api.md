# 从入侵 Tesla API 中吸取的教训

> 原文：<https://thenewstack.io/lessons-learned-from-hacking-the-tesla-api/>

上周，特斯拉[宣布](http://www.teslamotors.com/blog/all-our-patent-are-belong-you)不会对“善意”使用其专利的人提起诉讼但该公司并不总是对其技术如此开放。其特斯拉 Model S API 从未打算在公开，但几乎从一开始，特斯拉车主就开始在 GitHub 上记录其 API 调用，最终在[养蜂平台](http://docs.timdorr.apiary.io/)上构建他们自己的 API。

在旧金山的 API Days 上，养蜂场首席执行官 Jakub Nesetrill 讨论了特斯拉的故事如何表明在像汽车这样的东西的背景下，真的没有私有 API 这种东西。Nesetrill 在会议上接受采访时说，特斯拉的例子表明了私有 API 可能从一开始就存在的问题。在特斯拉的案例中，查看 API 的人了解到，它并不适合 HTTP 协议，而且 GET 方法在用于具有现实后果的 API 操作(如解锁汽车和打开暖气)时存在问题。

[黑客入侵特斯拉 API](https://thenewstack.simplecast.com/episodes/hacking-the-tesla-api)

更令人不安的是，安全分析显示，特斯拉建立了自己的用户认证，但这并不符合强大的安全实践。该协议还不完善。

乔治·里斯在去年八月的一篇[文章中详细描述了 API 可以做什么以及如何被利用。](http://broadcast.oreilly.com/2013/08/authentication-flaws-in-the-tesla-model-s-rest-api.html)他写道:

*   *除了可信的 SSL 连接(次要的)之外，它不能在任何通道上安全运行*
*   *需要与第三方共享用户密码(主要)*
*   *不存在使用活动令牌对应用程序进行编目的机制(重要)*
*   *只有一种不一致的钝器机制可用于撤销对受损应用程序的访问(中度)*
*   *令牌在 3 个月内自动过期会鼓励应用程序不正确地存储您的电子邮件和密码(显著)*

Apiary 已经记录了 70，000 个 API。大多数都是由刚开始开发 API 的公司开发的。第一次尝试时，公司在获得正确的 API 设计方面有问题，这是一个问题。特斯拉是汽车领域提供可编程服务的领导者，做了许多正确的事情，如远程更新。但是新的 API 开发者经常试图使它变得简单并偷工减料，这可能会使最终用户难以操作他们自己的机器。

“底线——对于汽车，不要试图重新发明轮子,”Nesetrill 说。开发一个私有的 API 是没有意义的，特别是当有一大群有动机的用户为了他们自己的目的将它文档化并创建一个更适合他们自己的需求的时候。

特色图片[通过](https://www.flickr.com/photos/jacksnell707/10210963236/in/photolist-fdy1of-buuigx-fJrDVY-8kjqBn-buui2p-6XEwCZ-e9URFd-daNfxB-6drUa6-ag4iGF-f1yaKM-f1Nqkd-f1y5Fg-32DLSF-fdzUEL-fdkwRp-gwHiRy-8d2Hi9-32DKKx-32DL3F-32DN7t-32JidA-6C7nph-8d2FT3-8cYqqx-8cYpjR-8cYp7e-8cYpHM-gyiRCh-9gAHj1-6C3fbV-m5kB24-6ESeAq-6C3ft8-99JjqW-99Jj9E-99JjwY-fYw7Fd-8TECxm-32JkyY-99JjiQ-32Jk41-9UFq4U-32Jjp3-32DNVe-32DMz6-32DSbZ-RwftL-cgDGMG-9Rto8p) Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>