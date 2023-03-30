# OSS 开发者如何在不改变许可的情况下采取道德立场

> 原文：<https://thenewstack.io/how-oss-devs-can-take-ethical-stances-without-license-changes/>

虽然开放源码倡议(OSI)对开放源码软件的定义非常明确——必须“不歧视个人或群体”和“不歧视努力的领域”——但根据道德考虑，谁应该被允许使用开放源码软件的问题长期以来一直存在争议。

在过去的一个月里，这个话题再次成为[争论的焦点](https://lists.gnu.org/archive/html/libreplanet-discuss/2022-03/msg00044.html)，因为俄国入侵乌克兰导致开发者呼吁全面禁止像 [GitHub](https://github.com/github/feedback/discussions/12042#discussioncomment-2276190) 和 [GitLab](https://gitlab.com/gitlab-org/gitlab/-/issues/353869) 这样的公司；一些开发商甚至采取了行动。本月早些时候，我们[写了](https://thenewstack.io/where-does-open-source-fit-into-russias-war-with-ukraine/)关于开源网关 [Scarf](https://about.scarf.sh/) 如何开始[限制俄罗斯政府和军事实体通过其网关访问开源软件包](https://about.scarf.sh/post/standing-with-ukraine)。

正如我们当时注意到的，当 Scarf 采取这一行动时，有一个主要的区别:开源软件的分发与它的许可是分开的。OSI 定义中的这些点与许可有关，而不是某个实体主动向其他实体提供软件。

从那以后，围绕这些想法的讨论一直在继续，本周，[软件自由保护协会](https://sfconservancy.org/)的政策研究员兼常驻黑客 Bradley m . Kuhn 的一篇文章认为 [copyleft 不会解决所有问题，只是其中的一些问题](https://sfconservancy.org/blog/2022/mar/17/copyleft-ethical-source-putin-ukraine/)。

这篇文章特别对开源软件可以通过许可限制的方式有效地影响变化这一观点提出了质疑。他在这个话题上花了近 3000 字，然后尖锐地提到了俄罗斯问题——与本月早些时候斯卡夫得出的结论类似。库恩认为“除了软件自由，自由/开源软件许可证并不是推进社会正义事业的有效工具”，相反，开发者有道德义务通过其他方式表明立场。

“例如，自由/开源软件开发者应该拒绝专门处理那些不给工人支付生活工资的公司的 bug 报告，”库恩举了一个例子。

具体到俄罗斯，库恩再次指出分发是抗议的一个途径，同时仍然符合自由和开源软件的原则。

“现有的每一个自由/开源软件许可证都允许任意分发；软件自由保证了拒绝发布软件新版本的权利。(也就是说，Copyleft 并不要求您在互联网上为所有人发布您的所有软件，也不要求您给予所有人同等的访问权限——相反，它只要求您选择给予软件合法访问权限的人也获得 [CCS](https://sfconservancy.org/copyleft-compliance/glossary.html#ccs) )。因此，自由/开源软件项目应该避免让普京轻易获得自由/开源软件的更新，”库恩写道。

所以，对于那些想要站在道德立场上的开源维护者来说，也许让库恩的长篇文章为你提供一个论点，让你保持良心的清白，因为你忽略了一两个拉取请求或者拒绝分发——所有这些都是道德抗议。

## 本周的节目中

*   **Go 1.18 获得泛型和更多:**自从本专栏的[第一次迭代以来，我们一直在写的变化，也是 Go 社区讨论了很长时间的变化，终于来了。随着 Go 1.18](https://thenewstack.io/week-programming-go-2-0-question-complexity/) 的[发布，该语言终于支持使用参数化类型](https://go.dev/blog/go1.18)的[通用代码，这是十多年来最受欢迎的特性。除此之外，Go 1.18 成为“第一个将 fuzzing 完全集成到其标准工具链中的主要语言”，并增加了一个新的](https://go.dev/blog/why-generics) [Go 工作区模式](https://go.dev/doc/tutorial/workspaces)，这使得使用多个模块变得简单，更不用说性能提高了“高达 20%，这是由于 Go 1.17 的注册 ABI 调用约定扩展到这些架构。“我们会写更多关于这个话题的内容，但是 [Darryl Taft](https://thenewstack.io/author/darryl-taft/) 已经在 New Stack】对这个故事进行了深度挖掘，他采访了[史蒂夫法兰克王国](https://www.linkedin.com/in/stevefrancia/)，Google Cloud 的产品&Go 的战略负责人，他称这个版本是“不朽的”，所以我们会引导你去那里了解更多细节。
*   **Docker Desktop 自诩 Mac 速度提升 98%:**Mac OS 上的 Docker Desktop 用户有一个大的[速度提升成就](https://www.docker.com/blog/speed-boost-achievement-unlocked-on-docker-desktop-4-6-for-mac/)期待随着 [Docker Desktop for Mac 4.6](https://docs.docker.com/desktop/mac/release-notes/) 的发布。Docker 表示，该版本“包含大量改变，大大提高了 macOS 用户的文件共享性能”，例如“名为 [virtiofs](https://virtio-fs.gitlab.io/) 的新实验性文件共享实现”和“macOS 主机和 Docker VM 之间文件同步的方式”。有了这些变化，该公司说它已经看到“完成文件系统操作的时间[减少了 98%](https://github.com/docker/roadmap/issues/7#issuecomment-1044452206)。”Mac 用户需要[启用 virtiofs](https://docs.docker.com/desktop/mac/#experimental-features) ，包括 Docker 个人免费用户在内的所有用户都可以使用。

*   **GitHub 为动作引入了部分重新运行:**我们都经历过:你正在运行某种构建过程，看着每个动作成功完成，直到一个动作失败，你不得不重新开始整个过程。GitHub 动作就是这样，但是现在 GitHub 增加了[执行部分重新运行](https://github.blog/2022-03-16-save-time-partial-re-runs-github-actions/)的能力，这允许你只重新运行失败的任务或者一个单独的任务。除了这一新功能，GitHub 表示，它还“对导航进行了改进，使您能够看到以前运行的完整结果。”该公司还指出，“另外，如果你使用 GitHub 托管的跑步者，你可以通过减少计费分钟数来节省资金。”执行部分重新运行的功能可通过新的下拉菜单获得，也可直接从 logs 视图获得，并且每次重新运行都会提供一个确认对话框，其中列出了将重新运行的所有作业，包括所有下游依赖关系的作业。如果你不是通过网站使用 GitHub，也可以通过 GitHub REST API 和命令行工具进行部分重新运行。
*   **渐进式网络应用速成班:**如果你听说过渐进式网络应用(PWA ),但还没有尝试过，微软提供了一种方法让[在 30 天内](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/summary)学习渐进式网络应用，其 [30 天的 PWA](https://aka.ms/learn-pwa/30Days-blog) 系列。在探索[基础构建模块](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/02) (HTTPS、服务工作者和 web 应用清单)之前，本系列先从了解[什么是 PWA](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/01)开始，然后深入探讨如何使 PWA [可安装](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/03)、[可靠](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/04)、[离线工作](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/05)，以及[支持](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/core-concepts/06)。这个系列在上周刚刚完成，在[博客文章](https://microsoft.github.io/win-student-devs/#/30DaysOfPWA/summary)中有完整的总结，所以去尝试一下一些人认为的构建跨平台移动应用的潜在未来吧。买家请注意，苹果缺乏对 PWAs 的支持有点问题，但[开放网络倡导组织正在处理此事](https://thenewstack.io/owa-takes-on-apples-browser-ban-for-pwa-parity/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>