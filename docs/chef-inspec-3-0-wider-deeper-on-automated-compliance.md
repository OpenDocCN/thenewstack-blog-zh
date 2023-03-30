# Chef InSpec 3.0:更广泛、更深入地实现自动化合规

> 原文：<https://thenewstack.io/chef-inspec-3-0-wider-deeper-on-automated-compliance/>

自动化厂商 [主厨](http://www.chef.io/) 继续打造其 InSpec 合规工具，旨在使其更易于使用，覆盖范围更广，尤其是在高度混合的环境中。

今天发布的[InSpec 3.0 为](https://blog.chef.io/2018/10/16/announcing-inspec-3-0/) [Terraform](https://www.terraform.io/) 引入了插件架构、改进的异常管理和自动化合规性，Terraform 是一个开源工具，它将 API 编译成声明性配置文件，可以更容易地在团队成员之间共享。

InSpec 是一种用于描述安全性和合规性规则的开源语言，旨在用于软件交付过程的所有阶段，而不会对该过程产生副作用。

Chef 的产品和工程高级副总裁 Corey SCO bie[在发布会上表示:“在异构环境中建立和维护合规性是一项艰巨的任务，不断变化的监管要求和快速发展的混合 IT 战略使这项任务变得更加艰巨。](https://www.linkedin.com/in/coreyscobie/)

InSpec 3.0 的新功能:

*   **插件架构，**可用于 InSpec 和 Train，构建 InSpec 的[传输接口库](https://www.x.org/releases/X11R7.7/doc/xtrans/xtrans.html)扩展了可开发用于 InSpec 的通信协议和资源类型的范围。
*   **改进的异常管理**使跳过特定节点上的某些 InSpec 控制的执行变得更加容易，并跟踪可接受的故障，以提高核心审计和补救能力并最大限度地减少混乱。
*   **工作流增强 API，**配置文件*之间的稳定 API*——类似于厨师食谱的合规性测试组——和*属性*——使用户能够修改如何进行测试的数据。对概要文件打包(出售)机制的改进允许开发人员更容易地迭代带有依赖项的 InSpec 概要文件。
*   **Terraform 的合规性:**此供应器插件可在 terra form 运行期间执行，以在一次操作中验证虚拟机和云基础架构的状态。此外，Inspec-Iggy(“Inspec Generator”，或 I.G .)使用户能够从 Terraform 状态文件生成合规性控制。
*   **兼容谷歌云平台**，以插件的形式为 GCP 提供原生支持。它还在 [Chef Automate](https://www.chef.io/products/automate/) 中提供优质 InSpec 内容，以支持互联网安全中心(CIS) [针对 GCP](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/) 的基准测试，从而确保跨云应用和基础设施的合规性。
*   **改进了控件的元数据接口:** InSpec 3.0 引入了基于键值的描述接口，允许对控件进行更细粒度的跟踪和重复数据删除，以增强合规性报告。它还允许用户创建自己的元数据类别，以满足自己的报告需求。

InSpec 最初用于测试操作系统和节点配置及服务，但随着 2 月份 [InSpec 2 的发布](https://thenewstack.io/moving-beyond-limits-infrastructure-testing-inspec-2-0/)，扩展到了基础设施机群的全栈测试。InSpec 2 增加了对在云环境(如 Microsoft Azure 和 AWS)中测试配置的支持，以及速度和工具方面的改进。它使开发人员能够使用 Automate 作为合规性配置文件的来源，存储用于合规性和安全审计的 InSpec 报告，并能够以 JUnit 格式导出报告，以便集成到 Jenkins 等 CI/CD 工具中。

与此同时，Chef 已经从关注基础设施转向更加以应用为中心的观点。正如 Chef 的高级产品经理张秀坤·里希特在《新堆栈制造商》的一集里所解释的那样，随着应用程序在不同环境之间移动，为它们设置的安全性和合规性规则也需要随之移动。

在[的另一集](https://thenewstack.io/how-aws-uses-chef-in-a-post-container-world/)中，AWS 的[高级软件开发经理 Jonathan Weiss](https://www.slideshare.net/jweiss) 和[软件开发经理 Mark Rambow](https://www.linkedin.com/in/markrambow/) 讲述了 Chef 如何让他们在基于容器的世界中规模化运营。

根据[2018-2019 年世界质量报告](https://software.microfocus.com/en-us/assets/application-delivery-management/world-quality-report-2018?)，自动化在测试和安全方面继续增长，但[的使用率仍然很低](https://thenewstack.io/testing-automation-perspectives/)。对 1，700 名 IT 决策者的调查发现，只有 16%的性能测试案例是用测试自动化工具执行的，安全测试也有类似的比例。

在毕马威的调查中，超过一半的首席信息官和首席合规官表示，他们没有实现合规自动化，只有五分之一的人制定了明确的战略来实现这一目标。

根据[毕马威会计师事务所的 Amy Matsuo](https://www.prnewswire.com/news-releases/kpmg-study-finds-majority-of-companies-are-not-yet-automating-compliance-activities-300713691.html) 的说法，虽然公司正在自动化日常运营任务以提高效率和削减成本，但“下一步是组织从在运营流程中使用自动化转向部署 it 以实现合规性分析和预测目的。为此，他们必须首先确定可自动化的合规活动的优先级，同时设定预期投资回报。”

厨师是新堆栈的赞助商。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>