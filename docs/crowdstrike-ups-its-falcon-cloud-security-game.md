# CrowdStrike 升级其猎鹰云安全游戏

> 原文：<https://thenewstack.io/crowdstrike-ups-its-falcon-cloud-security-game/>

并非所有的云安全程序都基于开源软件。全球安全公司 CrowdStrike 提供了其[猎鹰平台](https://www.crowdstrike.com/falcon-platform/)，该平台使用在其专有的[威胁图数据库](https://www.crowdstrike.com/falcon-platform/threat-graph/)和专利智能过滤技术上运行的人工智能来提供云安全服务。5 月，CrowdStrike 将推出其新的以对手为中心的[云原生应用程序保护平台 CNAPP](https://www.crowdstrike.com/cybersecurity-101/cloud-security/cloud-native-application-protection-platform-cnapp/) ，以加速云环境和工作负载的威胁搜索，并减少响应所需的时间。

## 什么是 CNAPP？

CrowdStrike 高级产品营销经理 [Gui Alvarenga](https://www.linkedin.com/in/guilhermealvarenga/) 表示，“CNAPP 是一个一体化的云原生软件平台，可以简化对潜在云安全威胁和漏洞的监控、检测和应对。随着越来越多的组织采用 [DevSecOps](https://thenewstack.io/devsecops-why-security-shouldnt-be-sacrificed-for-speed/) ，他们正在寻找确保云原生应用程序安全性、保护业务关键型工作负载以及简化运营的方法。CNAPP 将多种工具和功能结合到单个软件解决方案中，以最大限度地降低复杂性并促进开发运维团队和开发运维团队的运营。”此外，它在整个[持续集成/持续部署(CI/CD)](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/) 应用生命周期中提供端到端云和应用安全性。

这是通过一个通用的云活动仪表板将 CrowdStrike 广受欢迎的 [Falcon Horizon](https://www.crowdstrike.com/cloud-security-products/falcon-horizon-cspm/) 、一个[云安全状态管理(CSPM)](https://www.crowdstrike.com/cybersecurity-101/cloud-security/cloud-security-posture-management-cspm/) 模块和 [Falcon 云工作负载保护(CWP)](https://www.crowdstrike.com/products/cloud-security/falcon-cloud-workload-protection/) 模块结合在一起实现的。有了它，安全和 DevOps 团队都可以优先考虑他们最重要的云安全问题，解决运行时威胁并追踪云威胁。

这些更新还包括使用 [Falcon Fusion](https://www.crowdstrike.com/falcon-platform/falcon-fusion/) 、CrowdStrike 的[安全协调、自动化和响应(SOAR)](https://thenewstack.io/automating-security-7-major-benefits-of-a-soar/) 框架来自动化亚马逊网络服务(AWS)补救的新方法；谷歌云平台(GCP)的新自定义错误配置指示器(IOMs 为 Microsoft Azure 和更多内容提供防止基于身份的威胁的新方法。

这种新方法提供了基于代理(猎鹰 CWP)和无代理(猎鹰地平线)的解决方案。您可以决定哪种方法最适合保护您的 CI/CD 管道中的云应用，而 AWS、Azure 和/或 GCP clouds CrowdStrike 会推荐其基于代理的 CWP 解决方案，因为它支持运行前和运行时保护。相比之下，仅无代理的方法只能提供部分可见性，并且缺乏补救功能。

尽管如此，CrowdStrike 的首席产品和工程官 [Amol Kulkarni](https://www.linkedin.com/in/amolsk/) 指出，CrowdStrike 与其他供应商的不同之处在于它提供了基于代理和无代理两种方法。“此外，”Kulkarni 继续说道，“我们为组织提供针对云计算和混合云环境的云工作负载、容器和 Kubernetes 的违规保护，这些组织可以访问 150 多个云对手的实时警报和报告”

## 特色功能

CrowdStrike 专注于对手的 CNAPP 功能包括:

### 猎鹰地平线和猎鹰 CWP 的新中央控制台

*   云活动仪表板。将 Falcon Horizon 的 CSPM 洞察与 Falcon CWP 的工作负载保护统一到单一用户体验中，以确定首要问题的优先级、解决运行时威胁并实现云威胁追踪，从而加快调查和响应速度。

### 猎鹰地平线的新功能

*   AWS 的自动化补救工作流。通过由 Falcon Fusion 支持的引导式自动补救来应对威胁。工作流提供了解决问题和减少事件解决时间所需的上下文和说明性指导。
*   Azure 身份访问分析器。防止基于身份的威胁，并确保 Azure AD 组、用户和应用具有基于最低特权的强制权限。此功能扩展了 Falcon Horizon 现有的 AWS 身份访问分析器功能。
*   GCP 错误配置的自定义指示器(IOM)。通过符合业务目标的自定义策略，确保安全性是每个云部署的一部分。该功能扩展了 Falcon Horizon 现有的针对 AWS 和 Azure 的自定义 IOM 功能。

### 猎鹰 CWP 的新能力

*   猎鹰集装箱检测。借助机器学习(ML)、人工智能(AI)、攻击指示器(IOAs)、深层内核可见性和定制危害指示器(IOCs)以及行为阻止，自动防御针对容器的恶意软件和复杂威胁。
*   流氓容器检测。随着集装箱的部署和退役，维护最新的库存。此外，扫描恶意图像，识别并阻止以特权或可写身份启动的容器，这些容器可被用作攻击的切入点。
*   防止容器漂移。发现运行时创建或修改的新二进制文件，以保护容器的不变性。

## 风险评估数据

这是跨平台的许多新特性。据澳大利亚能源公司的戴夫·沃星顿，数字安全和风险部总经理[杰梅纳](https://jemena.com.au/)称，这是一件好事，“我见证的一大好处是，CrowdStrike 不断创新和增强其云安全产品，如猎鹰地平线，我们用它来监控我们的云环境，检测错误配置、漏洞和安全威胁。”在一项 CrowdStrike 案例研究中，沃星顿补充道，“T2，我第一次有了自信地与执行委员会对话所需的数据，并准确地传达了我们在用户、服务器和网络中看到的风险水平。”

任何一个面临敌意的 C 级安全概述的 IT 人员都知道，这最后一点并不是一件小事。如果你一直处于这种尴尬境地，那就有足够的理由去看看 CrowdStrike 最新的多级安全服务。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>