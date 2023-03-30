# Stytch 的 API 优先无密码认证方法

> 原文：<https://thenewstack.io/stytchs-api-first-approach-to-passwordless-authentication/>

虽然多年来，管理密码一直是一场噩梦，但几十年来，在疫情期间，越来越多的人订购外卖，在网上购买从驱蚊剂 T2 到狗粮的一切东西。

这只会让人们更加意识到，用户需要记住所有不同账户的密码，公司需要应对安全和客户转换问题。

这为创造基于密码的身份认证的替代解决方案增添了动力。

总部位于旧金山的 [Stytch](https://stytch.com/) 就是这样一家初创公司，它旨在帮助开发者通过 API 优先的方法，更容易、更安全地为他们的应用程序添加认证。

创始人[里德·麦金莱-斯坦普尔](https://www.linkedin.com/in/reed-mcginley-stempel-17362245/)和[朱莉安娜·兰姆](https://www.linkedin.com/in/juliannaelamb/)来自 Plaid，该公司为像 Venmo、罗宾汉或比特币基地这样的网站的用户创造了将他们的账户与银行联系起来的技术。在那里，他们发现密码是他们最大的安全威胁，也是潜在客户退出的最可能的原因。

“这些都是让我们非常兴奋的事情，如果你能建立一个开发者体验公司，让每个工程师在构建应用程序或网站时，都能轻松地从一开始就嵌入无密码身份验证，会怎么样？”首席执行官麦金莱-斯坦普尔说。

## 无密码的嗡嗡声

最近人们对无密码认证很感兴趣，像微软、谷歌和 Slack 这样的公司实现了它的一些变体。

[Gartner](https://www.gartner.com/smarterwithgartner/embrace-a-passwordless-approach-to-improve-security) 预测，到 2022 年，60%的大型和全球性企业以及 90%的中型企业将在超过 50%的使用案例中实施无密码方法。不过，这不一定是事实。[微软最近报道](https://www.microsoft.com/security/blog/2022/02/03/cyber-signals-defending-against-cyber-threats-with-the-latest-research-insights-and-trends/)只有 22%使用其云身份解决方案微软 Azure Active Directory (Azure AD)的客户使用强身份认证保护。

与 [Oso 正在为授权](https://thenewstack.io/oso-tackles-unbundling-security-authorization/)所做的一样，Stytch 旨在为开发者提供一种类似 Stripe 的体验，将无密码[认证](https://thenewstack.io/how-do-authentication-and-authorization-differ/)添加到他们的应用程序中。

“我们主要为开发者提供 API 和 SDK，将无密码身份验证嵌入到他们的应用中。因此，我们有一个不同产品的平台，您可以从中挑选并以对您的用户、您的用例有意义的方式组合在一起，”Stytch 首席技术官 Lamb 说。

这些产品包括电子邮件、魔法链接、短信、WhatsApp 链接、[定时一次性密码](https://stytch.com/blog/introducing-totp-authentication/)以及谷歌认证器、谷歌登录、脸书和 OAuth 集成等认证应用。

该公司最近宣布了其首款使用 [WebAuthn](https://stytch.com/blog/an-introduction-to-webauthn/) 的生物识别产品，该产品允许用户使用 TouchID 或 FaceID 等内置设备生物识别技术或 YubiKey 等硬件密钥登录。麦金莱-斯坦普尔说，它正在探索的功能之一是网站的生物识别登录。

该公司还进行了第一次收购，Y Combinator 支持的无代码无密码竞争对手 Cotter。

## 客户端库和 SDK

它提供了用于 Python 、 [Ruby](https://github.com/stytchauth/stytch-ruby) 、 [Node.js](https://github.com/stytchauth/stytch-node) 和 [Go](https://github.com/stytchauth/stytch-go) 和 [Javascript SDK](https://stytch.com/docs/sdks) 的客户端库，作为普通版本或 React 组件。Android 和 iOS SDKs 以及加密钱包正在开发中，该功能允许用户通过 [MetaMask](https://metamask.io/) 或另一个基于以太坊的加密钱包，在区块链上使用你的应用程序无缝认证自己。

它的身份验证 API 是围绕 REST 原则组织的，具有面向资源的 URL，返回 JSON 编码的响应，并使用标准的 HTTP 响应代码。

您可以将它集成到任何后端语言中。

“API 为您所构建的最终用户体验提供了如此多的灵活性和所有权。因此，您可以将我们的认证集成到您的产品中，然后自己构建您的整个前端和 UX，这样您就不必牺牲任何品牌、设计和 UX 元素，”Lamb 说。

“拥有一个真正干净的 API 可以抽象出所有复杂的身份验证部分，但可以让开发人员最大限度地控制他们的用户体验。”

她解释说，它还让你可以灵活地在对你的应用有意义的时间点集成认证。

“因此，我们经常谈论的一件事是基于路由的身份认证，这基本上意味着从登录的会话中进行升级。因此，您可能需要一个身份验证因素来获得帐户的读取权限。然后，如果你去做一个更危险或敏感的行动，如更新送货地址或查看帐单信息等。，您可以执行另一个身份验证事件，以提高该操作的安全性。”

[https://www.youtube.com/embed/T4rcmzAdp44?feature=oembed](https://www.youtube.com/embed/T4rcmzAdp44?feature=oembed)

视频

## API 优先的方法

麦金莱-斯坦普尔认为 Auth0 和 Okta 是最接近的竞争对手，尽管 Okta 去年以 65 亿美元的价格收购了 Auth0。此外，还有一系列其他竞争对手，包括 HYPR、Magic、1Kosmos、Authentiq 等等。

他指出 Stytch 的 API 优先方法是一个主要的区别。

“我们今天听到的很多关于现任者的抱怨是，他们真的很不灵活，所以工程师很难用他们做他们想做的事情。他们也很难拥有 UX、用户界面和设计，”他说。

“你知道，如果你是一家使用第三方注册和登录的公司，你必须给予他们很多信任，让他们在用户入职期间接管用户体验的核心部分。许多拥有一流设计的公司和前端工程团队都想拥有这种体验，这不是现有公司能真正做到的。”

他解释说，他们不太灵活的原因之一是，他们围绕密码即服务构建了整个体系结构。

“如果你正在为密码构建第三方服务，那么你的灵活性是有意义的，因为你想确保你永远不会允许那些开发者接触密码，因为那样会对其他应用程序构成风险。如果开发者可以为一个用户存储密码，并说该用户在 10 个不同的网站上使用同一个密码，这实际上是一种安全责任，如果你提供这种灵活性的话。”

他说，无密码认证的好处是能够改善用户体验，同时也为开发者提供了更大的灵活性，因为他们不需要处理可能被用来利用其他账户的问题。

在他的【不无聊】博客中，前投资银行家 [Packy McCormick](https://www.packym.com/) 写道:

*Stytch 是反对密码战争中的一个军械库，它的客户可以从中选择他们需要的武器来消除密码。在和平时期，它作为一个创造性的铸造厂，客户可以在其上创建新的无缝身份认证体验。无论是哪种情况，Stytch 都使数字产品更加安全，同时提高转化率和收入。它建立了 API-first，因为它知道它的客户比 Stytch 更了解他们的客户，还因为它知道集体创造力将导致它自己无法预测的紧急行为。*

## 创造性用例

麦金莱-斯坦普尔说，该团队经常对客户使用其工具的方式感到惊讶。

“我们一直在使用一个流行的例子，它是一个大麻购物平台，希望在结账时为您创建一个用户帐户。因此，一旦你添加了信用卡信息，他们就会让你加入忠诚度奖励计划。

“如果我们只是给你一个窗口小部件，说‘这是你的注册和登录窗口小部件’，我们可能不会想到支付结账流程中的人们会想要创建用户帐户，然后在他们将来回到商户 B、C、D 时对他们进行认证。

“所以有很多这样的场景……当你有问题要解决时，我们会想出比你作为工程师所能想象的更少的创造性用例。”

一年前的 1 月份，Stytch 宣布了 625 万美元的种子轮，随后在 7 月份进行了 3000 万美元的 A 轮融资，在 11 月份进行了 9000 万美元的 B 轮融资。麦金莱-斯坦普尔说，该公司的员工人数已经从一年多前的 6 人增加到 37 人，预计明年将增加两倍。

它吸引了来自格子呢、比特币基地、Intuit、Zillow、Quizlet、Carta 和 Stitch Fix 的工程师和设计师。

这并不是唯一一家投资解决密码问题的公司。去年 6 月，总部位于波士顿的 Transmit Security 在首轮融资中筹集了 5.43 亿美元的巨额资金。一个月后，总部位于旧金山的 Magic 公司也进行了 2700 万美元的首轮融资。

拥有新堆栈的 Insight Partners 投资了 Transmit Security，以及上个月宣布的 password manager 1Password 的 6.2 亿美元 C 轮融资。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>