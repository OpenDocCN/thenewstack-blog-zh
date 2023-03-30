# 本周编程:代码对于编码是必要的吗？

> 原文：<https://thenewstack.io/this-week-in-programming-is-code-necessary-to-coding/>

本周每个人似乎都感兴趣的一些消息是谷歌的“[低代码环境应用程序制造商，](https://sdtimes.com/lowcode/googles-low-code-environment-app-maker-is-now-available/)”的普遍可用性，它承诺“让你的团队轻松地从原型迭代到部署的应用程序”，尽管他们缺乏编码经验和计算机编程艺术的正式培训。

对于大多数开发人员来说，我不得不想象对于这类消息的反应，就像大多数这类“低代码”解决方案一样，介于“祝你好运”和“谢天谢地，现在我不用这么做了”之间。对我来说，每当我看到这些新的、低代码选项中的一个，它都会让我重新思考作为一名开发人员、编码人员、程序员或其他我们想称呼自己的人到底意味着什么。

我总是回想起那些从《发现》杂志的封底手动复制基本代码的早期日子。这是学习编码的精髓。这还包括通过摆弄汇编代码，或者在学习读写文件时破坏一些重要的数据，或者其他任何事情，从而意外地损坏了我的引导扇区。它包含了某种本质上的不可接近性和困难——几乎就像是一种欺侮。那是进入计算机程序员的上流社会的费用。

然而，对于一名开发人员来说，这些真的有必要吗？还是更单纯的一种思维方式？

太多时候，这些低代码产品似乎为不熟练的人提供了轻松开发应用程序的承诺，但我敢说，技能不在于知道代码，而在于知道如何给计算机编程——如何告诉计算机做什么，以及如何与另一端的人互动。当然，还有更深层次的编码和理解(这也远远超过了我自己微薄的理解)，但即使开发一个简单的“业务线”应用程序，正如[公告](https://www.blog.google/products/g-suite/build-apps-your-business-needs-app-maker/)所称的，也不仅仅需要对代码的技术理解。这些天，我看着我九岁的侄女学习使用[麻省理工学院的 Scratch](https://scratch.mit.edu/) 进行“编码”，虽然她不必与这些同样可怕的初始权利作斗争，但她正在学习如何思考每一步和可能性。她正在学习解释边缘用例，以及一个步骤如何导致下一个步骤，以及她如何不能想当然。电脑完全按照她说的去做，不多也不少。任何希望为自己的企业开发应用的人——不管他们是否了解实际的“代码”——都需要准确地体现这些技能。

谷歌甚至在介绍 App Maker 时也承认了这一点:

[https://www.youtube.com/embed/rq0GeJXxfNI?feature=oembed](https://www.youtube.com/embed/rq0GeJXxfNI?feature=oembed)

视频

代码不是编码者，而是思维方式。这些低代码解决方案为那些不愿花时间理解代码，但愿意花时间学习如何像程序员一样思考的人打开了编码的世界。与此同时，对于那些已经了解如何编码的人来说，低代码似乎也让生活变得更容易，如果你问我的话，这是……非常棒的。

## 本周的节目中

*   **TypeScript 大步前进:**如果 TIOBE 指数是一个指标，TypeScript 终于大步前进，因为[终于加入了 TIOBE 100 强](https://jaxenter.com/typescript-tiobe-june-2018-145492.html)。TIOBE 索引跟踪语言的受欢迎程度，JAXEnter 报告说“TypeScript 终于在#93 首次亮相”，评论说“虽然许多人都表达了他们对这种 MS 语言的热爱，但它从未在广泛的受众中太受欢迎。”继续读下去，看看这一次语言流行的其他变化，包括 PHP 和 Visual Basic 的使用显著增加。
*   **Fo 为 Go 带来了函数式编程特性:【JAXEnter 的另一个故事向我们介绍了 [Fo，它是 Go](https://jaxenter.com/meet-fo-go-superset-145570.html) 的一个实验性超集。根据这篇文章， [Functional Go](https://github.com/albrow/fo) ，或 Fo，到目前为止有一个特性——通过泛型的类型多态性。从本质上说，这个特性使得“编写灵活的高阶函数和类型不可知的数据结构成为可能”，并且“让我们一瞥 Go 使用一些新的语言特性会是什么样子，并让我们探索这些特性如何交互，以及可以用它们构建什么。”事实上，Fo 还处于最初的实验阶段，但是它似乎在这周的 Go 社区中引起了轰动。**

*   **脸书的声纳开源:**接下来，SDTimes 报道[脸书已经开源声纳](https://sdtimes.com/os/facebook-open-sources-sonar/)，它的可扩展调试工具“最初是为了帮助脸书工程师管理使用多个不同模块的复杂性而创建的”根据脸书的声明，Sonar 提供了“一种高度灵活、直观的方式来检查和理解他们的 iOS 和 Android 应用程序的结构和行为……通过提供更直观和互动的体验，可以扩展以适应工程师的特定需求。“这个工具现在[可以在 GitHub](https://l.facebook.com/l.php?u=https%3A%2F%2Ffbsonar.com%2F&h=AT1hsbBsmbjh6mgTw7s5FlAwPC9Tipf0Te2ahzs8P1Ux6C7BC6H-xGnyY7_L1QmNm_q2o41f8u96W7kRE1kH-Z5y9h0O-FlLh2GLdadENbbQfsXQQzkY1NJTEo7OuSqmbJ7hBJ0f1WEfOQ) 上获得，脸书提供了一个关于[如何实现声纳插件的快速指南](https://fbsonar.com/docs/getting-started.html#setup)。
*   **不再有第三方 Chrome 扩展安装:**谷歌正在禁止第三方 Chrome 扩展安装， [Techcrunch 向我们解释了为什么我们不能再有好东西了](https://techcrunch.com/2018/06/12/google-puts-an-end-to-chrome-extension-installs-from-third-party-sites/)。本质上，直到这一声明，“在网络商店发布应用的开发者也可以从他们自己的网站启动应用和扩展安装”，他们有时会欺骗。从 2018 年 9 月 18 日开始，这些内嵌安装将不再存在，Chrome 用户将被重定向到 Chrome 网络商店来安装该扩展。
*   Snapchat Snap Kit 的传言是真的:有传言称 Snapchat 正在开发 SDK，ProgrammableWeb 报道称这些传言确实是真的，因为 [Snapchat 发布了 Snap Kit](https://www.programmableweb.com/news/snapchat-launches-snap-kit/brief/2018/06/14) ，称其为“基于该公司之前对第三方开发者采取的封闭方式的重大声明” [Snap Kit](https://kit.snapchat.com/) 雇佣“一系列 API，让开发者在第三方应用中访问 Snapchat 功能”，包括四个基本组件:创意套件、登录套件、Bitmoji 套件和故事套件。这些套件使开发人员能够访问 Snapchat 摄像头，使用 Snapchat 凭据登录第三方应用程序，在集成的应用程序中使用 Snapchat Bitmoji 贴纸，以及在第三方应用程序中嵌入 Snapchat 故事。[直接用 Snapchat](https://accounts.snapchat.com/accounts/login?continue=https%3A%2F%2Faccounts.snapchat.com%2Faccounts%2Fsso%3Fclient_id%3Dsnap-connect--prod) 申请访问。
*   **将 Node.js 部署到 App Engine:** 谷歌本周宣布，你[可以将你的 Node.js 应用部署到 App Engine 标准环境](http://cloudplatform.googleblog.com/2018/06/Now-you-can-deploy-your-Node-js-app-to-App-Engine-standard-environment.html)，这让你“无需担心底层基础设施就可以部署 web 和移动应用”，并享受“零配置部署、零服务器管理和自动扩展功能”谷歌还提供了一个[快速入门指南](https://cloud.google.com/appengine/docs/standard/nodejs/quickstart)，告诉你如何在 App Engine 上开始使用 Node.js。

谷歌和微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>