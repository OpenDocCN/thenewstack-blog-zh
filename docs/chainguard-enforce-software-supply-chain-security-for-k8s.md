# Chain guard Enforce:K8s 的软件供应链安全

> 原文：<https://thenewstack.io/chainguard-enforce-software-supply-chain-security-for-k8s/>

仅在半年前，[零信任安全](https://thenewstack.io/zero-trust-security-and-the-software-development-lifecycle/)公司 [Chainguard](https://chainguard.dev/) 的联合创始人 [Kim Lewandowski](https://www.linkedin.com/in/kimsterv) 说，“默认供应链安全是我们的使命，让开发者真正容易做正确的事情。”现在随着 [Chainguard Enforce](https://www.chainguard.dev/chainguard-enforce) 的测试版发布，它的第一个产品，一个针对 Kubernetes 工作负载的原生软件供应链解决方案，已经上市了。

全新的护链器 Enforce 由四个主要组件组成。这些是策略代理、构建系统集成、持续验证和证据湖。它还包括一个开发人员友好的 CLI 和 UI。

只读策略代理提供每集群策略和 webhook 配置支持，并且可以跨多集群环境进行集中管理。即使在第一个版本中，代理也集成了许多 Kubernetes 平台，如 EKS、AKS 和 GKE。Enforce 将与 Kubernetes 支持的任何容器一起工作。

## 基于标准的

策略代理也准备好运行一组精选的策略定义。这些都是基于开源[软件工件供应链级别(SLSA)](https://slsa.dev/) 和 NIST [安全软件开发框架(SSDF)](https://csrc.nist.gov/Projects/ssdf) 标准。

策略代理支持定义自定义策略的完整策略语言。据莱万多夫斯基所说。“我们从一套非常规范的政策开始，这些政策是为关键管理层和 SLSA 级别设计的，没有成熟的语言。”展望未来，Chainguard 的开发人员也在考虑使用[Configure Unify Execute(CUE)](https://cuelang.org/)一种开源语言，带有一组用于定义策略的 API。

Chainguard Enforce 包括为这种流行的 CI 平台构建系统集成。其中包括 GitHub Actions、CircleCI、BuildKite、GitLab 和 Jenkins。这使您能够为容器的源代码配方建立记录。Chainguard 还声称，DevOps 团队安装和配置这些构建系统集成只需要不到一天的时间。

然而，Enforce 不包括漏洞扫描。然而，它可以和第三方扫描仪一起工作。这样，您就可以拥有一个无缝的安全工作流，减少误报。

为了确保您的容器无故障，需要进行持续的验证检查，以确保您部署的容器映像符合您定义的策略。如果有任何偏差，就会触发警报。

## 证据湖

最后但同样重要的是，证据湖是一个实时资产清单。这些数据可以增强开发人员工具、事件恢复、调试和审计自动化。此外，还有针对 Slack 和吉拉等流行警报和票务平台的集成。

对于这一切，Chainguard 团队带来了开源和安全标准的专业知识。正如该公司所说，“我们在构建这个工具时考虑到了这些利益相关者和开发者，希望在默认情况下使软件供应链更加安全。”

Enforce 的基础是开源的 Sigstore 项目。它通过为容器化程序的构件创建数字签名来保护软件供应链。

综上所述，Enforce 使您能够构建、管理、确保持续的法规遵从性，并实施策略来保护您免受供应链威胁。但是，正如[Forrester 安全分析师 Sandy Carielli](https://www.forrester.com/analyst-bio/sandy-carielli/BIO14484) 指出的那样，“集装箱安全面临着许多挑战，从积压的图像到集装箱蔓延，再到意识差距和控制差距，Chainguard 解决方案专注于控制差距。客户仍将需要一系列其他工具和流程来满足集装箱安全要求。”

甚至，Enforce 在保护您的开发人员的程序免受软件供应链灾难方面向前迈出了一大步，而无需耗费大量时间处理令人头疼的手动安全工作流程。值得你关注。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>