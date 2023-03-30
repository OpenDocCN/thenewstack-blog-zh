# Kubernetes 1.20 增强了操作员的体验，并为容器运行时带来了新的特性

> 原文：<https://thenewstack.io/kubernetes-1-20-enhances-the-operator-experience-and-brings-new-features-to-the-container-runtime/>

[](https://www.linkedin.com/in/hillary-benson/)

 [希拉里本森

作为 StackRox 的产品主管，希拉里本森负责产品战略、产品设计和产品管理。她在安全行业和情报界拥有超过 10 年的经验。在加入 StackRox 之前，她带领团队为国家安全局执行技术情报收集任务，并在私营企业担任红队操作员和安全工程师。希拉里拥有乔治城大学沃尔什外交学院安全研究硕士学位和麻省理工学院管理学学士学位。](https://www.linkedin.com/in/hillary-benson/) [](https://www.linkedin.com/in/hillary-benson/)

本月初，Kubernetes 1.20 向社区发布了 42 项新的和更新的功能增强。随着 Kubernetes 背后的团队继续以新的创新推动 Kubernetes 的快速发展，1.20 版的发布反映了 Kubernetes 平台的发展，更新了关键技术，如容器运行时，并改善了最终用户和操作员的体验。

在 Kubernetes 1.20 的 42 个新特性中，16 个是在 alpha 中发布的，15 个升级到 beta，11 个升级到 stable。用户将很高兴看到许多关键功能的增强，包括正常的节点系统关闭、kubectl 调试、PID 限制、CronJobs 的更新、IPv4/IPv6 双栈支持、卷快照操作等等。还值得指出的是，Docker 运行时弃用机制正在发生重大变化，并且已经修复了 kubelet exec 探测超时。

## **功能增强:节点正常关闭**

在 Kubernetes 1.20 中的许多用户友好的功能更新中，优雅的节点关闭功能(现在在 alpha 中)通过确保 kubelet 知道节点系统关闭来改进 pod 终止。由于该功能已得到增强，允许 kubelet 知道节点系统关闭，因此操作员需要进行的故障排除和调试工作将会减少，从而改善了 pod 终端。

### **功能增强:进程 ID 限制**

过程 ID (PID)限制已经升级到 GA，不再要求用户配置`SupportNodePidsLimit`。这一改进增加了对配置 kubelet 的支持，以限制单个 pod 可以使用的 PID 数量。这将限制它们对节点上其他 pods 的影响，并确保应用 pods 不会导致 PID 耗尽，从而阻止主机守护进程(如容器运行时或 Kubelet)运行。还有一个额外的安全好处是，它可以防止坏进程(如加密挖掘应用程序)消耗太多资源。

### **功能增强:CronJobs**

CronJobs 已更新，以解决可伸缩性和其他问题，目标是在 1.21 或 1.22 版中将其升级为稳定版本。为了尝试新的实现，必须启用`CronJobControlerV2`特征标志。这个特性是在 1.4 版本中引入的，现在仍然被广泛使用，甚至在生产环境中也是如此，但是它还没有达到稳定的状态。

### **功能增强:IPv4/IPv6 双栈支持**

Kubernetes 在版本 1.16 中首次添加了对向 pod 和服务分配 IPv4 或 IPv6 地址的支持，而不是整个集群。版本 1.20 中引入了许多更新，因此，这个特性仍然保留在 alpha 中。对双栈模式的本机支持非常重要，它将提供几个好处来适应不同类型的 Kubernetes 工作负载，但预计这一功能进入测试版还需要一些时间。

### **功能增强:卷快照操作**

随着 Kubernetes 成功地解决了如何提供适当的原语来支持利用快照的更高级的存储用例，卷快照已经发展到稳定状态。在 1.20 版中，该功能提供了一种创建和管理卷快照操作的标准方法，作为一种可靠的数据恢复机制。

### **显著变化:Docker 运行时弃用**

用户知道 Docker 运行时支持[将在未来几个版本——可能是 1.22——中从 Kubernetes 中移除](https://thenewstack.io/this-week-in-programming-kubernetes-says-dont-panic-about-docker-deprecation/),这一点很重要。许多 Kubernetes 平台，如 Azure Kubernetes Service (AKS)和 Red Hat OpenShift，已经转移到其他容器运行时，如 containerd 和 CRI-O，因此它们可以保持与 Kubernetes 的容器运行时接口(CRI)兼容。Docker 运行时与 Kubernetes 的 CRI 不兼容。此外，Dockershim，Kubernetes 目前需要使用 containerd 的工具，将在 1.22 或未来的版本中删除。

值得注意的是，与 Docker 运行时分离的 Docker 映像可以继续用于任何符合 CRI 的运行时——这是因为 Docker 映像符合标准化开放容器倡议(OCI)格式。在自己的集群上运行开源 Kubernetes 的用户应该开始适应这种 docker 运行时弃用。然而，如果使用受管理的分发 Kubernetes 服务，如 OpenShift，提供商可能会帮助验证关闭 Docker 运行时对环境没有影响。

### **显著的变化:修复了 Kubelet Exec 探测超时**

Kubelet exec 探测超时是一个长期存在的问题，最终在 1.20 中得到修复。Exec 探测器现在将考虑字段`timeoutSeconds`，如果没有指定值，则默认为一秒。这可能需要更新当前的 pod 规格，因为以前的探头会无限期运行。

现在，您不必立即检查 pod 定义。通过将新的特性门`ExecProbeTimeout`配置为 false，可以恢复到以前的行为。但是，在未来的版本中，此功能门将被删除。

### **其他更新**

在 1.20 版本中，API 优先级和公平性已经升级到测试版，该特性现在默认启用，将有助于管理请求。`EndpointSlice` API 也经历了额外的变化。版本 1.20 对第三方设备监控插件的支持也逐渐稳定。这使得深入了解设备插件提供的设备的容器级指标成为可能。

## **Kubernetes 的未来**

我们继续看到 Kubernetes 在生产中部署的快速增长，这些最新的功能可能会进一步加速这种采用。随着 Kubernetes 为其用户提供的功能越来越多，它正在巩固自己作为集装箱化的支柱，在许多情况下，也是数字业务的支柱。有关 Kubernetes 1.20 的更多信息，请查看官方[发行说明](https://kubernetes.io/docs/setup/release/notes/)以获得完整的变更列表。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>