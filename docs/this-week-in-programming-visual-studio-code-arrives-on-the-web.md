# 本周编程:Visual Studio 代码出现在网络上

> 原文：<https://thenewstack.io/this-week-in-programming-visual-studio-code-arrives-on-the-web/>

微软本周继续向开发者主导地位进军，推出了[Visual Studio Code for Web](https://vscode.dev)的，这是该公司非常受欢迎的([主要是](https://thenewstack.io/eclipse-theia-offers-a-true-open-source-alternative-to-visual-studio-code/))开源代码编辑器的轻量级版本，完全在浏览器中运行。

现在，在你变得太兴奋之前，Web 的 VS 代码并不是运行在浏览器中的 VS 代码的真正全功能版本，因为它没有后端来支持它，这意味着它的主要目的是用于客户端 HTML、JavaScript 和 CSS 应用程序。

“由于 VS Web 代码完全在浏览器中运行，与桌面应用程序相比，有些体验自然会受到更多限制。例如，终端和调试器不可用，这是有意义的，因为你不能在浏览器沙盒中编译、运行和调试 Rust 或 Go 应用程序(尽管 Pyodide 和 web containers 等新兴技术有朝一日可能会改变这一点)，”微软解释道，并补充说代码编辑、导航和浏览“稍微有些微妙”。

也就是说，VS Code for the Web 能够为 C/C++、C#、Java、PHP、Rust 和 Go 等流行语言提供语法着色、基于文本的完成和其他类似功能，而 TypeScript、JavaScript 和 [Python](https://devblogs.microsoft.com/python/python-in-visual-studio-code-september-2021-release/#a-rich-python-editing-experience-in-the-browser-via-github-dev) 则“全部由在浏览器中本地运行的语言服务提供支持”，因此提供了“更好”的体验，而上述那些 Web 语言，如 JSON、HTML、CSS 等，将提供最佳体验。与此同时，扩展——这是使用 VS 代码的主要原因之一——通常适用于用户界面定制(并且可以[与您的其他环境](https://code.visualstudio.com/docs/editor/settings-sync)同步),但是，再一次，对于那些后端特性来说就不那么适用了。

抛开警告不谈，VS Code for the Web 确实为你的平板电脑、Chromebook、甚至你的 XBOX 提供了一个轻量级、随处可用的代码编辑器。

现在，说了这么多，我们不得不问—在开发环境向 web 的转变中，其他主要的云提供商在哪里？虽然在过去的一年半时间里，由于 COVID 的存在，我们除了听到远程这个和远程那个之外，什么也没听到，但似乎只有微软真正给予了关注。该公司的每一步行动似乎都是为了让他们更深地陷入你经常听到的无处不在的“开发者体验”。

虽然亚马逊和谷歌等公司似乎在这个领域无所事事，但微软并不是唯一一家专注于提供远程开发者体验的公司。例如，Eclipse 基金会去年提供了它所说的“T0”一个真正的替代 Visual Studio 代码的开源软件， [Eclipse 忒伊亚](https://theia-ide.org/)和 Eclipse 基金会执行董事 [Mike Milinkovich](https://ca.linkedin.com/in/mikemilinkovich) 说他希望这只是一个开始。

“我们多年来一直在说，开发者工具的未来是浏览器。开发人员已经使用他们的浏览器完成了绝大多数日常任务，代码编辑是最后一个移动的，”米林科维奇在一封电子邮件中写道。“微软最近发布的 vscode.dev 就是对这一趋势的认可。我预计在接下来的几个季度里，每一家真正的云供应商都会效仿。”

与此同时，GitPod 一直在这个领域努力工作，上个月刚刚推出了自己的开源[OpenVSCode Server](https://github.com/gitpod-io/openvscode-server)，它也允许开发人员在浏览器中运行上游 Visual Studio 代码。Gitpod 联合创始人 [Johannes Landgraf](https://de.linkedin.com/in/johanneslandgraf) 指出 [GitHub1s](https://github.com/conwnet/github1s) 是这些项目的原始灵感，并指出它们缺乏计算作为一个定义特征。

兰德格拉夫写道:“受 GitHub1s 的启发，[github . dev](https://github.dev/)/[VS Code . dev](https://vscode.dev/)将 VS 代码的 web 工作台放在浏览器中，无需访问计算。“虽然这是另一个验证，表明我们已经达到了开发软件的方式和地点的临界点，但 Gitpod 和 Codespaces 等平台远不止如此。想想在云中进行专业软件开发所需的计算、操作系统、语言服务器和所有其他工具的编排和供应。”

虽然 Landgraf 显然有一个观点，但 VS 代码对于 Web 来说就像是周五 5 美元的烤鸡——当它闻起来很香，它让你进门，然后你知道，你已经在其他东西上花了 100 美元……比如 GitHub Codespaces，它毕竟是几乎完全一样的东西，除了它提供所有这些后端服务，更重要的是，对微软来说，它不是免费使用的。更重要的是，一旦你让所有的开发者完全迷上了 VS Code、Codespaces、GitHub 和其他东西，Azure 现在就不会太远了，不是吗？

## 本周的节目中

*   **GoLang 在 Go 1.18 中踩下泛型的刹车:**虽然今年早些时候 Go 的泛型添加终于得到了[的批准](https://thenewstack.io/this-week-in-programming-go-approves-generics-long-at-last/)，但 Gophers 可能还需要再等一会儿才能完全进入语言核心库。 [Rob Pike](https://twitter.com/rob_pike?lang=en) ，Go 最初的设计者之一，本月早些时候提交了一份提案，建议他们[不要改变 1.18](https://github.com/golang/go/issues/48918) 中的库，而是暂时将这些改变移入 [golang/x/exp 库](https://pkg.go.dev/golang.org/x/exp)。exp 存储库是语言存放“实验性的和不推荐使用的”包的地方，这些包不包括在 Go 安装的二进制下载中，这意味着它们仍然可以被那些稍微花点心思去获取它们的人使用，但默认情况下不包括在内。Pike 认为泛型是“该语言自创建以来最大的变化”，并且“如何在标准库中使用这些思想需要很好的思考和规划。”Pike 说，现在不是直接将更改放入核心库，而是将它们放入 exp 库，这样它们“可以在生产中测试，但可以在一两个周期内进行更改、调整和发展，让整个社区尝试它们”，然后，“一旦它们吸收了一些，并通过经验进行了更新，我们就将它们移到主 repo 中，就像我们对其他外部开发的包所做的那样，但有信心它们在实践中工作良好，值得我们的兼容性承诺。”快速浏览一下对该提案的评论，似乎表明这将是正式添加泛型的前进方向，但似乎还没有什么是板上钉钉的。

*   **IBM 介绍开源混合云指南:**IBM 说[最近发现](https://developer.ibm.com/blogs/oreilly-open-source-skill-survey-blog/)开发人员应该把时间集中在磨练他们的开源技能上，而不是学习使用单一类型的公共云所需的专有技能。毕竟，“每个主要的云平台都在其基础设施中使用开源软件。”因此，该公司[推出了](https://developer.ibm.com/blogs/contribute-to-a-new-open-source-cloud-guide/)“[开源云指南](https://open-cloud-guide.dev/)，该指南强调了在混合云环境中很重要的各种用例，突出了这些领域中重要的开源项目，并讨论了各种云如何在其产品中使用开源。”对于每个使用案例，该指南提供了概述、对传统解决方案的解释、关键的开源项目，然后重点介绍了云提供商如何利用开源解决方案。IBM 表示，该指南旨在回答关于开发人员的技能如何转化为混合云环境开发的问题，包括主要的云提供商和最常用的开源技术。然而，该指南并不完整，IBM 正在寻找开发人员来为其做出贡献。
*   **为 GitHub Universe 做好准备:**没错，下周就是 GitHub 的年度开发者大会， [GitHub Universe](https://githubuniverse.com/?utm_source=announcement&utm_medium=blog&utm_campaig=register) ，而今年的活动是完全虚拟的，有一堆不同的环节。在会议的准备阶段，GitHub 已经发布了一个关于 GitHub Universe hosts 的简短的 [Q & A，其中包括一些关于会议书签的建议。建议的会议包括代码空间入门、使用 GitHub 代码空间和 VS 代码在云中编码、Github Enterprise 的新特性、使用 GitHub Mobile 在旅途中完成工作、通过 GitHub Enterprise 执行信息安全政策以及思科对现代应用安全的看法。首先，如果你还没有注册，请前往](https://github.blog/2021-10-18-meet-github-universe-hosts-start-building-schedule/)[注册参加 10 月 27 日至 28 日的活动。](https://githubuniverse.com/?utm_source=announcement&utm_medium=blog&utm_campaig=register)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>