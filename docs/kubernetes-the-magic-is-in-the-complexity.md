# Kubernetes:神奇之处在于复杂性

> 原文：<https://thenewstack.io/kubernetes-the-magic-is-in-the-complexity/>

任何关于 Kubernetes 的讨论最终都落在一个常见的抱怨上:它是复杂的 T2。这就是为什么 Kubernetes 的学习曲线如此陡峭，以及为什么开发人员的经验经常被认为是缺乏的。在众多围绕 Kubernetes 涌现的公司和技术中，有相当一部分将降低复杂性作为其核心优势之一。

那么为什么 Kubernetes 如此复杂呢？这种抱怨有多合理？让我们开始吧，因为它很复杂。

## **复杂性是个问题吗？**

“这是一个非常强大的平台，”Kubernetes 服务提供商 Fairwinds 的战略副总裁 Joe Pelletier 谈到 K8s 时说。“如果你想运行真正出色的运营，这是最好的平台，但我们已经知道，运行出色的运营仍然是一件复杂的事情。”

复杂性是否是一个问题通常归结于用户的复杂程度。这不仅仅是一个个人技能的问题——不是所有的工程团队都有相同的技能水平，或者在尝试新项目时都一样得心应手。事实上，许多组织最终发现采用 Kubernetes 所需的程序和组织上的改变比向个人传授新技术更具挑战性。

对于非常复杂的团队来说，无论是在技术上还是在适应新工作方式的能力上，Kubernetes 的复杂性都不太可能成为问题。随着 Kubernetes 变得越来越主流，复杂性管理成为一个严重的问题。

当然，仅仅是弄清楚如何管理复杂性，或者涉水通过用于保护 Kubernetes、管理资源使用、连接到存储、连接到传统环境、桥接公共云和私有云的许多技术，都是一项重大努力。“复杂性的一部分在于可供选择的方案数量太多，”Pelletier 说。

在某种程度上，称库伯内特为“情结”可能是不公平的。毕竟，Kubernetes 是为处理用[微服务](https://thenewstack.io/category/microservices/)构建的应用而设计的。云监控公司 [Sumo Logic](https://www.sumologic.com) 产品营销副总裁 [Kaylan Ramanathan](https://www.linkedin.com/in/kalyanramanathan/) 说:“这些应用程序一开始就相当复杂。“它不再是一个整体了。它是许多服务，与其他服务进行对话。“更复杂的是，这些应用程序在不断变化。

因此，考虑到 Kubernetes 所做的一切，它所处的生态系统以及它被设计来支持的应用类型，如果 Kubernetes 是简单的，那将是令人难以置信的。Kubernetes 的存在是为了帮助管理容器化微服务架构的复杂性。

然而，拥有这样一个复杂的编排平台可能会导致具体的问题。“当出现问题时，复杂性会影响交付速度和恢复速度，”Kubernetes 之上的应用管理框架 [Shipa](https://www.shipa.io) 的创始人 [Bruno Andrade](https://www.linkedin.com/in/bruno-a-a369028/) 说。

那么能做些什么呢？

## **这是谁的问题？**

“在我看来，Kubernetes 是为了协调基础设施，”安德拉德解释说。“Kubernetes 是很棒的中间件，但是要使用 Kubernetes，您必须知道什么是部署集，持久卷和持久卷声明是如何工作的。我认为问题是我们把开发者拖到了这个水平。”

或者，正如 Ramanathan 所说，“这是一个字母汤，你必须了解它才能运营好 Kubernetes。”这只是在应用层。

实际上，Kubernetes 复杂的坏名声部分可能是由于不习惯处理基础设施的开发人员通常无法获得 Kubernetes 完全隐藏的无缝体验。这看起来很复杂，因为有很多东西他们并不真正理解。把它想象成学习一门新的语言:开始时，它看起来非常复杂，但当你成为专家时，一切都变得不费力了。

“我认为我们在库伯内特生态系统中看到的一部分是有许多不同的成分，”Pelletier 说。至少，通常有一个平台或开发团队主要负责 Kubernetes 的工作。可以说，他们的“客户”是开发人员，许多人认为他们最终被迫与 Kubernetes 进行过多的互动。Kubernetes 对平台团队来说并不复杂——基础设施是他们的专长。但是对开发者来说…哎呀。

## **你如何解决复杂性？**

首先，似乎很少有人认为核心 Kubernetes 本身应该变得不那么复杂。相反，有不同的方法来管理复杂性，不需要改变“引擎”，只需要放入一个更好的方向盘。

Fairwinds 的开源软件主管 Robert Brennan 解释说:“实际上，它似乎是安装在 Kubernetes 之上的东西。“因此，如果你最终发展到需要更多控制的地步，你可以随时进入核心 Kubernetes，亲自动手。”

Kubernetes 的公共云提供商版本通过托管 Kubernetes 服务、专门构建的仪表板和一套自动化工具降低了复杂性，许多其他商业项目也是如此。一般来说，这些选项比普通的 Kubernetes 更加固执己见，但是它们有助于平台团队和开发人员简化事情。这通常表现为安装护栏，以确保开发人员不会把事情搞砸。

在组织和程序层面，降低复杂性的关键是通过自动化:当有人必须手动转动所有旋钮时，Kubernetes 会感觉复杂得多，但一旦正确的自动化工具到位，配置或策略只需设置一次。

## **Bug 还是特性？**

很难说复杂性不是 Kubernetes 设计的核心特征。它被有意设计成具有高度可配置性、适应性和可扩展性。几乎根据定义，这意味着它非常复杂。“没有人有不能被 Kubernetes 解决的用例，”布伦南解释道。

与此同时，同样清楚的是，这种复杂性是一个巨大的进入壁垒，尤其是对于已经在处理复杂的应用程序体系结构并且可能不是最复杂的云推进工程团队的大型组织而言。

随着 Kubernetes 从处于云革命最前沿的组织使用的技术转变为主流企业技术，复杂性问题可能必须得到更彻底的解决。有大量证据表明，社区正朝着这个方向发展，在未来，将会有“给我所有旋钮”人群和“让它简单”人群的选择。然而，用户只需要明白他们可以拥有无限的灵活性或者简单性，但是不能同时拥有两者。

监管 Kubernetes 项目的云计算原生计算基金会是新堆栈的赞助商。

在 [Unsplash](https://unsplash.com/s/photos/magic?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上由 [Artem Maltsev](https://unsplash.com/@art_maltsev?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>