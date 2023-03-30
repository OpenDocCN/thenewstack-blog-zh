# 决定 Docker 桌面的时候到了

> 原文：<https://thenewstack.io/the-time-to-decide-on-docker-desktop-has-arrived/>

自从 [Docker 第一次宣布更新其订阅等级](https://www.docker.com/blog/updating-product-subscriptions/)并普遍[搅动技术社区](https://thenewstack.io/this-week-in-programming-docker-and-the-internet-of-entitlement/)以来，现在已经五个月了，一些人称此举有点像“[的诱饵和开关](https://twitter.com/jbeda/status/1432803352853684227?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1432803352853684227%7Ctwgr%5E%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Ffeedly.com%2F)。虽然订阅更新做了一些改变，但引起所有骚动的一个是让 Docker Desktop 成为一些用户的付费订阅。

根据 Docker 定价页面，对于那些拥有超过 250 名员工或年收入超过 1000 万美元的公司，Docker Desktop 起价为每月 5 美元，新宣布的 Docker Business 订阅层起价为每月 21 美元。属于这一类的企业有五个月的时间来做决定——他们是订阅，还是寻找 Docker Desktop 的替代产品？

嗯，决定的时间已经很接近了，因为 Docker Desktop 的宽限期很快就要结束了:2022 年 1 月 31 日，很快。当然，你什么都想好了，对吧？

好吧，好像做决定还不够难，SUSE 本周出来宣布 Rancher Desktop 1.0.0 已经到来。

现在，我们已经在去年讨论过将 [Rancher Desktop 作为 Docker Desktop 的替代品](https://thenewstack.io/this-week-in-programming-ranchers-docker-desktop-replacement/)，但那是在 [Rancher Desktop](https://rancherdesktop.io/) 仍处于 v0.5 版本的情况下，而且根据 SUSE 工程和创新总裁[盛亮](https://www.linkedin.com/in/shengliang)的说法，“几个主要功能将在 GA 之前推出。”

“在 SUSE，我们希望让在桌面上使用 Kubernetes 的体验更加轻松简单。SUSE 软件架构师 Matt Farina 在 [1.0 发布的博客文章](https://www.suse.com/c/rancher_blog/rancher-desktop-1-0-0-has-arrived/)中写道:“那些开发应用程序或将它们打包以在 Kubernetes 上运行的人需要一个易于使用的本地环境。”。

法里纳说，作为使 Kubernetes 的使用“更容易、更简单”的一部分，Rancher Desktop 使用 [k3s](https://k3s.io/) 为您提供您选择的 Kubernetes 版本，以便您可以与生产环境相匹配，并为那些使用 nerdctl 或 Docker CLI 的用户提供 containerd 或 dockerd 作为容器引擎。

在 Twitter 上被吹捧为 Rancher Desktop 潜在替代品的功能包括在新的 Mac M1 硬件上操作的能力。然而，其他人说，Rancher Dekstop 在与 Docker Desktop 一起使用时甚至更好，而不是取代。

当然，当我们去年与 Docker 谈论所有这些变化时，他们(以及一位 Gartner 分析师)断言[取代 Docker 桌面不会那么简单](https://thenewstack.io/docker-defends-desktop-pricing-says-support-led-to-faster-features/)。或许，在你做出最终决定的时候，我们会给你留下 Docker CEO 斯科特·约翰斯顿在那次采访中的话。

“五年来，我们已经发布了四个主要版本，下载量高达数亿次。永远不要说永远——这是软件，当然，有人可以备份一卡车的钱，把钱扔给一群工程师等等——但是，假设一夜之间，人们可以在他们的桌面上用一堆开源软件拼凑出一个解决方案，你知道，只要你看看那里的数字，“约翰斯顿说。“那等于五年几百个工程人月的工程投资吗？我的意思是，我会让你做数学。”

## 本周的节目中

*   **TypeScript 编译器选择 Golang 端口而不是 Rust 重写:**虽然看起来 [Rust 是 JavaScript 基础设施的未来](https://leerob.io/blog/rust)，但该基础设施的一个创建者决定改用 Golang。 [DongYoon Kang](https://twitter.com/kdy1dev?lang=en) ，可扩展 Rust 平台 [SWC](https://swc.rs/) 的创造者，本周写道，他将[移植 tsc 到 Go](https://kdy1.dev/posts/2022/1/tsc-go) 而不是 Rust，尽管 Rust 重写的初步发现比 tsc 执行类型检查快 62 倍。“最终，我意识到，重写一个像 tsc 这样的大型项目是极其困难的。但是性能的提高是令人兴奋的。这让我尝试了另一条路:移植而不是完全重写。因此，我开始研究 TypeScript 源代码，”康写道。“tsc 使用了大量的共享可变性，许多部分依赖于[垃圾收集](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science))。尽管我是 Rust 的拥护者和信徒，但我觉得它并不适合这里的工作。使用 Rust 要求我在这个特定的项目中过多地使用不安全的 T12 除此之外，Kang 指出共享可变性和循环可变引用是不使用 Rust 的进一步原因，因为 Rust 旨在防止这种行为。将 tsc 移植到 Go 的工作由 Vercel 资助，Kang 表示，他们计划在未来对其进行开源，并建立一座桥梁，以便与一起使用这一新版本的 tsc。然而，如果你的必备清单上恰好有一个基于 Rust 的类型检查器，你可以随时关注一下 [tyty](https://zackoverflow.dev/writing/tyty) ，上周大家都在谈论的基于 Rust 的类型检查器。

*   Visual Studio 2022 Mac 版增加了 M1。NET 6: 而 [Visual Studio 2022 和。NET 6 于去年在 Windows](https://thenewstack.io/visual-studio-2022-and-net-6-finally-arrive/) 机器上发布，随着[Visual Studio 2022 for Mac Preview 5](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-5/)于本周发布，Mac 的全面发布仍在进行中。然而，这个预览版在最终版本上做了一些大动作，因为它现在正在运行。NET 6 和苹果的 M1(基于 ARM 的)处理器上。根据博客帖子，“这一变化带来了一些立竿见影的绩效，并为团队在未来更快地创新奠定了基础。”此外，正在努力将 IDE 迁移到“完全原生的 macOS UI”，他们说这一迁移已经完成了 95%。Preview 5 通过将文档切换器和文档大纲移植到原生用户界面进一步推进了这一努力，这提供了[好处](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-1-is-now-available/)，例如提供“舒适的 Mac 用户体验”和“对辅助技术的更好支持”。[Visual Studio 2022 的预览版 5 可供下载](https://aka.ms/installer/preview)，所有的更改都在[发行说明](https://docs.microsoft.com/en-us/visualstudio/releases/2022/mac-release-notes-preview)中有所概述。
*   **Visual Studio 2022 中更快的代码搜索:**谈到 Visual Studio 2022，微软表示，前面提到的[去年年底发布的](https://thenewstack.io/visual-studio-2022-and-net-6-finally-arrive/)已经提供了更快的代码搜索，“与 Visual Studio 2019 相比，95%的搜索速度提高了两倍以上”，并且[Visual Studio 2022 中的代码搜索将会变得更快](https://devblogs.microsoft.com/visualstudio/code-search-in-visual-studio-is-about-to-get-much-faster/)。最近发布的 [Visual Studio 2022 17.1 预览版 3](https://docs.microsoft.com/en-us/visualstudio/releases/2022/release-notes-preview) “引入了文件中的索引查找，使你的搜索体验更快，”他们写道，并提供了一个图形，显示预览在一秒多一点的时间内返回结果，而 Visual Studio 16.4 需要 20 多秒。新的代码搜索需要快速更改设置，并通过在后台加载时索引项目并创建索引来工作。“当用户执行‘查找’时，这个索引被用来从搜索中删除文件，以便更快地完成搜索，”他们写道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>