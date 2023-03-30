# 用 Node.js 构建特性标志的标准接口

> 原文：<https://thenewstack.io/building-a-standard-interface-for-feature-flags-with-node-js/>

[](https://www.linkedin.com/in/vincegando/)

[Vince Gandolfo](https://www.linkedin.com/in/vincegando/)

[Vince 是 LogDNA 的一名软件工程师，他主要负责 LogDNA 的后端服务，使用 Node.js、Elasticsearch、Kubernetes 等等。他研究过 LogDNA 的许多特性，包括归档、使用配额和模板库。](https://www.linkedin.com/in/vincegando/)

[](https://www.linkedin.com/in/vincegando/)[](https://www.linkedin.com/in/vincegando/)

特性标志是许多现代开发过程的重要组成部分。它们帮助我们将部署从发布中分离出来，并获得对用户访问的更多控制，它们还允许我们打开和关闭特性。然而，仅仅启用特性标志是不够的。为了有更可预测的版本，有必要为如何使用标志创建一个标准过程。

在 LogDNA，特性标志是我们软件开发生命周期(SDLC)的一部分，但没有以标准的方式组织，这导致了整个组织的混乱。例如，在我们的 web 应用程序中，特性标志有多个来源。从那里，他们以一种不可预知的方式被组合到一个地方。这使得很难知道什么优先，存在什么覆盖。

在后端，特性标志被附加到数据库中的帐户记录上，甚至存储在环境变量中。在数据库中存储标志会带来复杂性和风险——当标志需要更新时，这正是您试图避免的事情 *—* ,因为您必须手动修改生产数据库或使用工具进行批量更新。此外，不再需要的旗帜被到处乱放会造成混乱。

## 采用黑暗发射

为了解决这些痛点，我们采用了[黑暗启动](https://launchdarkly.com/?utm_content=inline-mention)。现在，我们有了一个存放所有功能标志的中心，以及推出新功能的标准流程。我们不仅可以挑选特定的帐户来切换特性，还可以基于特定的属性来定位帐户。

例如，我们支持十几个 IBM 环境中的客户，以及我们在 LogDNA 基础设施上托管的直接客户。有些情况下，我们希望只为 IBM 帐户或 LogDNA 帐户切换一个特性。launch crystally 甚至提供百分比推出，只有一定百分比的帐户看到一个新功能。这有助于 A/B 测试，并有助于在新功能出现问题时减少影响。使用 launch crystally，无需回滚即可禁用帐户的功能，这在发生事故时很有帮助。或者，如果某个功能顺利地推广到某个百分比的客户，我们可以轻松地将其提升，以便所有客户都能看到该功能。

采用 LaunchDarkly 帮助我们更快地行动，进行更多的试验并降低风险。然而，我们希望通过创建一个与服务交互的标准化接口来进一步推动它的功能。

## Node.js 客户端

由于我们的代码库是用 Node.js 编写的，所以我们决定围绕 LaunchDarkly 的 node-server-sdk 构建一个包装器。我们希望它能够从 launch crystally 读取标志，执行一些验证，并在发送到 launch crystally 以请求功能标志之前格式化用户数据。

客户端的最初实现工作得很好，但是我们最终遇到了一些问题。在测试过程中，我们发现我们需要添加大量代码来捕获 launch crystally 的 sdk 客户端发出的请求，并模拟它收到的结果。这太费事了，需要特定于供应商的逻辑才能让测试工作。此外，这将需要在每个项目中重复我们想要添加我们的客户。我们不得不回到绘图板，以一种使测试简单的方式设计客户端。

在新版本的客户端中，我们希望抽象出特定于供应商的逻辑，并消除对客户端功能进行猴子修补的需要。客户端现在有几个新的存储后端选项，它们决定从哪里读取功能标志。“内存”后端维护一个本地存储，只是一个普通的旧 javascript 对象，用于添加和读取标志，而“虚拟”后端只是返回您传递给它的默认标志值。这两个新的后端选项对于测试来说都很棒，并且使得将客户端添加到我们的任何存储库变得更加容易。最后，“launch crystally”后端直接从 launch crystally 读取标志，就像以前的版本一样，主要用于生产中。

特性标志客户端现在可以放在我们代码库中的任何地方。它只需要添加少量代码，并且用它进行测试相对简单。

## 结论

对于 LogDNA 工程团队来说，采用 launch crystally 是推出健壮的特征标记过程的第一步。使用定制的 Node.js 客户端来标准化我们与服务的接口将这一过程提升到了一个新的水平，现在我们比以往任何时候都更有信心进行部署。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>