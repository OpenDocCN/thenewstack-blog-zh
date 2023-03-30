# 酱油实验室:竞争优势的关键管道自动化

> 原文：<https://thenewstack.io/sauce-labs-pipeline-automation-key-for-competitive-advantage/>

[沙司实验室的史蒂夫·黑兹尔称管道自动化是竞争优势的关键](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage)

随着从瀑布到敏捷再到持续交付的转变，软件测试经历了几次必要的转变，其中最重要的是测试自动化。在最新一集的[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中，[Sauce Labs](https://www.linkedin.com/in/sahazel/)的联合创始人兼首席架构师 Steve Hazel 加入我们，讨论自动化测试的发展，Sauce Labs 一直处于这一领域的前沿。

Hazel 给出的最佳建议是积极投资，自始至终实现部署流程的自动化。在过去的 10 年里，他观察了他们的客户，发现那些从开始到结束都完全实现了流水线自动化的公司比他们的竞争对手走得更快。

“您应该进行按钮式部署，从‘我在笔记本电脑上编写了代码’到代码投入生产，经过全面测试，如果在生产中检测到问题，它会回滚，实现 100%自动化，包括如何启动将要运行它的基础架构，绝对是一切。”您可以看到，与自动化程度为 40%或 60%的公司相比，100%的公司的创新速度要快得多。它是巨大的。"

Sauce Labs 成立于 2008 年，以使用 Selenium 为基础，为应用程序提供功能性的连续测试，一直处于自动化测试的前沿。黑兹尔说:从那以后发生了很多变化。

Hazel 说，开始时，有自动化工具，但是他们自动化了测试的瀑布方法。然后，重点是加速手动测试。

虽然他们在这方面取得了成功，但是向敏捷的转变改变了测试需求。一旦每隔几个月或几周运输一次 ti，测试的需求并没有相应地下降。相反，需求变得更加严格，质量保证(QA)测试成为一个巨大的瓶颈。他说，在发货前进行质量保证阶段的整个想法已经行不通了。由此，Selenium 成为这个更快的世界中自动化测试的明显领导者。

随着世界转向移动，许多想法转移到了移动测试中。而随着微服务的加入，事情又变了。由于部署环境的灵活性，您可以实现完全自动化、滚动部署、canary 部署和自动回滚。

所有这些都带来了新的问题，并有可能使软件出现错误。

“如果你看起来不像‘我们是在让我们的客户免于任何错误吗？’“因为你永远无法让你的顾客免于所有的错误，”他说，“如果你反过来看‘我们在保护顾客免于错误方面做得有多好？’我们让多少百分比的错误通过？"

## 生产中的测试

黑兹尔说，虽然你总是需要在生产前做测试，但没有什么比生产流量更重要了。“你将你的应用暴露在比你在测试中能够复制的更多种类的行为中。”

但是生产中的测试最好被认为是在你已经习惯的测试之上的一个额外的测试层，而不是一个替代。

Hazel 看到越来越多的公司进行更多的自动化测试，以及更多类型的测试。随着软件对于越来越多的企业变得越来越重要，持续的自动化测试变得至关重要。

## 酱油实验室做什么

在敏捷世界中，测试是一个大问题。软件是在小的包中构建的，需要快速但全面的测试，并且需要快速的测试结果。

Sauce Labs 提供了并行运行全面测试的能力，因此完成全面测试套件所需的时间很快。

“我们提供的是一个基于云的测试执行环境，它将大规模并行运行你的测试，”他说。“我们最大的客户在不同的浏览器、不同的移动平台和移动版本上同时运行数千次测试，以便在短时间内获得反馈。”

这种自动化只是基础，他说。“当您运行这些测试时，我们会从日志、浏览器、移动设备、屏幕截图、测试视频、测试结果等收集数据。从这些海量数据中，他们开始在此基础上构建分析功能。”

例如，该软件可以在测试失败之前指出有一个 JavaScript 错误，并返回控制台错误。它可以看到从特定的测试运行开始的失败，他们可以显示什么不同，并建议什么可能被破坏。“当我们强调其中一些事情时，我们缩短了理解问题所在和解决问题所需的时间，”他说。“这是很多团队的加速器。”

当你能缩短找出问题所在的时间，你会走得更快更好。

## 自动化的安全性

黑兹尔说，简而言之，你的管道越自动化，你的系统就越安全。由于大多数管道自动化包括自动升级和对每个浏览器或移动设备配置运行测试，所以旧的版本和控制问题不再是问题。这也意味着所有的代码在发布之前都经过了相同的测试。

他说，这很好，因为“你的安全性取决于你最少被检查的软件。”因此，让管道完全自动化对于安全性来说是一个巨大的好处。

收听以了解使用开源组件进行测试，如何在跨分布式系统进行测试时管理安全性，Sauce Labs 堆栈有什么不同，以及 Sauce Labs 是如何命名的。

### 在这个版本中:

[2:41:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=2:41) 您能谈谈从 Selenium 到瀑布测试的转变，以及这一过程在过去几年中发生了怎样的变化吗？
[9:45:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=9:45) 新环境中的测试
[12:45:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=12:45) 您能谈谈测试、开源服务的集成以及组织在使用它们时需要考虑的问题吗？
[16:56:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=16:56) 酱有部分是开源的吗？
[20:30:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=20:30) 探索生产测试的新层面
[22:12:](https://thenewstack.simplecast.com/episodes/steve-hazel-of-sauce-labs-says-pipeline-automation-is-key-for-competitive-advantage?t=22:12) 如果你能传授给听众一条智慧，会是什么？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>