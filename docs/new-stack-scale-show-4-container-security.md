# 新的 Stack @ Scale 播客，Show 4:集装箱安全的界限

> 原文：<https://thenewstack.io/new-stack-scale-show-4-container-security/>

在 New Stack @ Scale 播客的第四集中，我们的月度节目由 New Relic 赞助，探索伴随动态服务和系统的各种问题，New Stack 创始人 Alex Williams 和共同主持人 Fredric Paul(New Relic 的主编)与两位嘉宾一起讨论横向扩展架构新领域中的容器安全。

[Jim Reno](https://www.apcera.com/leadership/jim-reno-0) 是 Apcera 的首席安全架构师，Armon Dadgar 是 HashiCorp 的联合创始人兼首席技术官；两位都为讨论带来了丰富的宝贵经验，并提供了值得关注的实际见解。

[显示 4:集装箱安全](https://thenewstack.simplecast.com/episodes/show-4-container-security)

威廉姆斯说，从历史上看，安全部门一直致力于保护端点，他承认“今天几乎有无限个端点，转变是提供更深入的数据分析来寻找异常等。”

“不仅仅是数据分析，”他说。“我们看到规模和分布式系统的概念正在发生巨大变化。”

Dadgar 列举了三个这样的变化:“广泛采用分布式系统是其中的一个方面。从更传统的整体系统向更现代的微服务架构转变。此外，第三次浪潮是从基于机器的虚拟化向基于应用的虚拟化的转变。”

然后他总结了网络困境。Dadgar 说:“过去我们在一个过程中通过功能边界进行通信，现在我们在离散的机器之间通过网络进行通信和数据流动。这带来了一系列安全挑战，而这些挑战在我们采用传统的整体式方法时根本不存在。”

“总的来说，微服务和面向服务的架构是扩展复杂性的正确方法，而网络是进行这种链接的正确场所。但安全挑战是真实的，必须解决，我们不能只是把它藏在地毯下面。”

他描述了经典的[InfoSec triad](https://www.techrepublic.com/blog/it-security/the-cia-triad/)——机密性、完整性和可用性——以说明集装箱安全应该解决的内在风险，每个人都承认，随着遥测数据的数量继续超过我们的手动分析能力，自动化将在安全方面发挥更大的作用，更不用说监控了。

在另一个关键时刻，当 Paul 问组织中谁应该在如此依赖微服务的环境中负责安全时，Reno 说开发人员可能需要承担一些责任。

“软件安全性的一个问题一直都是这样，”Reno 说，“安全性的问题被认为是事后的想法。大部分都归开发人员所有，从我的开发背景来看，我也要承担一部分责任。人们并不总是很早就想到这一点。”

“开发人员很容易说，‘我的工作是让软件在那里工作；我们需要向客户传递价值。在传统模式中，对此有一定的容忍度，因为你可以说，“一旦这些东西被部署到数据中心，就会有外围安全。”"

“在容器领域，这种情况必须改变，特别是因为你现在谈论的是开发人员从许多不同的来源提取可执行代码。他必须为现在应用程序中的内容承担一点责任。这不再是他的全部准则了。他编译的都不是开源的。他现在从某人身上提取的是二进制图像，你必须知道这些图像来自哪里。”

Reno 说，安全永远是每个人的责任，但在这种环境下，开发者可能需要把它放在更优先的位置。“我们需要做的事情之一是给他们工具和系统，帮助他们做到这一点。”

Dadgar 说，他喜欢向客户指出安全性是一个范围——他们想投资多少来确保安全？

“你在安全方面投入的努力只会增加成本，但没有一个完美的安全系统，”他说。“没有你能到达的终点线。你只会让破解系统变得更加困难。根据你的投资水平，参与的人会有所不同。”

“在大型组织中，您有自己的信息安全团队，他们代表着真正的高投资。你将雇佣安全专家，他们的工作就是日日夜夜考虑如何保护系统，”他继续说道。“另一方面，你可能会说，‘这种投资对我们来说不值得。“我们更看重我们的灵活性，或者说我们更看重上市时间……我们不想让安全性成为我们的检查点。”作为一个组织，这是一个有意识的决定。"

“如果你要说，‘这是我的开发人员的责任，’”dad gar 说，“那么你就是在强迫他们做出取舍，因为他们的时间是有限的。”

“我一天有 8 个小时。我是不是每天花 8 个小时发布一个新功能？我是不是每天花 7 个小时发布一个功能，花 1 个小时在安全上？或者我花 7 个小时在安全性上，每天花 1 个小时在新功能上？”

“这是无法逃避的，”他说。“权衡是最基本的，成本是无法计算的。”

要订阅新的 Stack @ Scale 播客或查看其他剧集，请访问新 Stack 的播客部分。

Apcera 和 New Relic 是新堆栈的赞助商。

特征图片:[钥匙](https://www.flickr.com/photos/120600995@N07/14028600474/in/photolist-nnEfaY-ds26Et-bh4AGB-jnDBtq-5E2411-333pUJ-aXeGui-5Mj9Mt-2A1ugP-7fvHxP-efQwGU-mbGm6V-eaxabV-3Y2GN8-7HAXU6-8pqD9P-6JZufR-k5hFmS-8TGdkk-d3cZjS-fMe73q-qZJaEt-792ti2-8ATonx-cgGrt5-MLVm9-pT3U7W-oFetj2-2eL2kX-6L6jF3-mTZywC-fswHHC-ttmZMR-5W81Gq-og74CT-5yD8Wu-dL8A1w-x5jct-mGWpiE-5qr3Pu-qpzMDz-5gR5Cr-2sjeFh-8eNMk7-uaCiFU-mG1o17-8f7RRJ-nwyRPY-bxDRqZ-6Vwor7)由 [Jacqui Brown](https://www.flickr.com/photos/120600995@N07/) 制作，授权于 [CC GA 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>