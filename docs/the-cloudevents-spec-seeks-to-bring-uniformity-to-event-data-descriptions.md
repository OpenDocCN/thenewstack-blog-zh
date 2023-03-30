# CloudEvents 规范寻求统一事件数据描述

> 原文：<https://thenewstack.io/the-cloudevents-spec-seeks-to-bring-uniformity-to-event-data-descriptions/>

[CloudEvents](https://github.com/cloudevents/spec) ，一个以通用方式描述事件数据的规范，已经到了 1.0，从与[云原生计算基金会](https://www.cncf.io/announcement/2019/10/28/serverless-specification-cloudevents-reaches-version-1-0/) (CNCF)的沙盒项目进阶到它的孵化器。

由于缺乏描述事件的通用方法，开发人员不得不不断地重新学习如何处理来自不同系统的事件。它还抑制了库、工具和基础设施的开发，如 SDK、事件路由器或跨系统传递事件数据的跟踪系统。

根据 IBM 高级技术人员兼无服务器工作组和 CloudEvents 项目联合主席 Doug Davis 的说法，CloudEvents 源自 [CNCF 无服务器工作组](https://github.com/cncf/wg-serverless)，尽管无服务器中的事件数据与任何其他基础设施没有什么不同。CloudEvents 最初于 2018 年作为沙盒项目被 CNCF 接受。

事件数据本身不是特定于服务的。他说:“任何时候，当你发送一条以事件为代表的信息时，CloudEvents 都会发挥作用。

该规范旨在提高事件系统的互操作性和跨产生或消费事件的服务的可移植性，使它们能够独立开发和部署。

每个生成事件的系统通常都有自己的格式、自己的标记方式、自己的命名约定。但在很多情况下，当涉及到基本的事件处理时，中间件类型的产品(如事件网关)对语义相似的数据进行操作，如事件类型、流、是推还是拉、谁产生了事件。

“我们不会试图强迫每一个事件都符合我们的命名方式，”戴维斯说。“这是正常事件之外的额外元数据。可以把它想象成 HTTP 头。它在主体之外，但是在一个标准的位置和标准的格式中，所以如果用户想要做基本的中间件路由、过滤之类的事情，他们将知道在哪里可以找到它。

“这就是 CloudEvents 试图做的事情——在明确定义的位置用明确定义的元数据来扩充或注释现有事件，这样中间件就可以完成处理，而不必了解流经系统的每一个事件。”

它应该是将请求路由到适当的组件并便于该组件适当处理事件所需的最小信息集——尽管它本身不包含路由信息。这些数据可以在别处找到。

该项目从定义一组核心元数据(ID、源、specversion 和类型)和可选属性(包括 datacontenttype、dataschema、subject 和 time)开始。此后，它又有了扩展属性等等。数据包预计为 64KB 或更少。

CloudEvents 还提供了如何以各种格式(如 JSON)和协议(如 HTTP、AMQP、MQTT 和 Kafka)序列化事件的规范。

该项目的贡献者包括 AWS、Google、微软、IBM、SAP、Red Hat、VMware 等。

CloudEvents v1.0 已经在 Knative 的事件框架、Red Hat 的 EventFlow、Eclipse Vert.x 和 Debezium、SAP 的 Kyma、Servelss.com 的事件网关等项目中实现。在该规范创建后不久，微软宣布通过 Azure 事件网格为 Azure 中的所有事件原生支持 CloudEvents。

Davis 说，对于 GitHub 或 GitLab 等事件提供者来说，CloudEvents 可以提供更好的互操作性，只需在现有消息中添加几个 HTTP 头。

对于事件消费者来说，开发人员可以从 GitHub 请求所有事件，但是只有推送事件和基础设施不需要知道 GitHub 事件和 GitLab 事件，因为通用的语法。

戴维斯称 [Knative](https://thenewstack.io/amidst-controversy-the-knative-serverless-software-keeps-growing/) 为云事件的终极用例。

“不管事件是如何被传递到系统中的，即 Kafka、HTTP 或任何传输方式，只要他们能够转换为 CrowdEvents，路由基础设施、订阅机制、那些具有过滤功能的序列操作或并行操作进行过滤或任何路由，所有这些东西都在 CloudEvents 属性上工作……他们可以编写所有的基础设施，而不知道进入系统的事件的任何事情，并完成所有的编排，”他说，以前每次添加都需要专门的代码。

他说，CloudEvents 社区将在 KubeCon 讨论下一步计划。一些流传的想法是加密，一个关于如何编排功能的工作流文档，以及一个订阅 API，您可以从特定的云提供商那里请求事件。

![](img/f38bbb6abc5c5c343ada781ba89c8a85.png)

[KubeCon + CloudNativeCon NA](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 将于 11 月 18 日至 21 日在圣地亚哥举办，并与 11 月 18 日的[无服务器从业者峰会](https://www.cncf.io/events-well-be-at/serverless-practitioners-summit-2019/)同期举办。

云原生计算基金会、KubeCon + CloudNativeCon NA 和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>