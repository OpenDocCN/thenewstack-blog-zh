# Terraform vs. Ansible:哪个最适合你？

> 原文：<https://thenewstack.io/terraform-vs-ansible-which-is-best-for-you/>

[](https://www.linkedin.com/in/derekm1215/)

 [德瑞克·莫根

德里克是 Spacelift 公司的开发者拥护者。他在许多环境中工作过，从处理“实际金属”的国际托管服务提供商到托管服务提供商，再到大型培训公司。他还利用 Kubernetes 和其他尖端工具创办了一家制造技术提供商。德里克还拥有一家培训公司，morethancertified.com。](https://www.linkedin.com/in/derekm1215/) [](https://www.linkedin.com/in/derekm1215/)

为了获得更高的速度、安全性和可靠性，组织正在转向多云基础设施。手动管理拥有多个云提供商的大规模基础架构是不可行的。

这就是企业使用基础设施即代码(IaC)服务的原因。它使组织能够用代码定义基础设施。

编码的基础设施易于生产、维护、扩展和复制。它简化了基础架构的供应、配置和部署。

在众多可用的 IaC 工具中， Ansible 和 Terraform 在许多组织中相当流行。虽然 Ansible 和 Terraform 具有相似的功能，但它们有几个根本的区别。我们将在本文中仔细研究这些差异。

## 什么是 Terraform？

[Terraform](https://www.terraform.io/) 是一款开源的 IaC 工具，可以管理和配置多个云提供商的基础设施，包括 AWS、Azure、Linode 和 Oracle。它可以使用 API 连接不同的基础架构主机，以实现复杂的管理场景。由于 [Terraform 的模块化](https://spacelift.io/blog/what-are-terraform-modules-and-how-do-they-work)，可以使用提供商和社区构建的模块来扩展功能。

## 什么是 Ansible？

[Ansible](https://www.ansible.com/) 是一款开源的 IT 自动化工具，旨在实现供应、配置管理、应用部署和手动 IT 流程的自动化。虽然 Ansible 可以用于供应，但它在配置现有基础设施和自动化日常基础设施任务方面表现出色。

## Terraform 和 Ansible 的区别:

Terraform 和 Ansible 能够管理基础设施和与之相关的关键任务。许多开发人员一起使用它们，因为一个擅长配置，另一个擅长配置。

但是当您必须只选择一个进行操作时，您必须分析 Terraform 和 Ansible 之间的差异:

1.  流程编排与配置
2.  氯化氢对 YAML
3.  声明性与程序性
4.  可变与不可变
5.  状态管理
6.  云与内部

## 1.流程编排与配置管理

协调是创建基础架构和连接多个云提供商以构建虚拟机、网络组件和数据库的过程。该过程保持基础结构处于开发和运行应用程序所必需的状态。

配置管理包括在基础设施上安装软件、执行自动化的日常 IT 任务以及修补/更换损坏的软件。

Terraform 拥有广泛的解决方案来部署和维护可扩展的基础设施。不可变的代码、声明性脚本、状态管理和社区构建的模板使 Terraform 成为一种灵活的供应服务。

Ansible 专注于活动的配置方面。可变的逻辑和程序脚本有助于快速更新应用程序，并使依赖关系保持在功能状态。

Terraform 和 Ansible 都可以做编排和配置。然而，Terraform 是一个编排工具，Ansible 倾向于配置。

## 2.氯化氢对 YAML

Terraform 用户使用 HashiCorp 配置语言(HCL)定义资源。它是一种解释型语言，旨在用于基础设施部署。

Ansible 使用 YAML 语法，这是一种为配置管理设计的数据序列化语言。

## 3.声明性与程序性

机器可以通过两种方式接收指令:

*   程序性的:给机器一步一步的指令来执行任务。系统自上而下遵循清单来实现目标。
*   声明性的:结果是定义好的，机器可以采取任何方法来获得结果。

Terraform 的语言 HCL 遵循声明性逻辑。开发人员定义他们的基础设施，并使用`terraform apply`命令使基础设施达到期望的状态。系统读取状态文件，并相应地添加、删除和修改资源。

Ansible 是程序性的，这意味着被称为 [Ansible Playbook](https://www.redhat.com/en/topics/automation/what-is-an-ansible-playbook) 的脚本将从上到下执行。这就像提供一个包含执行一个动作的序列化步骤的蓝图。

## 4.可变与不可变

不可变的基础设施意味着基础设施的组件不能被改变和替换。如果您必须更改一个元素，您必须用更新的元素构建新的基础设施，并用它替换旧的基础设施。

修改基础结构中的单个组件会带来兼容性风险。创建一个单独的，测试其可靠性，然后用它代替旧的是安全的。

Terraform 构建不可变的基础设施。

但是这是一个耗费时间和资源的过程，不能用于频繁的任务，比如更换网络服务器或更新防火墙。这就是 Ansible 更适合配置的原因，因为它是可变的，可以快速修复/更改依赖关系，而无需从头重新创建一切。

## 5.状态管理

地形状态文件存储基础设施资源的更新信息。Terraform 将状态文件数据与现有资源进行比较，并根据需要修改基础设施资源。对基础结构的任何变动和更改都会保存到文件中。您可以随时查询 Terraform 状态文件，以了解当前的基础架构组件。

Ansible 不跟踪现有的配置状态。预期的更改会在所有目标机器上自动执行。它根据引入的更改维护现有状态，但是您必须查询当前状态才能了解执行细节。

谈到状态管理，Terraform 提供了一个全面的解决方案。

## 6.云与内部

Ansible 不区分本地和云基础设施的配置。一旦配置完成，您就可以使用 Ansible 配置组件。

Terraform 处理 API 以使用云提供商的资源来设置环境。因此，其功能仅限于本地基础设施。如果基础设施建立在本地，Ansible 是更好的选择。

## Terraform 和 Ansible 与太空电梯

如果能用 Terraform 做编排，用 Ansible 做配置，岂不是很棒？

太空飞船使这成为可能，也更容易管理。Spacelift 在历史上能够通过 Terraform、Pulumi、AWS CloudFormation 等管理生态系统的其余部分，现在它通过 [Ansible 支持](https://spacelift.io/blog/spacelift-ansible-integration-beta)获得了基础设施拼图的另一大块。

Spacelift 是一个复杂的持续集成和部署(CI/CD)平台，用于基础设施即代码。它是由长期的 DevOps 实践者根据以前的大规模安装经验设计和实现的。

您可以在不到一分钟的时间内从零到完全管理您的云资源，没有任何先决条件。它与该领域的大公司整合得很好——特别是 GitHub 和 AWS。

## Terraform vs. Ansible:选择哪一个？

Terraform 更适合创建和维护云资源。总是更新的状态文件保持基础结构信息的相关性，使复制更容易。使用 HCL 编写声明性代码非常简单。社区制作的模块为资源调配提供了可定制的模板。

Ansible 是管理配置的好选择。可变的配置允许用户快速改变有问题的元素。Ansible 也可以配置本地基础设施。Ansible 使用 YAML，它是专门为创建配置文件而设计的。

然而，更好的选择是通过太空运输同时使用它们。

但是，如果您只能选择一个，请检查您的基础架构，并找到团队需要帮助的地方—编排或配置。然后相应地选择 IaC 服务。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>