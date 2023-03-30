# 微前端如何重组开发团队

> 原文：<https://thenewstack.io/how-micro-frontends-can-restructure-development-teams/>

微前端并不一定是新的——这个术语是在 2016 年创造的——但这种方法正在获得关注，像[宜家](https://thenewstack.io/ikeas-concept-kitchen-of-2025-it-cooks-interacts-and-composts/)、[网飞](https://thenewstack.io/intel-poaches-open-source-execs-from-netflix-apple-to-boost-linux-efforts/)和 [Spotify](https://thenewstack.io/spotify-reboots-ospo-earmarks-109000-for-open-source-projects/) 这样的公司都在采用它。

“如今，许多公司已经在使用微前端，”总部位于慕尼黑的开发公司 [Smapiot](https://smapiot.com/) 的解决方案架构师、《微前端的艺术》一书的作者[Florian Rappl](https://dev.to/florianrappl/writing-the-art-of-micro-frontends-31ce)说。"几乎财富 500 强中的每个人都在以这样或那样的方式接触微前端."

Rappl 在上周的 Code PaLOUsa 2022 期间进行了关于微前端和无服务器前端的虚拟演示，这是在肯塔基州路易斯维尔举行的开发者区域会议。他认为微前端是 web 开发的下一次发展，紧随微服务的趋势而来，到目前为止，微服务主要影响后端开发。

他解释说，Microfrontends 采用模块化的方法进行前端开发，到目前为止，它主要停留在单一的开发方法上。

“通常情况下，你最终只能得到一个单一的前端解决方案，”Rappl 说。“所以你有了所有这些良好的解耦以及后端和前端的一切，你就有了一个[整体架构](https://thenewstack.io/has-monolithic-architecture-gotten-a-bad-rap/)。”

## 重组前端开发团队

该前端通常由一个大型、非常集中的团队在一个大型解决方案中开发。这就产生了问题。首先，团队数量本身对于 sprints 来说是笨拙的，并且通常是由技术或技能组织的，而不是跨职能的业务需求。第二，单片前端使发布和修复具有挑战性，他说。

“缺点是部署版本太大了。这意味着，如果只需要做一个补丁，这可能会非常困难，你可能需要精挑细选，你可能需要去问每个人，“嘿，你的功能准备好了吗？””他说。

他说，通过转移到微前端，前端开发团队可以分成更小的跨职能团队，为业务能力编写模块，而不是由技术或技能组织的专业团队。他指出，跨职能团队可以是由 8 名开发人员组成的三个团队，而不是一个由 24 名开发人员组成的大团队。

“然后，你可以共享某些东西，比如通用功能，一个库可能是，例如，一个模式库，这样，这些模块已经得到了一些现成的东西，这很棒，因为他们不需要重新发明轮子，”他说。“他们只能专注于他们想要覆盖的业务领域，这很好，因为归根结底，这是资金流入的地方。”

他补充说，如果需要的话，微前端还可以允许开发者部署在不同的框架中。

“如果某个东西想在不同的框架中发展，就不应该被禁止，对吗？它实际上应该得到支持，”他说。“这并不意味着它受到鼓励。你仍然可以获得最好的体验，仅仅依靠一个或者说最少的前端框架

## 微前端的模式

Rappl 还讨论了微前端的两种实现模式。第一种是服务器端组合，它依靠反向代理来提供页面的不同组件。

“这是真正的微前端方法，”Rappl 在一篇详述微前端模式的[博客文章中解释道](https://blog.bitsrc.io/6-patterns-for-microfrontends-347ae0017ec0h)。“为什么？正如我们已经看到的，微前端应该运行在服务器端。因此，整个方法肯定是独立工作的。当我们为每个小的前端片段配备专用服务器时，我们可以称之为微前端。”

另一端是客户端组合，它消除了对反向代理服务器的需求。

以最简单的形式，这可以通过使用 *< iframe >* 元素来实现。不同部分之间的交流是通过 postMessage 方法完成的，”他写道。

启动时间可能会慢一点，但这种方法可以非常非常快，他在演讲中说。

他说:“你真的可以拥有非常动态的解决方案，不仅从用户的角度来看，尤其是从开发者的角度来看，感觉就像魔术一样。”。

## **微**前端的框架

Rappl 使用 [Piral](https://piral.io/) ，这是一个用于构建门户应用程序和微前端架构的框架。Rappl 关于[微前端](https://www.youtube.com/watch?v=nq-0uNd9dv0)和[无服务器前端](https://www.youtube.com/watch?v=Rd_O-3yrIbI)的演示是可用的，并展示了如何使用该工具创建微前端的简要演示。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>