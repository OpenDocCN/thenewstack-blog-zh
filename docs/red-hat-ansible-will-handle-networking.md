# Red Hat Ansible 将 IT 自动化扩展到网络

> 原文：<https://thenewstack.io/red-hat-ansible-will-handle-networking/>

Red Hat 还扩展了 Ansible IT automation 软件 T1 来配置网络设备。

[新功能](https://www.ansible.com/networks)包括对通过安全外壳(SSH)、命令行界面(CLI)和应用程序接口(API)自动化网络基础设施设备的本机支持，以帮助客户协调新类别的工作负载，包括异构网络设备，而不必投资购买多种工具或将它们编织在一起。

Ansible 高级工程总监 Tim Cramer 表示，过去六个月来，Ansible 一直在酝酿网络支持，这是一项由用户主导的努力。该公司聘请了曾在 Arista Networks 和思科工作过的[彼得·斯普瑞加达](https://www.linkedin.com/in/sprygada)来领导这项计划。

“我们让运营商告诉我们他们想怎么做，”克莱姆说。“使用 Ansible 作为一种单一的语言，他们可以慢慢地改变过程的方法，因为他们已经习惯了。例如，他们可以设置一个新的交换机，看看它是否适用于 Ansible，然后他们可以开始使用 Ansible 进行更新和其他操作。我们有很多用户把我们往这个方向拉。供应商已经抓住了这一点；他们真的很喜欢。”

> 计划是拥有允许用户在所有主要供应商交换机上进行 CRUD 操作的核心模块。

Red Hat 正在发布其网络核心模块的第一个版本，该版本将与 Ansible 2.0 一起工作，并支持 Arista Networks 的 EOS 思科以应用为中心的基础设施(ACI)、思科 IOS、思科 IOS XR 和思科 NX-OS；积云网络的 Linux 瞻博网络的 Junos 操作系统；和惠普企业 OpenSwitch。对其他供应商的支持将在以后推出。

“这实际上是由用户和运营商推动的。我们真的想确保这里有操作员的声音，”Cramer 说。

Cramer 说，Sprygada 过去参与了几个标准论坛，这些倡议往往试图将变化推给运营商——这些努力通常会随着时间的推移而失败。

“所以我们所做的就是把这些都扔掉，”克莱姆说。“我们说，‘我们不需要试图创建一个标准的数据模型来自动化网络的东西。“我们在数据中心使用一种标准语言，这是可行的，为什么我们不试着把它扩展到网络上呢？”我们将从简单开始，然后添加高级选项，例如，真正深入研究您可以用 Cisco 交换机做的所有疯狂的事情。

Cramer 说，计划是拥有允许用户在所有主要供应商交换机上进行 CRUD 操作的核心模块。它还将从供应商和 [Galaxy](https://www.ansible.com/blog/finding-a-needle-in-a-galaxy-of-roles) 中的角色那里获得代码捐赠，以便能够设置这些代码。

“我们有一个很好的趋势，因为用户正在把供应商拖到同一个地方，”他说。“我现在可以包括网络设备，而不是针对我的环境的一部分运行重头戏，确保我有一个用于基础架构管理的单一 DevOps 工具。”

StackPointCloud 的首席执行官马特·鲍德温(Matt Baldwin)称，网络已经远离 Ansible 太久了。

他说:“现在，我可以将网络设备包括在内，确保我拥有一个用于基础架构管理的单一 DevOps 工具，而不是针对我的环境的一部分运行一部重头戏。”

“这是一个伟大的公告，我认为 Ansible 社区将会重视它——无论是开发人员还是运营团队；网络工程师现在可以加入 DevOps 大家庭。

“我还希望 Red Hat 鼓励和接受开源贡献，以扩大网络框架内的支持，而不是将它封闭和局限在企业内，”他说。“这是 Ansible 长期以来需要走的一个方向。很高兴看到 Red Hat 开始统一 DevOps 体验。”

Red Hat 还参与了最新的 Linux 基金会合作项目 [FD.io](https://thenewstack.io/linux-foundation-takes-networking-fd-io/) ，致力于为网络和存储软件创建一个 io 服务框架。

Red Hat 将在 3 月 9 日举行一次网络研讨会，更详细地解释 Ansible 的网络功能。

思科和 HPE 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>