# Red Hat 将备份、快照引入 OpenShift 容器存储

> 原文：<https://thenewstack.io/red-hat-brings-backup-snapshots-to-openshift-container-storage/>

开源企业软件提供商 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 为其[open shift Container Storage](https://www.redhat.com/en/technologies/cloud-computing/openshift-container-storage)推出了新的功能，该功能与其 [OpenShift Kubernetes](https://www.openshift.com/blog/enterprise-kubernetes-with-openshift-part-one) 平台密切合作，为其客户提供增强的数据弹性功能。[Red Hat open shift Container Storage 4.6](https://access.redhat.com/documentation/en-us/red_hat_openshift_container_storage/4.6/html/4.6_release_notes/introduction)增加了快照、[open shift API for Data Protection(OADP)](https://access.redhat.com/articles/5456281)，以及三个备份解决方案对新功能的支持，还有几个正在开发中。

“如果你看看传统的裸机甚至虚拟化环境，状态通常与应用程序紧密耦合。它产生了一个非常单一的体系结构，肯定有很多好处，尤其是当您考虑灾难恢复、备份等这类主题时。这是一个非常容易理解的架构，以及如何处理一致性和备份等问题，”Red Hat 混合云对象存储营销经理 [Pete Brey](https://www.linkedin.com/in/petebrey) 解释道。"有了 Kubernetes，情况就大不相同了，因为在持久卷中，状态与应用程序是分离的."

Brey 说，最近，Kubernetes 已经从开发人员可能会尝试的东西转移到企业将在生产中运行的东西，因此，这些企业已经来到 Red Hat，寻找他们已经开始期待的与传统应用程序架构和基础架构相同的数据弹性功能。

“他们希望我们不仅仅是一个存储提供商，”Brey 说。“他们希望我们提供数据服务，即围绕数据弹性、数据安全性、数据治理、数据发现、数据编目和数据效率的服务。”

在 Red Hat OpenShift Container Storage 4.6 中，可定制的时间点快照和持久数据卷的克隆将由[容器存储接口(CSI)](https://kubernetes-csi.github.io/docs/) 协调，尽管 Brey 进一步澄清了 CSI 和 open shift 容器存储本身并不负责全部功能。相反，应用程序本身需要通过在启动快照之前停止 I/O 和刷新缓冲区来管理一致性。

OpenShift 容器存储用户将能够通过 OpenShift 用户界面或 OpenShift 数据保护 API(OADP)访问这些数据弹性功能和配置，这也使 Red Hat 的合作伙伴生态系统能够将其数据保护解决方案与 OpenShift 集成。

[https://www.youtube.com/embed/KsHT-ZwCsX8?feature=oembed](https://www.youtube.com/embed/KsHT-ZwCsX8?feature=oembed)

视频

Brey 说，使 IT 团队能够使用他们现有的解决方案和知识是此次发布的重要组成部分。

“组织终于意识到 Kubernetes 的事情不会消失。是真的。甚至 DB2 数据库现在也可以在 Kubernetes 上运行。Brey 说:“您的数据保护团队、所有知识、所有工具、他们构建的所有基础架构，以及他们投资的 300 万美元，您不需要将它们扔掉。“IT 组织有许多关于如何进行备份的知识。我们不会要求您丢掉所有的知识，重新学习如何进行备份和恢复，例如，使用 Kubernetes。

为此，Brey 表示，Red Hat open shift Container Storage 与三家支持新功能的存储供应商一起推出，包括用于 Kubernetes 的[TrilioVault](https://www.trilio.io/triliovault-for-kubernetes/)、 [IBM Spectrum Protect Plus](https://www.ibm.com/products/ibm-spectrum-protect-plus) 和 [Kasten K10](https://www.kasten.io/product/) ，还有几家正在开发中。

展望未来，Brey 表示“业务连续性和灾难恢复部分”将是下一个重点，Red Hat 预计将在未来三个月内提供新的功能。

由[马库斯·温克勒](https://unsplash.com/@markuswinkler?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/storage?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>