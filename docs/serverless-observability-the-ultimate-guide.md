# 无服务器可观测性:最终指南

> 原文：<https://thenewstack.io/serverless-observability-the-ultimate-guide/>

[](https://www.linkedin.com/in/emrahsamdan/)

 [艾姆拉·萨姆丹

艾姆拉是桑德拉公司的产品副总裁。他热衷于无服务器、可观测性和混沌工程。](https://www.linkedin.com/in/emrahsamdan/) [](https://www.linkedin.com/in/emrahsamdan/)

可观察性是一种应用程序状态，它为您提供了理解出错原因所需的洞察力，以及帮助您理解错误发生原因的跟踪和追踪功能。

在任何应用中，高可观测性是高可用性的先决条件。为了在无服务器应用程序中实现可观察性，重要的是获得一个完整的画面——而不仅仅是大多数提供者关注的单个函数调用的快照。

本文探讨了可观察性的问题，以及无服务器环境如何使其复杂化。然后，我们将浏览本地和第三方无服务器可观测性工具，并描述最终可观测性的旅程。

我们还邀请您[下载更详细的无服务器可观察性指南](https://www.thundra.io/whitepaper/serverless-observability-the-ultimate-guide?utm_source=newstack&utm_medium=paid&utm_campaign=WP-Serverless%20Observability-The%20Ultimate%20Guide&utm_content=lp_slsObsUltGuide)，本文正是基于该指南。

## 定义可观察性

可观察性的目标是让您能够全面、端到端地了解应用程序的所有性能特征。因此，真正的可观察性不仅仅是代码的快照，而是将执行上下文、事件系统和第三方集成服务整合到应用程序行为的整体画面中。

测试验证系统对“已知”问题的正确性。监控检查“已知”指标，以评估系统的健康状况。另一方面，可观察性是通过应用程序的工具实现的状态，这样开发人员就有足够的信息来处理“未知”可观测性对于构建一个可维护的系统至关重要。

## 无服务器应用中的可观测性挑战

当谈到可观察性时，无服务器应用程序尤其具有挑战性。在分布式微服务架构中，每个单独的服务都相当大，并且足够复杂，可以在服务交互级别上理解。可观察性可以通过检查机器特性以及清晰地显示控制流路径的连贯堆栈跟踪来实现。

然而，在无服务器的应用程序中，事件驱动的功能是完全不同的，孤立地运行，并且非常短暂。很难分析它们的潜在副作用(如部分加工的批次)。

简而言之，任何对无服务器应用有用的可观察性特征都需要从头开始构建。因此，在开发过程的每个阶段，记住您的最终状态应用程序的可观察性是很重要的。

## 使用 AWS 工具的可观察性

幸运的是，AWS 并没有忽视无服务器可观察性问题，它提供了两个有助于无服务器应用程序整体可观察性的关键资源:AWS CloudWatch 和 AWS X-Ray。

当出现问题时，这些工具是您的第一道防线，了解每个工具在无服务器应用程序中扮演的角色非常重要。

### AWS 云观察

[AWS CloudWatch](https://aws.amazon.com/cloudwatch/) 是默认情况下与 AWS Lambda 集成的日志和指标摄取和可视化套件。然而，你需要考虑 CloudWatch [的限制和成本](https://blog.symphonia.io/posts/2017-01-24_danger-in-the-details-scalable-cloudwatch-metrics-for-aws-lambda)——这在无服务器的环境中不能很好地扩展。例如，如果失败的函数是共享一个共同来源的 Lambda 函数请求链中的一个，那么现成的函数级 CloudWatch 日志就有问题。这里的解决方法是实现 CloudWatch 可配置的[度量过滤器](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/MonitoringLogData.html)来聚合不同的函数日志。

### 自动气象站 X 射线

AWS Lambda 的另一个本地可观测性解决方案是 [AWS X-Ray](https://aws.amazon.com/xray/) ，这是一个分布式跟踪系统，旨在帮助查明无服务器架构中的故障。然而，X-Ray 和 CloudWatch 并没有紧密集成到一个内聚的 UI 中。试图对无服务器事务进行故障排除的开发人员需要在 CloudWatch 和 X-Ray 之间不断切换，以获得系统状态的完整视图。

那么有没有更好的解决办法呢？

## 开源软件的可观察性

像 CloudWatch 和 X-Ray 这样的提供商工具让你接近一个完整的可观察性图片，但它们有其局限性。例如，设想一个涉及第三方服务的无服务器请求。如何将第三方服务的运行时和失败代码整合到您的整个系统图中？此外，X-Ray 拥有覆盖 AWS SQS 和 SNS 的分布式跟踪支持，但基于 DynamoDB、Kinesis 和 Firehose 构建的应用程序需要构建自己的分布式跟踪机制。

幸运的是，开源的可观察性和可视化工具的出现填补了这些空白，提供了更大的可定制性和灵活性。

### 可观测性数据生成

构建定制的无服务器可观测性的第一步是生成系统的可观测数据。这个领域最初的参与者是 [OpenTracing 项目](https://opentracing.io/)，它是一组独立于提供者的库和 API，可用于检测无服务器应用程序。这已经发展到包括遥测和度量在内的[开放遥测项目](https://opentelemetry.io/about/)。这些库是为 AWS Lambda 函数构建定制跟踪系统的关键部分，提供经过测试的可重用模式和最佳实践。

### 可视化工具

一旦你生成了你的可观察性数据，你需要连贯地呈现它。在系统级别概念化故障时，原始日志输出不是特别有用。两个领先的开源追踪可视化工具是 [Zipkin](https://zipkin.io/) 和 [Jaeger](https://www.jaegertracing.io/) 。这些工具以可读格式显示生成的跟踪和指标，缩短了补救时间。

## 桑德拉全自动可观测性

随着无服务器应用程序变得越来越复杂，内置的可观察性工具通常会变得非常有限。一种解决方案是使用开源框架构建定制的解决方案。然而，这些工具的实现通常是劳动密集型的，并且随着应用程序的发展，维护起来也很困难。在这种情况下，您会希望求助于第三方工具来实现价值与努力的最佳权衡。

桑德拉为开箱即用的无服务器应用程序提供了一个全面的可观察性套件，只需最少的配置就能正确报告应用程序的所有无服务器功能。桑德拉的嵌入式库提供了完全自动化的可观察性，与 AWS Lambda 执行层集成，可以在函数生命周期的任何一点自动检测您的函数。桑德拉强大的可视化功能还可以编译所有你需要的数据，以跟踪无服务器应用程序中的故障和错误行为。

通过使用桑德拉软件开发工具包注入您自己的应用感知工具逻辑，您可以进一步扩展桑德拉的全自动无服务器可观测性解决方案。

## 通向终极可观测性的旅程

可观察性给在无服务器环境中工作的开发人员带来了独特的挑战。像 CloudWatch 和 X-Ray 这样的内置工具提供了一个良好的开端，但当你设计一个完全可观测的系统时，它们有一些限制，成本可能会高得令人望而却步。

开源工具允许您在这些限制的基础上进行构建，从而为您的应用程序提供一个更加完整和可定制的画面。然而，当大规模实现时，开源工具往往是劳动密集型的，并且简单的定制可能会遇到问题，因为它们在您的组织中传播。

像桑德拉这样的第三方工具完全弥合了无服务器可观测性的差距，给你一个自动化和手动观测技术的最佳组合。通过在 CloudWatch 等第三方解决方案的基础上构建，在 Lambda 执行时与它集成，桑德拉为您提供了开箱即用的功能，这需要整个开发团队在开源驱动的平台上维护。

借助桑德拉，您可以在几分钟内为您的无服务器应用程序部署完全可观察的后端，并满怀信心地开始故障排除。

[*访问桑德拉网站*](https://www.thundra.io/whitepaper/serverless-observability-the-ultimate-guide?utm_source=newstack&utm_medium=paid&utm_campaign=WP-Serverless%20Observability-The%20Ultimate%20Guide&utm_content=lp_slsObsUltGuide) *下载关于无服务器可观测性的全面指南。*

亚马逊网络服务是新堆栈的赞助商。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过推特或脸书访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>