# 必须保护的不仅仅是银行应用程序接口

> 原文：<https://thenewstack.io/its-not-only-banking-apis-that-must-be-secured/>

乔纳斯·伊格博姆

乔纳斯是 Curity 公司的销售工程总监。他的专长是身份和访问管理，以及特权用户、数据库和应用程序的访问控制解决方案。

API 经济快速增长的事实不再是新闻，而是常识。[许多报告](https://nordicapis.com/20-impressive-api-economy-statistics/)现在描述了用于不同目的的 API 使用的急剧上升。随着公共和内部 API 的使用不断升级，报告还显示 API 攻击急剧[激增](https://nordicapis.com/api-abuse-on-the-rise-why-should-organizations-be-worried/)。迫切需要保护 API，但是，正如大多数软件专业人员所知，公司并不总是将安全性放在首位。

近年来，许多非金融 API 都泄露了用户信息，包括特斯拉、Peloton、LinkedIn 和万豪的违规事件。虽然这些数据可能看起来不重要，但泄露的信息可能会被用来发起进一步的攻击，尤其是网络钓鱼攻击，在此期间，更重要的用户数据可能会落入攻击者手中。考虑到这一点，保护 API 不仅对银行是必要的。任何 API，无论是公共的还是内部的，都需要强大的安全性来阻止不断升级的攻击，以保护它们所暴露的信息。

保护 API 的核心是基于令牌的架构。另一方面，部署静态 API 密钥的遗留方法是不可取的:如果 API 密钥丢失、被盗或被共享，则必须在使用该 API 的客户机中轮换和更新它。这不是一个非常灵活或可扩展的模型。首先还有获取 API 密钥的问题。无论是用户还是系统请求访问 API，都必须以某种方式对检索过程进行认证。

## 令牌验证

API 可以承担验证用于保护 API 的访问令牌的责任。访问令牌可以有多种格式，但 JSON Web 令牌(JWT)是最常用的方法。当应用程序或服务调用 API 时，JWT 在授权头中传递。JWT 的一个优点是它直接持有一组声明，API 本身可以使用这些声明来确定或授权将什么信息返回给调用者。API 可以用多种语言开发，但是令牌验证的实现是相似的。Curity 为不同的 API 实现提供了几个代码示例，为实现这种方法提供了一个很好的起点。

使用 jwt 的缺点是，至少对于公共应用程序来说，它们可能包含个人身份信息。这通常是你不想公开分享的事情。相反，公共应用程序处理不透明的(按引用)令牌要好得多。这种令牌只是一个唯一的字符串。接收不透明令牌的 API 可以通过调用身份提供者(IdP)来自省令牌。然而，这对于频繁执行的 API 来说成本很高。更好的方法是利用 API 网关来处理自省处理，这样 API 就可以使用它的资源来提供内容。

## API 网关

将 API 网关放在公共和内部 API 之前是添加新的安全措施的一个好方法。网关可以基于策略和谁在调用 API 来限制 API 调用的速率。检查请求有效负载的漏洞，比如注入攻击，通常是大多数现代网关也可以处理的事情。

API 网关也是处理 API 调用的身份验证和授权的绝佳场所。一些网关具有开箱即用的基本处理能力，但在许多情况下，利用[幻影令牌](https://curity.io/resources/learn/introspect-with-phantom-token/)方法或[分割令牌](https://curity.io/resources/learn/split-token-pattern/)方法会产生更安全和健壮的实现。网关可以使用作用域处理访问令牌的初始验证和粗粒度授权。这将使 API 免于运行初始令牌验证和频繁的自检调用。此外，它还减少了对 API 本身的未授权调用。无论是使用幻影方法还是分割令牌方法，公共应用程序都不需要持有 JWT。API 网关获取 JWT，并在将 JWT 发送给 API 之前对其进行验证。此时，API 显然可以根据需要使用 JWT 来确定返回什么数据。

将这些模式与现代 API 网关集成起来相当简单。在 Curity，我们多年来一直与几家网关提供商合作，并开发了插件来简化集成过程。如果 API 网关是架构的一部分，那么集成一个基于令牌的方法来保护 API 应该是一个既定的目标。

## 开发者门户

随着组织开发的 API 越来越多，开发人员应该有一个标准的方法来理解如何使用它们。这就是为什么一个好的[开发者门户](https://nordicapis.com/6-examples-of-great-developer-portals/)是 API 提供者和需要使用它的开发者之间的关键链接。我们不会在这里探究 DevPortal 的内部工作方式，但是一个关键的组件是管理 API 访问。这通常涉及生成一个 client_id 或 secret，或者管理可用于获取访问令牌的证书，这些令牌将授予对 API 的访问权限。

DevPortal 还用于跟踪 API 的使用情况，并可以关联谁或什么在访问 API 以及访问的频率。基于令牌的架构可以通过将特定的 client_id 映射到开发人员(或应用程序)来帮助保护 API。例如，通过这种方式，API 网关可以根据提供的令牌确定谁在访问 API。为了使这个过程自动化，通常使用[动态客户端注册(DCR)](https://curity.io/resources/learn/openid-connect-understanding-dcr/) 在 DevPortal 和身份提供者(IdP)之间建立一个集成。使用 DCR，DevPortal 会在 IdP 中自动生成一个控制令牌发放的新客户端。这在令牌分发和开发人员或应用程序之间创建了一对一的映射。它还允许完全控制和监视 API 的访问方式。

## 令牌处理程序

另一个考虑因素是单页面应用程序(SPA)如何处理访问令牌。在 SPA 前端处理和存储令牌有很大的安全隐患。spa 容易受到跨站点脚本攻击(XSS ),并且不能安全地存储任何类型的令牌。除此之外，浏览器正在移除对第三方 cookie 的支持，例如，如果令牌服务在不同于 SPA 的域上运行，则在 cookie 中存储刷新令牌变得越来越困难。

[令牌处理模式](https://curity.io/resources/learn/the-token-handler-pattern/)可以缓解这些问题。令牌处理程序提供了可以与 API 网关集成的组件。SPA 将仅直接与令牌处理器通信，而不是直接与令牌服务通信来获取令牌。令牌处理程序负责处理令牌，并将安全的 SameSite cookies 发布给用于身份验证和授权的 SPA。

令牌处理程序可以是 API 网关或 API 代理上的插件。在这篇[概述](https://curity.io/resources/learn/token-handler-overview/)中有关于令牌处理程序的更多细节，在这篇[“使用令牌处理程序模式的 SPA”](https://curity.io/resources/learn/token-handler-spa-example/)文章中有一个工作示例。

## 不仅仅是银行

API 经济已经爆炸式增长，并且还在继续增长。因此，保护 API 不再是事后的想法。API 安全不只是针对银行类 app。在任何新的 API 项目中，都应该从头开始实现一个健壮的基于令牌的架构，以实现最高级别的 API 安全性。这一点，再加上 API 网关和一个好的 DevPortal，将保护 API 并为开发者使用 API 铺平道路。对于 SPA，考虑使用与 API 网关或 API 代理集成的令牌处理程序，以避免在易受 XSS 攻击的 SPA 中直接处理令牌。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>