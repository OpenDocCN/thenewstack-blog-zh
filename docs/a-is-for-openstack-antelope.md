# a 代表 OpenStack 羚羊

> 原文：<https://thenewstack.io/a-is-for-openstack-antelope/>

13 年前，美国宇航局艾姆斯研究中心和 T2 Rackspace 的开发人员独立提出了开源基础设施即服务(IaaS)云的想法。今天，我们称之为云 [OpenStack](https://www.openstack.org/) 。现在，继[发布 Austin to Zed](https://www.zdnet.com/article/openstack-from-austin-to-zed/) 之后， [OpenInfra Foundation](https://openinfra.dev/) 发布了羚羊，这是世界上部署最广泛的开源云基础设施软件的第 27 个版本。

今天，它不仅仅是一个开源云，它已经成为 Linux、OpenStack 和 Kubernetes infra structure(LOKI)trifecta 堆栈的一个组件。随着羚羊的发布， [OpenStack](https://thenewstack.io/bad-news-for-cloud-computing-openstack-use-plummets-and-discounts-dry-up/) 带来了一系列增强，包括与 [Kubernetes](https://kubernetes.io/) 和其他开源技术的更强集成，以及对高级硬件的扩展支持，以满足其快速增长的用户群。

## 新发布节奏

羚羊推出了新的发布节奏，允许部署选择每年一次升级，而不是传统的六个月周期。第 28 个版本 OpenStack Bobcat 定于 2023 年 10 月发布，将是一个非跳过级升级发布过程(非 SLURP)版本。

这种转变是由 OpenStack 客户推动的，如 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) ，它在其 [Red Hat OpenStack 平台(RHOP)](https://www.redhat.com/en/technologies/linux-platforms/openstack-platform) 中使用 OpenStack。红帽的 OpenStack 工程总监伊奥汉·格林解释道，“红帽的客户要求我们在稳定性和新近性之间取得平衡。”这种转变使得 Red Hat 和其他 OpenStack 分销商更容易在最新软件和稳定性之间实现平衡。

[2022 年 OpenStack 用户调查](https://www.openstack.org/user-survey/2022-user-survey-report)显示，Kubernetes 现在部署在超过 85%的 OpenStack 部署中。因此，为了改善其在羚羊版本中的 [Kubernetes](https://thenewstack.io/kubernetes/) 支持，OpenStack 容器编排服务 [Magnum](https://docs.openstack.org/magnum/latest/) 已经更新为在 [Fedora CoreOS](https://getfedora.org/en/coreos/) 36 和 37 上支持 Kubernetes v1.24。它还被[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 重新认证为 Kubernetes orchestrator。

OpenStack 贡献者还在羚羊版本中扩展了对新硬件的支持。[其数据块存储服务 Cinder 现在为惠普 XP iSCSI 和 FC、可替换的 NVMe-TCP 和 NetApp NVMe-TCP 提供后端驱动程序。](https://wiki.openstack.org/wiki/Cinder)

[讽刺的](https://wiki.openstack.org/wiki/Ironic)，OpenStack 裸机供应服务而不是阿兰妮斯·莫利塞特之歌，现在将应用指标从讽刺导体服务导出到 [Prometheus](https://prometheus.io/) 实时指标事件监控和警报服务。以前这些只能通过 [statsd](https://github.com/statsd/statsd) 访问。

由于 OpenStack 的虚拟机(VM)供应服务 [Nova](https://docs.openstack.org/nova/latest/) 的变化，运营商可以管理专用 CPU 的功耗。如果它们当前没有被任何实例使用，或者该实例已被停止，则通过使它们脱机或更改它们的调控器，这使您能够降低功耗和成本。

至于安全性，OpenStack 的[网络连接即服务(NaaS)](https://thenewstack.io/orange-relies-opnfv-transform-networks-future/) [中子](https://wiki.openstack.org/wiki/Neutron)实现了安全的基于角色的访问控制( [sRBAC](https://thenewstack.io/7-expert-strategies-for-managing-rbac-on-openshift/) )。这是由 [Glance](https://docs.openstack.org/glance/latest/) 执行的，这是一种允许用户发现、检索和注册虚拟机和容器映像和元数据的映像服务。

## 变更和发布功能

羚羊总共包括来自 110 多个组织和 40 多个国家的超过 601 个贡献者创作的 9，794 个变更。新功能、安全更新和一个名为 [Skyline 的技术预览项目、一个仪表盘](https://wiki.openstack.org/wiki/Skyline)都是该版本的进步。

此外，OpenInfra 基金会宣布了其[准成员类别](https://openinfra.dev/members/)的两个新成员: [Python 软件基金会](https://www.python.org/psf-landing/)和 [Rust 基金会](https://foundation.rust-lang.org/)。

这是一个自然的进步，因为在 [OpenInfra](https://thenewstack.io/how-openinfra-can-solve-the-global-connectivity-crisis/) 软件项目中使用了 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) 和 [Rust](https://thenewstack.io/rust-vs-go-why-theyre-better-together/) 编程语言。比如 OpenStack 就是建立在 Python 之上的。open infra[Kata Containers](https://katacontainers.io/)社区支持一个容器运行时，该运行时提供具有 VM 安全性的容器的速度，该社区正在继续其大规模的“改进”,以获得更好的性能和安全性。Python 和 Rust 都非常适合 OpenInfra 用例，Python 适合高级集成，Rust 适合低级安全基础设施。

有关羚羊发布功能的完整列表，请参见[发布说明](https://releases.openstack.org/antelope/)。现在可以下载 [OpenStack 羚羊版](https://www.openstack.org/software/antelope)。尽情享受吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>