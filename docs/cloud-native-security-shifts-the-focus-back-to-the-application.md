# 云原生安全性将焦点转移回应用程序

> 原文：<https://thenewstack.io/cloud-native-security-shifts-the-focus-back-to-the-application/>

云原生计算正在给应用程序的开发、部署和运行方式带来翻天覆地的变化，毫不奇怪，它也正在改变信息安全的规则。例子:无服务器计算。

在最新一期的 New Stack makers 播客中，我们采访了 Check Point Software 的云安全策略师 T2，他一直站在这些变革的前沿。Solow 共同创立了 Protego Labs，这是无服务器安全领域的先驱。安全厂商 Check Point 很早就看到了安全墙上的文字[在 2019 年吞噬了](https://www.checkpoint.com/press/2019/check-point-extends-leadership-in-cloud-security-with-unmatched-serverless-protection/) Protego。《新书库》出版商亚历克斯·威廉姆斯和 TNS 执行主编乔布·杰克逊主持了这一集。

[云原生安全将重点转移回保护应用](https://thenewstack.simplecast.com/episodes/cloud-native-security-shifts-the-focus-back-to-securing-the-application)

Solow 在播客中解释说，Protego 开始的地方 Serverless 是云原生计算带来的变化的一个很好的例子。无服务器工作负载会弹出，并在完成后立即消失。它迫使安全专家重新思考或“全面地”思考如何保护应用程序。攻击者可能无法使用无服务器调用来创建用户帐户或获取大量用户数据，但通过使用无服务器调用作为更大进入的支点或以不必要的费用打击帐户持有人的帐户，仍然可以造成损害。

Solow 认为，在许多方面，无服务器安全的最佳实践应该作为所有应用程序安全的通用指南。最近，许多软件安全领域都在关注保护应用程序之外的东西，比如网络。但无服务器提供了根据具体情况锁定单个系统和云调用的机会。以前，保存应用程序的容器可能捆绑了数百个系统调用，因此跟踪每个调用做什么以及它应该(和不应该)如何与其他服务交互的成本会非常高。但是，将这些调用分解成单独的操作，使安全专业人员能够对每个调用应用“最小特权”，确保没有人执行他们不应该执行的任何操作。

当然，这种方法以前也尝试过，比如用 SELinux T1，但是在很多情况下，为系统调用手工制作一套策略对任何一个开发人员来说都是一项繁重的工作。Protego 早期的名片——现在是 Check Point 武库的一部分——是自动检查无服务器代码，看看每个调用需要做什么，然后，通过扩展，找出代码需要什么系统或云权限来完成这项工作。然后很容易授予这些权限并阻止所有其他操作，从而保护应用程序。

有了无服务器，最小特权的概念变得非常强大。他说，如果我们可以说‘嘿，这个函数只能从这个表中读取’或‘这个函数只能向这个桶中写入’，那么应用程序的大部分攻击面就可以“通过将这些权限降至最低而消失”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>