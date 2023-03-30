# 建造真正的天网

> 原文：<https://thenewstack.io/building-the-real-skynet/>

“终结者”电影系列中的具有自我意识的人工智能系统天网是这个自动化时代的隐喻，也是我们对那些将解放我们或使我们成为他们命令的奴隶的系统的真正恐惧和迷恋。

天网，[，我们今年早些时候写的](https://thenewstack.io/a-messaging-network-for-drones-called-skynet/)，也是克里斯·马蒂厄的公司 Octoblu 的原名，该公司正在开发一种机器对机器网络，或物联网网络的网格，它们共享一个公共的 API 或通信协议。原来的天网开源项目现在由 Matthieu 管理，独立于 Octoblu。

在本月早些时候的 [Defrag 会议](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CCAQFjAA&url=http%3A%2F%2Fwww.defragcon.com%2F&ei=NeZ4VMWJBsiwogTGmoEo&usg=AFQjCNHKgJpFhzW9v4ilhnO7vQf1FLneNQ&sig2=HsJJTSSjHOGxcS48SLLh6w&bvm=bv.80642063,d.cGU)上，Matthieu 讨论了如何使用 Octoblu，设备可以在他的公司开发的网络上发现、查询和发送消息给其他设备。New Stack 创始人亚历克斯·威廉姆斯(Alex Williams)出席了发布会，并录制了这段录音。

对于其他录音，请访问新堆栈的播客部分[。](https://thenewstack.io/podcasts/)

[建造天网](https://thenewstack.simplecast.com/episodes/building-skynet)

Matthieu 正在开发他描述为不可阻挡的学习网状网络，它使用许多协议，不同的设备通过各种协议进行通信，类似于机器对机器即时消息(M2M IM)神经网络。

以下是关于他正在构建的项目的更多信息:

*   单一的天网 API 支持以下物联网协议:HTTP、REST、WebSockets、MQTT(消息队列遥测传输)和 CoAP(受限应用协议)。
*   Skynet 是开源的，是一个多协议和跨协议的平台，任何使用该语言的设备都可以相互通信。
*   网状网络上的每一个资源都有一个 UUIDs 一个 36 字符的设备凭证，它与具有自己的 UUID 的网状网络相关联，最终使它成为一个 UUID 网络。
*   该平台还需要能够支持 uuid 的发现和向其他 uuid 发送消息的能力，在这种情况下，它应该能够根据给定的搜索标准搜索一组 uuid。
*   安全性足够灵活，可以由 UUID 来控制，它可以发现和发送消息，还可以指示哪些 UUID 可以订阅或以白名单和黑名单的方式进行配置，所有这些都集成到平台中。
*   API 位于每个已知的本地协议之上，其中相同风格的 REST API 应用于每个协议，以共享相同的通信平台并通过网状网络进行交互。
*   神经处理单元(npu)是每个天网设备内部的芯片，允许天网控制设备并根据需要与之连接。
*   Octoblu Skynet 操作系统运行在 Arduino、Spark 设备和 Pinocios 上，通过添加更多微控制器(基本上是一个具有 32K RAM 的草图), Arduino 能够在线并从多播的网状网络请求 UUID 并与之连接。
*   通过移动天网网络，任何能连接到网状网络的人也能控制它。
*   Skynet 有大约 30 个内置在平台中的 API，包括企业 API 和基于浏览器的设计器来拖放它。当事件和消息通过 Skynet 流动时，它们与 API 实时对话，API 还为登录用户提供 UUID。
*   这就产生了一个平台，在不同的协议之上，通过简单的拖放浏览器和 API 将所有的东西集合在一起。
*   如果有一个设备不会说这种语言，就有一个网关，它带有一个插件，可以将该设备包含在混合协议中。
*   思科估计，到 2020 年，将有 500 亿台联网设备，这是联网设备的指数级增长。

特征图片:[成彬 Im](https://www.flickr.com/photos/golbenge/) 的:[终结者](https://www.flickr.com/photos/golbenge/7495464600/in/album-72157611324962762/)在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下获得授权。

亚历克斯·威廉姆斯编辑并促成了这个故事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>