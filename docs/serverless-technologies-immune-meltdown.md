# 无服务器技术也不能幸免于崩溃

> 原文：<https://thenewstack.io/serverless-technologies-immune-meltdown/>

(编者注:这篇报道与最初发布的版本有所不同，为了进一步审查技术准确性，删除了一些材料。)

由于 Meltdown 安全补丁带来的内部和基于云的 CPU 挑战，工程师和 DevOps 领导正在分享运行其系统的成本影响和性能降级。

TNS 分析师劳伦斯·赫克特(Lawrence Hecht)上周对 Sysdig、AWS 和红帽 的综合报道指出，一些早期数据显示，这些影响可能会成为一个持续的问题。Meltdown 安全补丁将继续需要更高的 CPU 工作负载来解决英特尔和其他处理芯片中的漏洞。毕竟，芯片本身并没有打补丁，安全补丁必须围绕硬件工作，这意味着应用程序和基础设施运营费用跃升至一个新常态。

发展迅速的东南亚出租车、送货和支付提供商 Grab 是最新一家记录金融危机对其基础设施影响的公司。虽然他们的无状态[弹性云计算](https://aws.amazon.com/ec2/) (EC2)实例相对安全——他们只是终止了现有的实例并启动了新的实例——但对其弹性缓存和 Redis 实例的影响(正如 [Sysdig 也报告了](https://sysdig.com/blog/making-sense-of-meltdown/))是 CPU 利用率急剧上升。

Grab 在争分夺秒地管理其性能峰值:其流量峰值出现在周五，因此它需要在最繁忙的客户需求期之前不断实施任何潜在性能问题的解决方案。随着 AWS 开始对 ElastiCache 节点执行滚动补丁，Grab 的工程师可以观察他们的 CPU 峰值，看到故障转移被触发到一个新节点，然后再次观察新节点被打补丁，迫使新的 CPU 罢工。这种洞察力让 Grab 的工程师引入了更多的 Redis 集群和更多的碎片，以更好地分散负载，从而使新的平均 CPU 使用率达到大约 24%至 30%的峰值。

Grab 和其他公司的经验表明，Meltdown 的影响因所执行的工作负载类型而异。但是，与其他架构安排相比，无服务器工作负载是否更不受性能(和价格)峰值的影响？

自 1 月 3 日以来，亚马逊网络服务几乎每天都会发布定期新闻更新，宣布 Meltdown 和 Spectre 的安全补丁。到 1 月 4 日，所有运行 Lambda 功能的 AWS 基础设施实例——AWS 无服务器产品的核心——都已被修补，无需最终用户采取任何行动。

对于无服务器用户来说，这与那些管理自己的云基础架构(包括 EC2 上的云基础架构)的云用户(例如，他们面临着审查是否在 Windows 实例上启用了自动更新的繁琐任务)的场景截然不同。总的来说，DevOps 工程师被鼓励修补他们的实例操作系统，但是，像 Grab 的工程师一样，可能需要对所有常规和业务关键型工作负载的性能影响进行更全面的分析。

无服务器行业专家认为，可能会有一些轻微的熔毁无服务器的影响。有人推测，当 Lambda 将一个实例(本质上是一个容器)放到后台时，这个过程可能会对性能产生很大影响。Amazon 空间、内核空间和最终用户的工作空间之间存在本地安全差异，因此安全补丁可能会导致新 Lambda 函数的冷启动速度变慢。

专题图片:罗克珊·德斯加涅斯在 [Unsplash](https://unsplash.com/search/photos/melt?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>