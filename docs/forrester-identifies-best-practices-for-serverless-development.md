# Forrester 确定了无服务器开发的最佳实践

> 原文：<https://thenewstack.io/forrester-identifies-best-practices-for-serverless-development/>

Forrester 分析师 Devin Dickerson 研究这种方法的趋势和最佳实践，他说，无服务器开发正在迅速成熟。

迪克森是《T2》的第一作者，这是一份关于无服务器开发和交付最佳实践的新报告。新的堆栈要求 Dickerson 解释开发人员需要了解无服务器环境中的部署。

Dickerson 说，在许多方面，无服务器的增长可以追溯到 DevOps 运动，该运动将一些运营问题推回到开发中。

“随之而来的是，开发人员突然之间不得不担心比以前更多的运营问题，”他说。“无服务器是有益的，因为它消除了开发人员的操作顾虑[……]。”

当然，[无服务器并不意味着字面上的无服务器](https://thenewstack.io/serverless-has-unlocked-a-new-world-of-cloud-mashups/)。只是服务器是托管的，是虚拟的。但是对于开发者来说，无服务器消除了许多操作上的麻烦——这可能是它受欢迎的原因。在 Forrester 的 2022 年开发人员调查中，2452 名开发人员中有 33%表示他们目前正在使用无服务器架构，另有 30%表示他们希望使用该架构。

## 将服务设计为短暂的实例

使用无服务器的最大考虑之一是应用程序部署在只有在被事件调用或触发时才运行的函数中。

Dickerson 说，使用传统的基于微服务的应用程序，甚至是单片应用程序，开发者可以全面了解生产中的情况。对于无服务器应用程序来说就不是这样了，在无服务器应用程序中，有些部分有时根本不运行。

“当你设计一个无服务器的应用程序时，你必须考虑到它不会一直运行，”Dickerson 说。“一旦它们不再奔跑，它们就会消失。”

为此进行设计意味着使微服务具有独立的、单一职责的功能。报告指出，这还意味着设计执行后又消失的功能。

“当无服务器开发人员为短期运行的独立工作负载进行构建时，他们可以获得自主水平扩展的好处，可以在一小部分时间和一小部分成本内完成，”该报告称。它补充说，功能有效载荷应该很小，并减少依赖性，以提供最佳性能。

报告指出，如果存在具有零星需求的独立工作负载，无服务器架构可以很好地工作，但如果你有“难以并行处理的序列化工作单元”，这不是最好的方法。

## 将功能即服务与事件驱动的微服务配对

虽然[功能即服务](https://thenewstack.io/3-use-cases-driving-adoption-functions-service/)平台——如 [AWS Lambda](https://thenewstack.io/first-malware-running-on-aws-lambda-discovered/) 、 [Azure Functions](https://thenewstack.io/azure-functions-serverless-computing-handling-iot-devices/) 和[Google Cloud Functions](https://thenewstack.io/serverless-everything-you-need-to-know-about-google-cloud-functions/)——是开发的关键，但 Forrester 认为它们只是一个起点。作为最佳实践，开发人员还可以将功能与事件驱动的微服务配对。

Dickerson 说:“有些无服务器应用程序是完全无服务器的，所以你可能会有这样一种情况，你已经开发了一种功能，这种功能的用例适合于无服务器地完成所有事情。”“但更常见的是，你会看到无服务器功能以及微服务和整体云原生应用。”

报告称，将微服务构建为消费和发出事件的离散功能，可以让开发人员“充分利用函数式编程的短暂横向扩展优势”。它推荐了将事件驱动的微服务实现为功能的四个步骤:

1.  **设计事件和领域的分类**。它补充道, [GitHub Actions](https://thenewstack.io/simple-load-testing-with-github-actions/) 可以帮助实现微服务功能。
2.  **使用事件队列推动自动扩展性能。**“开发者可以配置无服务器平台，以监控事件队列的深度，并在性能开始下降时做出适当的响应，”该报告指出，并将其比作“当你站在一条长队中，三名店员突然打开窗户为客户服务的美妙时刻。”
3.  **设计允许多个微服务响应同一个事件。**
4.  **假设一个服务的多个版本可能对同一个事件做出响应。**“开发人员可以使用金丝雀和蓝/绿部署来评估生产中的新服务版本。”它补充说，无服务器框架和工具，如无服务器框架的 Canary 插件，可以实现这一功能。

## 设计函数时考虑自动缩放

要在设计功能时考虑自动伸缩，请将活动分解成可以单独部署的独立小任务。报告警告说，开发人员还应该尽量减少功能等待部署的时间，因为执行时间是无服务器环境中最大的成本驱动因素。

此外，Forrester 指出，由于紧密耦合，传统的大型关系数据库管理系统在无服务器环境中不能很好地工作。“相反，无服务器开发人员使用更快的 [NoSQL](https://thenewstack.io/getting-started-with-nosql-and-java/) 方法和状态机工作流(如阶跃函数)将状态从他们的业务逻辑中分离出来，”报告称。

## 通过容错服务拥抱变化

最后，Dickerson 建议，通过发现关键故障点、降低集成风险和其他可预测的故障线，提前为故障做好计划，并使用[混沌工程](https://thenewstack.io/why-chaos-engineering-isnt-just-for-operations/)和测试来测试应用程序的故障策略。

一个在不同时间运行多个无服务器功能和接收事件的应用程序需要一种更健壮的测试方法，在这种方法中，开发人员试图模拟生产中可能出错的情况。[网飞](https://thenewstack.io/why-netflix-rolled-its-own-node-js-functions-as-a-service-runtime/)已经利用这种混沌测试方法取得了巨大的效果，他补充道。

“混沌工程本质上是当你试图打破你自己的系统[……]目的是创造更有弹性的应用程序，”迪克森说。这不是无服务器独有的，但这是一种应该与无服务器一起使用的技术

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>