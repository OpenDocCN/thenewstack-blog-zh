# Solomon Hykes: Dagger 为 CI/CD 带来了 Docker 的希望

> 原文：<https://thenewstack.io/solomon-hykes-dagger-brings-the-promise-of-docker-to-ci-cd/>

对于 [Dagger](https://dagger.io/) 背后的团队来说，上个月[发布了](https://dagger.io/blog/public-launch-announcement)公开测试版的“用于 CI/CD 管道的便携式开发套件”，这个开源初创公司有点像是第二幕。三位联合创始人 — [索罗门·海克斯](https://www.linkedin.com/in/solomonhykes/)、[安德里亚·卢扎尔迪](https://www.linkedin.com/in/aluzzardi/)和[塞缪尔·阿尔巴](https://www.linkedin.com/in/samalba/)、 — 都在 Docker 工作了近十年，海克斯在 2018 年离职前创立了这家公司。现在，该团队已经重新加入到构建 Dagger 的行列，根据其介绍性的博客帖子，“允许 DevOps 工程师快速构建强大的 [CI/CD 管道](https://thenewstack.io/category/ci-cd/)，然后在任何地方运行它们。”这个总结立刻让我想起了团队之前的努力。

Hykes 在接受 New Stack 采访时解释说，Dagger 解决了 DevOps 工程师面临的问题，这些问题包括必须跟上软件团队的增长、现在交付的软件规模，以及通过日益复杂的管道实现自动化的需求。

“我们确定了主要的痛点，主要的瓶颈，也就是胶水，”他说。“DevOps 工程师花了大部分时间将一堆专用工具粘在一起，而胶水本身就是问题所在。基本上是他们拼凑的剧本。它们很难测试，很难适应新的需求，很难调试，通常，你需要在不同的工具和语言之间转换，以便将它们结合在一起。我们让他们去掉胶水。相反，他们可以玩乐高来获得一套标准的组件，它们之间的标准接口，以及如何组合它们的统一模型。”

通过 Dagger，DevOps 工程师使用他们选择的语言 — 构建动作，Hykes 提供了 Python、Go、TypeScript、Ruby、Java 和 shell 脚本作为示例 — ，然后使用[提示定义](https://cuetorials.com/overview/foundations/#definitions)声明性地将它们组合在一起，提示定义描述了输入、输出、子动作以及它们之间的连接。Dagger 对 CUE 的使用超越了传统的选项，如 YAML 或 JSON，它不仅提供了描述数据的能力，还提供了逻辑能力。例如，CUE 不仅描述数据类型，而且可以强制这些类型；以及对数据的约束，例如最大值或最小值。

Dagger 唤起 Docker 记忆的部分原因是集装箱化是其方法论的核心。Dagger 通过将动作容器化，使 CI/CD 管道可以在开发人员和 CI 环境中运行。Hykes 解释说，然后使用 CUE 将这些动作拼凑在一起，创建有向无环图(DAG)。这将整个过程分为命令性动作和声明性定义，Hykes 认为这是“理想模式”。

“每一个生存时间足够长、拥有足够多用户的管道系统都开始向同一个理想模式靠拢，”Hykes 说。“我们只是从那里开始，而不是晚些时候到达那里并试图把它栓上。”

所有这些部分的组合是一个 CI/CD 管道平台，它不仅能够共享单个操作，还能够在任何可以运行容器的地方运行管道。

当我建议 Dagger 听起来有点像“CI/CD 的 Docker”时，Hykes 忍不住同意了，并警告说“有几个主要的区别”。据他估计，Docker 的一个不足之处是真正创造了一个共享的生态系统。有了 Docker Hub，用户需要相信共享的东西是安全的，因为它们是二进制文件。Dagger 的[很快就会推出名为 Dagger Universe](https://github.com/dagger/dagger/tree/main/pkg/universe.dagger.io) 的 hub，共享的片段是 CUE 文件的形式，因此它们对检查是开放的。除此之外，Hykes 还解释说，Dagger 是有意比 Docker 更开放，所有的项目开发交流都是公开的，比如在他们的 [Discord channel](https://discord.gg/ufnyBtc8uY) 上。Hykes 还表示，Dagger 比他的前公司提供了更多的平台。

“我们给你一种语言，我们给你一个 API，我们给你一个开发工具包，可以导入的包。这是真正的开发人员体验，这改变了产品的性质，因为这意味着随着社区的发展，他们实际上能够共享他们编写的一些代码，并重用彼此的代码，”Hykes 说。“Dagger 的全部意义在于，你可以安全地重用别人的动作。如果你愿意，你可以把你的管道分成动作，并与世界分享，所以这就像一个常规的代码生态系统，就像 Python 或 Go 一样。”

目前，Dagger 团队和社区正在寻求巩固该项目，该项目在 Apache 2.0 许可下可在 GitHub 上获得[，并朝着最终的 1.0 版本努力。除此之外，该团队还在考虑提供一个基于云的匕首，该匕首将提供额外的功能，如基于角色的访问控制(RBAC)或可见性。](https://github.com/dagger/dagger)

Hykes 说:“一个显而易见的唾手可得的成果是你的供应链的可见性。“你知道，谁在部署什么，在哪里部署，为什么部署。或者，反过来:现在生产中运行的是什么，它来自哪里，谁接触过它？”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>