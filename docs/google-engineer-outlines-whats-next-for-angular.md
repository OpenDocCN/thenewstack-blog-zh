# 谷歌工程师概述 Angular 的下一步

> 原文：<https://thenewstack.io/google-engineer-outlines-whats-next-for-angular/>

谷歌的开发者关系工程师[艾玛·特沃斯基](https://www.linkedin.com/in/emmatwersky/)说，Angular 版本 15 计划于 11 月发布，届时谷歌将引入友好的堆栈跟踪，以帮助准确识别代码错误所在，以及一种优化图像组件的方法，这将在网站的[第一次内容丰富的描绘](https://web.dev/first-contentful-paint/)中产生重大改进。

Twersky 在本月马萨诸塞州波士顿举行的 [Progress 360 会议](https://thenewstack.io/progress-360-how-panera-fixed-its-application-validation-gap/)上展示了“Angular 的新功能”。尽管标题如此，演讲的很大一部分还是集中在 Angular 过去的反复，以及这些变化是如何为谷歌下一步用 Angular 做什么打下基础的。

## 常春藤项目:“在汽车行驶时更换汽车引擎”

[谷歌](https://thenewstack.io/google-inks-deal-with-nist-to-boost-open-source-chips/)正在快速迭代 Angular——去年发布了 12 和 13 版本，今年 6 月发布了 14 版本。Twersky 说，所有这些工作——包括 Ivy——实际上是为将来的框架改进打下基础。 [Ivy](https://docs.angular.lat/guide/ivy) 是 Angular 下一代编译和渲染管道的名称，它是 Angular 版本 9 的默认视图引擎。

Twersky 告诉开发者说:“常春藤计划被宣布了，也许过早，但是很久以前了，它花了很长时间来开发。”“这是一次完整的重写，我能给出的最好的类比是，这就像是在汽车还在行驶的时候更换发动机。”

这个新引擎给 Angular 提供了更好的类型检查、错误报告、调试、更小的包大小；但它真正做的是实现谷歌计划的未来改进。她说，随着 Ivy complete 的完成，谷歌的计算资源减少了 90%，这反过来又导致谷歌最大的 Angular 应用程序的构建时间减少了约 50 分钟。

## 谷歌的棱角军队

她说，Angular 团队也在这个时候推出了征求意见稿(RFC)。她说，RFC 是反馈的机会，也是引入实验性变化的机会。在版本 13 和 14 中，谷歌还开始发布开发者预览版，允许开发者测试谷歌正在考虑实施的内容，但意识到它可能会被改变，谷歌不一定承诺支持向后兼容。她说，这是为了帮助框架更快地发展。

“如果我们有一个设计文档，为什么不分享它，为什么不与数百万使用 Angular 的开发人员进行战斗测试，为什么不提前思考一些有趣的案例？”她说。“我们真的要带着棱角分明的军队一起解决问题。”

她补充说，谷歌已经推出了超过 15 个 RFC，但其中两个最大的 RFC 提到了独立的组件，即 NgModules 的移除，ng modules 是特定于角度的模块，用于配置注射器和编译器，以便帮助将相关的东西组织在一起。

在此期间，该团队的另一个修复措施是:更好地支持调试和诊断，具体的细节和错误信息指导，以及通过与 Chrome 团队和第三方资源的合作支持的 Angular dev 工具。

## 独立组件

Twersky 说，NG 模块是新开发人员必须学习 Angular 的另一件事，但它令人困惑，因为其他编程语言使用术语“模块”来表示其他东西。

“Standalone 旨在简化所有这一切，并简化入门步骤，”她说。通过引入独立真标志，您可以直接引导您的组件，而不需要模块

她的想法是，现在整个应用程序都可以是独立的。她补充说，这是一个重大变化，得到了谷歌创造的新的[API](https://thenewstack.io/state-of-the-api-lack-of-api-design-skills-a-key-problem/)的支持；它还承诺对 API 的任何修改都是向后兼容的。

## Angular 版本 15:收获收益

“现在我们进入第三阶段，这是我们努力工作的成果，”Twersky 说。“坦率地说，这一阶段尚未发生。版本 15 定于 11 月，所以这是非常投机和早期预览。但这里的想法是[……]我们解锁的一切。”

她说，第 15 版将会看到对完全独立的支持。

她说:“我们有一些对每个人都有益的东西，默认情况下是 zone JS 支持的异步堆栈获取，但我们只是称之为更好的堆栈跟踪。”这是通过与 Chrome 的另一项合作实现的，即使使用开发人员没有编写的开源代码和错误发生的地方，也可以更容易地削减相关内容。

版本 15 还承诺使路由器树可摇动，这基本上从代码库中删除了未使用的代码。她说，在编写路由器的独立版本时，该团队能够集成关于路由器模块的许多不再需要的东西，使其更加稳定。她说，新的配置 API 允许开发者对路由器 API 的主要部分进行重组。

“在最后阶段，我们想要做的和北极星提供的只是你需要的，我们必须扔掉很多路由器，所以如果你不使用它，我们就不再需要为你提供它。Angular 的想法是，我们有很多代码，但你的应用程序不会使用所有的代码。所以在编译的某个时候，我们可以去掉很多你不用的代码。”

谷歌正在考虑的其他变化:

*   默认情况下隐藏 CLI 配置
*   MDC。 [MDC Web](https://thenewstack.io/html-css-and-the-path-to-accessible-web-design/) 是 Google Material Design 团队创建的一个库，为建筑材料设计组件提供可重用的原语。根据他们的路线图，Angular 团队正在将这些元素整合到 Angular 材质中。“因此，如果你使用有棱角的材料，MDC 就像是最新最闪亮最容易获得的规格，这是默认情况下发生的，”她说。
*   围绕[水合](https://thenewstack.io/javascript-hydration-is-a-workaround-not-a-solution/)等发展趋势征求意见。

*披露:Progress Software 支付了 Loraine Lawson 参加其在波斯顿的会议的费用。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>