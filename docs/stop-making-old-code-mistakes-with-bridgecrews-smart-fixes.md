# 使用 Bridgecrew 的智能修复，停止犯旧代码错误

> 原文：<https://thenewstack.io/stop-making-old-code-mistakes-with-bridgecrews-smart-fixes/>

当[帕洛阿尔托网络(PANW)](https://www.paloaltonetworks.com/) 收购 [Bridgecrew](https://bridgecrew.io/) 时，目标是实现“左移”安全性，而 [Prisma Cloud](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 成为第一个跨整个应用生命周期提供安全性的云安全平台。现在，随着[智能修复](https://bridgecrew.io/blog/smart-fixes-team-secure-coding-fix-suggestings-iac-security/)的发布，更容易理解为什么 [PANW 为 Bridgecrew](https://www.paloaltonetworks.com/company/press/2021/palo-alto-networks-completes-acquisition-of-bridgecrew) 支付了大约 1.56 亿美元。

Bridgecrew 的主要产品是开源、静态代码分析[基础设施 as Code (IaC)](https://thenewstack.io/infrastructure-as-code-6-best-practices-for-securing-applications/) scanner、 [Checkov](https://www.checkov.io/) 。使用它，您可以扫描由 [Terraform](https://terraform.io/) 、Terraform plan、 [Cloudformation](https://aws.amazon.com/cloudformation/) 、 [AWS SAM](https://aws.amazon.com/serverless/sam/) 、 [Kubernetes](https://kubernetes.io/) 、 [Dockerfile](https://www.docker.com/) 、 [Serverless](https://www.serverless.com/) 或 [ARM 模板](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/overview)提供的云基础架构。然后，它使用基于图表的方法检测安全性和合规性错误配置。

## 查找 IaC 策略违规

Smart Fixes 通过与 [Bridgecrew 云安全平台](https://bridgecrew.io/platform/)集成，将这一功能向前推进了一步。在那里，它会在您的云代码中查找 IaC 策略违反情况。然后，它会提供修复建议。

它通过自动跟踪修复策略违规的先前代码更改来实现这一点。如果 Smart Fixes 发现这些相同的代码修复一次又一次地发生，它将在任何时候发现其他类似的违规时开始建议这些修复。“智能修复”算法只在代码发生三次以上的变化时才给出建议。

或者，正如 PANW 产品经理 [Tohar Zand](https://www.linkedin.com/in/tohar-zand-918292157/) 所说，“在 Bridgecrew，我们认为安全需要遵循 SRE 的最佳实践[自动消除辛劳](https://sre.google/workbook/eliminating-toil/)或不必要的手动任务。这有助于提高代码质量，消除人为错误，并提高生产率。”

## 内置修复建议

怎么会？Bridgecrew 认为“生产率的最大消耗之一是中断流程，手动研究如何解决问题。”在那一点上，我不会对他们提出异议。

然后，鉴于许多开发人员对安全性知之甚少，Bridgecrew 在其 [IDE 插件](https://bridgecrew.io/blog/vs-code-extension-inline-iac-scanning-fixes/)中内置了数百个修复建议，作为[拉请求注释](https://bridgecrew.io/blog/pull-request-comments-fix-suggestions/)，以及在其集成 GitHub 平台中的[。关键是，您可以在不离开工具的情况下找到违反策略的解决方案。](https://bridgecrew.io/blog/keeping-infrastructure-secure-on-every-commit-with-bridgecrew-and-github/)

就目前而言，那很好。智能修复让它更进一步。它不是提供一般性的修复，而是监视您的编程，找出开发团队的常见问题，并自动提供修复。例如，如果您经常从您的堡垒主机错误地键入 SSH 的 IP 地址或相同的加密密钥来加密数据库，它将会调出正确的地址或加密密钥。犯了太多的错别字，我很欣赏这项服务。

## 自动跟踪代码更改

具体来说，它会自动跟踪代码更改，如添加、删除和更改，从而修复违反策略的情况。如果相同的更改出现三次以上，并且部署的频率超过 20%,智能修复将在该更改再次出现时给出提示。换句话说，您可以创建自己的“智能修复”，无需人工干预。

当您应用智能修复时，Bridgecrew 会向您的版本控制系统(VCS)打开一个“拉”请求。然后，在将代码更改提交并最终部署到项目之前，您可以进行任何额外的检查。

## 智能修复可用性

目前，智能修复只在 Bridgecrew 的项目页面上可用。它将很快在 Bridgecrew 的其他集成中提供。此外，PANW 将在未来几周内为多个回购和复杂补救智能修复(需要多个资源变更的补救)添加智能修复。

对我来说这听起来很有希望。鉴于契诃夫的成功，超过 400 万的下载量，我会去看看。不过，智能修复的代码目前还不可用。最终，它将被开源。目前，要使用它，你需要[订阅每月 99 美元的 Bridgecrew](https://bridgecrew.io/pricing/) Standard 或每月 999 美元的 Bridgecrew Premium。你还可以免费踢 [Bridgecrew 和 Smart Fixes 的轮胎两周](https://www.bridgecrew.cloud/login/signUp?__hstc=95155075.a612d08abac4acdb35cbf713a961069b.1639603062955.1639603062955.1639603062955.1&__hssc=95155075.3.1639603062955&__hsfp=3366380536)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>