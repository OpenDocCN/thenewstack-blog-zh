# 无服务器和工作流:现在和未来

> 原文：<https://thenewstack.io/serverless-and-workflows-the-present-and-the-future/>

[](https://stackstorm.com/)

[Dmitri Zimine](https://stackstorm.com/)

[Dmitri Zimine 是 StackStorm 的创始人兼首席技术官，stack storm 是一个受 DevOps 启发的开源事件驱动自动化平台。过去，Dmitri 领导团队设计和构建面向云和数据中心的软件，包括 VMWare vSphere、Opalis Integration Server(现为 Microsoft System Center Orchestrator)和 Mistral(open stack 工作流服务)。在 Extreme Networks，Dmitri 推动战略创新，促进开源贡献。他目前热衷于无服务器、DevOps 自动化、边缘计算和物联网。](https://stackstorm.com/)

[](https://stackstorm.com/)[](https://stackstorm.com/)

无服务器驱动工作流的回归。主要的云都有类似的产品，有些 nits 做的比其他的更好。但是仍然需要编排跨云应用程序。

三年前，我写了一篇文章“工作流的回归”，描述了当时 DevOps 的需求:多步自动化过程的更高层次的编排和协调。现在我们见证了新一代的工作流工具，这一次的驱动力是无服务器的。

## 无服务器需要工作流吗？

无服务器架构不是基于事件的吗？是的，他们通常是。当谈到驯服低延迟的无限数据流时，函数式编程、事件流和事件源是完成这项任务的最佳工具。

然而，只有少数解决方案成长为真正的事件采购，并实现了“事件回复”天堂的令人信服的承诺。更多情况下，问题更简单:以特定的顺序协调对少数函数和 API 端点的一系列调用，在调用之间传递数据，并保持状态。对这类问题误用基于事件的编程[使得解决方案难以推理、难以调试](https://speakerdeck.com/jboner/how-events-are-reshaping-modern-systems?slide=25)，并且经常导致反模式，比如将调用和数据转换逻辑分散到函数的代码中。

工作流正好适合这里，因为它们擅长三个关键需求:编排逻辑，在任务之间传递数据，以及保持清晰、透明的操作状态。

在无服务器中，工作流不会取代基于事件的架构，而是在合适的地方对其进行补充。典型的例子 Nordstrom 的规范无服务器事件源“Hello Retail”使用工作流来协调逻辑顺序和解决方案大部分的状态。

不足为奇的是，所有三大云都争相引入工作流即服务产品。

## 微软 Azure 先来了

微软 Azure 第一，有 [LogicApps](https://azure.microsoft.com/en-us/services/logic-apps/) 。通过[工作流基金会、](https://msdn.microsoft.com/en-us/library/jj684582.aspx) [系统中心协调器](https://docs.microsoft.com/en-us/system-center/orchestrator/learn-about-orchestrator?view=sc-orch-1807)和 [Powershell 工作流](https://docs.microsoft.com/en-us/system-center/sma/overview-powershell-workflows?view=sc-sma-1807)利用其在工作流管理方面的专业知识，微软实现了在 LogicApps 之前被认为不可能的事情，吸引了开发人员和非开发人员。它有一个图形化的工作流编辑器，并由基于 JSON 的坚实的[工作流定义语言](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-workflow-definition-language)的程序员天堂提供支持，但具有在任务之间发送数据的强大功能，更不用说 150 个现成的连接器来集成“一切”。

亚马逊网络服务随后推出了 [StepFunctions](https://aws.amazon.com/step-functions/) ，放弃了不那么简单的[简单工作流服务](https://aws.amazon.com/swf/)。对市场的急于求成导致了低劣的操作体验:例如，您希望在修改工作流时丢失执行的历史记录吗？但是它的基础—[Amazon State Language](https://states-language.net/spec.html)—是坚实、简单和简洁的，具有出色的数据引用功能和丰富的重试和捕捉错误处理功能。这种简单是有代价的:不支持分支和连接等高级工作流模式，只支持顺序和并行块。

谷歌终于加入了这个团伙，放弃了“不是在这里发明”的态度，并采用开源的 [AirFlow](https://airflow.apache.org/) 工作流引擎来提供谷歌云平台、 [Cloud Composer](https://cloud.google.com/composer/) (这个名字让人想起 [Extreme Workflow Composer](https://www.extremenetworks.com/product/workflow-composer/) ，另一个基于 [OpenStack Mistral](https://docs.openstack.org/mistral/latest/) 的工作流自动化工具)。AirFlow 长期以来一直是工作流专家的首选，拥有用于工作流定义的 Pythonic 域特定语言(DSL)、围绕有向无环图(DAG)的良好架构、操作和挂钩的可扩展性，以及 XCom——Google 对跨任务通信工具的昵称(几乎没有记录，但足够了)。你可以在这里找到一个很好的[气流概念概述](https://medium.com/@dustinstansbury/understanding-apache-airflows-key-concepts-a96efed52b1a)。

也有一些新的更小的工作流项目，比如来自 Fn 项目的[流，或者来自我们自己的](https://github.com/fnproject/flow) [StackStorm](https://github.com/StackStorm/st2) 的[或 questra](https://github.com/StackStorm/orchestra) 。

## 对于无服务器—他们都能完成工作

正如您所看到的，这些工作流引擎在它们支持的工作流原语、操作便利性、它们可以进行的调用种类以及扩展它们的容易程度方面有很大的不同。他们在许多微妙的方面有所不同。但是它们有一个共同点:它们被赋予生命来连接无服务器架构。说到无服务器:通过一些开发工作和独创性，他们都可以完成工作。值得关注的两个方面——定价和对解决方案体系结构的影响。

在定价上，AWS StepFunctions 和 Azure LogicApps 是可比较的:它们以状态变化/函数调用来计量使用。一些人认为单位价格太高了——比 FaaS 高 100 倍。更令人担忧的是:正如 Ben Kehole 指出的那样，价格和使用限制让我们对这些工作流即服务(WFaaS)产品的用途感到困惑。至于 Google Cloud Composer，它的定价完全不是基于调用的:它基于运行底层气流所需的 IaaS 资源进行计量。这可能会剥夺 Cloud Composer 佩戴无服务器徽章的资格:无服务器，[根据一个定义，](https://medium.com/@PaulDJohnston/a-simple-definition-of-serverless-8492adfb175a)是在没有人使用的情况下运行起来不需要任何成本的东西。

对架构的影响表现为解决方案利用了一些工作流特性，或者解决了缺少 if 的问题。例如，LogicApps 支持带有“for_each”关键字的[“多实例数据”工作流模式](http://www.workflowpatterns.com/patterns/data/visibility/wdp4.php)，因此可以在工作流级别处理数据数组。StepFunction 没有对它的支持，这将处理数组的责任推到了解决方案级别，或者推到了 Lambda 函数中。

让我们面对现实:尽管工作流产品在功能上有所不同，但它们的优缺点——甚至它们的价格——都不会成为您选择云提供商的决定性因素。恰恰相反:您可能会使用来自您已经选择的云的 WFaaS，享受其优点并吸取其缺点，就像我们总是对 PaaS 所做的那样。除非你想反抗，用你自己的方式去做，用在任何云上，甚至是跨越云的方式去做。

## 多云？

多云是现实吗？有人说已经来了。但是从在不同的云上拥有账户到生产跨云解决方案充分利用最好的云服务还有很长的路要走。无服务器功能是将服务和平台粘合在一起的一种方式，但仅靠 FaaS 是不够的。

感受到这种需求，[Serverless.com](http://serverless.com)推出了事件网关来促进事件源，以促进跨云无服务器解决方案。在这种解决方案成为现实的情况下，我相信也有跨云工作流即服务的空间，以在需要时提供简单的编排和状态管理。如果发生这种情况，Gartner 将把它命名为 XCloud WFaaS，有人可能会在它上面出名并赚几个钱。当这个空间仍然空着的时候，在此期间有什么选择？

**1)选择一个 WFaaS 来编排所有云。**在你的云中找出 API 漏洞。选择哪一个既经济又有技术含量。从技术上来说，Azure LogicApps 可能更强大，或者 Workflow Composer 因其开源根源而具有吸引力。然而，从经济上来说，在云中调用函数很便宜，但是 AWS API 网关调用的费用很高；如果您的大多数调用都在 AWS 内部，您可能不喜欢 AWS 账单上的 AWS API 网关行。(这不是工作流与事件的问题，而是跨云障碍:事件网格的潜在用户面临同样的挑战)。

**亲自策划。**获取工作流库，构建您自己的无服务器工作流解决方案。如果这听起来像是自己托管 AirFlow，其实不是，我将再次强调“无服务器”和“库”以突出区别。一个解决方案将使用 FaaS 本身——从这里得到提示[并依赖于可以嵌入代码的开源工作流库，而不是作为服务推出。挑什么库？如果你仍然容忍操作中的 Java(如果你正在阅读新的堆栈，这是不太可能的)，看看](https://read.acloud.guru/some-lessons-learned-about-lambda-orchestration-1a8b72a33fd2) [Activiti](https://www.activiti.org/documentation) ，抛弃可怕的 BPEL 部分，并确保将它用作一个库。或者看看 StackStorm 的[或 questa](https://github.com/StackStorm/orchestra) 工作流库，把它作为无服务器本身运行(在旧金山的 [ServerlessConf 2018](http://serverlessconf.io/) 上问我怎么做，我们会在那里演示)。

如果您的解决方案在技术上很好，那么就申请 XCloud WFaaS 的空白空间，并努力使其在经济上也很好——我们可能会成为您的用户。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>