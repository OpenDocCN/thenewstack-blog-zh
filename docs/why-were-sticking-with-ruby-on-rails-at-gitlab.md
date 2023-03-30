# 为什么我们在 GitLab 坚持使用 Ruby on Rails

> 原文：<https://thenewstack.io/why-were-sticking-with-ruby-on-rails-at-gitlab/>

当 David Heinemeier Hansson 创建 Ruby on Rails ( [采访](https://corecursive.com/045-david-heinemeier-hansson-software-contrarian/))时，他是以他在 PHP 和 Java 方面的经验为指导的。一方面，他不喜欢 Java 的冗长和僵化使 Java web 框架变得复杂和难以使用，但他欣赏它们的结构完整性。另一方面，他喜欢 PHP 最初的易用性，但不喜欢这类项目容易陷入的困境。

这些似乎是排他性的选择:你要么变得平易近人而杂乱，要么结构良好而难以使用，选择你的毒药。我们过去常常在服务器级操作系统(如 Unix)和客户端操作系统(如 Windows 和 MacOS)之间做出类似的、也同样困难的区分，前者稳定但难以使用，而后者易于使用但经常崩溃。

每个人都认为这种二分法是天赐的，直到 NeXT 在一个坚实的 Unix 基础上提供了一个漂亮、平易近人、非常流畅的 GUI。如今，“服务器级”Unix 不仅能运行漂亮的 GUI 桌面，还能运行大多数手机和智能手表。

因此，事实证明，除了历史上的偶然事件，可接近性和崩溃实际上并没有联系，web 框架中的可接近性和混乱性也是如此:它们是独立的坐标轴。

这些独立的轴在右下角开辟了一个非常理想的开放点:一个可接近的、结构良好的 web 框架。

凭借其坚实的元可编程 Smalltalk 传统和良好的 Unix 集成，Ruby 被证明是 Ruby 创始人 DHH 用 Rails 填充表格右下角的完美工具:一个极其平易近人、高效和结构良好的 web 框架。

当 GitLab 的联合创始人 Dmitriy Zaporozhets 决定从事运行他(和你)的版本控制服务器的软件时，他也有 PHP 背景。但是他没有坚持熟悉的东西，而是选择了 Rails。

Dmitry 的选择可能是有先见之明或偶然的，但它非常适合 GitLab，部分原因是 David 成功地实现了他对 Rails 的目标:良好架构的可接近性。

## 为什么模块化？

 [西德·西伊布兰迪

Sid 是 DevOps 平台 GitLab，Inc .的联合创始人、首席执行官兼董事会主席。Sid 花了四年时间为 U-Boat Worx 建造休闲潜艇，并在荷兰司法和安全部(Ministerie van Justitie en Veiligheid)从事 Legis 项目，该项目开发了几个创新的网络应用程序来帮助立法。他第一次看到 Ruby code 是在 2007 年，他非常喜欢它，以至于自学了编程。2012 年，作为一名 Ruby 程序员，他遇到了 GitLab，并发现了他对开源的热情。不久后，Sid 将 GitLab 商业化，从初创公司到全球企业，git lab 的注册用户已经超过 3000 万。](https://www.linkedin.com/in/sijbrandij/) 

在前面的部分中，假设模块化是一个理想的属性，但是正如我们也看到的，仅仅假设事情是危险的。那么，为什么，在什么情况下，模块化实际上是可取的？

在他 1971 年的论文“[关于将系统分解成模块的标准](https://prl.ccs.neu.edu/img/p-tr-1971.pdf)*”*中，大卫·l·帕纳斯给出了模块化系统的以下(期望的)好处:

*   开发时间应该“被缩短，因为独立的小组将在每个模块上工作，几乎不需要交流。”
*   应该有可能“在不改变其他模块的情况下，对一个模块进行剧烈的改变或改进。”
*   应该可以一次一个模块地研究系统。

Fred Brooks 后来在“[神话中的人月](https://en.wikipedia.org/wiki/The_Mythical_Man-Month)”中强调了减少沟通需求的重要性，额外的沟通开销是老话“在一个晚的软件项目中增加人员会使它更晚”的主要原因之一

## 我们不需要微服务

模块化通常是难以捉摸的，因为它非常受欢迎，大多数系统的默认架构是[大泥球](http://laputan.org/mud/)。因此，可以理解的是，设计师们从现存最大的软件系统中获得了灵感:万维网，它必然是模块化的；它不能以任何其他方式发挥作用。

使用单独的进程组织本地软件系统，使用 [REST](https://www.ics.uci.edu/~fielding/pubs/dissertation/fielding_dissertation.pdf) 架构风格组合的微服务，确实有助于通过操作系统加强模块边界，但成本很高。这是实现模块化的一种非常笨拙的方法。

运行现在的免费分布式系统的困难和成本是巨大的，一些性能和可靠性问题记录在众所周知的分布式计算的[谬论](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)中。简而言之，性能和可靠性的成本是巨大的，因为耗时纳秒且从不失败的函数调用被慢三到六个数量级且确实失败的网络操作所取代。如果必须在几乎没有工具支持的情况下跨多个服务跟踪故障，那么故障将变得更加难以诊断。

您需要一个相当复杂的 DevOps 组织来成功运行微服务。无论如何，如果你在一个需要复杂程度的规模上运行，这真的没有什么不同，但是很可能你不是谷歌。

但是，即使你认为你可以管理所有这些，重要的是要注意，所有这些偶然的复杂性是在你的问题的原始本质复杂性之上的；微服务无助于降低复杂性。即使是所希望的模块化改进也没有丝毫保证，通常发生的情况是你得到一个[分布式泥巴球](http://www.codingthearchitecture.com/2014/07/06/distributed_big_balls_of_mud.html)。

## 单轨铁路

通过让好的架构变得可接近和高效，Rails 允许 GitLab 开发一个[模块化的整体](https://medium.com/@dan_manges/the-modular-monolith-rails-architecture-fb1023826fc4)。模块化的整体与分布式的泥巴球正好相反:一个结构良好、架构良好、高度模块化的程序，作为单个进程运行，并且尽可能地[乏味](https://about.gitlab.com/handbook/values/#boring-solutions)。

尽管将 GitLab 构建成一个整体对我们来说非常有益，但我们并不教条地看待这种结构。建筑遵循需求，而不是相反。虽然 Rails 对于我们的目的来说是一种优秀的技术，但是它也有一些缺点，其中之一就是性能。幸运的是，大多数代码库中只有一小部分是性能关键的。我们使用自己的用 Go 编写的 [gitaly](https://docs.gitlab.com/ee/administration/gitaly/) 守护进程来处理实际的 git 操作，使用 [PostgreSQL](https://thenewstack.io/two-sizes-fit-most-postgresql-and-clickhouse/) 来处理非存储库持久性。

## 开放式核心

最后但同样重要的是，我们的模块化整体将我们的开放核心商业模式从美好的理论变为现实。尽管 Rails 本身并不能实现这一点——那将是我们出色的贡献者和工程师——但它确实奠定了适当的基础。

为了获得开源的真正好处，贡献者必须能够获得可用的源代码。为了在面对来自各种来源的贡献时保持体系结构的完整性，并在开放和封闭组件之间保持一条清晰的分界线，代码必须具有良好的结构。听起来熟悉吗？

有一个合适的插件接口不是更好吗？或者更好的是，以微服务为模型的服务接口？一句话:不。这些方法不仅强加了部署和集成的障碍，远远超出了“我对源代码做了一个小的改动”，它们经常过于严格地强制架构约束。预测所有未来的扩展点是一件徒劳的事情，幸运的是我们没有着手去做，也没有必要去做。

通过我们枯燥的模块化整体，用户和其他第三方开发者可以并确实为核心产品做出贡献，给我们带来巨大的杠杆作用，以及无与伦比的创新速度和可扩展性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>