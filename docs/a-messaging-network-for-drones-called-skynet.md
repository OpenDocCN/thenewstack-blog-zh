# 无人机获得了一个被恰当地称为天网的信息网络

> 原文：<https://thenewstack.io/a-messaging-network-for-drones-called-skynet/>

在过去的九个月里，一家名为“天网”的公司一直致力于无人机之间相互对话的机器对机器(M2M)系统。天网以《终结者》电影系列中具有自我意识的人工智能系统命名，旨在运行于单个网络或物联网网络网格上，这些网络共享一个公共 API 或通信协议。在这种情况下，设备可以发现、查询并向网络上的其他设备发送消息。

首席执行官克里斯·马蒂厄(Chris Matthieu)是语音 API 和应用的早期开发者之一。有了天网，他把注意力转向了无人机。他最近为我们详细介绍了这项技术，展示了无人机的能力以及人们正在建造的新堆栈，以使机器变得越来越复杂，如 Matthieu 拍摄的视频所示。

[https://www.youtube.com/embed/CCr17B1gSPw?feature=oembed](https://www.youtube.com/embed/CCr17B1gSPw?feature=oembed)

视频

Matthieu 说，天网正在十几个亚马逊 EC2 服务器上运行，拥有近 50，000 个注册的智能设备，包括: [Arduinos](http://www.arduino.cc/) 、 [Sparks](http://spark.io/) 、 [Raspberry Pis](http://www.raspberrypi.org/) 、 [Intel Galileos](http://www.intel.com/content/www/us/en/do-it-yourself/galileo-maker-quark-board.html) 和 [BeagleBoards](http://beagleboard.org/) 。天网通过新的轻量级容器技术 [Docker](https://www.docker.io/) 作为物联网平台即服务(PaaS)和私有云运行。该平台用 Node.js 编写，并在 GitHub 上以 MIT 开源许可发布。

Matthieu 说，单一的天网 API 支持以下物联网协议:HTTP，REST，WebSockets， [MQTT](http://mqtt.org/) (消息队列遥测传输)，以及 [CoAP](https://en.wikipedia.org/wiki/Constrained_Application_Protocol) (受限应用协议)，用于保证消息传递和低带宽卫星通信。每个连接的设备都分配有一个 36 个字符的 UUID 和秘密令牌，作为设备的强凭据。可以分配安全权限，以允许设备可发现性、配置和消息传递。

该公司管理着一个目录服务，用于查询符合搜索标准的设备，如“旧金山的所有在线无人机”，Matthieu 说。符合搜索条件的 uuid 数组被返回，允许用指令发送一个或所有这些 uuid 的消息。每个连接设备的存在(在线/离线)由实时 WebSocket 通信管理。MQTT 允许 SkyNet 在设备从离线状态重新连接时向它们发送消息。

天网最近发布了其[物联网中心](https://github.com/skynetim/hub)，允许用户将有或没有 IP 地址的智能设备直接连接到天网，包括:Nest、Phillips Hue 灯泡、Belkin Wemos、Insteons 和其他不太智能的设备，如串行端口设备和 RF(射频)设备。这不仅允许任何设备连接到互联网，还允许人们在不通过制造商的云和应用程序的情况下向智能设备发送消息。智能设备集线器插件是[节点。JS NPM](https://www.npmjs.org/search?q=skynet-plugin) 模块使它们易于共享、扩展和部署。

Matthieu 说，该公司最近还发布了一个天网操作系统。它将任何 Arduino 兼容设备(Arduino、Spark、Pinoccio 等)转变为互联网上具有消息功能的硬件设备。当 Arduino 启动时，它使用内置的以太网插孔或 wifi 芯片(或以太网/wifi shield)来连接和验证 SkyNet 不需要 CPU 来控制设备。通过内置的 [firmata](http://firmata.org/wiki/Main_Page) 和天网信息，一个人可以打开和关闭 Arduino 引脚(包括发光二极管、伺服系统、电机、功率继电器等。)并从连接到传感器的引脚读取。

> 你可以用胶带把这些设备中的一个绑在一个带有小型太阳能电池板和充电电池的灯柱上。它可以智能启用你的城市街区。

用于连接物联网的可视化工具 NodeRed 现在连接到天网，可以通过拖放设计器控制连接的智能设备网络。

**一个会说话、会飞的网络**

真的没有办法亲自管理世界上所有的互联设备。设备将不得不自己做出决定，通过网状网络进行连接。

这个新网络的结果将在许多方面取决于世界上事物的开放性，以便它们能够互操作。这意味着与今天的云服务提供的网络大不相同。更重要的是，无人机和世界上的事物将通过通信相互依赖——就像我们人类今天所做的一样。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>