# WP 引擎“无头”，跳到 Jamstack 中

> 原文：<https://thenewstack.io/wp-engine-goes-headless-jumps-in-the-jamstack/>

托管 WordPress 提供商 [WP Engine](https://wpengine.com/) 已经引入了 [Atlas](http://www.wpengine.com/atlas) ，这是一个新的无头 WordPress 产品，提供了该公司声称的“唯一的无头解决方案”，其中包括动态节点层、静态内容交付网络(CDN)层和无头内容管理系统(CMS)层。

在传统的 WordPress 部署中，数据和它的表示紧密耦合在一起，WordPress 模板和内容在运行时使用 PHP 转换成 HTML。在一个无头的 WordPress 部署中，内容和它的表现是分离的，而是通过一个应用编程接口(API)来提供。虽然 headless WordPress 为开发人员提供了额外的步骤——访问内容并将其呈现给最终用户——但它也将开发人员从 PHP 的半静态特性中解放出来，并允许他们以多种方式解释和呈现内容。

[WP Engine 的首席软件工程师、](https://www.linkedin.com/in/jason-bahl-a6b98627) [WPGraphQL 插件](https://www.wpgraphql.com/)的创建者杰森·巴赫尔说，他以前在一家报社使用过一个无头的 WordPress 实现，那里的内容传统上是通过 PHP 在网络上呈现的，但也有一个使用 React Native 的移动应用程序，甚至被发送出去打印实体副本。虽然 WordPress 充当了熟悉的数据输入点，但他们能够将内容分发到多个渠道，否则这些渠道将无法使用。

该公司使用 Jamstack 技术集合将数据从渲染层中分离出来，这些数据可以通过 API 获得

有了 Atlas，WP Engine 不仅进入了无头内容管理系统领域，还进入了 Jamstack 领域，其中 JavaScript、API 和标记的组合同样将内容从其表示中分离出来。Atlas 通过 API 提供可访问的内容，可以将内容预编译成静态 HTML，然后通过内容交付网络进行分发，提供极快的最终用户体验。

“Atlas 为机构提供的一项功能是，例如，你可以使用 React Native 构建移动应用程序，也可以使用 React Native 构建 web 应用程序。因此，您可以让您的团队使用相同的工具在不同的平台上构建前端，”Bahl 在接受采访时解释道。“我认为，将内容与表现分开，可以让那些希望随着时间的推移节省成本的机构共享资源。你不必雇佣专门的移动团队和专门的 web 团队。现在，您可以共享两个项目的资源。”

然而，Jamstack 正在发展，许多供应商增加了无服务器功能来提供动态内容而不是静态内容，有了 headless WordPress，它只是开发人员可用的许多表示方法之一。Bahl 强调，虽然 Jamstack 只是许多可能性中的一种，但 Atlas 的真正好处是让开发人员在一个地方就能获得完全托管的体验。

Bahl 说:“你有一个托管 WordPress 的供应商，一个你的构建工具的供应商，有时还有一个不同的托管供应商。”“Atlas 将这一切都放在一个房子里，所以你可以将你的 WordPress、你的节点托管你的构建工具、你的 CDN，都放在一个屋檐下，放在一个计费计划下，放在一个屡获殊荣的支持团队下。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>