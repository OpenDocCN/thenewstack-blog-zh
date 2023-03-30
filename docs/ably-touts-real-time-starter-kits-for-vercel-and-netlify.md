# 巧妙地为 Vercel 和 Netlify 推销实时入门套件

> 原文：<https://thenewstack.io/ably-touts-real-time-starter-kits-for-vercel-and-netlify/>

[Figma](https://thenewstack.io/figma-targets-developers-while-it-waits-for-adobe-deal-news/) 、 [Google Docs](https://thenewstack.io/google-docs-switches-to-canvas-rendering-sidelining-the-dom/) 、Miro——这些应用已经用实时、协作的能力宠坏了最终用户。现在，最终用户，尽管他们很讨厌，也想从其他网络应用程序获得同样的功能。

实时公司[巧妙地](https://ably.com/)想要帮助开发者填补这个空白。上周，这家总部位于英国的平台即服务公司在 [Vercel](https://thenewstack.io/vercel-offers-new-figma-like-comments-for-web-developers/) 的模板市场上推出了一个预建的 [Next.js](https://thenewstack.io/vercel-delivers-next-js-12-the-sdk-for-the-web/) [初学者工具包](https://vercel.com/templates/next.js/ably-nextjs-starter-kit)，该工具包提供实时功能，包括实时协作。Ably 也在 [Netlify](https://thenewstack.io/netlify-acquires-gatsby-its-struggling-jamstack-competitor/) 上提供了类似的工具。

Ably 的首席产品官 Tim Buntel 告诉 New Stack 说:“如今你可以在很多网站上看到这些虚拟形象。“用户不希望必须点击网页上的刷新才能看到他们可能在 web 应用程序中看到的数据的实时更新。”

Buntel 认为，实时是当今应用程序开发的两大趋势之一。另一个是 Vercel 和 Netlify 等平台真正改变开发者交付内容的方式的能力。

“我们也看到客户希望实时和多人体验不再是谷歌文档或 Miro 中的小众功能，但人们希望开始在各种不同的应用程序中看到这一点，”Buntel 说。“这就是此次发布的真正目的，即认识到这些新平台的增长将改变开发者为客户获取价值的方式，然后让他们在这些应用中带来客户真正想要的体验。”

## 前端开发人员的实时用例

Ably 提供了[API](https://thenewstack.io/key-concepts/apis/)和[SDK](https://thenewstack.io/paypal-enhances-javascript-sdk-with-typescript-type-definitions/)来为网络和移动应用添加实时功能。启动工具包，除了支持多人体验和聊天，还支持前端和后端之间的数据同步。一个用例可能是实时监控客户在网站上购物时还有多少商品库存，并自动更新。它还支持数据广播，在这种情况下，大量用户会对同时接收相同的数据感兴趣，例如公告或体育比分。实时的另一个流行用例是启用推送通知，特别是当它涉及实时位置数据时，例如提醒客户送货即将到达。

“如果我自己只是一名开发人员，我对实时一无所知，但如果我使用 Vercel 来建立我的网站，我现在可以很容易地在我的应用程序中添加光标跟踪或实时数据更新或聊天等内容，而我自己并不具备这方面的专业知识，”Buntel 说。“这种多人体验或实时聊天，或数据同步，实际上是许多客户端需要通过我们的 API 和 SDK 实时连接的任何东西，开发人员可以将这些不同类型的功能添加到他们的应用程序中。”

## 一次点击和一个实时 API

他说，该启动工具包为开发人员提供了连接到 Ably 平台的能力，并使管理用户状态和实时底层复杂性变得容易。他说，该模板包括一个图库，开发者只需点击一下就可以使用该功能。初学者工具包然后引导开发人员从 Ably 获取 API 密钥。他解释说，Ably 与 Netlify 的工作方式类似，开发者可以从 [Netlify 的集成中心](https://www.netlify.com/integrations/)选择 Ably 插件，实时功能将被放到应用程序中。

“如果你想想那些实时体验，它们都利用了相同的底层基础设施，”他解释道。“因此，它创建了一个 WebSocket 连接，即客户端和服务之间的持久连接，以维护这些客户端之间的状态。所有这些复杂性通常需要您了解分布式系统或实时架构才能完成。我们处理这种复杂性，因此开发人员可以立即开始交付这些体验。”

Buntel 说，Ably 也是一个无服务器平台，因此它可以管理全球实时基础设施运营的扩展挑战。通过 Vercel starter kit，Vercel 为应用程序提供了工作流和托管平台，同时巧妙地提供了连接，使实时片段成为可能。

“Vercel 和 Ably 都是无服务器的，所以开发者不需要维护他们自己的服务器或后端基础设施，”他告诉 New Stack。“Vercel 将允许您托管应用程序的客户端，并生成和托管应用程序的客户端，然后从该客户端应用程序中，[它]可以连接到，以协调该应用程序的实时组件。”

该公司发布了一个分步教程，解释了如何用 Ably 和 Next 构建一个实时聊天应用程序。Js 。Ably 还提供了一个免费层，允许开发者在进入付费层之前尝试功能。它还宣布了其 [Ably Terraform 提供商](https://registry.terraform.io/providers/ably/ably/latest/docs)的发布，这使得开发者能够以代码管理他们的 Ably [基础设施。](https://thenewstack.io/infrastructure-as-code-is-a-movement-ready-to-boom/)

Buntel 说:“对于不想考虑部署软件的复杂性的开发人员来说，像 Vercel 这样的平台是很棒的(或 Netlify)，因为他们消除了启动服务器和部署基础设施的任何复杂性。”“但是，对于许多大型公司来说，他们希望自己保持对复杂基础架构的控制。TerraForm 是最常用的工具之一。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>