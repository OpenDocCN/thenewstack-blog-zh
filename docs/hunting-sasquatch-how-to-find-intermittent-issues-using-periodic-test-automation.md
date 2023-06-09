# 狩猎大脚野人:如何使用定期测试自动化发现间歇性问题

> 原文：<https://thenewstack.io/hunting-sasquatch-how-to-find-intermittent-issues-using-periodic-test-automation/>

Tricentis 赞助了这篇文章。

在美国民间传说中，大脚野人是一种难以捉摸的类似猿的生物，在荒野和文明的边界上很少见到。在软件领域，我们有自己的 Sasquatch 版本:在复杂系统中出现的恼人的、难以发现的间歇性问题，软件开发人员通常不相信它的存在。

但是问题确实存在，你的团队需要解决它。正如 [Paul Grizzaffi 在 Accelerate San Francisco](https://www.tricentis.com/resources/accelerate-sf-2019-hunting-sasquatch-finding-intermittent-issues-using-periodic-automation/) 的演讲中所展示的，定期的测试自动化会有所帮助。

以下是方法。

## 什么导致间歇性问题？

 [拉尼尔·诺维尔

Lanier Norville 以前是一名记者，目前负责 Tricentis 的软件开发和测试趋势。她喜欢强调测试人员的贡献，他们通常是无名英雄，将世界从无法量化的挫折和错误灾难中拯救出来，由于他们，从未见过生产环境。她住在亚特兰大，认为奶酪是五种主要食物之一。](https://www.linkedin.com/in/lanier-norville-73729a6/) 

由于持续集成的兴起，间歇性问题近年来有所增加。开发人员更早、更频繁地集成不同代码分支的这种做法有很多好处，包括更容易解决大多数问题。然而，持续集成确实使得捕捉来自古怪的测试环境、定期维护和竞争条件的间歇性问题变得更加困难。

在这些场景中，间歇性问题最常见的原因和最难防范的原因是竞争条件。当以不确定的顺序接收到两个事件时，会出现这种情况。

例如，当一个系统应该接收多个事件，但不能预测这些事件的顺序时，在理解如何处理它们时就会出现问题。当这种类型的竞争情况发生时，我们会遇到一个间歇性的问题，也就是北美野人。

## 为什么竞态条件如此难以测试？

今天的软件很复杂，通常依赖于与多个第三方组件的交互。来自这些应用程序的事件进入系统的顺序是不可预测的，有许多可能的排列和组合。由于这种复杂性，手工枚举所有可能性至少是一项乏味且容易出错的任务。自动化，对于信息系统和其他任务来说，也越来越被视为一种必要，尤其是随着运营规模的扩大和对许多组织来说变得更加复杂。然而，这项任务也不容易自动化。这是因为竞争条件在本质上是不可预测的。即使我们可以创建一个脚本来列举足够复杂的系统中的每一个可能的事件序列，也有太多不同的东西需要测试，以至于大多数团队都没有资源。

## 你如何发现间歇性的问题，比如比赛条件？

持续集成不会很快实现，这意味着我们需要找到一种更好的方法来发现和处理由竞争条件引起的间歇性问题。这样做的关键在于四个步骤:

1.  **运行“每次部署时”脚本:**总是在部署时测试代码，以确保新集成的工作不会破坏任何东西。
2.  **用定期自动化来补充这些脚本:**定期重新运行所有或部分“每次部署时”脚本来再次检查结果，因为您寻找的东西越多，就越有可能看到它。这种做法增加了你看到难以捉摸的大脚野人的机会。
3.  **调查每一个发现:**每次事情失败，你都必须深入调查以确定失败的原因。
4.  在开发人员和测试人员之间保持良好的合作关系:这种合作关系对于高效和有效地提出和解决间歇性问题至关重要。

## 为什么周期性的测试自动化对于发现间歇性的问题如此重要？

周期性自动化善于发现间歇性问题，因为它运行在时间边界上，而不是事件边界上。虽然您的“在每次部署时”脚本只在代码发生更改时运行，但是定期自动化以设定的节奏定期运行，即使自上次运行以来没有任何更改。因此，定期自动化可以发现并隔离仅在特定情况下发生的问题。

## 使用定期测试自动化来发现间歇性问题的最佳实践是什么？

定期的自动化对于发现间歇性的问题很有价值，但是您必须有合适的框架来使它正常工作。首先，请遵循以下最佳实践:

1.  **关注失败，但不要忽视成功:**显然你需要解决失败，但成功也很重要，因为它们可以帮助你找出为什么软件在某些情况下能正常工作，而在其他情况下却不能。
2.  **快速行动——时间至关重要:**你等待解决故障的时间越长，代码或情况发生变化的可能性就越大。因此，当失败出现时，你需要尽快采取行动。
3.  **保持最小的噪音以避免失败疲劳:**只提醒相关人员(例如，那些在某个时间框架内集成新代码的人)关于失败，并且以一种突出的，但不生硬的方式这样做，以便他们在收到警告时能够注意并迅速行动。
4.  **只测试你准备修复的东西:**如果你没有准备好修复一个失败(这可能有很多原因)，那么你需要停止测试它。否则，你会让你的团队对需要立即解决的失败麻木不仁。
5.  信任您的自动化:信任问题远非理想，但确实会发生。当团队对自动化失去信任时，他们不太可能回顾结果，调查和报告问题，甚至不太可能找到问题的开始。为了有效地发现和解决间歇性问题，您需要信任自动化。

### 了解更多关于使用定期测试自动化发现间歇性问题的信息

[请查看 Tricentis Accelerate 2019 专题讲座，Paul Grizzaffi](https://www.tricentis.com/resources/accelerate-sf-2019-hunting-sasquatch-finding-intermittent-issues-using-periodic-automation/) 将向您介绍如何应用定期自动化来发现典型事件界限之外的问题，该方法如何与高容量自动化测试(HiVAT)相关联，以及它如何帮助您避免对故障脱敏。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>