# Falco 云安全监控现已登陆亚马逊网络服务

> 原文：<https://thenewstack.io/falco-cloud-security-monitoring-now-on-amazon-web-services/>

几年前谁会想到 Linux 的[扩展的 Berkeley Packet Filter (eBPF)](https://ebpf.io/) 会成为云原生安全监控工具的基础，比如 [Sysdig](https://sysdig.com/) 的 [Falco](https://falco.org/) 开源安全程序？现在，Falco，一个云原生运行时安全项目，即事实上的 [Kubernetes](https://kubernetes.io/) 威胁检测引擎，已经通过一个全新的 [CloudTrail 插件](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html)将其触角延伸到了[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)。

该公司在本月早些时候在洛杉矶举行的今年的 KubeCon+CloudNativeCon 上宣布了这一新产品。

这种结合将使您能够使用 Falco 规则实时检测 AWS 云服务中的意外行为和配置更改、入侵和数据窃取。这是基于一个新的 Falco 插件框架，允许任何人扩展 Falco，从 Linux 系统调用和 Kubernetes 审计日志之外的其他来源捕获数据。

Falco 已经与 AWS 的安全日志系统 Cloudtrail 合作了一段时间。但是，有了新的插件框架，集成两者就容易多了。

在此之前，您必须将 AWS CloudTrail 日志导出到数据湖或安全信息和事件管理(SIEM)中进行处理。一句话，就是慢。只有在导入之后，您才能搜索威胁和有风险的配置更改。

通过这种新方法，您可以使用 Falco 通过流方法来检查云日志。这使您可以实时检查日志，以便立即发现问题。

通过使用社区提供的现成规则，您可以立即让它发挥作用。这些映射到法规遵从性框架和最佳实践。您还可以使用 YAML 创建自定义规则来满足您的特定要求。

这种新方法还使得跨多个云管理关键日志和安全数据变得更加容易。展望未来，Sysdig 承诺，额外的插件将允许您使用一致的威胁检测语言，并通过对工作负载和基础架构使用一致的策略来弥补安全漏洞…最终。

目前，CloudTrail 和 Falco 的这对组合还是测试版。即便如此，今天的 [Cloudtrail](https://github.com/falcosecurity/plugins/tree/master/plugins/cloudtrail) 插件和相关的 Falco 规则可以:

*   读取 Cloudtrail 日志并将它们作为事件返回
*   在 Cloudtrail 日志中识别可疑或值得注意的活动。

截至今天，AWS CloudTrail 插件和额外的开箱即用规则是通过 [Falco GitHub 网站](https://github.com/falcosecurity/falco)提供的。您还可以在框架上构建新的插件。

Sysdig 希望明年年初正式发布。与此同时，他们希望让潜在的插件开发者看看这些 API，并在正式发布前提供反馈。

为什么现在看？正如 [Chris Aniszczyk](https://www.linkedin.com/in/caniszczyk/) ，[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)(CNCF)首席技术官所说，“Falco 插件功能为开发人员和安全团队提供了一个单一的威胁检测工具，在容器和云环境中使用单一的规则语言。这允许用户为工作负载和基础架构创建一致的策略，并弥补安全缺口。现在，社区快速创新的基础已经到位，可以将 Falco 扩展到其他云环境。”

对此，我要补充的是，任何能让我实时检查安全问题的东西都值得在我的书里看一看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>