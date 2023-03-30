# 物联网 API 的不同风格

> 原文：<https://thenewstack.io/the-different-flavors-of-iot-apis/>

物联网 API 最近获得了很多关注，各公司都在积极参与竞争。供应商提供了各种方法和功能，允许设备相互通信和基于云/网络的服务。目前，至少在我看来，关于所有这些事情将如何实现，甚至它们在现实世界中如何工作，画面还有点模糊。你最好现在就开始看一看，因为随着时间的推移，它只会变得更加复杂。这里有一些他们提供的公司和服务。

## **泽塔**

最近推出的 [Zetta 平台](http://www.zettajs.org/)，来自 [Apigee](http://apigee.com/about/) 希望成为各种物联网(IoT)设备的 API 中介。物联网行业面临的一个大问题是，创建和维护 API 是相当苛刻的。Zetta 在设备和云中都有帮助管理这种复杂性的部件。

使用轴辐式模型 Apigee 整合了各个设备之间的通信，通过服务器和网桥将它们连接到云基础架构。与所有单个设备节点交互的智能被抽象到云中，因此开发人员可以专注于构建服务和应用，而不必在设备上或边缘构建和重建所有小 API。Zetta 还负责在设备、服务器和云之间转换不同的协议。

自然，建立云基础设施来处理节点抽象需要资金。Apigee 计划通过向客户提供各种付费在线服务来覆盖后端基础设施。该软件运行在廉价的硬件上，如 Beaglebone 和 Raspberry Pi。

## 3 刻度

该公司将互联家庭视为其中的设备、集线器和网络。但它也认为它包括其他两个方面:“从墙外访问和控制家庭(由内向外)，并将数据、媒体和服务拉入家庭(由外向内)。”

## **滕布**

另一个 API 仲裁器叫做 [Temboo](https://www.temboo.com/) 。该平台充当第三方 API 之上的一层，使用代码片段来触发通过其云平台运行的复杂流程。代码片段被添加到您的设备代码中，可能是在 Arduino Yun 上，并提供了一种跨各种 API 的函数调用的通用方法。

不同 API 之间的代码片段格式相同。Temboo 还试图让开发者不必在每台设备上维护 API。如果您知道如何在一个应用程序中使用 Temboo，那么您就知道如何在所有应用程序中使用它。

## **喜洋洋**

Xively 使用免费和开放的库，让你连接不同类型的硬件，使用各种语言到他们的云服务。它们在 HTTP、sockets 和 MQTT 上提供了基于标准的 API，使连接到物联网变得容易。

我的观点是，与我们谈到的其他一些系统相比，Xively 更接近于硬件。在他们的 T2 网站上查看他们的产品和服务。

## **说话算数**

这家公司提供了一种将你的设备连接到云服务的方法，很像 Xively，使用开放 API、实时数据收集、设备状态消息等等。

TimeControl 是 ThingSpeak 提供的一项有趣的服务。该服务在预定义的时间从云中的用户帐户激活任何类型的 HTTP 调用。这为定期轮询设备和收集数据提供了许多可能性。使用定制的 HTTP 头、get、POSTs、put 和 DELETEs，该平台可以在远程单个硬件节点上触发各种响应和动作。

## **Crowsnest**

[Crowsnest](https://www.crowsnest.io/) 平台使用本地服务器将个人设备连接到云。该公司目前的发展水平处理树莓 Pi 上的相机。其他设备肯定会跟进，他们计划为受支持的设备使用插件模型。一旦一个设备的插件被创建，所有的 Crowsnest 开发者都可以在他们的项目中使用它。

## 我们将何去何从？

我仍然认为物联网相当不成熟，不完善。供应商，包括设备制造商和提供服务的供应商，都在试图找出如何在这个游戏中赚钱。这个故事中概述的公司是一个良好的开端。而且，就硬件而言，我们肯定有一个光明的未来。现在是时候享受乐趣，开始构建物联网的未来了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>