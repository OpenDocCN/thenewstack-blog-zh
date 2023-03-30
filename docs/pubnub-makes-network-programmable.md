# PubNub 为实时流媒体服务提供无服务器编程

> 原文：<https://thenewstack.io/pubnub-makes-network-programmable/>

在所有关于网络边缘的无服务器计算和编程的讨论中，位于三藩市的 T2 公共图书馆正在使这两者成为现实。

PubNub 基于 JavaScript 的 API 使开发人员能够将实时通信添加到他们的应用程序中，无论是实时聊天、多人游戏还是远程控制的物联网设备。

使用该公司的全球数据流网络(DSN)， [PubNub Blocks](https://www.pubnub.com/products/blocks/) 允许开发人员将应用程序逻辑直接编码到网络中，从而无需设置服务器来处理特定任务。

这些服务或“块”来自 PubNub 和第三方提供商，可以嵌入到流工作流中，以处理 IP 阻止、地理定位和地理编码以及过滤等任务。

一家拥有受欢迎品牌的公司可能希望开发一款聊天应用，以便其用户能够在大型活动期间获得在线实时体验。PubNub 首席营销官温迪·肖特说:[这就是 PubNub 模块派上用场的地方。](https://twitter.com/wmschott)

“你不希望有人说脏话或使用竞争对手的名字。现在，对于一个开发者来说，如果你输入一条聊天信息，他们必须把这条信息发送到一大堆服务器上，这些服务器什么也不做，只是分析你的信息寻找亵渎的内容，寻找竞争对手的名字并替换它，然后把它放回网络，然后发布给所有人。他们必须有大量的服务器来完成一个简单的功能——解析信息，”肖特说。

“使用 PubNub 块，他们可以编写一小段 JavaScript，这将允许他们在世界各地的每个边缘节点上运行我们的网络。当消息被发送时，我们将动态解析它，运行逻辑，并以低延迟和无启动时间将其推出。”

她称之为思科雾计算概念的体现。事实上，思科和爱立信刚刚又投入了 600 万美元，使公司的资金总额达到 4610 万美元。

该公司在全球使用 15 个数据中心，因此使用 PubNub 代码的设备连接到离他们最近的数据中心。所有的处理都在网络边缘完成，而不是发送到某个中央服务器。

“我们基本上是实时网络和实时计算的大型 CDN，”Schott 说。

该网络已经在超过 3.3 亿台设备上每月发布 1.8 万亿条消息。

使用持久套接字连接，该服务允许用户:

*   将消息发布到他们可以随时创建的渠道中。
*   检测设备是在线还是离线。
*   存储数据流以便回放——例如，如果你很晚才加入聊天，你可以回去继续聊天。
*   通过一个连接订阅数千个频道。

它的 HTTP 级请求和响应也可以用于物联网设备，以便在数据仍被送回进行分析的同时，快速发出异常警报——例如，允许用户呼叫维修。

该公司通过与其他在线服务提供商的合作来扩大其服务，包括 IBM Watson、T2 Wolfram Alpha 和 T4 send grid。Schott 说，举例来说，如果你想用英语聊天，但也要翻译成其他三种语言，你可以让 IBM Watson 在运行中为你做到这一点。

它支持 70 种不同的 SDK，如游戏开发工具 [Unity](https://unity3d.com/unity) 、 [Go](https://www.pubnub.com/docs/go/pubnub-go-sdk) 、 [Raspberry Pi](https://www.raspberrypi.org/) 等等。虽然它自己的代码是专有的，但它也支持开源项目，如 [Project EON](https://www.pubnub.com/developers/eon/) ，它连接了 [C3 图表](http://c3js.org/)和 [Mapbox 的地图小部件](https://mapbox.com)，用于创建仪表盘和可视化。

有一系列涵盖开放套接字的开源项目，包括 Node.js 的 [SocketCluster](http://socketcluster.io/#!/) 和 C++的 [RudeSocket](http://rudeserver.com/socket/api.html) 。在这方面，它与 Realtime、Pusher 和 Google 等竞争。

它的客户包括罗技、Adobe 和 Autodesk，尽管 Schott 说它在医疗保健领域越来越受欢迎，因为它符合 HIPAA 标准。

她描述了三层安全措施:

*   [传输层安全](https://luxsci.com/blog/ssl-versus-tls-whats-the-difference.html) (TLS)，对正在传输的数据包进行加密。
*   [高级加密标准](http://searchsecurity.techtarget.com/definition/Advanced-Encryption-Standard) (AES):“我们不保存密钥。我们无法解密用户的数据，”她说。
*   它有自己的访问管理器:开发者控制对个人、设备或渠道的访问。

“如果你的聊天对象变得粗俗，你可以写一个脚本，限制这个人听，但不能在这个频道上写，或者完全屏蔽这个人。它在不到四分之一秒的时间内在每个边缘节点上全局完成，”她说。

https://player.vimeo.com/video/181658936

*9 月 28 日，PubNub 将在旧金山举办一场关于网络流媒体的会议，Stream Conf 2016，届时将有思科、Gorilla Logic、微软、Mozilla、Signal FX 等公司参加。*

#### 2016 年 9 月 28 日 // 三藩市@宾利保护区

#### 2016 年 9 月 28 日 // 三藩市@宾利保护区

一切都在改变:从驱动数据流的软件架构到将数据流转化为增长业务的商业模式。加入技术思想领袖、软件架构师和开发人员的行列，探索在未来几个月和几年中如何管理、扩展、保护和利用不间断数据流。如果您负责将永不停机的应用程序或连接设备推向市场，这将是一个不容错过的活动！**使用折扣代码 TNS-100** 节省 100 美元

思科[和 IBM](https://blogs.cisco.com/tag/mantl)[是新堆栈的赞助商。](https://www.ibm.com/cloud)

特征图片:[留言板](https://www.flickr.com/photos/mujitra/10511181393/in/photolist-h1Qy2p-ETrQC-nZynod-8p9mo3-pU22E-vSRjD-Cs2XY-aF9gsX-7xhixp-9dMbhx-3M7FcU-aFd88N-ei29gn-5FTfg2-9uHAVk-eFvEms-4FEU4c-8hRWyY-eFpAhH-aeKzYn-nQBtX2-4EzSWu-c1KyYj-d8jz65-5ssq3L-6rWGcX-yCzPc-9atj-8bv8Kr-AsaNj-eFpzm6-8iQ3hG-8TSSHt-GtAsUG-9rcDc2-AsaNt-8TNo6H-e6ymVQ-9xhaVj-aQxVkx-8yCq2r-wpNz-eFpCTV-9xhb55-9xebsx-9P5PYd-yCzRz-hXFsA-6ajvn1-yTsmQ)由[三木大正天皇](https://www.flickr.com/photos/mujitra/)制作，2.0T19**CC 下授权。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>