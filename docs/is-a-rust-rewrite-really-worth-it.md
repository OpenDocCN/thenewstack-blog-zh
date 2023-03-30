# 一个 Rust 重写真的值得吗？

> 原文：<https://thenewstack.io/is-a-rust-rewrite-really-worth-it/>

“一个 Rust 重写真的值得吗？”这不仅仅是一个绕口令，这是一个让工程师们夜不能寐的难题。这种潜在的性能提升是否值得与一种非常受欢迎的快速发展的语言搏斗呢？

当然，对于重写 [Rust](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/) 最终会给你的项目和团队带来多大的回报，没有简单的答案。但是有很多吸引人的故事，关于为什么团队考虑重写 Rust，他们走的路，以及它最终如何为他们工作。

P99 CONF ，一个为痴迷于所有性能的工程师举办的免费虚拟会议，正在成为分享这些故事的首要场所。该会议致力于探索顶级工程师如何解决他们最棘手的高性能、低延迟挑战。毫不奇怪，Rust 总是在议程中占据显著位置。去年推特上讨论最多的会议包括 Bryan Cantrill 关于“ [Rust 和低延迟系统的未来](https://thenewstack.io/bryan-cantrill-on-rust-and-the-future-of-low-latency-systems/)”的旋风式主题演讲，以及 Glauber Costa 对“ [Rust 是安全的”的深入探讨。但是快吗](https://www.p99conf.io/session/rust-is-safe-but-is-it-fast/)？”它着眼于异步 Rust 开发陷阱，这些陷阱可能会影响您击中低 p99 的能力。

就 Rust 重写困境而言，Twitter 的布莱恩·马丁是去年 P99 CONF 的明星——我们期待马克·格里特在 Go 中避免 Rust 重写的故事今年能引起同等的兴趣和讨论。以下是对两者的快速浏览。

## 哎呦！“我用 Rust 重写了它”Twitter 软件工程师布莱恩·马丁

Twitter 服务的可扩展性和效率高度依赖于高质量的缓存产品。

当 Memcached 和 Redis 不能完全满足他们的需求时，他们开发了 Pelikan 作为缓存系统。Pelikan 的首要任务是“通过面向延迟的设计和精益实施实现一流的效率和可预测性”这最初是通过 C 实现实现的。然而，随后的两个项目以相当惊人的开发速度将 Rust 引入了框架。

当他们决定为 Pelikan 添加 TLS 支持时，Twitter 软件工程师布莱恩·马丁怀疑在 Rust 中可以比在 C 中更快更有效地完成这项工作。但要获得批准，Rust 实现必须匹配(或击败)C 实现的性能。

从性能角度来看，基于 Rust 的 twem cache(Twitter Memcached)的初始原型并不看好；他们将 P999 延迟提高了 25%到 50%,吞吐量降低了 10%到 15%。即使马丁加倍努力优化 Rust 原型的性能，他也只看到了极小的影响。在更令人沮丧的性能测试结果之后，他考虑了几种不同的实现方法。幸运的是，就在他权衡潜在的妥协时，他发现了一种新的存储设计，这种设计可以更容易地将整个存储库移植到 Rust。

当时，Martin 全力投入 Rust，开发了一个简化的单线程应用程序，所有内存分配都在 Rust 中管理。结果呢？100% Rust 实现不仅提供了等同于甚至超过 C 实现和 memcached 的性能，它还改进了整体设计，并使编码充满信心，这要归功于“令人敬畏的语言特性和工具”，Martin 随后深入研究了这些特性和工具。

点击此处观看 Brian 的完整会话:

[https://www.youtube.com/embed/y1pPAMM4SDQ?feature=oembed](https://www.youtube.com/embed/y1pPAMM4SDQ?feature=oembed)

视频

## “驯服围棋的内存使用，避免 Rust 重写”——秋田软件公司的创始工程师马克·格里特

马克·格里特目前是第四家创业公司，此前他曾在 Kealia 从事流媒体视频工作；Tintri 的虚拟机感知闪存数据存储，他是该公司的联合创始人；HashiCorp 跳马团队的可观察性；现在是 Akita Software 的 API 可观测性。

我们急切地期待着听到他进入和走出绝望低谷的旅程，并了解他为什么决定采取相反的道路，以避免生锈重写。当 [P99 CONF 2022 于 10 月 19 日至 20 日](https://www.p99conf.io/)上线时，你可以赶上他的会议并与他聊天。在此之前，这里是格里特的商店里有什么预览。

“去年夏天，我和我的团队面临一个许多年轻创业公司都面临的问题:我们应该在 Rust 中重写我们的系统吗？

“在做出决定时，我们主要是在 Go 中编写。我正在开发一个代理，它被动地监视网络流量，解析 API 调用，并将模糊的摘要发送回我们的服务进行分析。随着用户开始通过我们运行更多的流量，代理的内存使用量增长到了不可接受的高水平，影响了性能。

“这导致我在绝望中度过了 25 天，并让自己沉浸在 Go 内存管理、我们的技术堆栈和可用的分析工具的细节中，试图让我们的内存占用得到控制。Go 的全自动内存管理使得这不是一件容易的事。

“剧透:我获胜了，我们队还在用围棋。在这次演讲中，我将谈谈我的项目中的关键步骤和经验教训。我希望这个演讲能够帮助那些对减少围棋内存占用感兴趣的人，或者那些想知道切换到或退出围棋的[权衡的人。”](https://thenewstack.io/rust-vs-go-why-theyre-better-together/)

## CONF P99 的 40 多场免费虚拟会议

P99CONF 不仅仅是一个 Rust 发布会。WebAssembly、数据库、事件流、Gom Java、Linux 内核、OpenTelemetry、eBPF、Kubernetes、混沌工程、SLIs/SLOs——它们都在日程上。

10 月 19 日至 20 日，数千名工程师将聚集在网上:

*   探索来自优步、Lyft、Square、谷歌、红帽、甲骨文、Redis、微软等公司工程师的专业策略。
*   从多个角度探索性能策略——编程语言、CPU、前端、后端、框架和可观察性。
*   向 Bryan Cantrill、Avi Kivity、Charity Majors、Liz Rice、Gil Tene、Ron Pressler、阿明·罗纳彻、Alex Hidalgo、Malte Ubl 和 Steven Rostedt 等名人学习。

不要错过这个和你的同龄人一起进行为期两天的集中学习、技能磨练和社区协作的机会。[免费注册](https://www.p99conf.io/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>