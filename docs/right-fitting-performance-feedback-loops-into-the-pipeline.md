# 将“合适的”绩效反馈循环纳入管道

> 原文：<https://thenewstack.io/right-fitting-performance-feedback-loops-into-the-pipeline/>

[](https://www.linkedin.com/in/paulsbruce/)

[Paul Bruce](https://www.linkedin.com/in/paulsbruce/)

[Paul 是 Tricentis 公司 NeoLoad 的客户工程总监和 DevOps 顾问，帮助改造企业软件团队和交付实践。他组织了波士顿 DevOpsDays，波士顿 DevOps 社区，并主持了 o11yfest。您可以在以下网址了解更多信息:https://pauls Bruce . io .](https://www.linkedin.com/in/paulsbruce/)

我们想要什么？绩效反馈！我们什么时候想要它？看情况。

你交付软件的速度越快，反馈循环就变得越重要。有效地实现反馈循环的自动化方法就是要恰当地适应谁/什么/何时/何地的方面。通常，自动化反馈循环存在于管道和持续集成(CI)中。但是性能测试呢？适应 DevOps 和自动化上下文是不是太复杂了？

简而言之，当然不是。但这需要一点工程思维，并首先设定正确的目标。为什么性能工程师需要流水线驱动的性能反馈？几个确凿的理由:

*   在产品和特性生命周期的早期解决明显的错误通常更便宜。
*   长周期引入了延迟和上下文切换，这增加了出错的可能性。
*   自动化反馈要求我们从流程中剔除不必要的差异。
*   获得反馈有助于我们时刻做出更明智的决定。
*   频繁生成性能数据使我们能够了解一段时间内的趋势，而不仅仅是“大爆炸”点样本。

传统的负载测试和性能测试主要集中在大型复杂的完整预发布系统的端到端测试上。大多数自动化构建和打包周期只需要几分钟，而不是几小时，所以从时间的角度来看，传统的性能测试周期并不适合交付周期。端到端测试还有必要吗？是的。这个过程有必要继承我们本可以更早解决的缺陷、错误、反模式和错误假设吗？绝对不行。

智能方法需要将负载和性能测试“恰当地安装”到自动化管道中，因此我们可以获得可操作的早期信号(即反馈循环)。从工程师的角度来看，为了避免端到端后期验证的混乱，我们需要将性能验证过程分解成有意义的更小的反馈循环，以适应更短的工作周期。通过这种方式，开发人员和团队可以更早、更频繁地收到关于他们的变更的性能反馈，这样当我们进行端到端测试时，就不会发生火灾。

## **负载和性能测试现代化的 3 大挑战**

那么，从传统的性能测试迁移到现代自动化方法的主要障碍是什么呢？

*   **并非所有的系统和组件都是平等的，**因此没有一种方法可以全面适用。早期和晚期测试的适用性和候选资格需要讨论；选择正确的目标并应用渐进的测试策略。
*   **你做某件事越频繁，那些“棘手的部分”就会积累成大量的工作，除非自动化。特别是对于负载测试，基础架构、数据和环境的手动预配置通常需要花费大量时间。**
*   如果我们只是偶尔做一件事，会比经常做要花费更多的努力。脆弱的环境、脆弱的测试脚本、不同步的数据……因为我们没有持续地使用它们，所以我们解决这些问题的能力没有提高。

一个合适的性能测试工具带包括许多继承这些挑战的实践:负载测试(例如，模拟真实条件)、监控、模拟/虚拟化、测试数据管理/净化、经验采样等等。我工作过的大多数企业都已经部分或完全自动化了其中的许多组件，借助于像 Delphix、Mockiato、Tricentis NeoLoad、Grafana 和 Selenium 这样的工具。好消息是，当自动化这些方法时，没有什么是不可克服的；拥有一个坚实的愿景和方法可以调整和组织我们的工作。

## **自动化连续性能和负载测试**

很容易说测试自动化的目标是“走得更快”或者“加速交付”当它可靠地工作并产生可操作的结果时，这是适用的，但是达到“可靠”和“可操作”需要的不仅仅是负载测试工具。这就像 DevOps 的“人员、流程、技术”维恩图。如果你只是在解决问题的一个方面，你并没有真正解决整个问题。那么我们如何解决持续负载和性能测试中涉及的“人”和“过程”元素呢？

进入自动化。流程自动化让我们能够以一种机器可以代表我们执行的方式来阐明我们的目标、需求和活动。它揭示了我们在流程、技术和技能方面的差距，这是一件好事。我们需要知道我们的差距，以便恰当地解决它们。

为了自动化性能测试，产生有意义的和可操作的结果，人们需要就目标和结果进行交流。预先讨论 SLA、SLO 和 SLIs 是“左移”性能实践的一个重要部分。应该有某种性能标准接收过程。它可以是关于性能测试应该针对的系统和时间框架的简单的表格或问卷。目标是帮助产生基线自动化工件，如 SLA 定义和 API 测试细节。

当您将这些工件组合到一个管道中时(即我们的“过程”)，您还必须自动化负载基础设施供应/取消供应过程，以便您可以运行与被测系统(SUT)完全隔离的负载测试。Containers 和 Kubernetes 在提供基于标准的自动化基础设施方法方面取得了长足的进步，但是总有一百万种其他方法来管理这些资源。无论您采用什么配置策略，团队运行测试都不应该是复杂的。必要时获得反馈的自主权是加速交付的关键因素。

## **如果你的绩效实践没有自动化，你将会失败**

最后，自动化不应该只为单个团队服务。在更大的组织中，如果这只是局部的效率(对于一个性能卓越中心团队来说)，那么这种工作就没有力量倍增器。相反，许多团队可以使用的自动化，即使他们不是设置它的专家，也是真正帮助组织走得更快的。

在 DevOps 中，性能和可靠性工程的工作不仅仅是运行测试或者分析和整合结果。它为产品团队提供了一种自己完成这些事情的方法，同时还提供了围绕这些过程的安全防护栏和“良好实践”,因此团队可以随着时间的推移发展他们自己的绩效能力。

我看到许多成熟的大规模绩效实践已经从“绩效团队是一种孤立的服务”的心态转变为“绩效流程是一种自助服务”的方式。一个原因是，没有办法通过增加更多的全职人员来将“人”的绩效专长扩展到数百个团队。但主要是因为我们现在可以将我们的性能测试实践正式化(即自动化)到工作中，机器帮助完成繁重的工作。

从许多方面来说，适当地自动化您的负载测试实践“带来了痛苦”,并对组织加速交付的愿望带来了压力。我们需要重新思考传统做法，继承其有益的智慧，并适应当今的限制和挑战，而不是抛弃传统做法的反思方法。

## 我们将何去何从？

尽早且经常以较小的量运行性能测试是在管道中建立“合适的”自动化性能反馈循环的关键。以 API 为目标，从小处着手，建立自信和能力。

在我的[连续性能测试实用指南](https://www.tricentis.com/resources/practical-guide-continuous-performance-testing/)中，详细介绍了关于为成功过渡到自动化连续测试方法奠定基础的实用操作指南——包括优先化自动化内容的策略、开发专用性能管道的最佳实践、克服测试基础设施障碍以及确保可信赖的通过/不通过决策。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>