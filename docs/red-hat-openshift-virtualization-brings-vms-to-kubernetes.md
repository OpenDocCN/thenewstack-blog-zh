# Red Hat OpenShift 虚拟化将虚拟机带到 Kubernetes

> 原文：<https://thenewstack.io/red-hat-openshift-virtualization-brings-vms-to-kubernetes/>

早在容器变得流行之前，虚拟机(VM)就是虚拟化的事实标准，并且对于今天的许多公司来说仍然如此——即使那些现在看到容器和整个云原生 Kubernetes 生态系统的好处的公司也是如此。

许多组织可能永远不会看到从一种技术到另一种技术的全面迁移，在本周的[虚拟红帽峰会](https://www.redhat.com/en/summit)上， [Red Hat](https://www.redhat.com) 推出了 OpenShift 虚拟化的技术预览，以处理容器和虚拟机混合的混合环境。

“这基本上使 Kubernetes 不仅可以管理容器，还可以管理虚拟机，”Red Hat 核心云平台副总裁 [Joe Fernandes](https://www.linkedin.com/in/joefernandes1/) 在接受采访时说。“这是一个机会，可以为客户提供一种新的方法，让他们能够以更加云原生的方式管理这些特定的工作负载，并利用融合的管理平面，这实际上是由 OpenShift 支持的 Kubernetes。”

该公司表示，考虑到市场需求，此举是必要的。

“我认为虚拟机永远不会完全消失。这并不是说虚拟机中运行的所有东西都将被转移到容器中。当然，许多工作负载已经迁移到容器，许多新的工作负载从一开始就部署在容器中，”Fernandes 说。

该功能是 OpenShift 4.4 的一部分，open shift 4.4 是红帽企业 Kubernetes 产品的最新版本，在本周的虚拟红帽峰会上发布。随着 [OpenShift 无服务器](https://www.openshift.com/learn/topics/serverless)的全面上市，Red Hat 在一篇博客文章中声称，OpenShift 虚拟化为 OpenShift 用户提供了“跨虚拟机、容器和无服务器功能的一致开发体验”，并提供了“根据需要更新或不更新虚拟机”的能力。

OpenShift 虚拟化基于 [KubeVirt](https://kubevirt.io/) 社区项目，它通过使用 [KVM 基于 Linux 的管理程序](https://www.linux-kvm.org/page/Main_Page)来工作，该管理程序实际上运行在一个容器中，可以与其他容器化的工作负载并行运行。

## Red Hat 或 VMware

去年 8 月， [VMware 推出了 Project Pacific](https://thenewstack.io/vmwares-project-pacific-integrates-vsphere-with-kubernetes/) ，从相反的方向解决了同样的问题，将容器和 Kubernetes 引入其虚拟化平台 vSphere。Fernandes 说，区别在于你是否希望你的核心技术是 Kubernetes 或 vSphere，以及它们的未来在哪里。

“我们感觉我们提供的是一种更现代的云原生方法。如果您无论如何都要采用您的 Kubernetes，为什么不直接在裸机上对容器和虚拟机工作负载都采用它呢？我完全期待 OpenShift 和 vSphere 能够共存。我们有大量客户在 vSphere 上运行 OpenShift，”Fernandes 说。“这种情况不会消失，但对于一部分客户或我们共有的特定客户的一部分环境来说，直接在裸机上运行 OpenShift 和 Kubernetes 将是适合他们的架构。将容器和虚拟机工作负载置于其上的能力将会很有吸引力。”

Fernandes 还指出，在裸机上运行 OpenShift 虚拟化实际上会节省一些开销。

“当您运行虚拟机工作负载时，通常是在裸机环境中运行，否则您会在另一个虚拟机中运行一个虚拟机。Fernandes 说:“您必须在裸机上部署 OpenShift，实际上您已经取消了一层，即虚拟化层。“如果您在数据中心，现在您可以直接在裸机上运行它。您获得了简化堆栈效率。只是你运行 Kubernetes 的裸机服务器。”

OpenShift 虚拟化的全面正式发布预计在今年晚些时候进行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>