# 盖茨比黑仔的下一个 Drupal 带来了 Drupal CMS 无头

> 原文：<https://thenewstack.io/next-drupal-offers-frontend-developers-decoupled-experience/>

当谈到该公司的开源产品 Next-Drupal 时，来自第三章网络代理公司的 John Faber 有点像一个福音传道者。他毫不犹豫地喊出产品，并告诉你他对产品的确切看法。

他坚持认为 Drupal 需要成为一个无头 CMS。并非巧合的是，这正是 [Next-Drupal](https://next-drupal.org/) 所做的，通过使用流行的 [React framework Next.js](https://thenewstack.io/next-js-13-debuts-a-faster-rust-based-bundler/) 为 Drupal 的内容管理系统构建一个前端。Faber 声称这比单独使用 Drupal 创造了更好的开发者体验和更高性能的解决方案。

“Drupal 的前端一直是它的弱点，所以人们从来没有能够看到它作为一个内容架构平台的闪亮之星，因为 Drupal 的愚蠢前端总是碍事，”他说。“第三章已经(与 Drupal)合作了很多很多年，我们决定改变范式，以适应世界其他地方正在发生的事情，这是解耦的 Next.js。”

## Drupal 没头了

[New Stack 最近与 Drupal 创建者 Dries Buytaert](https://thenewstack.io/how-drupal-became-the-open-source-unicorn) 谈论了他的公司 Acquia 的新“开源、无头初学者工具包”，该工具包是作为基于 Drupal 的 Acquia CMS 的一部分宣布的。Faber 告诉我们 Acquia Next 初学者工具包是由第三章开发的，它使用 Next-Drupal 作为基础。他补充说，去年 11 月发布的 Next-Drupal 现在每周被下载 2000 次。

“它允许我们在一个非常轻量级的 React 框架上创建这些生产级前端，这个 React 框架是围绕即时访问构建的，”Faber 说。" Next 是从头开始构建的，旨在提供对远程数据的即时访问."

一个分离的框架通常是非常珍贵的。许多商业产品都提供 headless CMS，但 Faber 认为，问题在于，当公司使用这些托管解决方案时，他们实际上是在锁定的平台上构建内容基础设施，这些平台按规模收取溢价。

“他们拥有你的数据，对吗？随着你变得越来越大，这变得越来越昂贵，”费伯说。“你可以是一个小博客网站，获得一些病毒式的东西，突然之间，你每月支付 5，6，7 千美元。”

## 下一个——Drupal 对其他人

他说，Drupal 的目标是企业空间，而不是倾向于吸引中小型企业的 WordPress。企业需要新技术，Next-Drupal 在一个开源工具中提供了这种新的、无头的 CMS 方法。他补充说，虽然 WordPress 更容易使用，部署更快，但它更多的是关于页面构建，而不是 Drupal 关注的结构化内容和内容架构。

[盖茨比是另一个开源选项](https://thenewstack.io/gatsby-v3-0-offers-incremental-builds-to-speed-web-deployment-times/)，用 [Contentful](https://thenewstack.io/dont-call-contentfuls-content-infrastructure-cms/) 、 [Ghost](https://ghost.org/) 和 [Prismic](https://thenewstack.io/what-if-all-frontend-developers-were-jamstack-developers/) 等插件支持无头；Faber 称 Drupal-Next 为“盖茨比杀手”，并补充说，Next-Drupal 做盖茨比所做的一切，但更快更便宜。

他承认有些人讨厌 Drupal，但他认为这是基于 Drupal 的早期版本，尤其是版本 8，它利用了[Twig](https://twig.symfony.com/development)。他说，和 Twig 一起工作很难，也很慢。但是从那时起，Drupal 已经被改进为使用本机自带的 JSON API 调用。

“这就是我们踢 WordPress 屁股的地方… [in] [Drupal 9](https://www.drupal.org/about/9) …一切都是 100% API 可访问的，”他说。您可以将任何内容放入 Drupal，然后通过 JSON 调用就可以取出来。"

他将 Next-Drupal 比作 [Faust.js](https://thenewstack.io/wp-engine-expands-its-headless-solution-for-wordpress/) ，后者将 WordPress 的后端与前端分离。

“本质上它做了非常相似的事情，”他谈到 Next-Drupal 和 Faust.js 时说，“人们想离开 WordPress 前端。相信我，WordPress 前端是垃圾，一直都是。如果你把它解耦，现在它很美。”

他说，加州州立大学贝克斯菲尔德分校是一个从 Drupal 转向 Next-Drupal 的网站，试图让他们的网站更快。Faber 称，有了 Next-Drupal，他们的托管费用减少了 33%。

[Stacey Childress](https://www.linkedin.com/in/staceychildress/) 是贝克斯菲尔德加州州立大学拓展教育和全球推广的市场和系统总监。Childress 通过电子邮件告诉 New Stack，学校几年前曾考虑过无头方法，但发现该技术“不可靠，充满了技术问题，比我们在速度和整体用户体验方面可能取得的任何收益都大。”

柴尔德里斯说，他们对 Next.js 的体验非常不同。

“Next.js 平台和我们的特定用例对我们来说非常顺利，”Childress 说。“正如 Drupal 历史上的情况一样，我们可以根据自己的喜好对内容编辑器进行定制，几乎没有任何限制，但我们可以通过 headless/Next.js 架构为我们的潜在学生(我们的用户/客户)提供更好的前端体验。”

Childress 补充说，用户已经注意到速度的提高，内容编辑者对内容编辑体验以及“他们进行和测试更改的速度”感到满意。

Faber 希望世界知道 WordPress 并不是解决前端开发者体验问题的唯一产品。

“我们是真正的开源和真正的可组合堆栈，”Faber 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>