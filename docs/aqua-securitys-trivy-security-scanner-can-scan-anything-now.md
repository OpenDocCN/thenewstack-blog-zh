# Aqua Security 的 Trivy 安全扫描仪现在可以扫描任何东西

> 原文：<https://thenewstack.io/aqua-securitys-trivy-security-scanner-can-scan-anything-now/>

瓦伦西亚——在 KubeCon Europe ，[云原生安全提供商 Aqua Security](https://www.aquasec.com/?utm_content=inline-mention) 宣布其开源安全扫描仪 Aqua [Trivy](https://www.globenewswire.com/Tracker?data=MEVBxfrfNcaane-Gc9ErP2d3OHSKt15EqQIpyETnwnxMTOJncsntCy951brYUPwQakAsa4Ub8N6ynxfF9snJYnygvZAhTLp_DEj0We42i6w=) 可以扫描几乎任何与云原生相关的东西。比如什么？比如源代码、存储库、图像、工件注册、[基础设施即代码](https://www.globenewswire.com/Tracker?data=iY7ptPbur48hAp9AN-JQKKmijYfQAS8n_Bs6CpMm7rmZGey_h9Y_8Vj1R6o5tBBw4lnnEN1841yN6aYbBbtGBSJJFrITfi_YW581ywpzps89jTdfVrF_CfXoFhl-ZPS0ppbB9hAv4BbZ7BAVeSG-eg==) (IaC)模板和 Kubernetes 环境。我喜欢这个声音！

Trivy 将多个扫描程序合并成一个工具。Aqua Security 的首席技术官兼联合创始人阿米尔·杰比(Amir Jerbi)认为这是一个巨大的进步。“安全专业人员被要求使用的工具数量淹没了，在可能的情况下整合工具有助于团队变得更高效，”他说。

Aqua 声称它是针对云原生应用程序和基础架构的最全面的漏洞和错误配置扫描器。我不知道我是否会走那么远，但这个概念非常有吸引力。

毕竟，如果我的开发人员可以用一个工具完成大部分的安全错误扫描，这比使用其他程序的大杂烩要容易得多。这使得让你的团队购买 [DevSecOps](https://thenewstack.io/building-the-business-case-for-devsecops/) 更加容易。

## 关键特征

其特点包括:

*   使用 JetBrains、VSCode 和 vim 的集成开发环境(IDE)插件扫描专有和第三方代码中的问题，以进一步提高安全性。
*   生成完整的软件物料清单(SBOM)以提供软件组件的透明度，并恢复软件供应链中风险的可见性。
*   检测敏感的硬编码机密，如密码、API 密钥和令牌，以防止威胁参与者的未授权访问。
*   扫描正在运行的 Kubernetes 集群以获得风险的全生命周期视图，并审计法规遵从性。
*   可以集成到[持续集成/持续部署(CI/CD)](https://practical-tech.com/2018/07/10/continuous-integration-and-delivery-tool-basics/)

Trivy 将运行在 Alpine Linux、Debian/Ubuntu Linux 家族、Red Hat Enterprise Linux (RHEL)、SUSE Linuxes 和其他系统上。它还可以与 CI/CD 程序一起工作，如 GitHub Actions、Jenkins 和 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) CI。

### 小额保险费

Trivy 也被整合到 [Aqua 平台](https://www.aquaplatform.com/)作为 Trivy Premium。利用这一商业产品，您可以获得客户支持、优质内容和针对企业可扩展性的集中管理。

由于高级威胁情报、恶意软件扫描和扫描独立二进制文件的能力，Trivy Premium 还提高了漏洞识别的准确性。最后一种是应用程序，它们是直接安装的，不需要使用软件包管理器。在 Aqua 平台中，Trivy Premium 还集成了其他平台模块，如云安全状态管理(CSPM)和运行时保护，以改善云原生应用程序生命周期保护。

## Docker 桌面集成

此外，Trivy 最近被整合到 [Docker 桌面](https://www.globenewswire.com/Tracker?data=74WSvW5JReYT_Ojojx6X5kvstJc3if78gLbFkmcx2icGdCxcBsm8brVI5StaT7X4NvJrr1ADuIo3DovcFMT-YrUpgK2ooiajqCnXRbFN8iTWqMqvYXxfnRF-Ohb-TQv60_B3hNCFKjZFR8auYUAjHQ==)中。如果您已经在使用桌面，这使得将漏洞和风险扫描引入您的工作流变得更加容易。

Trivy 背后是一个庞大的云原生安全社区。拥有超过 100，000 名用户和近 12，000 名 GitHub 明星，它可以说是最受欢迎的漏洞和风险扫描器。如果我是你，我会尝试一下开源 Trivy。

如果你喜欢你所看到的，在 Aquasec.com[的 Aqua 平台](https://www.globenewswire.com/Tracker?data=t6xHIAWytJLeMl4guT6e4LKpFAIvjA2VnUR34_Tj2yTfD9b054M9UjH9A6yo5Q-PN-1xs2WwDP17rbd7NNU-KA==)上注册一个 Trivy Premium 的[免费试用。](https://www.aquasec.com/products/container-vulnerability-scanning/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>