# Vercel 为 Web 开发者提供了新的“类似 Figma”的评论

> 原文：<https://thenewstack.io/vercel-offers-new-figma-like-comments-for-web-developers/>

Vercel 的 CTO，Malte Ubl，还记得 Photoshop 统治像素化世界的时候。他休息了几个月，当他回来时，Sketch 已经接管了 Photoshop，因为它更适合设计 UI。此后不久，Figma 通过在其设计软件中引入协作工具来颠覆游戏。Ubl 说，谷歌文档以同样的方式改变了文字处理软件，用实时协作取代了长期的巨头微软 word。

[为网络开发者](https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/)提供前端堆栈的 Vercel，希望以 [Figma](https://thenewstack.io/adobe-buys-figma-what-does-this-mean-for-web-standards/) 和 Google Docs 改造各自工具的方式改变开发者的工作流程。到目前为止，在网站上获得反馈需要用户截屏页面，然后将其粘贴到 Slack 或 doc 中以获得反馈。该公司在圣诞节前几天正式推出了一个名为预览部署评论的协作工具。它允许团队成员在网页创建后对其进行评论。

他说，两个月后的数据显示，客户正在接受它。它每周收到约 5000 条新评论，自 12 月推出以来，评论总数约为 64000 条。

“我们实际上，无论如何，都不在与 Figma 相同的空间，但我们正在为工作流程的这一部分增加惊人的合作，”Ubl 说。“我们的绝大多数客户都在使用它。你必须从根本上把它看作是网络开发工作流程的转变，类似于人们从 Sketch 到 Figma 的转变。”

将类似 Figma 的协作添加到开发人员的工作流程中，标志着一种趋势正在形成。新的 Stack 已经报道了 StackBlitz 去年 10 月发布的 Codeflow。当时，StackBlitz 还宣布，在 Figma 投资之后，它将提供更加集成的协作体验。CodeSandbox 也在其 IDE 中提供协作支持。

## 它是如何工作的

Vercel 的产品只是在预览时将一个 JavaScript 文件注入到网页中。该文件加载工具栏，工具栏基本上是一个影子文档对象模型(DOM)元素。Ubl 解释说，在它的阴影里，也就是从主页面隐藏的地方，是应用程序运行的地方。

“这为您提供了直接进入数据主机所在的应用程序的灵活性，但无论如何都不会产生负面影响，这是我们必须非常清楚的一点，”Ubl 说。“显然，你不想破坏你正在帮助人们评论的网站。”

评论指的是什么非常清楚，因为它允许用户在站点元素上弹出评论。它可以仅限于一个开发团队，或者像 Google Docs 一样，有一个“共享链接”功能，这样开发者就可以从代理机构或客户那里收集意见。

“这绝对是在上下文中，现在这是实时传达给最初提出这个拉请求的人…任何人都可以跳进去，并做出改变，”他说。

评论也将向开发者展示关于评论员的重要元数据。例如，它将显示评论员的设备像素比率、他们使用的浏览器和部署的操作系统——所有这些都会影响网站的性能和美观。

## 与 Git 提供者集成

预览部署的注释也支持松弛集成，因此对话可以在松弛通道上继续。Comments 还支持三个 git 提供者； [GitHub](https://thenewstack.io/github-now-enables-you-to-find-and-fix-code-for-free/) 、 [GitLab](https://thenewstack.io/an-inside-look-at-what-gitllabs-web-ide-offers-developers/) 和 [BitBucket](https://thenewstack.io/this-week-in-programming-bitbucket-bids-adieu-to-mercurial-to-focus-on-git/) 。与这些提供商的集成提供了一个完整的反馈环，可以轻松访问关于开放/已解决评论的预览和数据。

“你把 Vercel 应用程序安装到你的 GitHub 中，然后 Vercel 得到一个 git，得到一个 web hook，每当对一个 pull 请求进行任何更改时，它就会调用它，”他说，“所以每次发生这种情况，它都会立即触发 Vercel 网站的构建。然后，我们会在“拉”请求中回发一条注释，告诉您这是您以前的部署，您可以在这里看到刚刚做出的更改。”

最后，它支持命令行界面工作流中的注释。通过 CLI 创建的部署将生成启用注释的预览部署链接。

尽管它主要是为团队私人使用而设计的，但 Vercel 通过让所有读者在 beta Next.js 文档网站上发表评论，对它进行了大规模的测试。Ubl 说，Vercel 为试运行建立了一些评论审核功能，但最终没有必要。他说，读者提交了数千条评论。

“这真的是为团队私人使用它，”他警告说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>