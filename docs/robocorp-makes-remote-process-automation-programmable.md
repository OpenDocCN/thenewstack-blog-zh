# Robocorp 使机器人过程自动化可编程

> 原文：<https://thenewstack.io/robocorp-makes-remote-process-automation-programmable/>

作为一名从事测试自动化工作的软件工程师， [Antti Karjalainen](https://twitter.com/aikarjal?lang=en) 看到了它与[机器人流程自动化(RPA)](https://thenewstack.io/what-is-robotic-processing-automation/) 的相似之处，在这项技术中，机器人承担日常任务，如点击通过批准保险索赔的流程。

尽管这项技术已经存在多年，但很少有 RPA 项目真正投入生产。事实上，T4 对 4000 名全球高管的调查发现，只有 8%的人表示已经大规模部署了自动化。

根据 Karjalainen 的说法，问题的一部分是市场上制造机器人的专有工具的限制，许可证的费用以及现有工具对开发者不友好。

他和联合创始人 [Teppo Koskinen](https://www.linkedin.com/in/teppo-koskinen/?originalSubdomain=fi) 、 [Jouko Ahvenainen](https://www.linkedin.com/in/joukoahvenainen/) 和 [Sampo Ahokas](https://www.linkedin.com/in/sahokas/?originalSubdomain=fi) 创建了 [Robocorp](https://robocorp.com/) 来解决这些问题。

他们在 Robocorp 网站上断言:“远离发展的人们给了我们昂贵、锁定和脆弱的嗡嗡声抑制器。”“没有公开性。没有分享知识的地方，没有学习的中心，没有社区意识或相互学习。我们都被束缚在公司的磨刀石上。”

### 自动化日常工作

“当我们开始的时候，我们看了一下 RPA，并且[看到]对公民开发者、对低代码类东西的高度重视，你知道，你的会计师可以在他们自己的例程中以自动化的方式使用这些产品。但那并没有真的发生。当我们实地查看细节时，我们没有看到这种公民开发者模式实际工作的很多实例。所以我们认为事实并非如此。一定会有这类 RPA 开发人员出现，我们应该建立专门为他们服务的实践，”Karjalainen 说。

RPA 适用于广泛的使用案例，并已用于自动化从电梯到大型机终端到动态 web 应用程序的任何东西。机器人可以接管日常任务，如点击工资单或医疗保健等业务流程[收入循环管理](https://robocorp.com/blog/robocorp-partner-implements-healthcare-automation-solution/)，让员工有时间从事更高价值的任务。

Cognizant 预测，从现在到 2023 年，进行常规和复杂决策的自动化将增长约 50%，人工智能、分析和 RPA 将结合起来，形成更智能的流程自动化形式。

ClearBridge Investments 是专利竞争对手 UiPath 的投资者，它认为 T2 市场目前价值 600 亿美元，并预测到 2030 年将增长到 2000 亿美元或更多。

这是一个拥挤的市场，有[供应商](https://www.gartner.com/doc/reprints?id=1-26YXUBYH&ct=210729&st=sb)，包括微软、Blue Prism 和 Automation Anywhere，以及[开源解决方案。](https://enterprisersproject.com/article/2020/4/rpa-robotic-process-automation-6-open-source-tools)

### 可编程 RPA

Robocorp 团队开始使建造机器人的过程可编程，他们的技术基于[机器人框架](https://github.com/robotframework/robotframework)，这是一个用于验收测试、验收测试驱动开发和 RPA 的开源自动化框架。该框架独立于操作系统和应用程序。使用纯文本语法，可以用基于 Python 或基于 Java 的库来扩展它。开放式 API 支持无数库和持久数据存储之间的通信。

用户可以在 [Robocorp Lab](https://robocorp.com/docs/developer-tools/robocorp-lab/overview) 或 [Visual Studio code](https://robocorp.com/docs/developer-tools/visual-studio-code/extension-features) 中使用 Robot Framework 或 Python 或两者来构建软件机器人，然后在控制室中编排它们。Robocorp Lab 是基于 [Conda](https://docs.conda.io/en/latest/) 的虚拟 Python 环境，是一个开源的包管理系统和环境管理系统。它具有语法高亮、代码完成、项目管理、调试以及容器和 Kubernetes 环境。

Robocorp Lab 为您的每个机器人创建了一个单独的 [Conda](https://docs.conda.io/en/latest/) 环境，使您的机器人及其依赖项与其他机器人和您系统上的依赖项隔离开来。这使您能够控制每个机器人所需的依赖项的确切版本。

它提供了 [RCC](https://github.com/robocorp/rcc) ，一套允许你创建、管理和分发基于 Python 的自包含自动化包的工具，以及用于构建和共享自动化的 [robot.yaml](https://robocorp.com/docs/setup/robot-yaml-format) 配置文件。

[控制室](https://robocorp.com/products/control-room)提供了一个仪表板来集中控制和监控跨团队、目标系统或客户的自动化。它提供了扩展安全性、治理和控制的能力。控制室有两个选项:云版本和用于私有云或内部部署的自我管理版本。

根据 Karjalainen 的说法，该平台允许用户用 Python 编写扩展或定制，这是专有系统的一个限制，并通过人工智能、机器学习、光学字符识别或自然语言理解的第三方工具来扩展自动化。

Karjalainen 说，基于云的系统允许你使用开源工具创建一个机器人，将其打包，然后将其分发到基本上任何平台上。想要在本地运行机器人的企业将安装一个代理软件。您可以重复使用和重新调整机器人的用途，以减少开发成本和上市时间。它还专注于基于使用的定价，而不是许可证。

### DevOps 焦点

他说，大多数 RPA 工具都是在 devo PS practices 兴起之前构建的，当开发人员谈论通过 GitHub 进行原生版本控制集成、持续集成以及在生产中自动或更新机器人的能力时，他们会感到兴奋。

他说，该平台的一个关键优势是能够解决经常困扰机器人的脆弱性。

因此，通常情况下，你会在自动化应用程序的最表层记录和回放用户操作。这导致了非常脆弱的机器人，一旦有变化就会崩溃。我们的技术允许您更深入地了解自动化，不仅可以访问表层，还可以访问 API，即数据层。我们称之为最佳路径自动化，它允许你在每一步……总是利用最健壮的方式来建立自动化，”他说。

[据首席执行官](https://www.thoughtfulautomation.com/) [Alex Zekoff](https://twitter.com/alexzekoff?lang=en) 称，面向中端市场公司的劳动力机器人即服务供应商 thinking Automation是 Robocorp 的早期接入合作伙伴，它很快发现专有 RPA 供应商的许可模式使其业务在财务上难以为继。

他的团队希望拥有自己的设计决策，并喜欢 Robocorp 支持更复杂需求的能力，而不是要求规定性的构建方式。他们不必管理服务器和其他基础设施；都只是自动化作为代码。泽科夫说，他的团队已经将机器人 T1 的建造时间缩短了一半，并计划进一步缩短。

总部位于旧金山的 Robocorp 在 6 月份宣布了由 Canvas Ventures 牵头的 2100 万美元的首轮融资，使其总融资额达到 3260 万美元。它还在其发源地赫尔辛基设有办事处。

“从 IT 组织到首席执行官和业务职能部门，对机器人流程自动化改变未来工作的能力的认识正在迅速增加。Canvas Ventures 的 [Grace Isford](https://www.linkedin.com/in/graceisford/) 在谈到这笔投资时表示:“大多数 Robocorp 客户在几周内以很低的价格构建并部署了机器人，这是对昂贵的许可证和现有解决方案实施时间的一个重大改进。”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>