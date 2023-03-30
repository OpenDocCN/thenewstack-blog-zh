# GUI、CLI、API:学习基础设施即代码的基本术语

> 原文：<https://thenewstack.io/guis-cli-apis-learn-basic-terms-of-infrastructure-as-code/>

[](https://www.linkedin.com/in/timothy-clegg)

 [蒂姆·克莱格

蒂姆在甲骨文的开发者关系团队中领导开发合作项目。在那里，他用当前和新兴技术、弹性架构和工具构建解决方案，让生活变得更加轻松。在 LinkedIn @timothy-clegg 上与他联系。](https://www.linkedin.com/in/timothy-clegg) [](https://www.linkedin.com/in/timothy-clegg)

基础设施即代码(IaC)可能不适合所有人，但它适合几乎所有人。在构建云原生应用程序或进行多云操作时尤其如此，在这些情况下，基础架构组件的数量不断增长，而应用程序发布到生产环境的速度从未放缓。

[IaC](https://developer.oracle.com/what-is-iac/?source=:ex:pw:::::TNS_Y&SC=:ex:pw:::::TNS_Y&pcode=) 帮助您在保持协调的 DevOps 流程所需的顺序的同时，跟上加速、扩大和减少资源的步伐。但是如何开始使用 IaC 呢？我总是发现最好从理解你会发现散布在主题中的流行词汇和首字母缩略词开始，并为每一个建立一个坚实的定义。

以下是我对接触和管理云资源的四种方式的看法，以及我在每种方式中看到的一些优点和缺点。先说四个:GUI、CLI、API 和 IaC 工具。

## **图形用户界面(图形用户界面，又名控制台)**

我们大多数人开始使用 GUI 管理云资源，它通常采用控制台的形式，带有方便的按钮和转盘，通常直观且易于使用。

虽然 GUI 组件对于最初学习一个系统或平台来说可能很棒，但它们并不总是最具可伸缩性或最高效的。GUI 需要时间来操作和手动用户干预，除非你正在使用一些自动化的指向和点击，比如 Selenium，但是这是一个很好的例子。

有了图形用户界面，只有当有人看到灯从绿色变成红色，或者点击一个按钮时，事情才会“工作”。使用 GUI 快速管理资源是困难的(阅读:**不可能的**),尤其是在 web 浏览器中运行的 GUI。仅仅是指向和点击的时间，加上等待浏览器更新…一个 GUI 并不是超级快的。

另一个缺点是，如果出现问题，该界面很难回滚操作。回滚通常包括大量的指向和点击，撤销之前所做的更改。这需要更多的时间和人力。

结论:GUI 对于学习一个新平台来说是很棒的，但是对于维护实验室/沙盒环境之外的任何东西来说肯定是不理想的。

## **CLI(命令行界面)**

CLI 比 GUI 好一点，因为它发出的不是指向和点击，而是文本命令。CLI 实际上是一个文本用户界面。许多 CLI 允许“无头”运行，这意味着它们不需要用户输入，因为所有的指令都可以在程序启动前提供。这里的一个好处是在自动化工作流程中使用 CLIs 更容易[。](https://blogs.oracle.com/cloud-infrastructure/post/introducing-o-the-easy-way-to-use-the-cli?source=:ex:pw:::::TNS_Z&SC=:ex:pw:::::TNS_Z&pcode=)

CLI 是管理 DevOps 部署的正确方向上的一步，但是除非使用某种脚本(shell 脚本、Ruby、Python 等)。)，使用 CLI 时不可能嵌入任何种类的逻辑。在这方面，CLI 并不比 GUI 更好。

结果:CLI 非常适合向部署发送单个命令——甚至是一串命令。然而，如果不使用更复杂的脚本逻辑，很难保持高水平的保证。

## **API(应用编程接口)**

谁不喜欢 API 呢？API 允许对软件服务进行编程控制和监督。最终，几乎所有东西都与底层 API 交互，包括 GUI 控制台和 CLI。

虽然可以用 API 自动化 IaC 控制，但这并不容易。我们中的许多人已经编写了与 API 交互的小脚本/应用程序来实现某些结果，这很棒，但是创建这样的脚本和应用程序需要大量的手动操作。对于我们许多人来说，为每种类型的管理需求定制一个脚本/应用程序需要时间。虽然这一过程提供了极大的可定制性——您所能做的是无限的——但是直接使用 API 对于日常管理任务来说是不切实际的或者不可扩展的。

所有的云提供商都提供了一个管理平台的 API。例如，在我看来，Oracle 为开发者和其他用户提供了一个很棒的 API 接口。此外，聚集和简化 API 交互的 API 工具也很有用，使得与 API 的交互更加容易。

结论:API 是一个必要的组件，但一般用户可能不会直接与之交互。

## **IaC 工具**

所以现在我们来看 IaC 工具，它是从头开始设计的，旨在帮助您使用代码管理基础设施资源。

使用 IaC 工具，每个资源都是用代码定义的，工具本身提供了必要的结构和逻辑来快速定义您需要和想要的环境。基本的框架，比如逻辑元素和 API 交互，被抽象出来，允许您专注于描述您需要/想要在环境中存在的资源。

IaC 工具是迄今为止构建和维护云环境最简单、最快速的方法——顺便说一下，并不局限于云。内部资源通常可以使用 IaC 工具进行管理。您是否使用多家云提供商？更有理由使用 IaC 来管理您的 IT 基础设施。

有了 IaC，许多开发人员在后端使用 git，允许您获得大量的更改历史，这也允许轻松快速的回滚。通过使用 git 存储代码定义，您可以使用标准的流程和工具来监控、管理和批准基础设施的变更。

此外，无论是使用策略即代码(如[开放策略代理](https://www.openpolicyagent.org/))，还是使用开放策略代理在 OCI 实施[策略即代码(如手动拉取请求/合并请求审查流程)，您都可以拥有一个可靠的审查/批准/合规机制，更不用说另一个独立于云/平台本身的审计跟踪了。](https://github.com/oracle-devrel/oci-pac-opa)

最常见和最流行的 IaC 工具之一是 HashiCorp 的 Terraform。虽然一些工具主要在配置管理领域工作，如 Ansible、Chef 和 Cinc，但 Terraform 更适合基础设施管理。

[甲骨文云基础设施(OCI)](https://www.oracle.com/cloud/?source=:ex:pw:::::TNS_W&SC=:ex:pw:::::TNS_W&pcode=) 支持许多 IaC 工具。例如， [OCI](https://docs.oracle.com/solutions/?q=&cType=reference-architectures%2Csolution-playbook%2Cbuilt-deployed&sort=date-desc&lang=en&source=:ex:pw:::::TNS_V&SC=:ex:pw:::::TNS_V&pcode=) 可以使用 Terraform 来管理基础设施资源，当与 Ansible 这样的传统配置管理工具结合使用时，它会变得非常强大。我们喜欢 Terraform，因为它很成熟，被广泛采用，可以与各种各样的云平台配合使用。

结论:对许多人来说，Terraform 是一条出路。如果你想开始，HashiCorp 提供了一系列七个“[开始——OCI](https://learn.hashicorp.com/collections/terraform/oci-get-started)”教程来帮助你。如果你是 Terraform 的新手，你有点生疏，或者你只是想填补你知识中的任何潜在空白，那些教程是值得学习的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>