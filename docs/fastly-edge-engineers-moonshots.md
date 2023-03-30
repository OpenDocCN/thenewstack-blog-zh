# Fastly 首席技术官负责边缘计算、招聘工程师和登月计划

> 原文：<https://thenewstack.io/fastly-edge-engineers-moonshots/>

[Moonshots 是 Fastly 的泰勒·麦克马伦](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen) 的炸弹

在这一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中， [Tyler McMullen](https://www.linkedin.com/in/tylermcmullen/) ，领先的内容交付网络(CDNs)[Fastly](https://www.fastly.com/)的联合创始人兼首席技术官，与我们坐在一起讨论他对速度的热情，为什么他的工程师需要花部分时间在不太可能成功的项目上，以及经验丰富的工程师会带来什么(除了他们的 C 和 Perl 知识)。

每天，互联网上有 10%的请求快速通过。基于他之前与 TNS 记者 Alex Handy 的对话，McMullen 讨论了边缘计算的业务用例，并分享了“非常大的”Fastly 堆栈。

它的堆栈分为数据平面和控制平面，客户的数据通过数据平面流动，控制平面运行数据平面。他说，关键在于使用高速反向代理服务器 [Varnish](https://varnish-cache.org/) ，以及允许公司工程师在边缘编写代码的 Varnish 控制语言(VCL)。

对于数据平面，该公司走老路，使用他们自己的服务器，遍布全球。这使得该公司能够控制自己的服务器和交换机，并为其编写了大量专有软件来优化其交换机和路由器。边缘计算允许公司简单地通过自己的堆栈传递客户的数据。

另一方面，控制平面在云中，大部分在[谷歌云平台](https://cloud.google.com/kubernetes-engine)上，但也有一些在内部运行。虽然这些都不是开源的，因为他们所做的规模对大多数企业都没有用，但 Fastly 对开源平台做出了广泛的贡献，包括在 Fastly 托管“几十个”开源项目，包括免费的 PyPy、Ruby 和 Varnish。

由于其堆栈的广度，该公司的代码在各种各样的语言。除了 VCL，它还使用了 Ruby、C、Perl、Python 和 Rust。

所有这些复杂性意味着该公司更喜欢招聘有经验的人，而工程师的平均年龄远远超过 30 岁。McMullen 说，公司能够雇佣更多有经验的工程师，部分原因是因为公司相信工作与生活的平衡。“大多数成年人不会在凌晨两点上班，”他说，“所以我们不会在这种情况下计划我们的时间表。”

有经验的工程师带来的是上下文和模式匹配的能力。他解释说，随着时间的推移，任何语言的程序员都会学到系统级的知识，这些知识可以移植到其他语言中。“他们会说‘我以前见过这种不同的形式，所以我们来谈谈吧，’”他说。

但真正让麦克马伦兴奋的是在 Fastly 保持 moonshot 心态，他认为大多数公司都应该这样做。他说，创办一家新公司本质上是一件轻而易举的事，但当公司稳定下来后，“你就变成了你一开始试图取代的竞争对手。”他认为这创造了一种精英文化。

因此，他要求所有工程师都参与登月计划，他将登月计划定义为追随那些不太可能成功的想法。该公司通常同时进行六个左右的登月项目。“不要太多，以至于成为人才和时间的巨大浪费，但也不要太少，以至于所有人都会同时失败，”他笑着说。

CTO 办公室的重点是启动 moonshot 项目，这些项目由跨职能团队发起和选择。他们从这个问题开始:我们的用户会发现什么是有用的，但永远不会想到的？

提出项目想法是 McMullen 真正欣赏他的工程团队的经验水平和广度的一个方面。他最喜欢的事情之一是让这些人在同一个房间里，看看他们能找到什么样的模式，以及他们如何将这些线索联系在一起。

听一听麦克马伦对如何比平常移动得更快的深入研究，他对来自经验的专业知识的极大尊重，以及他们现在正在进行的登月计划。

### 在这个版本中:

[4:49:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=4:49) 边缘计算的使用案例。
[7:46:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=7:46) 速度无服务器服务。
[8:13:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=8:13)fast ly 栈里有什么？
[11:49:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=11:49) 运行控制平面的复杂度。
[14:50:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=14:50) 随着工程师的平均年龄超过 30 岁，视角和模式匹配也随之而来。
[18:34:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=18:34) 斋戒内的月食。
[22:36:](https://thenewstack.simplecast.com/episodes/moonshots-are-the-bomb-with-fastlys-tyler-mcmullen?t=22:36) 为什么 Fastly 一直成功。

谷歌是新堆栈的赞助商。

由 [Chris Child](https://unsplash.com/photos/ploYEL9KbrQ?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/search/photos/moon?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>