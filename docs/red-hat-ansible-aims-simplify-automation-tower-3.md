# Red Hat Ansible 旨在通过 Tower 3 简化自动化

> 原文：<https://thenewstack.io/red-hat-ansible-aims-simplify-automation-tower-3/>

随着几层流程被视为数据中心基础设施的一部分，任何推广“数据中心自动化新方法”的公司都可能迎合 DevOps 社区、数据中心经理或首席信息官。周三， [Red Hat](https://www.openshift.com/) 宣布了对其 [Ansible Tower](https://www.ansible.com/tower) 自动化包的更新——如果你马上想到，让我们通知 DevOps 团队，请稍等。那不是红帽这次瞄准的观众。

正如[红帽子的 Ansible 工程高级总监 Tim Cramer](https://twitter.com/tjcramer) 告诉新的堆栈，Ansible Tower 版本 3 是面向桥另一边的所有 IT 经理和高管的一个游戏，这些 IT 经理和高管来自 Ansible Core 的典型 DevOps 用户。

“我们通常认为 Ansible Core 是一种非常自下而上的使用方式，”Cramer 说。“我们有很多人在网上找到它；这让他们的工作变得更容易，当他们开始这样做的时候，它在一个组织中火了起来。Tower 在销售上似乎更倾向于自上而下，更多的是经理们开始对 Ansible 在他们的组织中的使用进行控制。”

## 我们已经改造了

为了吸引这些管理人群，Ansible Tower 被打包成一种应用程序。对于版本 3，前端已经针对新的使用模式进行了彻底的重新设计，增加了仪表盘和数据汇总，这已经使实时分析市场受到经理和高管的欢迎。

“我们重写了我们的后端，并且[*在前端增加了*一个新的可视化，”克莱姆说。“过去很难弄清楚，尤其是对于第一次使用的用户来说，他们实际上如何访问剧本并运行它。因此，他们必须能够访问作业模板和库存，您必须拥有这些不同的可用权限，并且您必须弄清楚如何授予他们这些权限—这非常令人困惑。如果你成功了，那当然很好，但你必须到达那里。”

Cramer 告诉我们，随着新的可视化方案的出现，旧的“向导”式的类别遍历方案已经被一个双窗格布局所取代，他承认这在一定程度上是受亚马逊 AWS 成功的启发。类别列在左边的一列中，详细信息显示在右边的一组可滚动页面中。图形已经被简化和流线化，如顶部的例子。他说，对于那些只想从 Ansible 命令中获取 **stdout** 值的操作人员来说，这也应该会让他们的生活变得更加轻松。

与 Slack 的新一轮集成使运营团队成员、他们的经理和 Ansible 平台能够有效地合作，在一组新正式的*通知*发生时做出响应，如右图所示。

Cramer 解释说:“在一项工作成功或不成功完成时，你可以通过电子邮件、HipChat、Slack、IRC 或一般的 web 挂钩获得通知。所以你可以把它挂在 BMC[*服务台*或 ServiceNow 上，这样就可以启动流程中的下一个项目。”

例如，他继续说道，假设一个开发人员执行了启动一轮自动化测试的代码。当这些测试结果为阳性时，Tower 3 可以生成一条消息，然后由 ServiceNow 使用。这样，当测试完成时，可以通知生产操作人员，这样她就可以将代码推向生产。

## 你可以看看这个

最近几个月，Red Hat 一直在通过一个涉及专业服装零售商 J. Crew 的用例，向客户的高管推广 Ansible Tower。在最近的几次红帽活动中，包括最近的红帽峰会和之前的 AnsibleFest，红帽认为 Tower 生成的报告可以被运营部门以外的人理解。

[最近的一篇公司博客文章](http://eventsblog.redhat.com/2016/06/28/lessons-using-ansible-at-j-crew/)总结了这部分用例，其中一部分写道:“在 Red Hat 实现 Ansible Tower 的过程中，[ *J. Crew* ]发现该工具生成了很棒的报告。他们为经理、QA 团队等创建报告。通过这些报告，他们能够自动化日常工作，摆脱无意义的工作。毕竟，如果你雇佣了聪明人，你希望他们解决问题，而不是整天担心复印文件之类的事情。”

但不是无意的，Red Hat 的 Colby Hoke 立即在那句话后提到了 **tower-cli，一个**命令行界面。默认情况下，您可能会认为任何基于命令行的工具都只是为 DevOps 专业人员定制的。但 Hoke 指出，CLI 工具使 Ansible 能够与组织的现有配置管理和自动化框架集成，包括 Jenkins。

对于首席信息官来说，这一信息可能与报告可以大声朗读的消息一样有趣。

Ansible 的首席工程师解释说:“对于 Chef 来说，你真的需要能够编程——你必须是一名 Ruby 开发人员，才能真正让产品实现你所要求的自动化。“有了 Ansible，你就不用了。这是一种特定于领域的语言， [YAML](http://yaml.org/) ，它的设计使得编写 shell 脚本的人可以很容易地掌握它。人们将抓住 Ansible，并在几个小时内开始自动化事情。”

他还告诉我们，对于 Tower 3，“我们现在有能力实现物理网络的自动化。”他指的是直接处理网络交换机和其他设备的能力，包括来自思科、Juniper Networks 和 Cumulus 的部件——这是去年 2 月添加到 Ansible Core 2.1 的[功能。](https://thenewstack.io/red-hat-ansible-will-handle-networking/)

现在，凭借解决网络设备过于陈旧而无法包含自己的 API 的能力，物理网络自动化功能有助于 Red Hat 支持其支持*集成*——另一个贴近 Tower 目标受众核心的观察词。

Red Hat 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>