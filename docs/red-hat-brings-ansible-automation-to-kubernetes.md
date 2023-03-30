# Red Hat 为 Kubernetes 带来了可行的自动化

> 原文：<https://thenewstack.io/red-hat-brings-ansible-automation-to-kubernetes/>

Red Hat 的 [Ansible](https://www.ansible.com/) 自动化平台即将来到你身边的 [OpenShift Kubernetes](https://www.openshift.com/) 集群。本周在 [AnsibleFest](https://www.ansible.com/ansiblefest) 上，Red Hat 展示了与[高级集群管理(ACM)](https://www.redhat.com/en/technologies/management/advanced-cluster-management) 的一个可行集成，这是一个用于管理和扩展混合云[上 OpenShift 集群的工具，今年早些时候发布](https://thenewstack.io/kubecon-eu-red-hat-expands-openshift-to-the-edge-with-advanced-cluster-management/)。

ACM 提供生命周期集群管理、基于策略的管理和高级应用程序部署，加上 Ansible，Red Hat OpenShift 用户现在能够将 Ansible automation 直接插入到这些生命周期中，而无需专门的脚本或其他方法。

“你总是可以在 OpenShift 环境中使用 Ansible，但我们在这里所做的是对它进行检测。例如，在集群生命周期创建期间，有一个地方您可以实际配置一个可行的剧本以在适当的时间点运行，”Red Hat 副总裁兼管理业务部门总经理 Joe Fitzgerald 解释道。“您以前可以做到这一点，但挑战在于，当有人去配置一个群集时，他们是否是在脚本之外完成的？他们是在控制台上做的吗？它可能是一个打开票证的单行剧本，可能就这么简单，但现在，您可以插入它，而在以前，人们有责任说在正确的时间点呼叫的机制是什么。”

Fitzgerald 提供了许多可以使用 Ansible automation 的示例，包括在部署后将应用程序连接到负载平衡器，或者在流程和治理方面，Ansible 可以用于补救目的，在应用程序违反特定策略时发出警告，并根据需要使其恢复合规性。至于 Ansible 可能的各种自动化操作，这是该平台在过去一年中一直关注的事情，它引入了 [Ansible 内容集合](https://www.ansible.com/products/content-collections)。

这些集合现在有超过 55 个，提供由 Red Hat 维护的认证 Ansible 内容，而 T2 的私人自动化中心为 Ansible 用户提供了一种在内部分享定制剧本的方式。

虽然高级集群管理的名称似乎暗示该工具仅适用于那些更复杂的 OpenShift 部署，但 Fitzgerald 表示，相反，它已经看到了“无论范围和规模如何”对该工具的兴趣，“我们的客户群几乎普遍对 ACM 感兴趣。”

虽然一个组织可能只运行一个集群，但他们可能处于一个受管制的行业，需要执行策略，而 ACM 提供了这一点。类似地，对于运行几个集群的组织，ACM 提供了对集群健康状况的可见性，现在有了 Ansible 集成，ACM 充当了“一个管理控制平面，允许我们非常清晰地设计这些 Ansible 点。”

目前，Ansible 与 ACM 的集成正在 tech preview 中推出，正式发布日期尚未确定。与此同时，Red Hat 还展示了一个“概念证明”，Fitzgerald 说，这是对 Ansible 的巧妙调用。 [Knative](https://knative.dev/) 是一个开源项目，允许用户在 Kubernetes 上运行容器作为无服务器、事件驱动的工作负载。

“想想事件驱动的自动化，可以调用 Ansible 剧本，而不是 Python 或其他东西。然后，您可以开始在未来配置这样的事情，“当我收到这个事件时，我想运行这个剧本。”菲茨杰拉德说:“这是另一种方式，可以在发生事情时轻松实现自动化，而不是通过非常复杂的管道或让团队参与进来，以便在正确的时间点实现自动化。”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>