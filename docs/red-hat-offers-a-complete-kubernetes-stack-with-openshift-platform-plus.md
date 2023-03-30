# Red Hat 通过 OpenShift Platform Plus 提供了“完整的 Kubernetes 堆栈”

> 原文：<https://thenewstack.io/red-hat-offers-a-complete-kubernetes-stack-with-openshift-platform-plus/>

企业开源软件公司 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 本周在该公司的 [Red Hat 虚拟峰会](https://www.redhat.com/en/summit)上推出了最新的 Kubernetes 产品，并引入了 OpenShift Platform Plus。Red Hat OpenShift Platform Plus 将该平台称为“开箱即用的完整 Kubernetes 堆栈”，旨在提供构建、部署和运行任何应用程序所需的一切，只要红帽的 Kubernetes 平台 [OpenShift](https://www.openshift.com/) 能够运行。

更具体地说，OpenShift Platform Plus 将针对 Kubernetes 的 [Red Hat 高级集群安全](https://www.redhat.com/en/resources/advanced-cluster-security-for-kubernetes-datasheet) (ACS)、针对 Kubernetes 的 [Red Hat 高级集群管理](https://www.redhat.com/en/technologies/management/advanced-cluster-management) (ACM)和 [Red Hat Quay](https://www.redhat.com/en/technologies/cloud-computing/quay) 捆绑到一个产品中。

如果你看一下 Red Hat 的 Kubernetes 产品，就会发现一个明显的层次结构，从更多的自己动手的基本产品到功能齐全的产品。在基础上，有 Red Hat OpenShift，现在有三个产品。首先，有 Red Hat OpenShift Kubernetes 引擎，它在 Red Hat Enterprise Linux CoreOS 的基础上提供 Kubernetes。接下来，Red Hat OpenShift 容器平台为应用程序开发和现代化增加了开发人员和操作工具。最后，OpenShift Platform Plus 以这些附加工具为基础，作为单个捆绑包的一部分。

“在此之前，您可以购买 OpenShift，并添加 ACM、ACS 和 Quay。这样做的结果是，它大大简化了投资组合和产品。Red Hat 云平台市场洞察总监 Stu Miniman[表示:“客户在做多集群、混合云或多云时，我们认为这些是最有意义的。“OpenShift Platform Plus 也将成为我们未来增加其他产品的载体。所以，不要预先宣布任何收购，但如果我们进行另一项收购，那就有必要投资。”](https://www.linkedin.com/in/miniman)

OpenShift Platform Plus 已经整合了 Red Hat 之前通过收购获得的两个产品。首先，[ACM 是通过 IBM](https://thenewstack.io/red-hat-expands-openshift-to-ease-developer-use/) 收购该公司而来的，它最初是作为 [IBM](https://www.ibm.com/cloud?utm_content=inline-mention) 的[Cloud Pak for multi Cloud Management](https://www.ibm.com/cloud/cloud-pak-for-management)而诞生的，后来在 2020 年宣布成为 OpenShift 4.4 的一部分。接下来，ACS 其实就是四个月前[红帽刚刚收购 StackRox](https://thenewstack.io/what-red-hats-purchase-of-stackrox-means-for-openshift-security-and-observability/) 的实现。

“以前被称为 StackRox 的现在是 ACS:那是安全的供应链、安全的基础设施、安全的工作负载、Kubernetes-native，”Miniman 说。“Red Hat 在保护操作系统方面有超过 20 年的经验，我们在保护 Kubernetes 本身方面有超过 5 年的经验，这是在收购 StackRox 的基础上增强的安全性。”

当 Red Hat [今年早些时候收购](https://thenewstack.io/what-red-hats-purchase-of-stackrox-means-for-openshift-security-and-observability/) StackRox 时，它购买了一个安全平台，该平台在其安全产品中添加了一个“左移”组件。借助 ACS，Red Hat OpenShift Platform Plus 致力于保护供应链，提供云安全状态管理(CSPM ),旨在识别和修复有风险的云配置，并通过实施零信任安全状态来保护工作负载。

Miniman 强调，ACS 仍将作为独立产品单独提供，并指出 StackRox 的一半客户已经是 Red Hat 的客户，但其中近四分之三的客户正在使用亚马逊网络服务、微软或谷歌基于云的 Kubernetes 产品。至于 ACS 是否会开源，Miniman 说“当我们进行收购时，我们重申了我们的声明，我们的目标始终是 100%开源”，但他们还没有 OpenShift Platform Plus。他说会有一些关于 [Kubelinter](https://github.com/stackrox/kube-linter) 的消息，这是 StackRox 在收购时发布的一款开源静态分析工具，将在几周后在 Kubecon 上发布，再次强调开源在 Red Hat 安全方面的重要性。

“要想更加安全，最重要的一点是你需要保持更新。在开源世界中，它最大的优势之一就是它的移动速度。我们在构建解决方案的过程中发现，Kubernetes 存在一些我们没有发现的漏洞，因为我们要么在操作系统层面做了什么，要么我们在 Kubernetes 层面如何配置，”Miniman 说。“我们不担心‘哦，嘿，如果我们开源它，它会变得不安全吗？’不，恰恰相反。我们认为开源是安全做事的好方法。"

总的来说，Miniman 将 OpenShift Platform Plus 描述为在一个位置提供所有必要的部分，这在目前是不常见的。

“如果你看看云服务的获得和管理方式，通常你不会有这种杰作，”Miniman 说。“你通常会挑选你想要的东西，然后按需付费。”

展望未来，Miniman 表示，Ansible，Red Hat 的开源软件供应、配置管理和应用程序部署工具，可能会在 OpenShift Platform Plus 中出现，该公司将致力于使 ACS 体验与其其他产品更加无缝。

“你知道，我们已经重新命名了它，我们已经得到了正确的配色方案，但图形用户界面看起来有点不同于我们产品组合的其余部分，”Miniman 说，“所以，我们不仅致力于获得外观和感觉，而且随着时间的推移，这一整套产品之间的集成将更加深入和紧密。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>