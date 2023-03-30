# CNCF 的 CloudEvents 规范可以促进跨无服务器平台的互操作性

> 原文：<https://thenewstack.io/cncfs-cloudevents-spec-could-facilitate-interoperability-across-serverless-platforms/>

通过发布云事件规范，云本地计算基金会 (CNCF)希望促进无服务器平台之间更好的互操作性。该项目是在 0.1 版本迭代，并希望它将在 6 月被批准为 CNCF 沙盒项目。

CloudEvents 规范提供了(以前称为 OpenEvents)一条路径，允许任何两个组件传输一个事件，不管它们是函数、应用程序、容器还是服务，说， [Doug Davis](https://www.linkedin.com/in/doug-davis-05b9ba6/) ，IBM 高级技术人员，CNCF 无服务器工作组成员。

Davis 说:“就像 HTTP——以其最基本的形式——通过标准化如何表示关于正在传输的消息的明确定义的元数据来帮助任何两个组件之间的互操作性一样，CloudEvents 也在做同样的事情。“定义公共元数据将有助于将事件从任何生产者转移到任何消费者。”

CNCF 成立了无服务器工作组，以帮助关键的云利益相关者创建一种厂商中立的方法来实现无服务器，以及更广泛的事件驱动架构。到目前为止，工作组已经发布了 [一份白皮书](https://thenewstack.io/3-questions-serverless-technology/) 和一份当前无服务器玩家的景观。

创建 CloudEvents 是为了以一种通用的方式描述事件数据。在事件驱动的架构中，生产者需要能够在任何消费者监听之前生成事件，消费者需要能够标记对尚未生成的事件(或事件类)的兴趣。producer 应用程序可以在任何地方运行，并创建温度读数或体育比赛结果等数据。消费者是可以在任何地方运行的应用程序。然后是中间件，它可能将来自生产者的事件转换为消费者读取，或者基于特定条件过滤事件，或者监控事件流和 ops 数据。

这种类型的体系结构已经可能涉及多个参与者，每个参与者以稍微不同的方式描述事件，从而造成复杂性和互操作性的噩梦。

CloudEvents GitHub repo 宣布该规范的重点在于克服开发人员学习多种供应商和平台接收事件方法的挑战。“这也限制了库、工具和基础设施帮助跨环境传递事件数据的潜力，如 SDK、事件路由器或跟踪系统。我们可以从事件数据中获得的可移植性和生产力总体上受到了阻碍，”登录页面指出。

戴维斯更详细地解释道:“挑战主要来自于工作量的形式，以及事件接收器完成其工作所需的先验知识。例如，一个充当路由器的组件，根据事件的某些特征将事件调度到各种后端系统，应该能够做到这一点，而不必实际了解整个事件本身。”

Davis 说 CloudEvents 规范将支持这种类型的事件动作。“简单地定义公共元数据以及在哪里可以找到它，使人们更容易提取这些数据，”戴维斯说，并补充说，通过这种类型的规范，也将使企业能够开始为事件架构构建新的工具。

开发者可以 [注册获取更多信息](https://zoom.us/my/cncfserverlesswg) 关于 spec， [加入 CNCFG 的无服务器工作组](https://zoom.us/my/cncfserverlesswg) 的每周电话会议，或者查看[cloud events GitHub repo](https://github.com/cloudevents/spec)并直接投稿。

云本地计算基金会(CNCF)是新堆栈的赞助商。

专题图片:照片由[普里西拉·杜·普里兹](https://unsplash.com/photos/FOsina4f7qM?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/search/photos/track?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>