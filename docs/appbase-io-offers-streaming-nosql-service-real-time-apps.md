# AppBase.io 为实时应用提供流 NoSQL 服务

> 原文：<https://thenewstack.io/appbase-io-offers-streaming-nosql-service-real-time-apps/>

根据 [Appbase.io](https://appbase.io/) 创始人兼首席执行官[西达尔特·科塔里](https://github.com/siddharthlatest)的说法，构建实时应用程序并没有达到应有的实时性。这就是为什么密苏里州圣路易斯？总部位于的公司正将其重点转向前端开发工具。

[Appbase.io](https://appbase.io/) 是一个托管的 Elasticsearch 服务，内置发布/订阅支持，用于流文档更新和查询结果。

它通过 Javascript SDK 和 REST API 提供了基于事件的实时数据库 API、基于 ElasticSearch 的搜索功能和协作功能，如用户认证和安全规则。

“我们希望帮助那些希望构建实时功能的开发者。这可能就像聊天一样简单，就像优步试图利用地理区域的实时数据所做的那样，”科塔里说。

它被电子商务公司用于搜索和推荐；物联网公司使用传感器数据来构建仪表板，在各种使用案例中(一个客户希望获得其整个 CRM 渠道的仪表板)，谁的销售额最高，谁是下一个客户销售代表应该致电的客户。

他说，无人机公司 Aerial Insights 正在使用它，在地图界面上实时显示无人机收集的数据，商业用品网站 shopecelect 正在使用它作为搜索界面，类似 Coursera 的电子学习网站 ly earn 正在使用它进行搜索和推荐。

## 弹性搜索+流媒体

Appbase 提供了 Elasticsearch 在[流](http://news.appbase.io/top-10-uses-of-a-streaming-database/)模式下提供的每一个查询选项。Elasticsearch 有大约 150 种你可以创建的不同查询组合。您可以实现过滤器的组合——模糊、地理位置、术语、范围、多项——并在数据更新时直接传输 JSON 结果。

Kothari 解释说，作为一名开发人员，你可以订阅这些查询，每当你的数据库发生变化时，你的端点就会随着服务器获取数据而获取实时数据。

该公司最近宣布支持 Elasticsearch v5.6.4 版本,以及 Elasticsearch 2.x 版本的后端服务。

Appbase 使开发人员能够构建包含数据库功能的实时应用程序，而不需要多个数据库或现有的服务器设置。它还可以用于现有的后端基础设施或客户端。

Appbase.io 提供了一个完全受管的流数据库——一个历史数据更新源和一个实时查询端点——以及一个内置的套接字层。为了安全，它还提供了多个读/写令牌。

它提供了一个 webhooks 触发器，可以直接调用其他服务(如 Sendgrid、Urban Airship 或 Parse)的 REST API，然后这些服务可以向用户发送通知。

它被设计为一个 OLTP 系统，可以与 Amazon Redshift、Google Big Query 或 Apache Hadoop 等工具配合使用，以处理在线交易。

## 更多开发工具

Kothari 说，Appbase 与任何托管的 Elasticsearch 提供商竞争，包括母公司 [Elastic](https://www.elastic.co/) 本身，但也与 [Firebase](https://thenewstack.io/firebase-suite-google-fires-new-mobile-dev-powers/) 、 [Pusher](https://thenewstack.io/pusher-helps-bring-real-time-apps-masses/) 和 [PubNub](https://thenewstack.io/pubnub-makes-network-programmable/) 等公司竞争，尽管流媒体使其与众不同。

然而，他认为未来将属于那些在前端帮助缓解开发人员痛点的人。

“我们增加了流媒体，但我们意识到开发者在构建实时应用时遗漏了很多东西，”他说。

该公司为 Elasticsearch 创建了广受欢迎的开源插件 [dejavu](https://github.com/appbaseio/dejavu/) ，这是一个 web 用户界面，允许您直接导入 JSON 或 CSV 文件。它是使用 React v0.14.0 构建的无服务器应用程序，可以作为扩展或 Docker 映像使用。

它还提供了用于查询创建的 Mirage 数据浏览器和用于弹性搜索映射的 Gem GUI。

Kothari 表示，该公司已经“围绕构建实时应用所需的一切，建立了一个非常活跃的生态系统。”

Appbase 希望将构建实时应用的时间从过去的几周或几个月缩短到一周甚至几个小时。一个仍在路线图上的项目是实时消费者分析。Kothari 说，它计划寻求一种开放的标准化方法来证明丢失的工具。

它将注意力转向了构建用户界面的图书馆。

“就像 [Bootstrap](https://getbootstrap.com/) 或 [Materialize](http://materializecss.com/) 一样，它们会给你现成的用户界面，这样你就不会每次开始新项目时都要重写它。我们正在尝试做类似的事情，但是是针对数据驱动的用户界面。

“如果你正在建立一个电子商务商店，你很可能需要一个搜索框，你需要一个显示结果的地方，你需要显示所有这些不同的过滤器。这些是后端的查询。有些是历史性的—您正在构建一个连接到后端数据的 UI。…它可以被搜索。用例[包括]如果你试图建立类似 Airbnb 的东西，你想要一个列表的集合，或者像亚马逊一样，你想要电子商务方面。”

为此，它提供了 [Reactive Search](https://opensource.appbase.io/reactivesearch/) ，一个用于构建类似 Yelp 的搜索界面的 React UI 组件库，以及 [Reactive Maps](https://opensource.appbase.io/reactivemaps/) ，一个用于构建实时地图的 React UI 组件库。

[React](https://thenewstack.io/vue-js-big-china/) 继续成为领先的前端 JavaScript 框架，根据 JavaScript 2017 年的状态调查，比 [Vue.js](https://vuejs.org/) 、 [Angular 2](https://angular.io/) 、 [Aurelia](http://aurelia.io/) 和 [Polymer](https://www.polymer-project.org/) 之类的更受欢迎。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>