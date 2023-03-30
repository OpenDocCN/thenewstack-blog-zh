# 如何使用 Cookies 和令牌处理会话

> 原文：<https://thenewstack.io/how-to-handle-sessions-with-cookies-and-tokens/>

一个会话可以被认为是用户在一个给定时间范围内的活动。它从用户第一次与应用程序交互开始，在用户停止活动(显式或隐式)时结束。会话可以是匿名的(未经身份验证的)或经过身份验证的，但是当我们讨论会话时，我们通常指的是用户经过身份验证的会话。

认证会话允许应用程序[识别用户](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)并基于会话数据执行授权，而不需要用户重复经历[认证](https://thenewstack.io/how-do-authentication-and-authorization-differ/)过程。

用户可以隐式地结束会话，例如通过关闭浏览器或客户端，或者通过发起注销来显式地结束会话。像“记住我”这样的功能通常可以防止会话在退出浏览器时被丢弃。经过身份验证的会话也可能过期并失效。

## 会话不是单一的

用户成功通过身份验证后，身份验证会话开始。当使用 [OpenID Connect](https://curity.io/resources/learn/openid-connect-overview/) 时，用户向 OpenID Connect 提供者认证。身份验证成功后，OpenID 连接提供者将 ID 令牌返回给客户机，客户机验证令牌并创建一个会话。客户端还会收到一个访问令牌，甚至可能是一个用来调用下游 API 的刷新令牌。在此阶段，涉及三个环节:

*   与客户的对话
*   与 OpenID 连接提供程序的会话
*   与 API 的会话

每当用户与应用程序交互时，它都会利用客户端会话。与 [OpenID](https://thenewstack.io/just-in-time-authorization-with-openid-sse-and-caep/) Connect 提供者的会话可以在不同的客户端和应用程序上重用，提供了[单点登录功能](https://curity.io/resources/learn/sessions-and-sso/) (SSO)。这些会话通常由 cookies 表示。

应用程序可以使用访问和刷新令牌来代表用户调用下游 API。由于 API 使用访问令牌进行授权决策(这是认证会话定义的一部分)，令牌是另一个会话(API 会话)的构建块。

## 维护会话的工具

在接收并验证 ID 令牌后，客户端可以选择发布一个会话 cookie 来跟踪用户。它可以在内存或服务器端存储来自 ID 令牌的会话数据。例如，客户端可能希望保留用户名、身份验证时间或身份验证方法，然后丢弃 ID 令牌。

另一种类型的应用程序可以只在存储器中保存 ID 令牌来表示会话。如果需要，客户端还会在会话中存储访问令牌和刷新令牌(可选)。因此，在管理和维护应用程序的会话时，请记住以下工具:

*   饼干
*   代币
*   后端的会话数据
*   单点登录（single sign-on 的缩写）

尽管 SSO 属于 OpenID Connect 提供者的领域，但是应用程序仍然可以使用它来无缝地访问用户会话。如果使用，用户甚至不会注意到客户端更新了其会话。访问令牌与刷新令牌一起可以产生类似的效果。当与刷新令牌结合使用时，访问令牌可以长期存在，并且比客户端会话更长时间有效。因此，尽管客户端自己与用户的会话已过期，但它可能能够代表用户调用 API。

## 生命周期设计

如果您将应用程序看作一个程序的单个实例，那么处理会话和保护数据是非常简单的。短期访问令牌被用作 API 凭证，而[刷新令牌](https://curity.io/resources/learn/oauth-refresh/)可用于检索新的访问令牌，无需用户交互。当使用滚动刷新令牌时，新的刷新令牌与访问令牌一起发布，这降低了令牌被盗的风险。

然而，一个应用程序通常是几个组件的编排。它可能包括一个或多个客户端，如 web、桌面或移动客户端，以及后端的其他 API 和 API 网关或它们之间的反向代理。

用户可能同时与应用程序的几个组件进行交互。因此，在处理会话管理时需要权衡，在某些用例中，启用首选行为可能会很有挑战性。

一个简单的无状态设计可能是一个很好的起点，它使用短期访问令牌，这些令牌将很快到期，不需要被撤销。在一些应用程序中，用户可以同时从不同的客户端(设备)登录，而其他人则希望对此加以限制(比如付费墙)。在后一种情况下，必须能够立即撤销会话。

在撤销访问令牌时，要考虑令牌格式。使用[幻影令牌流](https://curity.io/resources/learn/phantom-token-pattern/)的不透明令牌可以被撤销，尽管网关需要被通知撤销事件。同时，JSON Web 令牌(JWT)是自包含的，所以 API 不会知道 JWT 是否被撤销，因为它不会在每个请求上都联系授权服务器。

## 用于会话管理的安全资源

有关会话管理概念的深入指南，包括订阅撤销事件等高级技术，请参见“[会话管理技术](https://curity.io/resources/documents/session-management-in-curity-identity-server/)”解决方案简介。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>