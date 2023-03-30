# Chef 在 Automate 2.0 版本中采用了以应用为中心的方法

> 原文：<https://thenewstack.io/chef-takes-an-app-centric-approach-with-the-automate-2-0-release/>

自动化和配置管理公司 [Chef](https://www.chef.io/) 本周在芝加哥 [ChefConf 2018](http://chefconf.chef.io/) 上大谈其帮助企业从以基础设施为中心向以应用为中心的 IT 转变的努力。

它宣布推出 Chef Automate 2.0，这是对其自动化平台的更新，最初于 2016 年 7 月发布；Chef Workstation 是用户执行临时任务的简化方式；Habitat Builder 的内部版本，以及对其合规自动化产品 [InSpec](https://thenewstack.io/chef-bulks-security-compliance-automation-cloud/) 的增强。

“我们看到工作单元从系统配置转变为应用程序部署。Chef 产品和工程高级副总裁 Corey Scobie 表示:[企业正在努力理解基础设施和应用生命周期管理的融合。](https://www.linkedin.com/in/coreyscobie/)

他描述了从基础设施焦点的转移，甚至包括容器。

“试图[采用]云和容器的组织开始遇到一些界限，因为我们不够以应用程序为中心，”他说，调用容器是打包的持续发展，但仍然采用以系统为中心或以基础设施为中心的方法。

“Habitat 做得非常好的一件事是找到应用程序打包和部署的通用模式，不管它是用一种已经灭绝的语言编写的 20 年前的应用程序，还是为云和容器世界构建的现代应用程序。”

由 Chef 赞助的 Dimensional Research 最近进行的一项调查的参与者报告了应用程序生命周期所有阶段的痛苦。在全球范围内接受调查的 347 名应用和运营专业人员中，只有 12%的人表示他们公司四分之三或更多的应用自动化与 DevOps 流程保持一致。

此外，61%的人说构建过程需要几天或更长时间，57%的人说部署需要同样长的时间。它还发现提升和转移是主要的应用程序迁移策略。

Chef Automate 2.0 采用单一控制平面实现基础架构和合规自动化，以提供闭环“检测、纠正、自动化”流程。斯科比指出，该公司使用 Habitat 对其进行包装。

“它允许我们转向持续更新、持续交付的软件方法。我们发布了一个更新频道，客户可以订阅并获得最新的更新，同时保证向前兼容性和版本之间的轻松迁移，”他说。

新功能包括:

*   新的工具和可视化，包括流事件馈送、趋势图和丰富的查询语言，用于增加透明度和调试。它提供了一个统一的控制面板，帮助用户在一个位置分析基础架构和合规自动化数据。
*   与 InSpec 2 的集成通过 API 增强了对 AWS、Azure 或 Google Cloud 上的云配置的合规性扫描。它还为 Cisco IoS 设备提供 30 种新资源以及基于无代理网络的策略评估，这是将现代合规能力扩展到网络设备的一项举措。它可以验证 AWS 和微软 Azure 策略，并在测试版中提供谷歌云平台支持。Chef 还扩展了配置文件集，以包括 10 多个新的 AWS 资源。该公司还宣称，Windows 系统的性能提高了 90%，Linux/Unix 系统的性能提高了 30%。
*   Automate 2.0 通过基于 Go 的微服务架构进行了重新架构，以提高速度和灵活性。它包括一个基于 REST API 的高性能 web UI，这意味着它可以支持来自一个安装的数万个节点。此外，它还提供了从以前版本自动迁移数据的就地升级，因此可以保留所有历史信息。

随着 Workstation 测试版的发布，该公司正在解决 Chef 入门困难的报告。

它将安装体验归结为一个二进制文件。它将在开发人员工作站或笔记本电脑上安装和设置基本的 Chef 组件。它提供了不仅在本地，而且在远程执行特定任务的能力，例如在目标服务器上自动安装 Chef 客户机并执行 cookbook。

Scobie 说，栖息地构建器的增强功能支持团队在任何地方构建、部署和管理任何应用程序，甚至是在内部，在那里它以“卫星服务器类型的方法”运行。

MarketsandMarkets Research 报告称，2018 年，内部部署预计将成为持续交付市场的主要方法，该市场预计将从 2018 年的 16.5 亿美元增长到 2023 年的 38.5 亿美元。涵盖了[shipped](https://thenewstack.io/shippable-server-offers-new-features-enterprise/)、 [Red Hat](https://thenewstack.io/red-hat-releases-a-framework-to-easily-package-applications-for-kubernetes/) 、 [Puppet](https://thenewstack.io/puppet-will-extend-infrastructure-automation-capabilities-distelli-acquisition/) 、 [Heroku](https://thenewstack.io/heroku-officially-embraces-cicd-automating-staging-github/) 、 [Cloudbees](https://thenewstack.io/jenkins-based-cloudbees-acquires-codeship-fill-ci-cd-portfolio/) 、 [Applariat](https://thenewstack.io/applariat-provides-fly-container-reconfiguration/) 以及 Chef 等公司，说明企业对公有云技术的接受度越来越高。

不仅如此，Dimensional Research 中有 81%的人表示他们正在采用多云策略。

增强功能包括:

*   更新的 Kubernetes 算子
*   出口到 Azure Kubernetes 服务
*   Kubernetes 的舵图导出器
*   开放式服务代理集成
*   Splunk 集成

这些修改来自于过去几个月的经验教训，比如如何更好地与 Kube 和 Kube 集群集成，调度服务等等。斯科比说，它们包括更多的挂钩，以发挥更多的栖息地原生能力。

Kubernetes 的操作员就像一个边车和代理人，做着人类会做的工作，产品营销总监 Julian Dunn 解释道。

“人们一直在编写非常特定的应用程序，即特定的数据库操作程序或 web 应用程序操作程序。这些管理功能类似于重新部署或配置更新。Kubernetes 世界的想法是，如果你希望你的应用程序具有这些功能，你必须一对一地编写这些，”他说，并补充说，如果你使用 Habitat，你不必这样做，因为它的管理界面可以跨应用程序工作。

[大厨、](https://www.chef.io/)红帽和木偶是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>