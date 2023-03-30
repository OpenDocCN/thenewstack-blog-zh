# 孔，在 1.0，一个服务控制平台

> 原文：<https://thenewstack.io/kong-at-1-0-a-service-control-platform/>

前身为 Mashape 的公司 Kong 已经发布了其核心开源 API 网关的第一版，也称为 Kong T3。这是近四年制作经验的结晶，客户包括诺基亚、纽约时报和哈佛大学。

Kong 1.0 是该公司构建服务控制平台的愿景的基础，该平台结合了人工智能、机器学习和其他先进技术，以中介服务的信息流。

“我们相信，未来所有的数据都将是动态的，将从数据池转移到一个可以随时在系统间代理信息的地方。Kong 的工程副总裁 [Geoff Townsend](https://www.linkedin.com/in/geoff-townsend-25058347/) 说:“Kong 一开始是一个网关，但我们在 1.0 发布后增加的功能将成为一个服务控制平台。据该公司称，到目前为止，该软件已经被下载了 4500 万次。

本周在 [Kong Summit 2018](https://konghq.com/kong-summit/?utm_source=pressrelease&utm_medium=referral&utm_content=1-0) 上，这家总部位于旧金山的公司将讨论 1.0 里程碑以及企业部分，包括开发者门户、开放 API 规范、自动生成和自动配置，以及明年年初推出的功能。

“我们希望您能够以一种简单的方式了解并记录通过该平台的事情。[我们将]从生产中的服务自动生成开放 API 规范，并且您将能够记录您没有记录的服务。使用开放的 API 规范来自动配置 Kong 的节点，这样您所记录的内容就与 prod 中的内容相匹配。他说:“有一个 API 地图，显示实时流量生成的拓扑结构。“孔在网络中处于有利位置，因此我们将能够进行一些异常检测和机器学习。”

Kong 构建在 Nginx 反向代理服务器之上。它[提供服务](https://thenewstack.io/mashape-opens-kong-a-microservices-proxy-built-on-nginx/),包括一个 RESTful API 接口，用于在一种注册表中注册 API 本身，以及一个插件平台，提供微服务经常借用的公共函数的基础。

“它解决了处理认证协议和系统的所有难题，”首席执行官 Augusto Marietti 先前告诉新堆栈。

日志是另一个可能被插件暴露给微服务的很好的常用服务，通过 Kong。

“对于那些拥有微服务架构的人来说，[Kong]不会改变它的编排方式，但它使它变得更轻，因为它可以从七个、十个或二十个微服务中删除许多常见功能，并将所有功能集中在 Kong 上…使它更轻，更易于维护，”Marietti 说。

雅虎！日本最近宣布，作为代理和路由所有 API 端点流量的单点，

Kong 帮助公司消除了为每个 API 进行身份验证和授权的冗余编码。它还使用 Kong 的金丝雀发布功能来评估一小部分用户的发布。

孔最近宣布[支持服务网状部署](https://konghq.com/blog/service-mesh-new-pattern-not-new-technology/)。去年在 2017 年的中尺度大会上，孔首席技术官[马可帕拉迪诺](https://www.linkedin.com/in/marcopalladino/)预测[API 网关和服务网格](https://thenewstack.io/api-gateways-age-microservices/)之间的相似性将继续增长。

传统上，API 网关用于处理单一应用程序和外部客户端之间的流量，而微服务架构在不同的微服务之间进行通信时，将大部分流量转移到内部。

“您仍然有外部客户端用例，但这将成为现在使用这些微服务的众多客户端之一，”Palladino 解释道。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>