# 基础设施即代码变为低代码/无代码

> 原文：<https://thenewstack.io/infrastructure-as-code-goes-low-code-no-code/>

基础设施即代码(IaC) 面临的挑战是，它可能会跨越多个领域，需要安全专业知识、开发人员编程技能和 it 运营的部署能力。

[DuploCloud](https://duplocloud.com/platform/) 的首席执行官兼创始人[文卡特·蒂鲁文达姆](https://www.linkedin.com/in/venkat-thiruvengadam-35a7396)说:“代码不会自己写出来——在操作和安全方面，你仍然需要大量的专业知识。“开发人员只是将基础设施用作代码和构建软件的想法，我认为它开始遇到挑战，因为虽然他们知道如何进行编程，但开发人员不知道运营，因为他们不是 IT[运营]人员，他们不知道安全，因为他们不是安全人员。”

标准普尔全球市场情报公司 [451 Research](https://451research.com/) 的分析师 [Jay Lyman](https://www.linkedin.com/in/jaylyman/) 表示，基础设施即代码工具越来越受欢迎，因为它们自动化并简化了在混合或多云环境中部署的复杂性，现在是在边缘计算中。

“这是我们看到基础设施即代码和 GitOps 的吸引力的一个重要原因，在这种情况下，您可以提供跨不同环境、跨开发测试和生产的一致性，”Lyman 说。“基础设施即代码，如果部署得当，可以帮助您降低一些复杂性；您可以减轻配置和环境漂移。”

“IaC 解决方案市场相对成熟，”道格拉斯·雷诺兹说，他是卡内基梅隆大学软件工程学院 CERT 部门的软件工程师，他已经研究过这个市场。

雷诺兹告诉新堆栈“你将看到的变化将更多地朝向基本上运行工具的协调器。“如果你选择 Ansible，很多时候是临时运行，或者有一台机器在运行它。厨师，你可以登录系统，手动执行代码来运行它。[……]所以我认为 orchestrators 带来的最大变化是，它基本上为您提供了这些工具的用户界面。”

Thiruvengadam 认为市场颠覆的时机已经成熟。Thiruvengadam 告诉新的 Stack 说，IaC 需要的跨学科技能——拥有安全、操作和编码经验的人——是一个利基。总部位于加州圣何塞的 DuploCloud 瞄准了那些需要一个[低代码/无代码](https://thenewstack.io/low-code-does-not-mean-low-risk/)解决方案的人。

“Duplo cloud 的总体想法是，你可以使用基础设施即代码，但你只需编写少得多的代码行，”他说。“许多不具备所有这三种技能的人仍然可以使用这项技术以同样的规模和效率运营，这是根本的核心优势。”

与依赖于现成模块或库的一些解决方案不同，Thiruvengadam 表示，DuploCloud 使用低级代码接口为其基于规则的引擎整合规则，然后该引擎运行规则以产生输出。

自托管单租户解决方案部署在客户的云帐户中。目前，它支持在 Amazon Web Services、Microsoft Azure 和 Google Cloud 上部署，也可以在内部运行。

该软件在虚拟机中运行，使用授予虚拟机的权限，通过 API 获得调用云提供商的权限。例如，[文档提到](https://docs.duplocloud.com/docs/faq)，在 AWS 中，它将通过实例配置文件，而在 Azure 中，它将通过托管身份。

DuploCloud 指出，配置漂移、系统故障、安全性和合规性控制由与云提供商交互的解决方案持续监控。Thiruvengadam 说，结果是它保持了配置的高保真度副本，这减少了错误，确保遵守合规标准，并提高了安全性。他补充说，该解决方案还保留了变化的历史。

DuploCloud 并不生成 [Terraform](https://thenewstack.io/how-to-scale-your-terraform-infrastructure/) 代码，而是在 Terraform 中提供了一个名为 DuploCloud Terraform Provider 的软件开发工具包。该文档称，这“允许用户使用 DuploCloud 结构来配置云基础设施，而不是直接使用较低级别的云提供商结构”。“这允许用户获得 IaC 的好处，同时显著减少需要编写的代码量。DuploCloud Terraform 提供程序调用 DuploCloud APIs。

Thiruvengadam 承认这是一个抽象层，它夺走了对老一代工具的一些控制，如[木偶](https://thenewstack.io/puppet-missed-the-kubernetes-boat-then-perforce-came-along/)和[厨师](https://thenewstack.io/chef-extends-security-and-compliance-across-hybrid-cloud/)。但他将这与 Java 和其他高级编程语言出现后 C 和 C++程序员经历的失控进行了比较:人们担心内存分配，但在 99%的用例中，Java orchestrator 在没有人工干预的情况下处理了这一问题。

“只是人们需要一些时间来接受这一点；现在，当他们写程序时，没有人谈论分配内存，”他说。“所以这只是让人们习惯并接受它。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>