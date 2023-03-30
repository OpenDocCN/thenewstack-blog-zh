# 在 OAuth 之外？下一代认证的 GNAP

> 原文：<https://thenewstack.io/beyond-oauth-gnap-as-the-next-generation-of-authentication/>

授权协商和授权协议(Grant Negotiation and Authorization Protocol，简称 g-nap)目前正在互联网工程任务组(IETF)的一个工作组中开发。在这里，我将讨论为什么开发 GNAP，以及它即将发布的第一版对你来说意味着什么。

提议的新 GNAP 认证标准产生于两个相互竞争的努力，TxAuth 和 OAuth . XYZ。GNAP 将解决 OAuth 的一些限制并包括新的特性。根据 [GNAP 工作组章程](https://datatracker.ietf.org/wg/gnap/about/)，该协议将用于授权、API 访问、用户标识符和身份声明。

GNAP 正处于讨论和迭代阶段，预计将于 2021 年开始分多个部分发布。这是[草案](https://www.ietf.org/archive/id/draft-ietf-gnap-core-protocol-05.html)。

## 为什么需要 GNAP？

 [丹·摩尔

丹·摩尔(Dan Moore)是 FusionAuth 母公司 Inversoft 的开发者关系主管，也是业内资深人士。Dan 于 2020 年加入 Inversoft，主要专注于帮助开发人员在他们的应用程序中利用 FusionAuth，同时建立一个对 Inversoft 的产品充满热情的开发人员社区。Dan 从事编码工作已经超过 20 年，在许多公司担任过 CTO、工程经理、顾问、承包商、技术培训师和软件工程师。这些公司包括 Transposit，文化铸造，食品走廊，镀锌，以及许多其他公司。](http://www.inversoft.org/) 

核心 OAuth 规范 [RFC 6749](https://tools.ietf.org/html/rfc6749) 得到了广泛的支持和部署，它可以扩展以支持新的用例，比如设备授权。此外，您可以利用 OAuth2 以及商业和开源工具来构建一个安全的身份验证系统。对于客户端来说，OAuth2 也比 SAML 之类的协议更容易实现。

然而，OAuth2 也有其缺陷。例如，要开始使用 OAuth2，您可能需要阅读十几个 RFC。即使最近在 OAuth 2.1 上的工作合并了一些 RFC，一些用例也需要通读多个标准文档。OAuth 2 的其他问题包括:

*   过时的开发人员人机工程学，包括大量使用表单参数。
*   不记名令牌存在安全风险。(“所有权证明”解决方案，如 [DPOP](https://tools.ietf.org/html/draft-ietf-oauth-dpop-02) 和 [MTLS](https://tools.ietf.org/html/rfc8705) 没有被广泛或容易地部署。)
*   OAuth 端点的发现是非标准且繁琐的。
*   [手机应用体验欠佳](https://tools.ietf.org/html/rfc8252)。

## GNAP 的特性和功能

像 [OAuth 2.1](https://fusionauth.io/learn/expert-advice/oauth/differences-between-oauth-2-oauth-2-1/) 一样，GNAP 的目标是解决 OAuth 2 的缺陷。以下是 GNAP 的一些亮点。

### 请求方和资源所有者的不同角色

在典型的 OAuth2 授权码授予中，资源的所有者可以授予对受保护资源的委托访问。假设所有者是请求授权的人。(有必要回顾一下规范中概述的角色。)

但是，请求访问受保护资源的一方可能与需要授予权限的资源所有者不同。请求方驱动资源客户端，它可以是浏览器或设备。受保护的资源位于资源服务器上。使用 GNAP，请求访问的实体可以不同于资源的所有者。

### 多重访问令牌

使用 GNAP，客户端可以在一个授权请求中请求多个访问令牌(而不是多个请求)。例如，您可以请求对一个资源的读取权限，而对另一个资源的读取和写入权限。

规范草案中的以下示例要求为三种不同的资源提供两种不同的令牌:photo-api、dolphin-metadata 和 walrus-access。这些资源可以是丰富的 JSON 对象，如 photo-api，也可以是简单的字符串，如 dolphin-metadata。

```
{  
   "resources":  {
      "token1":  [
         {
            "type":  "photo-api",
            "actions":  [
               "read",
               "write",
               "dolphin"
            ],

            "locations":  [
               "https://server.example.net/",
               "https://resource.local/other"
            ],

            "datatypes":  [
               "metadata",
               "images"
            ]
         },

         "dolphin-metadata"
      ],

      "token2":  [
         {
            "type":  "walrus-access",
            "actions":  [
               "foo",
               "bar"
            ],

            "locations":  [
               "https://resource.other/"
            ],
            "datatypes":  [
               "data",
               "pictures",
               "walrus whiskers"
            ]
         }
      ]
   }
}

```

### 作为一级对象的交互

在 GNAP，请求客户端声明它支持哪种交互。授权服务器使用交互来响应请求，该交互用于与资源所有者或资源客户端进行通信。

这些交互在 GNAP 规范中被定义为一级对象，为未来的通信提供了扩展点。交互可能包括重定向浏览器、在移动应用程序中打开 deeplink URL 或提供在其他地方使用的用户代码。

### 请求延期

与 OAuth2 不同，如果授权服务器确定授权可以继续，则 GNAP 提供授权标识符。在下面的示例中，如果在初始请求后需要修改或继续授权，可以向授权服务器提供授权标识符`access_token.value`。

```
{
   "continue":  {
      "access_token":  {
         "value":  "80UPRY5NM33OMUKMKSKU",
         "key":  true
      },

      "uri":  "https://server.example.com/continue",
      "wait":  60
   }
}

```

这一功能允许客户在情况变化时上调或下调访问权限。

如果客户端不再需要访问受保护的资源，您也可以取消授权。然后，授权服务器将撤销与该请求相关联的令牌，这与 OAuth2 不同，在 oauth 2 中，令牌可能不会被显式撤销。

## 加密密钥

密钥在多个层次上被编织到 GNAP 中。下面是从草案规范中摘录的一个样本请求:

```
{
   "client":  {
      "display":  {
         "name":  "My Client Display Name",
         "uri":  "https://example.net/client"
      },

      "key":  {
         "proof":  "jwsd",
         "jwk":  {
            "kty":  "RSA",
            "e":  "AQAB",
            "kid":  "xyz-1",
            "alg":  "RS256",
            "n":  "kOB5rR4Jv0GMeL...."
         }
      }
   },
}

```

## 内置身份识别功能

虽然 OAuth2 是一个没有身份概念的授权框架，但 GNAP 包含了内置的身份特性。如果客户端知道谁是资源所有者，它可以提供身份声明。另一方面，客户端可以在初始授权请求中请求关于资源所有者的信息。如果授权服务器确定所有者已经授予许可，则可以发布信息。

下面是草案中授权服务器响应的一个例子:

```
{
   "user":  {
      "sub_ids":  [  {
         "subject_type":  "email",
         "email":  "user@example.com"
      }  ],
      "assertions":  {
         "id_token":  "eyj..."
      }
   }
}

```

客户端对象的键值是签署请求的密钥。支持多种方法(例如，分离 JWS、连接 JWS 和相互 TLS)。此外，GNAP 草案支持无记名令牌，这在 OAuth2 生态系统中非常成功。

## 改进的开发人员人机工程学

OAuth 要求客户端使用 application/x-www-form-urlencoded 媒体格式发出请求。使用表单参数传输数据，表单参数可以被许多不同的客户端和大多数编程语言使用。然而，许多现代 API 使用 application/json 作为媒体格式。JSON 虽然有缺陷，但它允许比表单参数更丰富的对象结构。

使用 GNAP，您可以将许多对象折叠成简单的字符串，您不必使用嵌套结构，并且您可以通过引用来标识资源、交互和其他实体。所有引用可以是静态的，也可以是动态生成的。无论哪种方式，它们都允许授权服务器和请求客户端之间更容易的通信。

最后，使用 GNAP，一个端点以一种简化的方式开始请求客户端和授权服务器之间的所有交互，从而消除了查阅文档来确定何时必须调用哪个端点的需要。

## 后续步骤

贾斯汀·里奇提出了 [OAuth。XYZ](https://oauth.xyz/) 的概念，并作为 GNAP 规范的编辑之一，承诺如下:“GNAP 有一天将成为正式的标准，……而 XYZ 将过渡成为该标准的实现。”为此，IETF 工作组的一个主要目标是简化从 OAuth 2.0 和 OpenID Connect (OIDC)到新协议的迁移。

也就是说，至少在未来的两到三年内，你可以继续使用 OAuth2 和 OIDC 进行基于标准的认证(只要确保利用 [OAuth 2.1](https://fusionauth.io/learn/expert-advice/oauth/differences-between-oauth-2-oauth-2-1/) 的安全改进)。

随着 GNAP 的不断发展，考虑加入[邮件列表](https://mailarchive.ietf.org/arch/browse/txauth/)并进行合作。还可以查看 [GitHub repo](https://github.com/ietf-wg-gnap/gnap-core-protocol/) 中的修改，草稿正在这里编辑。即使你是 OAuth 的忠实用户，你也应该回顾一下 GNAP 规范，看看它是否比 OAuth 更适合你的用例，尤其是当草案变得更加具体的时候。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>