# 向头盔 3 移动

> 原文：<https://thenewstack.io/making-the-move-to-helm-3/>

随着 Helm 3 的发布，该项目渴望让用户尽快迁移出 Helm 2。在 [Helm 3](https://thenewstack.io/helm-3-is-almost-boring-and-thats-a-great-sign-of-maturity/) 中，生产力和可用性的提高、改进的安全性和向后兼容性的结合意味着迁移通常会很简单。

“如果你的 Kubernetes 集群上有 Helm release，你可以将它们从 Helm 2 转换到 Helm 3，只需拿起它即可，”Azure Container 计算和发布主管 Kubernetes 1.16 的首席项目经理[拉克伦·艾文森](https://github.com/lachie83)告诉新堆栈。“我们甚至将现有的操作动词命名为新动词，以便人们可以获得无缝体验并进行迁移。我们的目的是尽快让所有人都进入 Helm 3。”

如果你使用水平吊舱自动缩放器，移动到头盔 3 有一个警告；当你使用掌舵图更新一个版本时，新的三向合并保留了边盘，也将副本的数量设置回图表中定义的数量，所以检查你使用的任何提供 HPA [的图表没有设置副本的数量](https://github.com/helm/helm/issues/7090#issuecomment-559161443)。之前的行为是一个错误，Helm 2 与 Kubernetes 本身不同，但在某种程度上证明是有用的。

## **插入并运行**

从头盔 2 转到头盔 3 有两种选择。你可以把所有东西从头盔 2 移植到头盔 3(有一个 [2to3 插件](https://GitHub.com/helm/helm-2to3)可以帮助你)，这意味着头盔 3 会接管现有头盔 2 版本的管理工作。IBM 高级软件工程师兼 Helm 核心维护人员 Martin Hickey 向我们解释说:“你可以把它看作实时迁移。”。

“这是您查看您的集群并说‘我想今天转移到 Helm 3，但我不想丢失我所有的版本’的地方。”该插件将状态信息移动到新的状态信息位置，这意味着将你已经安装的任何插件拉过来，尽管有一些小的例外。该插件所做的是跨这些版本进行映射，并以 Helm 3 格式存储它们，但它不涉及该版本已经部署的 Kubernetes 对象。它无缝运行。它也有一个清理功能，将删除释放信息的所有头盔 2 的状态，而不触及 Kubernetes 对象，它会为你删除蒂勒。"

如果你使用插件中的清理选项，你将无法回到头盔 2，所以请确保你首先备份，并使用**–模拟运行**标志来检查版本将被正确转换。

另一个选择是相当不祥的命名为“扼杀者模式”，你逐步淘汰头盔 2，因为兼容性意味着头盔 2 和头盔 3 可以毫无问题地管理同一个集群，只要你把头盔 3 二进制文件放在你的路径中的不同文件夹或重命名为**头盔 3。**

“你有头盔 2 和头盔 3 树，管理同一个集群，随着时间的推移，你做的每一个新的部署，你使用头盔 3，随着时间的推移，你扼杀或逐步淘汰头盔 2 版本。最终，你会发现不再有任何头盔 2 版本部署，而你在头盔 3 上，”Hickey 解释道。

“由于我们在架构和基础设施方面进行了重大变革，这种方式非常有效。基本上，对于 Helm 2，您的 Helm 状态信息和配置信息位于一个单独的目录结构中，存储在集群中的发布数据以不同的方式存储，因此它们不会遍历每一个。”

名称空间对于由 Helm 3 管理的版本来说是不同的，因为它们不再是默认的 **kube-system** 名称空间，并且如果你使用了 Helm 2 配置的秘密(不是默认选项)，它们也在 Tiller 名称空间中，但是 Helm 3 的秘密存储在用户名称空间中。

如果你已经习惯了 Helm 2，并且你正在一个新的系统上安装 Helm 3，你不必担心迁移，但是你需要知道默认情况下它不会设置任何 repos。这是获取图表的更广泛变化的一部分。

## **图表发行的未来**

为了鼓励组织转移到头盔 3，头盔 2 正在进入维护模式，头盔 2.15 作为最终功能发布。在 Helm 3 发布日期(截至 2020 年 11 月 13 日)之后，错误修复将持续六个月，安全补丁将持续一年。在同一时间线上， [GitHub 图表报告](https://github.com/helm/charts)已被否决。

这部分是关于从不再适合云本地计算基金会项目(在中国不可用)的谷歌云存储中转移，部分是关于从图表的集中存储(实际上不包括所有图表)转移到联合模型。

相反，现在可以通过[舵毂](https://hub.helm.sh/)访问图表，现在更容易搜索(如果你想让自己的内部图表更容易找到，你可以运行自己的舵毂)。稳定和孵化器图表回购从未真正打算成为图表的单一来源，它们将于 2020 年 5 月 13 日从 Helm Hub 退市，届时 Helm 2 将开始获得安全修复。

Codecademy 高级 DevOps 工程师兼 Helm 项目维护者斯科特·里格比告诉我们:“Helm Hub 的存在是为了现在启用图表的联邦模型，Helm 3 可以搜索 Helm Hub 以获取图表并加载它们。

随着图表数量的增长，更多的图表维护者可能希望将他们的图表发布到 GitHub 页面上托管的 Helm repo 已经有一些[实验用 GitHub Actions](https://github.com/stefanprodan/gh-actions/tree/master/helm-gh-pages) 实现了自动化。[图表发布器](https://github.com/helm/chart-releaser)工具将很快支持使用 GitHub 动作将 GitHub repos 转化为 Helm Chart repos 里格比说，它一直在等待 GitHub 的行动普遍可用。

从长远来看，让 Docker 注册管理机构支持[云原生应用捆绑包](/microsoft-buck-shows-how-cnab-bundling-could-work-for-cloud-app-deployment/) (CNAB)的工作也将允许 OCI 注册管理机构为 Helm chart 服务。

“对于 Helm 2，如果你想存储图表，你可以将它们存储在 Helm repo 中；这是一个 HTTP，HTTPS 网络服务器，将提供 tarballs，”Evenson 解释说。社区不希望维护另一个回购协议，尤其是一个具有旧身份验证机制的回购协议。OCI 发行规范 v2 包括多种媒体类型，包括 Helm charts，它与 Helm 3 安全态势更匹配。

“我们可以利用该工具中的所有安全插件和授权模型，而不仅仅是 Helm 2 中的基本身份验证。我们想让它成为一个安全的体验，作为一个副作用，它现在集成到你所有的其他工具中。你现在可以在同一个空间存储你自己的图表，所以这是一个很好的集成体验。我们有很棒的集装箱仓库:我们把其他的文物放在那里怎么样？”

云计算原生计算基金会是新堆栈的赞助商。

由 [Erda Estremera](https://unsplash.com/@erdaest?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的特征图像。](https://unsplash.com/s/photos/moving?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>