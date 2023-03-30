# 84Codes 提供来自 Kafka、RabbitMQ、MQTT 的托管消息队列

> 原文：<https://thenewstack.io/84codes-provides-hosted-messaging-queues-from-kafka-rabbitmq-mqtt/>

物联网(IoT)设备的轻量级特性意味着将功耗和 CPU 开销保持在尽可能低的水平。这些设备仍然需要能够发送和接收消息，并可能相互通信。越来越多的项目被设计用于边缘计算，以提供更多的实时分析。

这使得[消息队列](https://wiki.aalto.fi/download/attachments/116662239/Message%20Queues%20in%20Industrial%20IoT.pdf?version=1&modificationDate=1481638941661&api=v2)——以及哪些最适合物联网项目——成为热门话题。消息队列可以帮助架构灵活，并使用不同语言编写的应用程序能够通信， Lovisa Johansson 指出，他是挪威云服务提供商 [84Codes](http://www.84codes.com/) 的开发人员，该公司专注于支持物联网服务。

当目标程序繁忙或未连接时，消息队列还为消息提供临时存储，并可以确保当流量峰值出现时，数据最终将被持久化和处理。

这完全取决于所需的通信类型。正如她指出的，每 15 分钟报告一次的温室温度监测器可以通过简单地将数据报告给另一个服务来处理而不是一直连接来减少网络带宽。

然而， [Forrester 预测](https://www.forbes.com/sites/gilpress/2017/11/09/10-predictions-for-the-internet-of-things-iot-in-2018/#7736ece35e7f)在 2018 年，物联网计算和自动化在边缘将会增加，例如，如果温度与设定参数不同，自动调节温度。Apache Kafka 的能力在这样的场景中发挥了作用，推动了对 Kafka 与 RabbitMQ 和 MQTT 协议的讨论。

## 托管选项

主机提供商 84codes 似乎已经覆盖了它的基础。84codes 的理念是开发人员永远不必安装或维护服务器，它提供了四个开源项目的托管版本:

首席执行官[Carl HR Berg](https://github.com/carlhoerberg)在 2012 年创立了 [84 Codes](http://www.84codes.com/) ，当时他在尝试将 RabbitMQ 与 Heroku 和 AppHarbor 结合使用时，看到了对 RabbitMQ 托管版本的需求。

到目前为止，这家瑞典供应商是单独销售服务的，而不是对整个公司进行品牌推广。

“当我们开始时，没有其他人提供 RabbitMQ 作为服务，当我们开始使用 Kafka 时，没有其他人这样做，所以我们在这些新服务方面进展非常快。在此之前，[公司]必须有内部人员来设置这些服务，这可能真的令人望而生畏，特别是在集群化的情况下，你必须设置 SSL 证书等等，”HR Berg 说。“我们喜欢这些产品，但它们可能很难安装和使用。”

该公司宣称拥有 20，000 多名客户，包括 Datek、Shutterstock、HP、KLM 和 Docker。

## 兔子 q

[RabbitMQ](https://content.pivotal.io/blog/understanding-when-to-use-rabbitmq-or-apache-kafka) 是一个分布式发布-订阅消息队列系统，通常作为一个节点集群运行，队列分布在各个节点上，并且可以选择复制以实现容错和高可用性。它原生使用 AMQP，这提供了跨语言的灵活性，并使用其他协议如 AMQP、MQTT、HTTPS、STOMP 和 WebSockets (Web-Stomp)作为插件。

AMQP 是一个安全可靠的协议，开销相对较低，但仍然比 MQTT 多。它提供持久的队列、集群、联合和高可用性队列。

根据需要，RabbitMQ 中的通信可以是同步的，也可以是异步的。其高度灵活的路由能力是其显著特点。

RabbitMQ 保证“至少一次递送”，但不保证“恰好一次递送”。

RabbitMQ 是一个用 Erlang 编写的快速消息代理。它丰富的路由功能和提供每条消息确认的能力是使用它的有力理由。

## 卡夫卡

[与此同时，卡夫卡](https://kafka.apache.org/)被设计成在发布-订阅消息和流中摄取大量数据。一个 Kafka 实例每秒可以处理 100，000 条消息，而 RabbitMQ 每秒可以处理近 20，000 条消息。

它的设计经久耐用、速度快且可扩展。它充当数据处理管道的网关，使用 Storm、Spark 和 Hadoop 等技术进行处理、查询和分析。

Janakiram MSV 在对新堆栈的[分析](https://thenewstack.io/apache-kafka-primer/)中解释说，面向消息的中间件，如 RabbitMQ，并不是专门为来自数千家出版商的 firehose 风格的数据流而设计的。

有了 Kafka，数据可以实时或离线处理，或者通过[“热”或“冷”路径](https://thenewstack.io/apache-kafka-cornerstone-iot-data-platform/)。

公司 84Codes [引用了](https://www.cloudkarafka.com/blog/2017-08-23-apache-kafka-iot.html)在家庭自动化中作为中央网关的用途，包括自动化安全、照明、家用电器以及供暖、通风和供暖/空调:

“系统生成的每一位数据都被组织成集合。这些集合对应于各种度量，如光强度、光使用、环境温度、负载消耗等。由于这些大多是片上系统物联网设备，它们使用轻量级协议进行通信，如蓝牙 LE (BLE)、Z-Wave 和 ZigBee。使用这些协议，数据被收集起来，并通过(这个)中央网关传递到数据处理管道。”

贾纳基拉姆·MSV 解释说，面向消息的中间件和 Kafka 的根本区别在于，客户端永远不会自动接收消息。他们必须明确地请求他们准备好处理的消息。

Kafka 的扩展性比 RabbitMQ 好得多——你需要做的只是添加更多的分区。还应该注意，RabbitMQ 集群不支持网络分区。

## MQTT

[消息队列遥测传输(MQTT)](https://thenewstack.io/mqtt-protocol-iot/) 是一种轻量级协议，旨在通过低带宽网络连接功率受限的设备。它的轻量级包结构在高延迟环境中节省内存和功率，使其成为机器对机器通信的首选协议。

连接的设备订阅 MQTT 代理上的主题。每当另一个设备或服务向主题发布数据时，所有订阅者都会自动获得新信息。代理还可以将类似的数据“推”给客户机。

MSV 解释说，它的设计目标与卡夫卡的不同。虽然它更适合于机器数据，但它不能处理大容量的接收。

缺点包括[缺乏加密](https://www.csoonline.com/article/3208325/internet-of-things/mqtt-is-not-evil-just-not-always-secure.html)，这将大大增加其开销，并且它不需要设备和服务器之间的认证，这些问题都是安全团队正在努力解决的。

PubNub 数据流网络上个月[宣布](https://www.pubnub.com/blog/new-improved-pubnub-mqtt-support-and-iot-capabilities/)支持 MQTT 设备。

“MQTT 似乎正在赢得物联网协议之战。低功耗物联网传感器很容易将数据啁啾到一个主题，然后让进程拾取数据进行处理，”T2 计算公司首席执行官克里斯·马蒂厄说。

“RabbitMQ 或 Kafka 更适合不同供应商的物联网设备运行不同协议的环境。您可以将他们所有的消息队列合并到一个单一的 MQ 平台中，而不是为每个协议部署不同的 MQ 平台。"

[https://www.youtube.com/embed/LKz1jYngpcU?feature=oembed](https://www.youtube.com/embed/LKz1jYngpcU?feature=oembed)

视频

有一些涉及组合的有趣用例:

*   为有听力障碍的人提供物联网信息平台的 Abilisense 正在使用 IBM Watson、无服务器平台 OpenWhisk、Kafka 和 MQTT 向用户发送警报，如烟雾警报或窗户破碎。

https://www.youtube.com/watch?v=z4qGil4ZjWE

以及其他选项:

*   谷歌去年 5 月宣布了云物联网核心，由两部分组成:一个 MQTT 桥，从现场的设备中获取数据，并将其发送到谷歌的发布/订阅服务。处理完数据后，第二个新部件—设备管理器—会将数据发送回连接的设备。
*   12 月，亚马逊发布了 Amazon MQ，这是一个为 [Apache ActiveMQ](http://activemq.apache.org/) 提供的[托管](http://www.i-programmer.info/news/141-cloud-computing/11350-amazon-releases-managed-message-broker-service-for-activemq.html)消息代理服务。

专题图片: [Patrick Bombaert](https://www.flickr.com/photos/capture-creation/) 制作的[蓝色地球和太空铁罐](https://www.flickr.com/photos/capture-creation/14447856391/in/photolist-o1H3mg-Xw2c23-cHNaNJ-2vVkpu-cTYoVy-dV5Zqq-dGiyJX-ArXs3-31Wy7h-J5kVyN-PaLkR-ezVoT8-74ee7U-73j4k9-73f4Bx-5BKHn4-73f4ir-73f46c-73f4Zg-73f4AK-UMrm2N-7fZGLR-74dKWU-73f3xV-73j2Vm-V8cgvU-7fS52E-9d3LX6-4RZm69-qZeNj-73f5hn-73j4qd-74edz7-73f3W4-7GxAsT-oiFbhS-C2QYAo-8BeELN-31RYg4-7YD1be-ftXivC-9Y6DGc-MDxXFm-7g3GDz-84qkZJ-br9Ayt-nZzkyt-7ga6ob-cczoLu-deS4SD)的生动图像，获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>