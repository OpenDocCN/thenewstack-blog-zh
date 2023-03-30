# 红帽拥抱发展警察

> 原文：<https://thenewstack.io/red-hat-embraces-devsecops/>

当 DevOps 将部署和更新速度提高到前所未有的速度时。我们很喜欢。当我们的安全失误以同样的速度加速时，我们就不那么高兴了。因此， [DevSecOps](https://thenewstack.io/devsecops-not-just-about-security/) 被创建来将安全性引入生产周期的开始。现在，在波士顿的[红帽峰会](https://www.redhat.com/en/summit)上，Linux 和云计算力量[红帽](https://www.openshift.com/try?utm_content=inline-mention)正[在其整个产品和服务阵容中拥抱 DevOpsSec 安全](https://www.redhat.com/en/about/press-releases/red-hat-unveils-new-levels-security-software-supply-chain-edge)。

现在，如果你是一个 Linux 管理员，你已经知道 [Red Hat 是领先的 Linux 安全公司](https://www.hpe.com/us/en/insights/articles/for-red-hat-security-is-a-lifestyle-not-a-product-1805.html)。当你听到一个新的安全漏洞时，你第一个看的地方是[红帽安全中心](https://access.redhat.com/security)，即使你运行的是 [Debian](https://www.debian.org/) 或 [Ubuntu](https://ubuntu.com/) 。展望未来，Red Hat 开始关注安全性，并在混合云环境中引入软件供应链安全模式。这意味着从内部到边缘和整个软件堆栈的多云。

## 软件供应链安全模式

怎么会？通过 [Red Hat OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift) 交付，完整的模式堆栈作为定义、构建和测试必要软件配置的代码。虽然目前只是预览版，但这种软件供应链安全模式汇集了从可信组件构建云原生应用程序所需的组件。

它通过[红帽 OpenShift 管道](https://docs.openshift.com/container-platform/4.7/cicd/pipelines/understanding-openshift-pipelines.html)和[红帽 OpenShift GitOps](https://cloud.redhat.com/blog/announcing-openshift-gitops) 使用 Kubernetes 本地的持续集成管道来实现这一点。这将使您在管理版本控制的同时使软件更加安全，有助于降低复杂性和节省时间。

“IT 安全性与软件版本或附加模块无关；它需要融入组织选择的任何技术，从操作系统基础到应用程序级别，”Red Hat 产品安全副总裁 Vincent Danen 说。“这是 Red Hat 对 DevSecOps 的承诺——使安全性不再是附加的东西，而是将应用程序从开发转移到生产的无缝组成部分，以在技术上和组织上帮助 IT 团队。”

## Sigstore

此外，通过[泰克顿链](https://github.com/tektoncd/chains)，图案将融入 [Sigstore](https://www.sigstore.dev/) 。这个开源项目使得加密代码签名更加容易。Kubernetes 1,24 已经采用了 Sigstore ,它使得工件在管道中签名变得更加容易，而不是在应用程序创建之后。通过向左移动安全性，它使加密签署发布文件、容器映像和二进制文件变得容易，从而提高了软件供应链的安全性。签名后，签名记录保存在防篡改的公共日志中。sigstore 将免费供所有开发者和软件提供商使用。这给了软件工件一个更安全的监管链，可以保护和追溯到它们的来源。

## Ansible，Kubernetes 的集群安全性

在相关的开发中，Red Hat Ansible Automation Platform 2.2 推出了 ansi ble 内容签名技术的技术预览版。这使您能够验证正在执行的自动化内容是经过验证的和可信的。

在生产中，这将在[Red Hat Advanced Cluster Security for Kubernetes](https://www.redhat.com/en/resources/advanced-cluster-security-for-kubernetes-datasheet)中推出。这将包括:

*   CI/CD 管道中的自动化开发合作，通过漏洞管理、应用配置分析和 CI/CD 集成，帮助保护边缘环境的软件供应链
*   威胁防护在运行时为常见威胁提供威胁检测和事件响应功能
*   网络分段，以实施工作负载隔离，分析容器通信并检测有风险的网络通信路径

## RHEL 9

如果你正在使用[Red Hat Enterprise Linux(RHEL)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)，让我们面对它，如果你读到这里，很可能你正在运行 RHEL，或者它的近亲之一，新的 [RHEL 9](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9-beta/html/9.0_release_notes/index) 带来了重大的安全改进。其中包括:

Red Hat Enterprise Linux 9 中的其他关键安全特性包括:

*   默认情况下，通过 SSH 禁用 root 登录，增强了 root 权限的安全性。这有助于防止通过暴力攻击发现根密码，并改善操作环境的基线安全状况。
*   集成 OpenSSL 3，支持最新的加密框架。这使 IT 团队能够制定新的加密算法来加密和保护敏感信息。
*   通过在默认情况下为数字签名禁用密码破解的 SHA-1 哈希函数，增强了安全最佳实践，提高了安全性。

综上所述，虽然 Red Hat 的大多数 DevSecOps 仍在开发中，但基于 Red Hat 的云未来看起来是安全的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>