# Cerner 如何利用 Concourse 的 CI 平台来管理环境

> 原文：<https://thenewstack.io/cerner-uses-concourses-continuous-integration-platform-regulated-environments/>

当 12 月初参加 SpringSource Platform 会议的其他与会者在那里听到企业 Java 的承诺时，更广泛适用的讨论也在进行。来自医疗保健系统集成商 [Cerner 公司](https://www.cerner.com/)的 [Greg Meyer](https://www.linkedin.com/in/gregmeyerhealthit/) 和 Bryan Kelly 做了这样一个演讲。两人讨论了他们在高度管控的环境中使用 [Concourse](http://concourse-ci.org/) 持续集成平台的情况。

Cerner 采用 Concourse 进行持续集成的旅程始于一个问题陈述:根据需要经常正式创建和部署高质量的代码。这听起来像是适用于任何团队的通用声明，但是这背后隐藏的问题来自于与他们的行业相关的治理和监管:医疗保健。

Meyer 说，Cerner 不仅作为一家医疗保健公司受到高度监管，而且它还通过了 ISO 9000 认证，这意味着它必须为它所做的一切制定清晰简明的政策和程序，包括软件开发。“我们的开发人员总是觉得他们遇到了有人告诉他们停下来，”Meyer 说。

Meyer 说，为了解决这个问题，团队“彻底改变我们看待开发过程以及这些过程与 ISO 过程的关系的观点。事情开始更加紧密地联系在一起。一旦完成，我就去做一个黑盒测试，也许这会自动启动一些东西，以制作一个工件来获得签署，然后它会返回到软件开发过程，等等。”

Meyer 说，许多团队将持续集成(CI)和持续部署(CD)视为独立的过程。在 CI 方面进行构建和测试之后，许多开发人员简单地将代码扔给 CD，然后与流程的其余部分隔离。

“很多时候，开发和运营之间的唯一沟通是通过 JIRA 的请求和票证:他们把他们的最终状态踢过墙，而我们进入 CD，”Meyer 说。

Meyer 说，为了帮助弥合开发和运营之间的差距，团队采用了 Concourse。“Concourse 是一种工具，它将软件开发、CI 和 CD 贯穿于从编码、取出到投入生产的整个过程。还有其他类似的工具，比如[詹金斯管道](https://jenkins.io/doc/book/pipeline/)。Concourse 做事情的方式非常短暂。构建作业启动一个虚拟机，完成它的工作，然后丢弃它。如果你曾经不得不管理詹金斯盒子，你会花 20%到 30%的时间来管理詹金斯盒子。所有这些都将随着 Concourse 而消失，”Meyer 说。

“这些管道是声明性的，用 YAML 语言编写。Concourse 有资源、工作和任务。资源是源代码存储库，或者最终状态以及它们的去向: [Artifactory](https://www.jfrog.com/artifactory/) ，或者类似 [Cloud Foundry](https://www.cloudfoundry.org/) 的东西，或者一个实例可以是资源。Meyer 描述了 Concourse 的内部工作方式，他说:“作业对这些资源起作用，任务是作业内部的实现细节。

“在这样一个完整的系统中，Concourse 在自动转移代码方面效率极高。“你可以像这样做 10 个或数百个部署，”迈耶说我们有五个环境来移动东西。Concourse 有一个很酷的东西，那就是 YAML 内部的分组机制。使用组，我们可以在逻辑上分割管道的各个部分。现在，您可以确定管道的所有部分在哪里。"

Meyer 表示，法规和治理严重限制了 Cerner 推动生产变革的频率。“我们被迫采用累积节奏的方法。我们只能偶尔发布产品。在我们把东西搬进去之前，我们必须在流程中提前两周发出通知。有一个节奏是做 CI/CD 的对立面，但现在，它就是这样。”

“我们已经在[亚马逊网络服务](https://aws.amazon.com/)和 [Pivotal Cloud Foundry](https://pivotal.io/platform) (PCF)上做了一个新的解决方案，现在我们不必担心单调的方法。我们可以通过微服务获得更多的流动性。我们的流程变得更加简化。我们从一个版本开始，构建并测试它。在它被部署到后端之后，如果不错的话，我们就转移到 QA，构建它，然后交付生产，”Meyer 说。

“你希望这些东西成为彼此的副产品。在 Concourse 中，您可以做的最酷的事情是，所有这些 ISO 流程都可以成为另一种资源。它根本不会改变管道。当我们进行集成测试时，我们可以在 JIRA 或 Confluence 中启动一些东西，这些东西可以向适当的人发送电子邮件。当他们签字同意时，我们有一个 Webhook，它在管道中被拾取，并将其移动到 QA。之后，它会启动另一个工件，需要有人签字同意，”迈耶说。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>