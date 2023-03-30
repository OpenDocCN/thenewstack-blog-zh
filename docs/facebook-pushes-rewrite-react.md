# 脸书推动重写 React

> 原文：<https://thenewstack.io/facebook-pushes-rewrite-react/>

开发人员现在一定已经习惯了突破性的改变。流行的 [JavaScript](https://www.javascript.com/) 框架已经被完全重写为 [React Native](https://facebook.github.io/react-native/) ，迫使开发人员重新编写代码以适应新版本。现在看来，[脸书](https://www.facebook.com)正计划为 16 版本的发布进行另一次重大的平台重写。

在本周的脸书开发者大会上，该公司详细介绍了 React 的[版本 15.5](https://facebook.github.io/react/blog/2017/04/07/react-v15.5.0.html) 即将到来的变化，并预览了被称为 [React Fiber](https://github.com/acdlite/react-fiber-architecture) 的完整核心重写。光纤对于 F8 来说并不是全新的，因为新的核心算法已经在之前的脸书活动中讨论过了。

例如，在 3 月份的 React Conf 2017 大会上， [Mozilla](https://www.mozilla.org/en-US/) 新兴技术团队的 [Lin Clark](https://github.com/linclark) 详细介绍了光纤领域即将发生的变化。目标是防止工作单元阻塞应用程序中的线程。React Fiber 能够控制处理线程，完成一些工作，然后放弃控制权，以便完成其他工作。这是通过处理截止时间来控制的，处理截止时间决定了 React 什么时候从工作中返回来检查是否到了做另一项工作的时间。

[https://www.youtube.com/embed/ZCuYPiUIONs?feature=oembed](https://www.youtube.com/embed/ZCuYPiUIONs?feature=oembed)

视频

这有助于防止单个进程在做一些普通的事情时独占系统，比如绘制界面或执行一些 CPU 密集型计算。纤程在进程被移入以完成工作时进入:纤程是与该工作相关联的对象，如果它们仍然适用，则被移入并复制到内存中。

脸书的工程经理 Tom Occhino 在 F8 的演讲中说，“如果我们能够在框架层面上安排要做的工作，并且将一些渲染优先于其他渲染，那将是非常棒的。奥奇诺说:“我们为呈现用户界面所做的工作并不都是平等的。

Occhino 说，React 纤维的突破性变化不是由脸书轻而易举地承担的。“我们不希望不得不重写数以千计的组件，我们也不希望 React 社区中的任何人不得不从头开始重写他们的应用程序。总会有一条渐进的道路通向我们明天想要达到的目标，”奥奇诺说。

为了进一步减轻恐惧，他暗示脸书用户已经使用光纤数周了。“日程安排功能目前是关闭的，但我们将随着时间的推移在我们知道会提供更好体验的地方开始启用它们，”Occhino 说。

Occhino 继续说，React Fiber 完全是流类型的，包括更好的错误边界，有更多的描述性错误和警告，从而帮助开发人员更轻松地跟踪问题。

React 并不是唯一一个以破坏向后兼容性的方式进行更改的项目。 [Relay](https://facebook.github.io/relay/) ，用于构建数据驱动 React 应用的开源 JavaScript 框架脸书在 F8 的第一天就被 Relay Modern 取代。中继是围绕 [GraphQL](http://graphql.org/) 建立的。

Relay Modern 的特点是重新设计了 API，减少了用户的困惑，同时保留了 Relay 的现有优势:并置数据和视图定义，以及声明性数据获取。这种新框架还具有性能改进和整体封装尺寸更小的特点。

当谈到会议的主题:各种形式的现实时，React 传遍了 F8。增强现实、虚拟现实和混合现实应用是 React VR 的目标。这个新的 JavaScript 框架专注于将[网络虚拟现实](https://webvr.info/)作为虚拟现实技术。在周二上午的主题演讲中，脸书创始人兼首席执行官马克·扎克伯格表示，虚拟现实和增强现实对公司的发展非常重要，他展示了公司正在开发的一些虚拟现实和增强现实环境。

今年，脸书正式成为最疯狂的主题演讲主题的旗手，因为在第二天，该公司开始讨论其太阳能互联网无人机的计划，该计划利用新开发的毫米波技术在 13 公里内传输高达 36Gbps。该公司还讨论了大型系绳天线的计划，这种天线将悬挂在一架小型直升机上，可以轻松传播无线互联网接入，而且没有巨型天线的碍眼之处。

目标是将快速互联网接入扩展到农村地区，并最终通过这项新的 ISP 服务支持电话、视频聊天和表面上的脸书虚拟现实会议。然而，这可能需要很长时间才能实现，因为在 F8 讨论的无人机舰队据说至少需要 10 年才能部署。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>