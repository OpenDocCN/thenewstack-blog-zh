# 如何以及为什么以正确的方式应对事件

> 原文：<https://thenewstack.io/how-and-why-to-respond-to-incidents-the-right-way/>

无论一个应用程序运行得多好，最终都会出现问题。这些问题可能由于很多原因而发生:代码/基础设施的变化、应用程序中的错误、用户奇怪的输入、反铲事故，甚至宇宙射线。不管你的应用程序做得有多好，总会有一些东西在你的应用程序中引起问题。

熟练操作员与不熟练操作员的区别在于他们如何识别和应对问题。在本文中，我将讨论什么是事件，为什么您需要关心他们的响应，如何使用事件响应平台来提供帮助，以及事件发生后应该做什么。

## 什么是事件？

对“事件响应”的一个常见误解是，它实际上是关于“中断响应”——处理应用程序变得不可用的时候。虽然中断肯定总是一个事件，但并不是每个事件都是中断。高延迟、流量的意外下降或增加，甚至更高数量的客户支持票证都可能是事件，可能具有不同的严重级别。

“事件”的一个好的工作定义是，应用程序的性能或可用性，或者一个关键的业务指标，与您的预期有显著差异的任何情况。

这包括停机—显然，您希望应用程序保持运行—但也包括上面提到的其他例子。

区分事件与问题或意外行为的另一个关键因素是需要对事件做出响应。这是现代运营实践的一个关键原则:事故应尽可能少发生，并应迅速处理，以最大限度地减少运营影响。

## 我们为什么以及如何应对事故？

对事件的响应做两件事:尽快结束事件，以及(理想情况下)防止同样的事件再次发生。为应对事故，通常遵循以下步骤:

*   **分流:**事件有多严重，谁能解决？情况越严重，越需要紧急通知相关人员/团队事故已经发生。
*   **解决:**一旦通知了相关人员，他们会修复导致事故的任何原因，以恢复正常运行。
*   **回顾:**应对突发事件的一个关键步骤是在事件解决后对其进行回顾。事件发生的原因(根本原因分析)？怎么才能避免呢？我们如何修改我们的应用程序、基础架构、警报或流程，以确保这种特殊事件不会再次发生？

这些步骤共同创造了一个良性循环，随着时间的推移，事故越来越少，影响越来越小。

## 事件响应平台应具备哪些功能？

为了尽可能轻松地解决事件，许多供应商已经发布了事件响应平台。以下是这种平台应该具备的一些关键特性:

### 集成

您的事件响应平台需要与您的可观察性和监控基础设施以及您的聊天/协作工具、票务系统和其他业务应用程序相集成。一个强大的集成库是一个良好的事件响应系统的重要特征。

### 警报分组

事件响应系统处理的警报可能来自许多来源，有时会同时出现(例如 AWS CloudWatch 警报和 Splunk Observability 云警报)。当这些警报涉及相同的基础架构或应用程序时，可靠的工具会将它们组合在一起，从而减少事件数量，并为响应人员提供上下文。

### 可靠、灵活的通知

如果能够解决事件的人不知道这件事，事件就无法解决。事件响应工具必须具有可以通过多种方法同时发送给多个人的通知。这些通知应该以灵活的方式进行配置，以便您可以决定什么适合不同严重级别的事件或不同的团队。

### 合理定价

许多在处理事件中作为利益相关者的人并不直接回应它们。许多事件响应工具按用户收费，因此价格昂贵。您可能希望选择一种工具，为只读用户提供免费或大幅降价的服务，这些用户可以确定事件的状态，但不能做出响应。

## 事发后呢？

审查事件并根据这些事件审查的结果进行更改是可靠和成功地运行现代应用程序的秘诀。事件解决后，下一步是事件审查(或“事后分析”)。在此过程中，将对应用程序、基础架构和人员发生的情况进行无过失分析。目标是确定到底发生了什么，为什么会发生，以及如何改变系统或流程，使事故不再发生。如何进行事件审查的完整描述超出了本文的范围，但是关键的要点是这些审查必须执行。

如果您不在每次事件后进行更改，事件将会继续发生，导致员工不满意、客户不满意、应用程序不太可靠，并最终导致更糟糕的业务结果。强大的事件响应工具和消除事件的正确心态是运行设计良好的应用程序的两个关键因素。使用这些工具并执行事故后审查将确保它在未来几年继续运行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>