# Microsoft Azure 容器实例现已为生产工作负载做好准备

> 原文：<https://thenewstack.io/microsoft-azure-container-instances-are-now-ready-for-production-workloads/>

据微软公司称，去年预演的[微软](https://azure.microsoft.com/en-us/?v=17.14) [Azure 容器实例](https://azure.microsoft.com/en-us/services/container-instances/) (ACI)现已准备好投入生产使用。

微软将 ACI 吹捧为一种“无服务器”服务，它提供容器，无论是 Linux 还是 Windows，作为基本的计算原语，就像虚拟机(VM)是原语一样。微软首席项目经理 [Gabe Monroy](https://twitter.com/gabrtv?lang=en) 解释说，有了这些“无服务器容器”，最终用户不必担心基础设施的供应或管理。亚马逊网络服务公司去年晚些时候推出了一项类似的服务，名为 [Fargate](https://aws.amazon.com/blogs/aws/aws-fargate/) 。

Monroy 说，在最初的 ACI 预览中，微软发现客户正在使用这些服务进行批处理、持续集成和事件驱动计算。每秒计费模式也非常适合突发的工作负载。为此，微软降低了定价，取消了初始化容器的费用。当前价格为:

该公司希望较低的价格将吸引更多长期运行的工作负载，如运行网络服务器。在单个 vCPU 和 1GB 内存上运行的单个容器每月的成本约为 41.47 美元(30 天)。

微软承诺任何容器组的正常运行时间服务水平协议为 99.9%。每个容器都通过虚拟机管理程序进行保护和隔离。服务[跨越 6 个地区](https://docs.microsoft.com/azure/container-instances/container-instances-quotas#region-availability):美国西部、美国西部 2、美国东部、西欧、北欧和东南亚。

该公司还在此次正式发布中增加了一些新功能，包括

*   添加了 Execute (EXEC)命令，为容器提供交互式外壳。
*   能够[监控 Linux 容器的 CPU 和内存利用率](https://azure.microsoft.com/blog/azure-monitor-general-availability-of-multi-dimensional-metrics-apis/)。
*   通过 DNS 名称标签给每个容器一个可靠的端点地址的能力。
*   Azure 门户已经升级，增加了指标警报和查看容器日志/事件的功能。
*   容器状态和日志输出可以通过 [Azure CLI 2.0](https://docs.microsoft.com/cli/azure/container?view=azure-cli-latest#az_container_attach) 读取。
*   一组[容器重启策略](http://docs.microsoft.com/azure/container-instances/container-instances-restart-policy#container-restart-policy)。
*   多种卷类型可以用于挂载到 Linux 容器，包括 [Azure 文件](https://docs.microsoft.com/azure/container-instances/container-instances-volume-azure-files)、 [gitRepo](https://docs.microsoft.com/azure/container-instances/container-instances-volume-gitrepo) 、 [emptyDir](https://docs.microsoft.com/azure/container-instances/container-instances-volume-emptydir) 和 [secret](https://docs.microsoft.com/azure/container-instances/container-instances-volume-secret) 卷。

对于那些使用 Kubernetes 的人来说，由于 Kubernetes 的 ACI 连接器，ACI 可以由开源容器编排引擎控制。“ACI 连接器允许您将 ACI 容器的世界与 Kubernetes 的世界联系起来。你可以通过便携式 API 连接器来驱动所有这些东西，”蒙罗伊说。

去年 12 月发布的虚拟 Kubelet 允许 ACI 容器轻松连接到其他 Azure 资源。“它在 Kubernetes 中显示为一个节点。它不是一个真正的节点，而是一个服务的桥梁。但你可以像安排其他节点一样安排它，”蒙罗伊说。

微软是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>