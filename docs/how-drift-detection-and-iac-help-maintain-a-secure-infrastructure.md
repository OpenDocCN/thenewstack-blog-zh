# 漂移检测和 IaC 如何帮助维护安全的基础设施

> 原文：<https://thenewstack.io/how-drift-detection-and-iac-help-maintain-a-secure-infrastructure/>

基础架构供应有时仍然会感觉像是一个无休止的重新发明轮子的循环，除非您有合适的流程和功能。对于许多组织来说，解决方案是采用基础架构即代码(IaC)来跨多个公共云和私有数据中心自动进行资源调配。

 [塔尔哈·塔里克

塔尔哈是哈希公司的首席安全官。从初创公司到财富 100 强企业，他在构建和扩展安全程序方面拥有数十年的经验。在 HashiCorp 之前，Talha 曾担任 Anki 的 CISO 和普华永道的安全咨询总监 FinancialForce，并在微软和 NCR 担任过各种安全领导职务。他还为世界各地的客户提供与重大敏感数据泄露、知识产权盗窃、黑客事件、法医调查、安全计划开发、安全运营以及威胁和漏洞评估相关的建议。](https://www.linkedin.com/in/talhatariq/) 

IaC 提供了一种更现代、更高效的方式来交付基础设施和基础设施变更，而不会出现瓶颈，从而加快了应用交付时间。但在您的 IaC 工作流程中安装护栏至关重要，因为不再有传统的基于票证的 it 流程来确保所有基础架构更改都遵循安全最佳实践。

作为 HashiCorp 的 CISO，我负责组织的安全，因此使用内置的[策略即代码](https://docs.hashicorp.com/sentinel/concepts/policy-as-code)护栏实施策略对于实现基础设施即代码至关重要。没有标准化和防护栏的 IaC 增加了安全事件的风险，因为在数百名开发人员和运营商每天都在提供动态基础架构并与之交互的环境中，缺乏治理并难以维护合规性。

作为 CISO，除了保证我的组织的安全，我还需要确保我们的安全解决方案是高效的。IaC 帮助人们调配基础架构，以协作和重用组件，同时满足多个团队(云运营、IT、R&D、安全、工程、合规和财务等)的跨部门目标。它还有助于增强安全性和数据治理合规性。

即使有了标准化的 IaC 工作流程，包括护栏，IaC 也不是完美的。它不是万灵药。在现实世界中，基础设施将不断变化和更新，以响应组织的目标和不可预见的事件。如果基础设施状态发生变化，与规范中定义的状态不符，这种现象称为“[漂移](https://www.hashicorp.com/resources/how-can-i-prevent-configuration-drift)”，可能会降低 IaC 解决方案的效率和安全性。这使得资源生命周期管理成为一个关键问题，而漂移检测是其中的一个关键组成部分。

为了最大化基础架构代码的价值，了解基础架构漂移的原因、影响(尤其是对安全性的影响)以及实施漂移检测和补救以帮助解决问题的最佳方法非常重要。

## 什么导致基础设施漂移

发生漂移的原因有很多。首先，可能存在组织中的每个人都没有使用已建立的 IaC 工作流的情况。这可能会在代码中定义的基础结构和实际的当前状态之间产生未记录的差异。

紧急情况是另一个常见原因。在“玻璃破碎事件”中，响应管理团队有时会决定绕过修补基础设施的标准程序，以尽快解决问题。这些类型的快捷方式会导致对资源的更改，这些更改很难在代码中跟踪和解决。

此外，云或服务提供商系统上的基本系统更新也会随着时间的推移而累积，随着您的基础架构规则和提供商系统逐渐分离，会导致重大偏差。例如，简单的 API 更改(通常针对第三方服务)可能会影响您的基础设施，而不会在代码中被跟踪。

最后，级联效应会使漂移检测变得更加复杂。例如，当更改或创建新的基础设施资源时，可能会有未编码的意外关联资源。这就产生了一种级联效应，即在没有人察觉的情况下，资源状态的变化会相互影响。

## 漂移对基础设施安全性和功能性的影响

随着云采用的增加，组织资源和流程变得越来越复杂，这可能会造成基础架构状态的不一致。如果没有标准的调整程序、通知或指导原则，即使是对基础架构的临时更改或最小的调整也会对业务产生重大影响，包括计划外停机、审计结果、安全事件、返工和未使用的资源。

最重要的是，未被认识到的基础设施漂移会产生多种风险，需要在它们成为真正的问题之前加以解决。漂移会极大地增加关键数据泄露的可能性，这可能是由于任务关键型系统错误地向公众开放，或者未知资源未得到保护。

此外，不了解 IaC 系统中没有反映的生产环境变化的开发团队几乎肯定要面对应用程序“突然”崩溃和部署项目意外失败的情况。

## 从漂移检测到漂移补救

那么，组织如何才能最好地处理漂移检测，当检测到漂移时，他们可以做些什么来补救这种情况呢？一些公司选择构建内部工具，一次检查所有状态的漂移，然后通过电子邮件向所有用户发送报告。但是这使得区分必要的变更和不必要的变更变得困难，因为变更背后没有上下文。另外，您可以对资源或记录的 IaC 状态进行手动更改。这种方法太耗时，不具备可扩展性。

这些挑战的根本解决方案归结起来就是回答两个关键问题:

1.  您如何确保实际的基础架构反映记录的基础架构状态，并通知适当的人员对任何检测到的偏差采取纠正措施？
2.  漂移检测解决方案能否通过与 IaC 平台无缝协作，同时作为工程和安全团队的中央信息来源，优先考虑效率和简单性？

## 集中可见性对于漂移检测至关重要

最终，关注漂移的团队应该寻找集成式漂移检测解决方案。理想情况下，这种类型的系统应该包括一体化的自动供应和集中管理，这样开发团队就可以持续监控基础设施状态以检测变化。在整合的环境中运行，系统应该能够向适当的团队发送即时通知，以便他们可以在资源发生变化时采取特定的纠正措施。

对于关注缩小安全差距的 CISOs 来说，这种解决方案有助于加强组织的整体安全状况，而不会增加不必要的运营负担。

具体来说，集成的漂移检测方法可以显著降低应用程序停机的可能性，这种停机可能会对用户体验以及最终的收入产生负面影响。它还可以使团队能够跟踪并快速处理系统更改，确定谁做出了这些更改及其原因，并记录这些更改以供将来参考或根据需要调整标准工作流。

最后，一个强大的漂移检测系统可以为团队提供一致的单一事实来源，使他们能够合作，从而提高运营灵活性。使用相同的信息可以避免购买或开发定制的工具或处理刷新状态的手动操作，同时提供卓越的可见性并加快解决问题的速度。

## 自动化、检测和警报

总的来说，自动化基础架构配置提供了显著的生产力和安全性优势。但是，如果您的基础设施发生了变化，而实际状态没有反映在记录的 IaC 状态中，该怎么办呢？漂移是现代动态基础设施的一个不幸的副作用，在这种基础设施中，变化是不断发生的。

为了最大限度地减少基础设施漂移的影响，您需要一个漂移检测系统，让您的运营团队能够了解情况，并在需要时提醒适当的人员采取行动。使用集中的自动化工具，在标准化流程下系统地协同工作，有望降低风险，提供更大的系统可见性，并使团队能够更快地解决基础架构问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>