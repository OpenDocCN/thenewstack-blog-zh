# 利用这一针对服务级别目标的 GitOps 友好规范，自动满足用户需求

> 原文：<https://thenewstack.io/automate-user-satisfaction-with-this-gitops-friendly-spec-for-service-level-objectives/>

希望通过一些[站点可靠性工程](https://thenewstack.io/site-reliability-engineering-cloud-native-operations/) (SRE)来加强运营的组织应该看看最近发布的 [OpenSLO](https://github.com/OpenSLO/OpenSLO) 规范，这是一个 GitOps 友好的模板，用于建立服务级别目标(SLO)，以指定甚至强制执行系统所需(和提供)的可靠性范围。

软件可靠性平台公司 [Nobl9](https://nobl9.com/) 启动了这个项目，它在 Apache 2 (APLv2)许可下于本周发布，正好赶上该公司将于本周举行的 [SLOConf](https://www.sloconf.com/) 。

 站点可靠性工程(SRE)的实践[建立在指标](https://thenewstack.io/usenix-the-3-measures-of-successful-site-reliability-engineering/)之上，是传统[服务水平协议](https://nobl9.com/resources/aligned-incentives-putting-the-so-what-in-modern-slos/)的数字细化。SLA 历来衡量系统的最低可接受性能。通常，无法满足 SLA 是退款甚至请律师的原因。

Nobl9 的首席运营官 Kit Merker 在接受新 Stack 采访时解释说，SLO 衡量的是相反的方面:客户(外部或内部)对服务满意的程度。它在用户满意度和完整的系统可靠性之间建立了一个增量——这个增量的成本会让任何服务提供商望而却步。了解用户满意的可靠性水平给服务提供商一个已知的开销，或“误差预算”，以尝试新的功能，并保持总的利润率。

Nobl9 首席执行官 Marcin Kurc 在一份声明中表示，通过这一规范，我们的想法是让 SLO 成为“现代 DevOps 生命周期中的一等公民”。

OpenSLO 盒子里是 SLO 的标准 YAML 规范格式，以及一个根据语法检查完整的 YAML 文件的解析器。通过使用声明性的 YAML 格式，OpenSLO 提供了一种将 SLO 嵌入操作流程的方法，不仅为观察，甚至为自动化创造了条件。SLO 文件可以与实际代码和具有“基础设施即代码”设置的文件一起签入 git 或另一个代码库，“所以你可以将其作为发布管道的一部分进行验证，”Merker 说。然后，系统设计人员可以自动执行自动缩放、警报消息传递和资源供应等行为，所有这些都基于即将到来的 SLO 数。

这些指标可以直接从应用程序性能监控软件中获得。Nobl9 本身已经与 Splunk、 [New Relic](http://newrelic.com/?utm_content=inline-mention) 、Datadog、 [Dynatrace](https://www.dynatrace.com/?utm_content=inline-mention) 和 [Lightstep](https://lightstep.com/?utm_content=inline-mention) 等可观测性提供商合作。Merker 认为，编写一个开放的标准将有助于最终用户在这些工具集之间切换，并且干扰最小。

Nobl9 首先为自己的平台创建了规范，但为其他人开放了规范。谷歌和微软前 SRE、OpenSLO 的贡献者尼尔·理查德·墨菲在一份声明中指出，不同组织间的通用架构有助于确保社区支持。

该项目的其他贡献者包括: [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 的 [Andrew Newdigate](https://gitlab.com/andrewn) 、 [Dynatrace](https://www.dynatrace.com/?utm_content=inline-mention) 的 [Juergen Etzlstorfer](https://github.com/jetzlstorfer) 和 [Alex Nauda](https://github.com/alexnauda) 和 [Ian Bartholomew](https://www.linkedin.com/in/the-ian-bartholomew/) ，他们都来自 Nobl9。

纽迪盖特指出，对 Gitlab 来说，制定 SLO 误差预算需要不同部门参与可靠性工程过程。

这项工作正在寻求额外的投入，特别是来自云供应商、应用程序生命周期管理供应商、咨询公司和其他开源项目的投入。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>