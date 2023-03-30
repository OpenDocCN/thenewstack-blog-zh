# Sysdig 的目标是通过政策收购实现 IaC 自动修复

> 原文：<https://thenewstack.io/sysdig-aims-for-iac-auto-remediation-with-apolicy-acquisition/>

云安全公司 [Sysdig](https://sysdig.com/) 已经开始收购[policy](https://apolicy.io/)的过程，作为其继续转移其安全产品套件的努力的一部分，不仅为 Sysdig 平台添加了解析基础设施即代码(IAC)配置文件错误的能力，还可以帮助对发现的任何问题进行优先排序和补救。

Apolicy 建立在现已毕业的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)项目[开放策略代理(OPA)](https://www.openpolicyagent.org/) 之上，但 Sysdig 首席执行官 [Suresh Vasudevan](https://www.linkedin.com/in/suvasudevan) 解释说，Apolicy 如何超越 OPA 的基本功能吸引了他们对该产品的兴趣。

“大多数将基础设施作为代码的公司甚至没有像他们在使用 OPA 或能够为 Kubernetes 环境解析各种不同源文件方面所做的那样深入。Vasudevan 说:“我们发现令人着迷的是，这次收购的主要驱动力是他们在自动修复方面所做的工作。“策略能够做到的是说，‘好吧，这是我在生产实例中看到的一个错误配置’，而不是仅仅将它指向安全团队和开发运维团队，他们能够做的是识别特定的 YAML 文件或映射到该生产事件的源文件，并创建实际的修复方案。”

Vasudevan 指出，Sysdig 通过其容器图像扫描和云安全状态管理(CSPM)工具，已经遵循了 DevOps 开发实践的左移趋势，收购 policy 的举动也遵循了 GitOps 的类似趋势，其中这些基础设施代码文件存储在基于 Git 的存储库中。随着 DevOps 团队现在承担编写 IAC 文件的任务，分析这些文件中的错误并修复这些错误的能力也进入了这些团队的领域。他说，policy 将直接修复错误的能力引入到 GitOps 工作流程中。

Vasudevan 说:“他们并不只是出现 1000 个错误，然后说，‘这里是你需要修复的所有错误’，而是实际上创建拉请求，这样如果开发人员说‘是的，这是正确的修复’，批准它，它就会自动部署到生产中。”

一旦收购完成，Apolicy 完全整合到 Sysdig 平台，Vasudevan 估计将在未来两到三个月内完成，它将为 Sysdig 用户带来一些特定的功能。

首先，策略将提供通过策略即代码来实施法规遵从性和治理的能力，帮助客户满足 SOC 2、HIPAA 和 PCI 等法规要求。接下来，policy 将帮助用户检测运行时漂移，并自动将配置返回到存储在中央存储库中的 IaC 源。最后，关于错误配置的警报及其相关修复将根据其优先级呈现给用户。

“想象一下，我有一个包含 10，000 个节点的集群，基本上每天我都要处理几百个配置错误，”Vasudevan 说。“即使我自动化了拉取请求，并创建了一个 JIRA 任务供开发人员查看，这也不能抹杀我正在处理 500 个这样的任务的事实。policy 所做的是，查看配置错误的严重程度，自动执行修复过程，然后根据哪些修复解决了高风险问题，哪些修复解决了低风险问题来确定修复的优先级。”

虽然添加 Apolicy 的功能对 Sysdig 意义重大，但 Vasudevan 解释说，真正的潜力是 Apolicy 与其现有工具的结合。他说，policy 通过将策略作为代码引入，极大地增强了 Sysdig 保护 Kubernetes 和 CSPM 的能力，但它的潜力还在于将自动补救添加到 Falco 运行时安全工具中。

“如果 Falco 检测到运行时违规，我们知道需要通过进行一些其他配置更改来纠正，即使 Falco 检测也可以使用这种补救工作流，这样我们就可以纠正它，不仅在您的生产环境中，而且在您的源代码文件中也是如此，”Vasudevan 说。“因此，这是对 CSPM 的极大补充，它将 IaC 安全性引入了我们的工作流程，但它也带来了一种我们可以在产品的不同部分使用的功能。”

收购完成后，整个 policy 团队将加入 Sysdig 团队，该产品将成为 [Sysdig Secure DevOps 平台](https://sysdig.com/secure-devops-platform/)的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>