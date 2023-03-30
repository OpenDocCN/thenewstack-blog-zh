# 敏捷团队可以对 API 采用设计优先的方法吗？

> 原文：<https://thenewstack.io/can-agile-teams-have-a-design-first-approach-to-apis/>

有些事情就是不能在一起，比如在任何科技活动中找到一杯像样的咖啡。(老实说，我刚刚接受了这样一个事实:演示越好，咖啡就越差。)但有时，事情会以你意想不到的方式发生，然而这种组合实际上是有效的。

当我们重新思考团队如何用 Kubernetes 构建和管理 API 时，这就是我们的感受:为什么我们不能有很棒的咖啡和很棒的演示呢？为什么团队不能一边构建一边迭代和实验？这也是我们在 API 方面全力以赴的原因。听我说完！

## 设计第一

 [克里斯托弗·琼斯

Christopher 在技术和产品管理领域拥有近 20 年的经验，从中小型企业到财富 50 强企业，他一直担任软件工程师、经理和总监。他是一名技术通才，利用自己丰富的经验，通过持续改进、有效协作和经验过程来帮助人们和组织解决复杂的问题。他会热情地参与任何关于敏捷、scrum 或烧烤的讨论。](https://www.linkedin.com/in/crjonesus/) 

当你听到“设计第一”时，警报开始响起，对吗？将会有架构师和分析师创建长期合同、多个电子表格或文档，以及无数次关于我们在某个时候将要构建什么的会议。

在设计上的大量投资通常会导致项目中的许多意外和不可预见的问题，更不用说在开发过程中学习偏离主计划时所涉及的团队之间的脱节。整个前提违背了敏捷原则。

但是如果我们让设计过程本身变得敏捷会怎么样呢？如果我们利用 OpenAPI 规范构建一个最小版本的 API(有些人可能称之为 MVP)，并在后端构建一个没有任何东西的 mock，只是为了测试它，会怎么样？

知道了答案，你的团队就可以很容易地合作，解决你构建原型时出现的任何问题，而不是在构建时去解决它们。

## 敏捷原则

为了理解设计第一的阻力，我们应该更仔细地看看[敏捷原则](https://agilemanifesto.org/principles.html)。早在 2001 年，一群行业领导者在周末聚在一起，创建了敏捷软件开发宣言，这是文档驱动的重量级软件开发过程的替代方案。这可以归结为四个关键价值:

*   **流程和工具上的个人和交互**
*   **工作软件**全面文档化
*   **客户协作**合同谈判
*   **根据计划应对变化**

敏捷团队以迭代的方式一起工作，协作创建工作软件，并在需求发生变化时做出响应。他们不会陷入关于合同、撰写文档或坚持僵化流程的广泛谈判中。而且他们绝对不需要文档或者详细的需求就可以开始。

## OpenAPI

如果我们谈论 API 开发，尤其是 RESTful APIs，我们不能忽略由 [OpenAPI 倡议](https://www.openapis.org/about)维护和驱动的 [OpenAPI 规范](https://spec.openapis.org/oas/latest.html)。OAI 最初基于 SmartBear 的 Swagger 规范，是一个标准化的、供应商中立的描述 API 的规范。

利用 OAI 作为设计工具意味着您的设计文档成为描述 API 功能和操作特性的开发工具。另外，您可以在进行更改时使用它来生成文档。

事实上，在 KubeShop，我们实际上以 OpenAPI 为中心[我们自己的 API 工作流程](https://kusk.kubeshop.io/)，作为功能和操作的单一来源，所以我们可以取消额外的配置文件，因为我们讨厌复杂的东西。

## 设计优先的方法

遵循敏捷开发的原则，并利用 OAI,“设计第一”看到团队在开发开始之前设计 APIs 构建模型，查看响应，然后合作创建合同来工作。

设计优先应该很快。API 规范应该很快完成，最好是在几个小时或几天内，API 的原型(或模拟)应该引导设计对话，并加速构建最终产品。

## 库斯克的案子

在 Kusk，我们厌倦了电子表格，并试图在孤立的团队中工作。我们追求真正的灵活性，所以我们为它创建了一个解决方案: [Kusk Gateway](https://kusk.kubeshop.io/) 。我们的 Ole Lensmar，[写了关于](https://medium.com/kubeshop-i/beta-1-release-of-kusk-gateway-openapi-driven-kubernetes-ingress-controller-bac5d2c03ed8)测试版的文章，完美地包装了 Kusk:

*"*[*Kusk Gateway*](https://kubeshop.github.io/kusk-gateway/)*是一个开源入口控制器/API 网关，它使您的 OpenAPI 定义成为 API 功能和操作方面的真实来源，支持使用 Kubernetes 进行 API 开发的迭代设计优先方法。"*

我们希望创建一个工具，将设计过程转移到 API 开发工作流程的中心。使用 Kusk Gateway，API gateway 知道您的 OAI 定义，并可以看到响应的样子，从而为最终用户生成模拟响应。这样，并行工作，您的后端团队可以开始构建真正的 API——实现更快的无代码原型！这种方法还将支持产品和消费者团队之间的协作，他们可以在构建 API 原型的同时一起工作于紧急设计。

随着实际后端功能的开发，这些原型可以被迭代地替换。看看这个[伟大的教程](https://kubeshop.io/blog/rapidly-prototype-your-apis-on-kubernetes-with-kusk-gateway)，它来自我们的 Abdallah Abedraba，介绍如何使用 [Kusk Gateway](https://github.com/kubeshop/kusk-gateway) 实现快速原型开发。

我们的愿景是一个工具，它支持迭代开发，简化协作并减少依赖的影响，因此您可以摆脱无休止的设计草案、电子表格和那些尴尬的会议，这些会议让您担心去团队异地静修，因为您已经与太多的利益相关者发生了冲突。

由于 OpenAPI 定义是 API 的功能和操作方面的事实来源，它实际上成为了您的配置和文档。您的开发团队可以将 API 的规范提供给 Kusk，并准备好入口资源——随时更新开发人员所做的任何更改。

## 试试 Kusk Gateway

看看 [Kusk Gateway GitHub 库](https://github.com/kubeshop/kusk-gateway)并下载[最新版本](https://github.com/kubeshop/kusk-gateway/releases)。安装说明和文档也可从[处获得](https://kubeshop.github.io/kusk-gateway/)。另外，如果你有任何问题或想法，请随时加入我们的[不和谐服务器](https://discord.gg/uNuhy6GDyn)并取得联系。

如果你今年 10 月参加了 kube con+CloudNativeCon North America,那就来和我们一起打个招呼，共勉一下科技盛会吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>