# 黄金路径从左移开始

> 原文：<https://thenewstack.io/golden-paths-start-with-a-shift-left/>

“左移”的概念与现代应用程序开发实践和哲学密不可分，如测试驱动开发、黄金路径和 DevOps，以及平台设计原则，如高级自动化、安全供应链和 GitOps。出于本文的目的，我们将定义“左移”的含义，就好像我们正在向一个对应用程序开发和交付过程一无所知的人解释它一样。

一般来说，左移意味着在制作软件的过程中更早地添加一个任务。在应用程序开发中，这应该意味着在过程的早期实现**结果**。不幸的是，自从进入现代开发术语以来，[左移经常导致团队将**决策**转移给开发人员](https://www.youtube.com/watch?v=91rtD9Os9Aw?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)。这可能看起来是一个微妙的区别，但是把错误的东西转移到左边会产生真正的问题。

向左转移结果的一个重要好处是，它有助于保持开发人员的生产力。当开发人员能够在流畅的状态下工作时，生产力就会提高。心理上下文切换是许多开发人员存在的祸根，当开发人员被迫在工作流程中做出决策和移交时，它会成为一种不受欢迎的干扰。上下文切换不仅增加了认知负担，更重要的是，它扰乱了开发人员的[流程状态，](https://www.youtube.com/watch?v=4NPArs4eR3c?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)这是任何实践一门手艺的人都觊觎和珍惜的东西，而编写代码**是**一门手艺。

这些年来，“左移*”*已经成为更早地将(通常)安全性纳入应用程序开发和交付过程的战斗口号。但是安全并不是左移有潜在好处的唯一领域。事实上，人们可以说[测试驱动开发](https://tanzu.vmware.com/content/blog/tanzu-application-platform-supports-developers-shift-left-testing?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)是左移的最早表现形式之一，因为它确保代码在整个过程中得到测试。因此，开发人员不必在花了几天、几周或几个月的时间编写代码后，再把它们送去测试。测试成为流程的一部分。

那么，当我们说向左移动是关于结果的时候，我们指的是什么呢？让我们再来看看安全性，因为现在这仍然是左移模型最流行的用法。尽管安全是一个有价值的结果，但作为一个结果，它过于宽泛和包罗万象，不切实际。将安全之类的东西分解成具体的或更离散的结果是一种更实际、更可持续的方法。

> 安全并不是左移有潜在好处的唯一领域。

作为一个例子，[安全软件供应链](https://tanzu.vmware.com/content/blog/ci-cd-software-supply-chain-enterprise-path-to-production?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)是一个特定的结果，就其本质而言，意味着支持开发者流和更好的开发者体验。沿着太阳风公司的黑客路线，以软件供应链深处为目标的攻击可以使 CVE 无法被流程/循环结束时进行的安全扫描检测到。然而，如果供应链安全是结果，我们可能实现密封的构建。重要的是，应用程序开发平台和工具不应给开发人员带来负担。理想情况下，你的平台让你[执行政策而不阻碍创新](https://tanzu.vmware.com/content/analyst-reports/innovation-insight-for-internal-developer-portals?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)。

漏洞意识是安全性的另一个不同结果。为了使漏洞意识有用，它需要与安全实施分开。虽然这可能看起来违反直觉(为什么你不想马上处理这个问题？)，它最终保留了心理语境。当我们将意识转移到左边时，我们让开发人员知道他们的代码与规定的策略相冲突，不会通过下一个门。这并没有阻止开发人员执行策略，策略可以覆盖从使用哪个容器映像版本到最后一次映像扫描的最小天数的任何内容。

另一个将意识和执行分开的例子是没有解决方案的新 CVE。当安全团队进行修复时，开发团队可以继续编写他们的代码，直到修复可用并且他们必须实现它。我们知道，心理环境的转换是以生产力和快乐为代价的，通过将意识与执行分离，开发人员可以保持这种环境，并最终保持他们的生产力。

同样，让我们看看应用程序性能或漏洞数据。我们可以说我们正在向左移动可观察性，但是可观察性不是一个结果。[可操作的应用程序数据](https://www.youtube.com/watch?v=4dg7jJDo9tU?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)是结果，应用程序层的轻量级可观察性是我们能够将其左移的方式。与我们谈论[可观察性时可能想到的不同](https://tanzu.vmware.com/content/analyst-reports/magic-quadrant-for-application-performance-monitoring-and-observability?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS3)，应用程序层可观察性让开发人员可以快速查看他们的应用程序如何运行，并帮助查明问题，以便他们可以在自己方便的时候进入并处理问题。

> 当向左移动时，以结果为导向可以保持开发人员流动，为生产铺平道路，增强安全性并释放创新。

另一个可以并且应该在开发过程中更早发生的结果是 API 评分和验证，这对任何认为自己是 API 优先的团队来说都是至关重要的。在这种情况下，我们可以看到工程师和开发人员如何在编写第一行代码之前对他们的 API 进行评分或验证。通过将评分和验证留到最后，团队可能已经花费了许多周期来设计和构建 API，结果却在注册过程中被拒绝。如果开发人员和开发团队在过程的开始就已经知道他们的组织对于 API 设计的必备条件，那么效率会高得多。

这些只是早期的例子，说明了在左移时以结果为导向如何能够更好地保持开发人员流动，为生产铺平道路，支持您的安全态势并释放创新。

在这篇文章的开头，我提到了黄金路径，我也想以此结束。自从 [Spotify 在 2020 年](https://engineering.atspotify.com/2020/08/how-we-use-golden-paths-to-solve-fragmentation-in-our-software-ecosystem/)引入这个想法以来，黄金路径已经在平台工程团队、业务线领导和应用程序开发团队中获得了很多关注，因为它们减少了开发人员生产过程中的摩擦。最基本的是，黄金路径为开发人员提供了一条简化的生产路径，受到他们的基础设施和运营、安全和平台工程团队的支持。黄金路径要想有效，就必须坚持左移原则。

然而，它们应该代表对决策和过程的信任的顶点，不仅仅是对创建它们的团队，也是对使用它们的开发人员。专注于深思熟虑、负责任地改变遗留结果的组织，将会设计出一条适合所有人的黄金之路。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>