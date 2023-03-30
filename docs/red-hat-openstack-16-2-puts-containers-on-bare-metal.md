# Red Hat OpenStack 16.2 将容器放在裸机上

> 原文：<https://thenewstack.io/red-hat-openstack-16-2-puts-containers-on-bare-metal/>

企业开源软件提供商 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 在今年的 [KubeCon+CloudNativeCon 北美](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)发布了 Red Hat OpenStack 16.2，该版本展示了与该公司 Kubernetes 产品 Red Hat OpenShift 的更紧密集成。

那些希望在虚拟机中运行云原生应用和传统应用的组织是 Red Hat 最新版本的目标，Red Hat 为其用户同时提供了裸机的优势和 Kubernetes 的可扩展性。[Red Hat 全球产品管理负责人 Sean Cohen](https://www.linkedin.com/in/cohensean/) 解释说，电信公司是一个明显的例子，它们将在这个最新版本中发现价值。

科恩在一封电子邮件中写道:“Red Hat OpenStack 平台集成上的新 Red Hat OpenShift 允许您拥有两个世界的最佳优势。对于电信服务提供商来说，这意味着将虚拟化网络功能(vnf)与云原生网络功能(CNF)并行运行，以实现裸机性能

同时，Red Hat OpenStack 16.2 为这些电信服务提供商提供了支持高性能工作负载的快速数据路径功能，他解释说，OpenStack Neutron 快速数据路径端口可作为虚拟机中的 PCI 设备使用，现在可以映射到 CNFs，“有效地为虚拟和本地功能提供等效的裸机性能。”

由于从 4G 到 5G 网络的持续转移，电信公司是此次发布的明显目标，尽管[认为 OpenStack 即将消亡](https://thenewstack.io/investigating-the-next-generation-of-infrastructure-as-a-service/)，Cohen 解释说，开源云计算基础设施项目最近出现了复苏，部分原因就在于此。

Cohen 写道:“请记住，OpenStack 仍然是许多电信服务提供商的支柱，为 4G 核心网络提供动力，并为全球约 25 亿移动用户提供服务，因此我们在这里看到的是 4G 部署的持续增长，以及新的 5G 部署。”

尽管如此，这些并不是唯一受益于 Red Hat OpenStack 16.2 的组织。相反，Cohen 说“我们预计我们的大多数客户将采用这一版本，以及希望在新的核心部署和边缘中引入最新加速和 OpenShift 集成的新客户。”

Red Hat 对边缘部署的整体关注进一步体现在其最新的[版本 Red Hat OpenShift 4.9](https://thenewstack.io/red-hat-openshift-4-9s-single-node-clusters-for-the-edge/) 中，该版本将单节点集群带到了边缘，OpenStack 16.2 通过开放虚拟网络(OVN)增加了可用性区域意识。这一新功能支持根据地理位置、电源和潜在停机时间对节点进行分组，从而允许进行调度，以确保以最高的可用性访问节点。

Cohen 解释说，总的来说，Red Hat OpenStack 16.2 为最终用户提供了一种混合策略，既可以沿着云原生工作负载运行传统工作负载，也可以混合私有云和公共云。

“混合云策略的最大好处是能够为每个任务或工作负载选择最佳解决方案，”他写道。“我们的许多客户希望在其大规模私有云部署中提供云原生工作负载，以便更快地创新和上市，并加快应用程序开发。他们可以通过允许 OpenStack 为 OpenShift 提供基础架构即服务(IAAS)，以及多租户、自助服务、负载平衡器和加密等补充服务来实现这一点，从而有效地允许 OpenShift 在 OpenStack 提供的基础架构上运行其容器化应用，并使用与虚拟机相同的 IaaS 服务。由于产品紧密集成，OpenShift 可以按需消耗 OpenStack 资源，无需用户干预，因此 [OpenStack 和 OpenShift](https://www.redhat.com/en/resources/red-hat-tested-openshift-openstack-reference-architecture) 的关系是互补的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>