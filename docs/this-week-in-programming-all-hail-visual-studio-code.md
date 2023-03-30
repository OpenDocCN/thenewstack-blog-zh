# 本周编程:向 Visual Studio 代码致敬

> 原文：<https://thenewstack.io/this-week-in-programming-all-hail-visual-studio-code/>

除了争论哪种编程语言是最好的，没有什么比争论代码编辑器更好的了？嗯，本周这场辩论的参与者宣布，我们已经进入了 Visual Studio 代码的时代，微软开发的编辑器已经“达到了前所未有的受欢迎程度和精致程度，奠定了可能意味着几十年市场主导地位的基础”，据开发者[罗本·克莱尼](https://www.linkedin.com/in/roben-kleene-38337459/)称。

根据克莱尼的说法， [VS Code](https://code.visualstudio.com/) 通过四个主要点实现了这种统治地位。首先，它已经达到了超越任何其他此类编辑器的受欢迎程度和主导地位。其次，它采用了“文本编辑器作为平台”的思想，突出使用了扩展，成为“它的最终形式”。第三，VS Code 已经“超越了桌面应用的范式，成为一个托管的 web 应用，甚至是一个参考实现。”第四，当然，这是一个简单的事实，它是“由一家强大的技术公司管理”，正在“积极地”开发它。

克莱尼很快向我们展示了 VS 代码在受欢迎程度上已经超越了其他编辑器，然后带我们回顾了各种基于文本的代码编辑器的历史，从很久以前的 [BBEdit](https://www.barebones.com/products/bbedit/index.html) 、 [Emacs](https://www.gnu.org/software/emacs/) 和 [Vim](https://www.vim.org/) ，到 [TextMate](https://macromates.com/) 、 [SublimeText](https://www.sublimetext.com/) 和 [Atom](https://atom.io/) ，最后是 VS 代码。他认为，这些编辑器的进化止于 VS 代码。

“没有其他地方可去了，”他写道 VS 代码。“相应地，一个新的文本编辑器不可能像以前的文本编辑器那样通过改进扩展来跨越代码。”

随着 VS 代码似乎完善了扩展的艺术，克莱尼引用了编辑器从桌面到 web 的转变，实现了 [GitHub Codespaces](https://code.visualstudio.com/) ，还指出随着由 [Eclipse Foundation](https://www.eclipse.org/) 维护的[忒伊亚](https://theia-ide.org/)IDE 1.0 版本的创建，“它也成为了某种标准”，他称之为“VS 代码的重新实现”正是在这一点上，我想知道一些人是否会提出争议，因为 Eclipse 忒伊亚的创建者将他们的实现称为“Visual Studio 代码的真正开源替代方案”[，但也许这无关紧要。](https://thenewstack.io/eclipse-theia-offers-a-true-open-source-alternative-to-visual-studio-code/)

克莱尼的最后一点，微软对 VS Code 的支持及其积极的开发，将编辑器与 Sublime Text 和 Textmate 的编辑器进行了对比，表明 VS Code 有更一致的发布节奏，这是由其公司支持者及其背后非常活跃的开源社区实现的。

除了谈论流行和赛马，Kleen 写道“这篇文章的目标是确定如果你重视长寿，VS 代码是否是学习的好投资，”他推测，“VS 代码给出了文本编辑器短暂统治时代结束的迹象。如果我们以其他类别的流行软件作为参考，它有可能在更长的时间内保持最受欢迎的文本编辑器的地位，可能长达几十年。”

你觉得怎么样？VS Code 会像克莱尼建议的那样，加入 Excel、Photoshop、Illustrator 等软件的行列吗？或者下一个替代者正在技术转弯处等着我们？

## 本周的节目中

*   **Visual Studio 增加了代码空间、Git 集成等等:**又是一周，又是一场数字会议，这一次微软 Ignite 走上了虚拟舞台。因此，我们本周有一些与开发者相关的发布活动，首先是 Visual Studio 2019 v16.8 预览版 3.1 中的所有[新功能。脱口而出，不是吗？该版本在 Git 集成、C++20 一致性等方面进行了改进。NET 生产力、Web 工具和 XAML，根据博客文章，随着 GitHub code spaces for Visual Studio 的](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-v16-8-preview-3-1/)[可用，现在在更令人兴奋的新特性中](https://aka.ms/codespaces-signup)可用。可用性是有限的测试版，但他们计划随着时间的推移推广到更多的人。至于 Git 集成，Visual Studio 现在增加了对 Git 源代码管理工作流的改进支持，并将默认的源代码管理提供程序更改为 Git，而不是 TFVC。最近刚刚获得批准的 C++20 也获得了一些改进的支持，Visual Studio 用户能够“在同一个项目中使用模块、概念、协程和(一些)范围。”这只是新内容的一个尝试，所以请确保点击查看[的完整报道](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-v16-8-preview-3-1/)。

*   **连接 Dapr 和 Azure API:**本周微软 Ignite 发布的一些有趣的公告与 Kubernetes 相关，首先是在 Azure API 管理服务中集成了[Dapr](https://cloudblogs.microsoft.com/opensource/2020/09/22/announcing-dapr-integration-azure-api-management-service-apim/)。根据这篇博客文章，这种集成“使运营团队能够直接将 Dapr 微服务作为 API 公开，并使这些 API 可被开发人员发现和轻松使用。”Dapr 是去年[发布的](https://thenewstack.io/microsofts-open-source-dapr-could-help-developers-build-agnostic-microservice-applications/)，我们当时被告知，它的名字“大致翻译为分布式应用运行时”，并且“专注于提供让开发者更容易构建微服务的构建模块”这种新的集成使得“用户现在能够应用 APIM 的[自托管网关](https://aka.ms/apim/shgw/overview)功能，在单个界面中管理他们所有的 Dapr APIs 以及其他 API。”欲了解更多信息，请查看此[完整演示报告](https://aka.ms/apim/dapr/walkthru)和此[APIM Dapr 整合政策的完整参考](https://aka.ms/apim/dapr/policies)。
*   **通向 Kubernetes 的桥梁:**希望在使用依赖项并从 Kubernetes 环境继承现有配置的同时编写、测试和调试代码的开发人员现在可以高兴了，因为微软的[通向 Kubernetes 的桥梁现在已经普遍可用](https://devblogs.microsoft.com/visualstudio/bridge-to-kubernetes-ga/)。通往 Kubernetes 的桥梁是一个迭代开发工具，在 [Visual Studio](https://aka.ms/bridge-to-k8s-vs-extension) 和 [VS Code](https://aka.ms/bridge-to-k8s-vsc-extension) 中提供，它将您的开发工作站连接到您的 Kubernetes 集群，让您无需过多担心外部依赖性和配置就可以进行编码。这个最新版本也可以与任何 Kubernetes 一起工作，无论是在云中还是在本地，并带来了端到端的测试和调试，以及在共享开发环境中独立工作的能力。

*   **开源 Calico for Windows:** 这最后一个离开发者领域有点远，但仍然值得注意——[Calico for Windows 已经开源](https://cloudblogs.microsoft.com/opensource/2020/09/22/calico-for-windows-goes-open-source/)。Calico 是“针对容器、虚拟机和基于本地主机的工作负载的开源网络和网络安全解决方案”，现在老虎团队[写道](https://www.tigera.io/blog/tigera-announces-open-source-calico-for-windows-and-collaboration-with-microsoft/)它“已经为您的生产环境做好了准备，就像 Calico for Linux 已经做了很多年一样。”有关完整的详细信息，请查看[发行说明](https://docs.projectcalico.org/release-notes/)，加入 Calico 用户松弛 [Windows 频道](https://calicousers.slack.com/archives/CF9M1U9RV)，以及[快速入门指南](https://docs.projectcalico.org/getting-started/windows-calico/quickstart)。
*   **GitHub Actions 改进了它的日志功能:**最后，GitHub 说它现在有了[更好的 GitHub Actions 日志体验](https://github.blog/2020-09-23-a-better-logs-experience-with-github-actions/)，这是“一系列将改善性能和用户体验的改变”这些变化包括简化的布局结构、更快的虚拟化滚动、更灵敏的搜索、交互式 URL、全屏查看、改进的 UI，以及最重要的是，更好的 ANSI、8 位和 24 位颜色支持。这是 GitHub 在过去几周内两次为我们带来一些甜美的 ANSI 着色。

*   准备好参加 DevFest，Google Devs！谷歌已经[宣布了 DevFest 2020](https://feedproxy.google.com/~r/GDBcode/~3/goB8MkXgUho/announcing-devfest-2020.html) ，我们距离该活动只有短短几周时间，该活动将于 10 月 16 日至 18 日举行。 [DevFest 2020](https://goo.gle/devfest) 将是一个虚拟的、社区主导的学习谷歌技术的周末，演讲者从[儿童开发者](https://developers.googleblog.com/2019/11/devkids-inside-look-at-kids-of-devfest.html)到[来自农村地区的自学程序员](https://www.youtube.com/watch?v=WQmfbS7dJGA&t=4s)到[初创公司的首席执行官和首席技术官](https://www.youtube.com/watch?v=9ayKuMKhlDE)等等。会议将涵盖多种谷歌技术，如 [Android](https://developer.android.com/) 、[谷歌云平台](https://cloud.google.com/)、 [TensorFlow](https://www.tensorflow.org/) 、 [Web.dev](https://web.dev/) 、 [Firebase](https://firebase.google.com/) 、 [Google Assistant](https://developers.google.com/assistant/howassistantworks?hl=en) 、 [Flutter](https://flutter.dev/) ，现在就可以[报名](https://goo.gle/devfest)参加。
*   **整合协同效应，跳出框框思考:**如果你和我一样，即使只是阅读这些文字也会让你手臂上的汗毛竖起来一点，你可能刚刚经历了把你正在阅读的任何设备扔到房间另一边的冲动。好吧，准备好调整收入流、提供客户体验和跳出框框思考，因为[战略沟通编程语言](https://github.com/rotoclone/strategic-communication)将为您提供“一种最佳的语言，以整体的方式推动工作。”成为一个优秀的人是如此痛苦和恐怖。哦，当你使用这种语言时，不需要评论。为什么？“战略沟通的语法达到或超过了企业话语的最高标准，因此评论是不必要的，也是不被支持的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>