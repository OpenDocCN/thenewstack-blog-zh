# Wicket 8:服务器端 Java Web 框架的新功能和未来

> 原文：<https://thenewstack.io/wicket-8-whats-new-and-whats-next-for-the-server-side-java-web-framework/>

紧随 Apache Wicket 8 T1 的发布，这个项目有更多的工作要做:甲骨文宣布它将在某个尚未确定的日期从 Java T3 中移除序列化，这个日期是 T2。

Wicket 是 21 世纪中期“Java 服务器端 web 框架之战”的少数幸存者之一，它严重依赖于序列化。

流行的面向组件的服务器端 Java web 框架帮助开发人员使用更少的代码行创建复杂的 web 应用程序。它被广泛应用于巴西空军、德国国家科技图书馆、日本警察厅和挪威外交部等机构。

它不同于其他 Java 服务器端框架。Wicket 允许开发人员考虑界面组件，如“页面”、“面板”、“按钮”、“链接”、“表单”和“列表视图”，而不是考虑进入应用程序的请求和处理请求。

新版本包含了对 Java 8 习惯用法的 Wicket API 的全面支持。一切都已升级，使 Java 8 成为最低要求的版本。

在某些情况下，它增加了对 lambdas 的支持，但不是全部。子类化仍然是 Wicket 组件的主要扩展机制。

已经为各种形式的模型(数据绑定)和行为(组件的适配器)提供了 lambdas 的工厂。

如果你使用 Lambdas，你需要存储动态功能并保存对它的引用，这需要额外的内存， [Martijn Dashorst](https://github.com/dashorst) 解释道，他是荷兰 Topicus 的软件工程师，也是 Apache Wicket 的副总裁。

他说，由于 Wicket 页面通常由数千个组件组成，所需的内存会增加，这解释了为什么该项目之前没有选择使用 Lambdas。

称为[行为](https://ci.apache.org/projects/wicket/guide/6.x/guide/advanced.html)的特性允许从外部修改组件。例如，您可以向标签组件(标签组件显示文本)添加行为，并向其添加单击行为。当用户点击标签时，如果该行为被附加到标签上，它将在 Java 端发出一次点击，这样开发者可以向其添加额外的行为。

“这是扩展组件功能的非常灵活和强大的方式。这些行为非常适合使用 Lambdas。他们有有限的方法可以实现，所以使用 Lambdas 的额外内存负担没有组件那么严重，”他说。

Wicket 8 最大的变化之一是组件的数据绑定。以前，您会使用文本字符串来绑定此属性。Wicket 8 中的 IModel 被设计成一个函数接口，允许开发者在任何可以使用模型的地方使用 Lambdas。新的 LambdaModel 允许组件的类型安全和重构安全的数据绑定。达肖斯特说，这是一种更安全、更快捷的评估 Java 代码的方式。

此外，检票口 8:

*   为 Java 8 中处理日期和时间的新类型增加了本机支持。它们可以被转换、验证并绑定到组件
*   在需要阐明 API 的地方使用 Java 的可选类型。
*   需要 Servlet 3.1。-现代服务器，如 Tomcat 8.x、Jetty 9.1+或兼容 Java EE 7 的服务器。

虽然开发人员不应该为 Wicket 8 重写应用程序，但该团队敦促用户参考[迁移指南](https://cwiki.apache.org/confluence/display/WICKET/Migration+to+Wicket+8.0)。

达肖斯特说，鉴于甲骨文计划消除序列化，该项目将寻求其他框架来处理它。

他说，该项目长期以来一直专注于组件和数据级别的安全性，使开发人员能够在开发过程中的每一步都添加安全检查。

当被问及 Wicket 的安全性时，考虑到与序列化相关的安全漏洞，Dashorst 解释说，存储的数据驻留在服务器上，不依赖于来自客户机的 Java 序列化数据。攻击者必须能够访问服务器。

他说，状态的存储不能通过 Wicket 远程访问——比如从连接到 Wicket 应用程序的浏览器。

Wicket 是开源项目[“yso serial”](https://github.com/frohoff/ysoserial)中被发现存在漏洞的项目之一，但它只能在[的概念证明](https://remoteawesomethoughts.blogspot.com/2016/08/apache-wicket-6230-deserialization.html)中被利用，并且有效负载不能通过 Wicket 交付。

“因此，尽管 Wicket 高度依赖于序列化，而且序列化存在安全问题，但我们并不认为我们对 Java 序列化/反序列化的使用是可利用的攻击媒介。任何攻击者都需要 Wicket 控制之外的额外访问机制来传递有效载荷，并欺骗服务器执行利用，”他说。

“也就是说，我们期待着为 Wicket 的状态保持实现新的数据存储，因为 Java 的默认序列化是一个全面的解决方案，相对较慢，使用大文件格式，如前所述，充满了漏洞。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>