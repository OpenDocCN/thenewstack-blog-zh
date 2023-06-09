# 维持无服务器操作的 7 个基本开发工具

> 原文：<https://thenewstack.io/7-essential-devops-tools-to-maintain-serverless-operations/>

这篇文章是探索无服务器基础的系列文章的第四篇。请每周一回来查看更多的分期付款。

[无服务器架构](https://thenewstack.io/serverless-101-how-to-get-serverless-started-in-the-enterprise/)因其支持更快开发时间的能力以及潜在的更低运营成本而受到关注，这是由于一种只为计算使用付费的模式。

这意味着，实施无服务器的公司不需要对提升计算能力的基础架构有太多的了解。无服务器架构的主要优势之一是支持自动扩展，因此无需 DevOps 持续监控何时需要调配新的服务器实例。

这样做的缺点是，在许多地方，如果事情没有按预期运行，或者产生的成本高于预期，那么对正在发生的事情的可见性就会降低。无服务器还可以将焦点移近应用程序级别，这带来了一系列全新的应用程序监控问题。

因此，在新兴的无服务器生态系统中，围绕 DevOps 工具的第一次生态系统繁荣可能是很自然的。云本地计算基金会的无服务器环境确定了至少六种 DevOps 工具，尽管也有平台无关的监控工具可以提供无服务器系统中的可见性。

这里有一些您应该知道的支持企业环境的最重要的工具。

## 1。云零

CloudZero 首席执行官兼创始人埃里克·彼得森(Erik Peterson)表示，CloudZero 自称是第一个为这个世界构建的无服务器智能平台，在这个世界里，云被视为新的计算机，亚马逊网络服务(AWS)等云提供商是新的操作系统。CloudZero 的平台使工程师、架构师和 DevOps 团队能够实时监控和了解他们的无服务器系统，并从一个统一的平台管理一个或数百个云帐户的延迟、错误和成本。

“我们解决的第一个问题是识别异常行为，发现无服务器系统中发生了什么变化，然后知道谁或什么做出了改变，”Peterson 说。

目前，CloudZero 可以进行 beta 测试，计划在 2018 年晚些时候发布正式版本。

## 2。仪表板鸟

[Dashbird](https://dashbird.io/) 是一个 AWS Lambda 监控调试平台。传统的应用程序性能监控方法通常通过远程 API 发送数据来收集日志，然后使用这些日志来创建仪表板和基于所接收数据的警报。不过，这种方法不适合无服务器，因为延迟太大。作为一种解决方法，Dashboard 为函数退休部署了一个标志，以显示它何时被重试或何时被第一次调用。

或许 Dashbird 的一个意想不到的用例是将其用作调试工具。无服务器的挑战之一是没有开发阶段，因此开发人员必须执行他们的功能，看看他们在现实世界中是如何运行的，然后找出如果它没有按预期执行会发生什么。Dashbird 的开源无服务器离线插件用于无服务器框架，可以模拟 Lambda 操作和 API 网关，允许开发人员创建开发阶段环境。

## 3。爱普生

[Epsagon](https://www.epsagon.com/) 帮助公司和开发者利用无服务器技术而不失去对其应用的控制，提供无服务器架构的端到端可见性和可视化。

Epsagon 还支持快速故障排除，显著减少系统停机时间。使用他们的技术，开发人员已经减少了 80%以上的故障排除时间。通过使用分布式跟踪和人工智能技术，该公司分析了应用程序的性能和瓶颈，在改善最终用户体验的同时保持成本不变。

Epsagon 的联合创始人兼首席执行官 Nitzan Shapira 表示，与成熟的无服务器生态系统中的其他 DevOps 工具一样，Epsagon 目前处于测试版，计划在今年晚些时候正式发布。

Shapira 表示，一些早期采用者包括数据分析初创公司、金融和移动应用程序开发人员。目前的一个客户是一家广告技术公司。“他们使用无服务器管道来分析他们的数据，”沙皮拉说。“他们让我们的交易视图页面全天开放。他们使用 Epsagon 对系统中的关键问题进行故障排除，并进行根本原因分析。他们报告说，每个开发人员使用 Epsagon 每天可以节省两个小时。”

## 4。蜂巢

[Honeycomb](https://honeycomb.io) 是一项服务，可以帮助发现通过简单的日志分析无法发现的关键问题。它允许用户在几毫秒内查询和可视化数百万个事件，并查看每个结果背后的原始数据。它不知道数据来自哪里——不需要代理或插件。Honeycomb 的首席执行官 [Charity Majors](https://twitter.com/mipsytipsy) 说，API 只接受带有写键的结构化数据 blob，这种方法“使其非常适合无状态、无服务器的代码片段”。

Majors 说，无服务器架构师使用 Honeycomb 的一个新的 DevOps 用例是新的跟踪功能。“跟踪和其他事件一样，只是一个事件，所以你可以将跟踪 ID 传递给你的无服务器函数，并看到一个瀑布图，显示你的时间和工作实际上花在哪里，”她说。她指出，有了 Honeycomb，你就有能力在广度优先的探索和深度优先的痕迹检查之间来回切换，然后再扩展到广度。例如，您可以缩小 bug 的范围，直到找到它的一个实例，然后跟踪该实例，然后缩小范围，查看受该 bug 影响的所有其他内容。

## 5。IOpipe

[IOpipe](https://www.iopipe.com/) 提供了一款[无服务器开发工具](https://thenewstack.io/iopipe-launches-lambda-monitoring-tool-aws-summit/)，专注于联合创始人兼首席技术官[Erica wind isch](https://github.com/ewindisch)所说的“应用运营”她说，在无服务器环境中，更重要的是在每次调用一个函数时观察应用程序中发生了什么。

IOpipe 旨在提供一套监控和调试工具，允许更深入地了解调用无服务器工作流的每个 Lambda 函数时发生的情况。使用 IOpipe，您可以在代码编辑器中工作，并添加 IOpipe 无服务器框架插件或在您的应用程序中使用我们的装饰器。然后，您可以在另一个窗口中打开 IOpipe，并将信息输入其中。

## 6。斯塔克里

[Stackery](https://www.stackery.io/) 的无服务器工具包帮助专业开发团队加速软件交付，在 AWS Lambda 上发布生产就绪的无服务器应用。随着其旗舰软件已经全面上市，塔加特现在正致力于无服务器的关键任务需求，重点是协作、治理和标准化。

“我们目前正在对我们的 CLI 和开发人员工作流程进行一些重大改进。我们正在创建市场上最高效的专业无服务器开发周期，并将在未来 30 天内发布这些更新，”Stackery 首席执行官[内特·塔加特](https://www.linkedin.com/in/nathantaggart/)说道，他的 DevOps 工具[之前已经在新的 Stack](https://thenewstack.io/emerging-ops-tooling-serverless-reveals-two-adoption-paths/) 中涵盖。

他提到了最近与一家企业客户的合作，该客户正在努力应对塔加特经常遇到的挑战:需要在一个无服务器架构内创建一个标准化的、可重复的发布流程。

“他们尝试使用 AWS SAM、CloudFormation 和无服务器框架，但在管理环境、自动化发布、配置 IAM 和运行测试需求方面遇到了困难，”他说。他说，公司选择 Stackery 进行环境管理、IAM 策略自动化和集中发布周期。

“现在，团队中的每个开发人员都可以在隔离的环境中快速建立应用程序的新实例。这使他们能够加快开发周期，并自动测试和发布每一个接受的拉式请求，”塔加特说。

## 7。桑德拉

桑德拉是为无服务器架构设计的可观测性解决方案。桑德拉的一些关键能力包括:

*   自动化插装:桑德拉不要求用户在代码中添加手动插装和日志语句来收集数据。代码被自动检测以收集相关数据，从而获得全面的可见性并快速解决问题。
*   完全可观察性:桑德拉收集并提供统一的环境度量、日志和跟踪视图，以便快速解决问题。
*   零开销:桑德拉支持异步(以及同步)数据收集，以确保对应用程序没有影响。
*   智能采样:桑德拉支持可配置的智能采样，以确保收集识别和排除问题所需的数据，同时控制成本。

虽然桑德拉还处于早期发布阶段，并计划在今年晚些时候正式发布，但早期采用者已经从该工具中发现了价值。

“早期采用者之一(一家全球金融公司)需要一种解决方案，以确保他们在转向无服务器架构时能够为其开发人员提供相同级别的可见性，”桑德拉联合创始人兼开发主管 Serkan ozal 说道。由于他们现有的 APM 工具无法在无服务器体系结构中工作，因此他们采用了桑德拉作为无服务器应用程序的可观测性解决方案

## 成熟的无服务器生态系统中的开发运维工具

虽然无服务器离成熟的技术市场还很远，但它正在快速发展，DevOps 作为生态系统玩家的早期领跑者是有道理的。由于基础设施决策被移交给云提供商管理，无服务器降低了一些可见性。

这带来了一些风险，需要在应用程序级别进行管理。正如来自 Epsagon 的 Nitzan Shapira 对无服务器模型整体解释的那样:“最难理解的是不同的资源、队列、数据库和触发器，以及它们现在是如何成为一个系统的一部分的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>