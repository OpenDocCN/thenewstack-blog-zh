# 我们如何为 gRPC 构建一个开源的替代方案

> 原文：<https://thenewstack.io/how-we-built-an-open-source-drop-in-replacement-for-grpc/>

[](https://www.linkedin.com/in/jtolds/)

[JT·奥利奥](https://www.linkedin.com/in/jtolds/)

 [JT 是 Storj 的首席技术官。他负责监督产品开发，并领导了 Storj 分布式云存储平台的重新架构。他之前是 Space Monkey 的工程总监，该公司于 2014 年被 Vivint 收购。JT 拥有犹他大学的计算机科学硕士学位和明尼苏达大学的计算机科学和数学学士学位。](https://www.linkedin.com/in/jtolds/) [](https://www.linkedin.com/in/jtolds/)

我们在 Storj 的团队正在构建一个分散的云对象存储，当我们决定使用 Go 构建它时，我们认为我们也可以在客户端/服务器交互中利用 [gRPC](https://grpc.io/) 进行对等远程过程调用。gRPC 是专为像我们在 Storj 建造的环境而设计的。它通过简单的代码生成、健壮的有线协议和低开销将服务连接在一起。此外，gRPC 也有很大的影响力。它是开源的，被云中的公司广泛使用——包括蟑螂实验室、Docker、Dropbox、IBM、网飞、Square、维基百科，以及更多你可能听说过的公司。

然而，我们发现 gRPC 需要改进——至少对我们来说是这样。这怎么可能？毕竟，gRPC 是由 Google 创建的，并且被所有“酷”的公司使用。但是对于下一代的分散架构，它不适合我们。因此，在尝试让 gRPC 为我们工作了太长时间之后，我们寻找一个替代方案。

## gRPC 的问题

当我们开始研究我们的对象存储产品以确定性能改进机会时，我们发现我们花了很多时间来对抗 gRPC。gRPC 是单片的，不是很模块化；它有许多功能膨胀。例如，gRPC 不是提供一种模块化的机制来建立底层的套接字传输，而是想要拥有整个拨号系统，并且在连接状态管理中产生了令人眼花缭乱的复杂性。当在凌晨 2 点进行调试时，我们想要一个简单得多的状态机。

不过这也不完全是 gRPC 的错——gRPC 是基于 HTTP/2 的，它也有自己的问题。在 Go 中，支持 HTTP/2 很容易给你的库增加几兆字节，同时也有生产问题，比如行首阻塞。总的来说，gRPC 及其依赖项的增加是巨大的，总共占了我们全部二进制文件的 1/5。我们还发现，它在我们网络的某些部分所利用的资源量超出了图表范围，占我们存储节点堆使用量的 81%。

我们需要一个精简的 RPC 工具，它做的事情稍微少一点，但是做得很好。所以我们建立了自己的框架——DRPC——它只有 3000 行代码，需要很少的依赖性，并且可以极大地改进我们系统中的许多重要功能。

## 介绍 DRPC:gRPC 的替代者

DRPC 是我们解决 gRPC 弱点的方法。它是 gRPC 的替代产品，所以如果您目前正在使用 gRPC，那么迁移到 DRPC(这个“D”不代表任何特殊的东西)就像更换您的协议缓冲区生成管道一样简单。我们甚至制作了一个例子，展示如何将一个实时服务迁移到 DRPC。

DRPC 保留了 gRPC 的许多关键功能。它支持单一的和双向的流请求，它有一个 HTTP/JSON 网关，它支持每个请求侧通道信息的元数据(像跟踪)，它减少了内存使用，它支持分层和中间件。在[自述文件](https://github.com/storj/drpc#readme)或我们的[文档](https://storj.github.io/drpc/docs.html)中阅读更多关于 DRPC 支持的功能(其中也包括一些令人印象深刻的性能基准)。

## 从 gRPC 迁移到 DRPC

当我们建立 DRPC 时，我们已经在生产服务中推广了 gRPC。为了在最短的停机时间内完成迁移，我们需要同时支持 gRPC 和 DRPC。这似乎是一项艰巨的任务，但最终我们实现了零停机时间的迁移。

我们这样做的方法是，我们观察到 gRPC 连接都使用相同的初始协议字节对。我们扩展了我们的传输层，通过一个开放的套接字对初始字节进行监视和解复用。如果前几个字节以“DRPC！！！1”，那么我们知道传入的请求不是基于 TLS、HTTP 或任何其他现有协议的 gRPC。通过这种交换行为，我们能够扩展我们的服务器，在相同的套接字和相同的端口上同时处理 gRPC 协议和 DRPC 协议。

一旦我们确信我们所有的服务器都支持 DRPC，我们就开始将所有的客户端升级到 DRPC。一旦我们确定所有的客户都升级到了 DRPC，我们就可以淘汰 gRPC。

对于 Go 程序员，我们已经在 DRPC 包中包含了这些相同的助手，并在这里提供了示例。

目前，我们已经在数万台服务器上使用了多年的生产 DRPC，因此您也可以随时使用。

## DRPC 自发布以来的改进

几周前，我们在[发表了一篇文章](https://www.storj.io/blog/introducing-drpc-our-replacement-for-grpc)，宣布公开推出 DRPC 供其他人使用。我们对这次接待感到非常激动！

它已经是我们在 Github 上第二高星级的存储库，是许多开发者社交媒体水坑中投票最高的提交，并引发了大量的讨论和兴趣。我们在 [Reddit](https://www.reddit.com/r/golang/comments/mznppb/introducing_drpc_the_storj_replacement_for_grpc/) 、 [Lobste.rs](https://lobste.rs/s/qo2qqk/introducing_drpc_our_replacement_for) 上，甚至在我们的 [Github 知识库的问题标签](https://github.com/storj/drpc/issues?q=is%3Aissue)上进行了许多令人兴奋的讨论。

人们似乎对 DRPC 感到兴奋——我们有志愿者帮助编写文档和额外的语言绑定，在发布后的几天里，我们发现了如何添加 Twirp 兼容性、Websocket 兼容性，改进了 Javascript 和浏览器交互的一些人体工程学，优化了代码以减少内存分配并进一步提高速度(有时分配减少了 90%，在一些微基准测试中速度提高了 7 倍)，以及其他一些东西。一个贡献者刚刚成功地让[她的 NodeJS 绑定](https://github.com/mjpitz/drpc-node)对 Go 流程起作用，反之亦然。

对 DRPC 来说还为时过早。我们已经有很多人告诉我们，他们正计划在他们的产品中采用它，或者转而使用它，所以现在我们可以兴奋地等着看(如果有人问，我们会帮忙的！)社区建立在什么之上！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>