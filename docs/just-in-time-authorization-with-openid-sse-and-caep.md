# OpenID SSE 和 CAEP 的实时授权

> 原文：<https://thenewstack.io/just-in-time-authorization-with-openid-sse-and-caep/>

依赖本地或云身份提供商(IDPS)向第三方 SaaS 应用或内部应用认证用户的企业通常面临实施有效访问控制或授权的挑战。

依靠像 RBAC 和 ABAC 这样的技术，特权通常会在任何时候超出任何用户的需求。这为越来越多的危害提供了机会，这些危害依赖于经过身份验证的用户滥用他们的访问权限来渗透、修改或擦除关键数据。

经过身份验证的用户可能代表疏忽或恶意的内部人员，或者劫持了内部人员的凭据或会话的攻击者。

## 即时存取

 [阿图尔·图尔什巴格瓦勒

Atul Tulshibagwale 是下一代企业授权解决方案的领先开发商 SGNL.ai 的 CTO。Atul 是企业身份专家，也是连续访问评估协议(CAEP)的发明者。他最近是谷歌的一名软件工程师，他的开创性博客文章开启了整个行业的运动，最终形成了 OpenID 基金会的共享信号和事件(SSE)框架和连续访问评估规范草案。他还是 OpenID 基金会 SSE 工作组的联合主席。在谷歌，他领导了 BeyondCorp API 的开发，这是谷歌 BeyondCorp 零信任解决方案的关键部分。此前，Atul 是 Trustgenix 的联合创始人兼首席执行官，Trustgenix 是一家联合身份先锋公司，后被惠普收购。Trustgenix 为联合身份标准(如 SAML 2.0 和 Liberty Alliance Framework)的开发做出了贡献。](https://www.linkedin.com/in/tulshi/) 

一种实现企业授权的新方法是通过在用户需要执行访问时及时确定权限，并在用户的任务完成后立即恢复这些权限，来实现对单个资产(例如，特定的客户记录或发票)的访问。

依靠典型的工作流或票证系统，如 ITSM 或 CSM，可以确定用户何时有权访问特定资产。然后，这种证明以特定权限元组的形式传播到实施访问控制的 SaaS 或内部应用程序。

这种方法有多种好处:

*   企业不必在 3P SaaS 和各种应用程序目录中传播静态组信息来实施授权控制
*   它减少了企业对静态角色的依赖，静态角色很难适应不断动态变化的组织结构——假设某人 X 被临时指派帮助团队 Y，因此必须访问团队 Y 的数据。
*   它通过动态支持适当的人在适当的时间在适当的应用程序中访问适当的数据，使企业更接近最低权限访问原则。
*   最近一些引人注目的危害(例如， [Okta](https://thenewstack.io/the-okta-mess-is-even-worse-than-it-appears/) )可以通过阻止受危害的终端访问如此大量的数据，使用即时访问来缓解。

## 利用 OpenID 标准

那么如何传播这种即时权限信息呢？这就是 SSE 和 CAEP 的 OpenID 标准发挥作用的地方。连续访问评估协议(CAEP)是作者在谷歌工作时由 T2 首先提出的。此后，它并入了 OpenID 基金会的一个现有的[工作组](https://openid.net/wg/sse)，该工作组使用类似的机制来解决一个相关的账户泄露问题。

由此产生的共享信号和事件(SSE)框架现在是为任何 API 实现安全的、隐私保护的 webhooks 的通用框架。它被 CAEP 和 RISC 标准所利用。这两个标准都非常成功；谷歌和微软[将其用于一些最繁忙的服务。](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/continuous-access-evaluation-in-azure-ad-is-now-generally/ba-p/2464398)

## 使用 CAEP 进行即时访问

应用程序通常以 OIDC 令牌声明的形式接收许可信息。 [SSE 框架](https://openid.net/specs/openid-sse-framework-1_0-ID1.html)(保留相同的首字母缩写 CAEP)的[连续访问评估配置文件](https://openid.net/specs/openid-caep-specification-1_0-ID1.html)定义了一个名为“令牌声明更改”的事件为了实现即时访问，初始 OIDC 令牌可能不包含任何权限声明，或者可能包含命名特定资产(如客户 id)的权限声明。例如，当客户支持员工被指派处理与特定客户相关的案例时，监视此类更改的服务可以发送 CAEP 令牌-声明-更改事件，该事件修改权限声明以包括与该案例相关的特定客户 Id。一旦案例结束，监控服务将发送另一个 CAEP 令牌-声明-更改事件，该事件将删除用户对该客户的访问权限。

然后，应用程序只需验证新用户是否拥有访问特定资产所需的权限。该应用程序可以将该许可信息与正在讨论的资产一起存储，并响应于它接收到的 CAEP 消息来更新该信息。

这里有一个 CAEP 事件的例子:

```
{
  "iss":  …  // standard JWT fields here.
  "events":  {  // this is the field defined by SSE
     "https://schemas.openid.net…<strong>token-claims-change</strong>":  {
        "subject":  {
          "format":  "email",
          "email":  "jane_in_support@mycompany.com"
        },
        "event_timestamp":  1615304991643,
        "claims":  {
          "customer_id":  "C2148",
          "access_allowed":  "read_write"  // or "none" to remove
        }
      }
  }
}

```

在上面的例子中，CAEP 事件使用户“Jane in Support”能够对指定的客户进行读写访问。作为对接收该事件的响应，应用程序可以为指定的客户提供对 Jane 的读写访问。相反，当支持部门的 Jane 完成他们的任务并关闭案例时，CAEP 事件会禁止他们访问指定的客户，这提供了一种在零信任环境中控制访问的强大方法。

## 与 RBAC 共存

如果您的应用程序已经实现了基于组的授权，那么即时访问可以与这样的现有控件共存。这可以通过两种方式实现:

*   一个应用程序可以提供对关键资产的即时访问能力，例如特定的敏感客户帐户，而其他资产继续依赖 RBAC 获得粗粒度的权限。这样做可以使应用程序将即时访问信息与 RBAC 信息分开。
*   特定的资产可以切换到使用动态组，这些动态组在响应 CAEP 消息时被填充和不被填充。如果应用程序未来继续使用基于组的访问控制，这种策略可能会更好。

## 摘要

*   RBAC 和 ABAC 没有有效地遏制特权蔓延，但事实上却助长了特权蔓延。
*   实时访问管理(JAM)是简化企业中细粒度授权的一个进步。
*   OpenID SSE 和 CAEP 等标准有助于向 3P·SaaS 应用传播所需信息。
*   即时访问管理可以补充现有的 RBAC 实现，提供更细粒度的访问控制，并潜在地减轻危害的影响。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>