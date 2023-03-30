# Dropbox 在其 API 中纠结于服务器状态困境

> 原文：<https://thenewstack.io/dropbox-wrangles-with-the-server-state-dilemma-in-its-api/>

Dropbox 开发人员有一个问题，那就是:Dropbox 存储中共享文件夹的内容应该有一个功能，允许用户只请求最近的更改。但是这个函数的参数组合长度超过了一个旧的万维网联盟(W3C)文档所说的——尽管不是很明确——在实现 GET 方法时要小心。Dropbox 是否应该实现 POST 方法，以一种 Web 不期望的方式？

让我们面对现实吧:如果 Dropbox 反其道而行之，但它的实现是可行的，那么它伤害的是谁？

## 你得到你所支付的

在 Web 开发人员中，超文本传输协议不是为了管理远程过程调用而创建的，它的设计者也没有为此目的而设想。在 HTTP 的创始文件之一，蒂姆·伯纳斯·李在 1991 年写的——这份文件今天看起来更像是 Evernote 上记下的东西——他突然用下面的话结束了他对 0.9 版本的想法列表:“请求是[等幂的](https://en.wikipedia.org/wiki/Idempotence)。断开连接后，服务器不需要存储任何有关请求的信息。

Berners-Lee 当时并没有意识到这一点，但他为使用 HTTP 实现服务之间的远程交互埋下了种子:请求不会改变服务器状态。如果是这样的话，Web 事务的异步性将使任何多用户数据库方案都变得不可能。

这个 0.9 版本的文档甚至没有 POST 这个词。

当 HTTP 显然将成为交易的交换时，POST 方法被创建来让浏览器(后来的“用户代理”)向服务器提供用于数据库的数据，数据的传输可能意味着状态的改变。POST 不是等幂的；由服务器第二次执行的一个方法可能会将状态更改为某种意想不到的状态。通常浏览器不允许在没有警告用户的情况下重新加载 POST。

这两种方法之间似乎有简单的区别。GET 看起来够被动，POST 更多的是需求。GET 不会改变它所获取的东西的状态；POST 确实会影响接收其数据的资源的状态。他们似乎彼此明显对立。所以你应该知道用哪一个，什么时候，为什么。

但它们并不完全是镜像的对立面，这就是问题所在。虽然 Berners-Lee 没有设想 GET 方法的最大长度，但是几年后，当 W3C 指定 HTTP 1.1 时，[它警告说，这样的最大长度实际上可能存在](http://www.w3.org/Protocols/rfc2616/rfc2616-sec3.html#sec3.2.1)。“服务器应该对依赖 255 字节以上的 URI 长度保持谨慎，”它说，“因为一些旧的客户端或代理实现可能无法正确支持这些长度。”

## 幂等的意想不到的优点

“HTTP 是为一个特定的分层文档存储和检索用例而开发的，”[Dropbox 开发团队周一在其公司博客上声明](https://blogs.dropbox.com/developers/2015/03/limitations-of-the-get-method-in-http/)“所以它并不完全适合每个 API 也就不足为奇了。也许我们不应该让 HTTP 的限制过多地影响我们的 API 设计。”

它是向其他开发者解释为什么 Dropbox 选择使用 HTTP 的 POST 方法而不是 GET 来实现一个名为/delta 的特定 API 调用的文档的一部分。Dropbox 并没有违反任何硬性规定。多年来，为了利用 HTTP 的消息数据字段作为长参数的位置，经常有人建议使用 POST 而不是 GET。

Java Server Pages 上的本教程的作者[说，POST 通常比 GET 更可靠，只要敏感数据被传递到服务器，就应该使用 POST 因为 GET 的参数以普通 ASCII 编码，作为查询字符串的附件。在 Diffen.com“比较任何东西”网站的这个教程中，一个评论者认为 POST 比 GET 更好，仅仅是因为它宽松的尺寸限制。所以如果 Dropbox 踩到了地雷，它以前就被踩过。](http://www.tutorialspoint.com/jsp/jsp_form_processing.htm)

但或许因为是 Dropbox，这一举动遭到了一些批评。Sabre 项目的首席开发人员和 PHP 框架互操作小组的成员 Evert Pot 周一在他的个人博客上称 Dropbox 的决定是“糟糕的 API 设计”。

然而，Pot 并没有把责任推给 Dropbox。“我们显然遇到了人为的限制，现有技术无法很好地解决这些限制，”他写道。他提出了一个替代方案，该方案于 2002 年首次被指定为 Web 分布式创作和版本控制(WebDAV)扩展的一部分，[这是一个官方仍在开发中的系统，用于实现 Web 服务器中文件的远程编辑和协作。](http://www.webdav.org/)

Pot 认为，报告可以有一个请求体，它是安全的，并且是幂等的。他说，它可能被遗忘了，因为 WebDAV 在很大程度上被遗忘了。“然而，它的语义是明确定义的，在任何地方都适用。我很乐意看到更多的人开始学习它，并将它添加到他们的 HTTP API 工具带中。”

Pot 链接到[他发布到 Stack Overflow](http://stackoverflow.com/questions/978061/http-get-with-request-body) 的这个六年前的问题，本质上可以归结为:如果任何 HTTP 方法都可以有请求体 POST 方法中使其对 Dropbox 有吸引力的部分——那么 GET 也可以有请求体。那么为什么不用呢？

在这段漫长的时间里，这个问题的最高评价来自 HTTP 的主要作者 Roy Fielding。Fielding 建议说，实际上，理论上 GET 可以像它的消息体一样被解析。但是既然它没有用，就不应该这样解析。

> “解析的需求与方法语义的需求是分开的，”Fielding 写道。"所以，是的，你可以用 GET 发送一个 body，不，这样做永远没有用."

尽管如此，一名开发人员周一对 Dropbox 的博客帖子做出了回应，评论称，在 GET 中使用请求体从未被明确禁止。但在周三发布的一篇评论中，保险业开发人员肖恩·钱伯斯(Sean Chambers)提出了一种“无状态”的解决方案，而是使用 PUT 方法:“你仍然可以通过对具有更新状态的‘delta’资源执行 PUT 来实施 HTTP 语义，”钱伯斯写道，“该资源的新状态将是你的其他两个资源之间的 delta。”

这样看来，解决 Dropbox 困境的方案是可行的，既不会破坏协议，也不会纯粹出于审美原因而遵循别人的原则。对所有开发人员来说，这个问题的长期解决方案可能是 W3C 修改 HTTP/1 和 HTTP/2 的规范，解释在新的上下文中应用旧方法的正确方式。

通过 Flickr Creative Commons 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>