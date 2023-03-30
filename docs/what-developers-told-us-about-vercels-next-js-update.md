# 关于 Vercel 的 Next.js 更新，开发者告诉了我们什么

> 原文：<https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/>

这是 Next.js 13 发行版中一个小的、不太知名的部分，它让前端开发人员 Sophia Andren 兴奋不已。

Andren 是加州圣地亚哥另类设计公司 candycode 的技术总监和 T2 开发者。她和设计师[杰西·沃特斯](https://jessiewaters.com/)参加了在三藩市举行的 Next.js 会议，以了解他们对 [Vercel 及其 Next.js 13 版本](https://thenewstack.io/next-js-13-debuts-a-faster-rust-based-bundler/)的了解。这将有助于他们保持网站更紧密的品牌，安德烈告诉新的堆栈。

两人都与所有主要的 [React](https://thenewstack.io/learn-react-delete-functionality-and-the-set-state-hook/) 框架合作过——包括 [Gatsby](https://thenewstack.io/getting-started-with-gatsby-the-cloud-native-static-site-generator/) 、 [Next.js](https://thenewstack.io/from-php-to-next-js-what-trivago-learned-rewriting-its-web-app/) 和[Remix](https://thenewstack.io/remix-os-peek-future-android-desktop/)——为客户服务，但在 10 月 25 日的会议之后，他们决定在 [Vercel](https://vercel.com/) 上使用 Next.js 为 [candycode 自己的网站](https://candycode.com/)服务。

具体来说，Andren 喜欢开发者工具包的变化，包括增强的字体支持，这使得使用自定义字体和谷歌字体更容易；增强图像优化组件；以及即时开放图(OG)图像生成，一个用于生成[动态社交卡片图像](https://vercel.com/blog/introducing-vercel-og-image-generation-fast-dynamic-social-card-images)的新库。

“对于那些倾向于未来技术的创意机构来说，Next.js 13 的发布确实是一个游戏改变者，”她说。“图像、字体和社交卡片的新改进，使得在一个注意力范围不断缩小、消费者期望不断增长的时代，打造精致的数字体验变得更加容易。”

## 涡轮包恐惧和爱

其中最有争议的一个消息是 Turbopack，一个新的基于 Rust 的 JavaScript 和 [TypeScript](https://thenewstack.io/key-concepts/typescript/) 捆绑器，将取代 [Webpack](https://thenewstack.io/airbnb-moves-from-webpack-to-metro-enjoys-shorter-build-times/) ，导致一名开发者在会议上评论说，她觉得地毯从脚下被拉走了。

Vercel 向观众保证，会有一条采用的道路，并且可以逐步实施。

但是对于 Github 软件工程总监 [Chiedo John](https://www.linkedin.com/in/chiedo/) 来说，这是个好消息。

“我非常喜欢 Turbopack 的发布！”约翰告诉新堆栈。“任何让人们保持心流状态的事情都会大有帮助。事实上，如此多的价值可以逐步采用，这是令人惊讶的，从成本角度来看，这是可行的。”

## 渐进采用:是的，请

总的来说，开发人员告诉新堆栈，他们对新版本印象深刻。虽然有些人在活动中表达了对 Turbopack 迁移问题的担忧，但 Vercel 似乎通过其增量采用方法缓解了这些担忧。

技术服务公司 [PeakActivity](https://peakactivity.com/) 的高级软件工程师[马修·刘易斯](https://www.linkedin.com/in/malewis5/)承认:“对于采用 Vercel 基于 Rust 的新捆扎机 Turbopack 有些担忧。“在与其他开发人员交谈时，一个常见的问题是对 CSS 的支持。然而，下一个团队在允许增量采用新功能方面做得很好，我相信他们的团队和社区会解决这个问题。”

## 新布局

自从 Next 在 5 月份发布征求意见稿以来，Lewis 一直很高兴听到新的布局。他很欣赏专家产品演示，这让开发人员看到了实现是如何进行的。

“Next 不仅提供了一个创新的功能，而且他们还通过给我们一个项目结构的标准来保持开发者的体验，”他说。“页面、布局、错误和加载的简单结构让开发人员在导航大型代码库时更有信心，并为我们提供了一个有效的解决方案来提供核心的用户体验基础。”

## React 服务器组件

杨章也喜欢新的布局系统，他说看到 Next.js 将自己定位于复杂的应用以及营销和电子商务网站令人兴奋。杨是一名软件工程师，也是基于的无代码内容管理系统的创始人之一。

“这也符合我们的方向，因为 Plasmic 是一个基于 React 的可视化构建器，涵盖网站和应用程序，”他说。

他称新的 React 服务器组件是“一项重大的架构变革”，“将 React 的性能提升到一个新的水平——通过部分水合作用。”

“我们已经看到新的竞争框架蚕食性能故事，但 React 服务器组件意味着您可以获得性能优势，而不会牺牲以 React 方式构建丰富、复杂的交互性的能力，”Zang 说。“重要的是，(Next.js) React 团队从来不害怕重新发明框架——这样做的同时带来一个向后兼容的巨大生态系统是一个巨大的挑战，他们总体上已经很好地应对了。”

他补充说，建立在 Next.js 这样的基础上对 Plasmic 实现软件民主化的目标至关重要。

一些开发者提到了一个共同的因素:对 Vercel 关注开发者体验的赞赏。

“Vercel 正在做革命性的工作，这将极大地改善开发人员的开发方式，”John 说。

Vercel 支付了 Loraine Lawson 参加会议的差旅费和住宿费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>