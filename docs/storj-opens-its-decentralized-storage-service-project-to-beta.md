# Storj 向测试版开放其分散存储服务项目

> 原文：<https://thenewstack.io/storj-opens-its-decentralized-storage-service-project-to-beta/>

Storj Labs 发布了其开源[同名的分散式云对象存储软件](https://github.com/storj/storj)的测试版，同时开放了该软件及其分散式云存储服务 [Tardigrade](https://tardigrade.io/) 的测试版。在接受新堆栈采访时，Storj Labs 执行主席兼临时首席执行官 Ben Golub 解释说，Storj 跟随其他家喻户晓的科技公司的脚步，允许其成员通过“共享”他们的资源来获利，在这种情况下，他们的空闲存储空间。

“AirBnB 是最大的没有一间酒店房间的酒店公司，Lyft 和优步是最大的没有一辆出租车的出租车公司。在我们的例子中，我们有一个云存储服务，但我们通过允许人们出租他们驱动器上的备用容量来构建它。事实证明，市场上绝大多数驱动器的利用率只有 25%左右，运行 75%的驱动器不需要更多的资金、电力或人力，所以人们很乐意为我们提供他们的闲置容量，”Golub 说。

用户体验与标准的云提供商是一样的，只是该公司声称其服务更快、更便宜、更安全。在后台，用户的数据被分割成许多小块，加密后分布在整个网络上。

Storj 最初是创始人肖恩·威尔金森(Shawn Wilkinson)的创意，在推出第 3 版(V3)之前，它已经经历了另外两次实现。Golub 解释说，V1“更多的是概念验证”，而 V2“发展得非常非常快”，拥有 150PB 和超过 100，000 个节点，但未能满足对其增长的预期。这让该公司踏上了通往 V3 网络的道路。

“V2 的设计无法提供企业级耐用性或性能，也无法扩展到千兆字节或更大范围。因此，我们学到了很多东西，并进行了大规模的重写，”Golub 说。“我们学到的一件事是，我们希望确保供应不会超过需求太多。人们加入网络出租他们的硬盘的原因之一是因为他们将获得报酬，如果没有足够的需求来填满它们，那么他们就会离开。现在，我们的增长更加适度，并确保我们的网络能够提供百分之百的耐用性、99.999 的可用性和极快的速度，现在我们已经实现了这一点。”

对于最新的重写，Storj 一直在进行 alpha 测试，公司声明称，其性能现在“可与亚马逊 S3 和其他集中式云存储提供商媲美”，Tardigrade 提供的上传和下载速度“是 S3 的两倍以上”，没有文件丢失，文件可用性超过 99.95%。

至于 Storj 如何实现这一切，对其所有存储提供商(或存储节点运营商)都有[严格的要求](https://storj.io/blog/2019/01/we-need-great-storage-node-operators-for-the-v3-network-have-you-got-what-it-takes-to-succeed/)和审计流程，这些存储提供商或存储节点运营商由在家中拥有高质量驱动器的个人和具有备用容量的数据中心组成。无论他们是谁，都要满足一些最低要求，包括每个存储节点服务一个专用处理器，最低 500GB，每月 2TB 带宽，上行 5Mbps 和下行 25Mbps，每月最多 5 小时停机时间。所有这些都通过长达一个月的测试过程得到了证实，包括确认需求的审计，但 Golub 强调，该网络的设计方式可以确保即使在大量节点不运行的情况下也能运行。

“我们构建网络时假设一些节点是坏的，要么运行不正确，要么是由坏人运行，因此网络被设计成能够真正适应这种情况。例如，当你上传到我们的网络时，首先发生的是使用只有你才有的密钥加密，这样无论是运行节点的人还是 Storj 本身都无法查看或理解你的数据，”Golub 说。然后它会被分割成大约 80 份，其中的 30 份可以用来把你的文件重新组合在一起。然后，这 80 个片段中的每一个都进入网络上的不同驱动器，每个驱动器由不同的人在不同的电源、不同的网络连接和世界的不同地方运行。这意味着我们真的能适应任何发生的事情，无论是风暴还是地震或类似的事情。”

With the move to beta, Storj Labs will begin welcoming select developers onto the network, with more than 10,000 developers on the waitlist soon able to begin deploying applications using Tardigrade as their storage back end, alongside all of the [Storj Labs Open Source Partner Program](https://storj.io/partners) members. For developers looking to integrate Tardigrade into their applications, they will be able to use the CLI and [libuplink developer library](https://godoc.org/storj.io/storj/lib/uplink) in Golang, C, and on Android, using the Minio S3 gateway.

Feature image by Tanja Schulte from Pixabay.

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>