# Flatcar Container Linux 商业版超越了 CoreOS 的根基

> 原文：<https://thenewstack.io/flatcar-container-linux-moves-beyond-coreos-roots-with-commercial-editions/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

自从[红帽收购 CoreOS](https://thenewstack.io/red-hat-will-acquire-coreos-greater-kubernetes-presence/) 使其 [CoreOS Container](https://thenewstack.io/say-goodbye-to-coreos/) Linux 成为自己产品的一部分以来，已经过去了将近三年。在收购后不久， [Kinvolk](https://kinvolk.io/) 将开源、容器优化的 Linux 发行版分叉开来，[将其作为一对一的替代](https://thenewstack.io/flatcar-linux-the-coreos-operating-system-lives-on-beyond-red-hat/)发布，称为 [Flatcar Linux](https://www.flatcar-linux.org/) 。

现在，在本月的 [KubeCon + CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)上，Kinvolk 通过在[Microsoft Azure market place](https://azuremarketplace.microsoft.com/en-gb/marketplace/apps/kinvolk.flatcar-container-linux-free)、 [AWS Marketplace](https://aws.amazon.com/marketplace/pp/B08MF9S9N4) 和[Google Cloud Platform market place](https://console.cloud.google.com/marketplace/product/kinvolk-public/flatcar-container-linux)上提供免费版本，以及发布两个商业可用和受支持的版本:Flatcar Container Linux Pro 和长期支持(LTS)。

容器优化的 Linux 提供了双重好处。首先，金沃尔克首席执行官克里斯·库尔(Chris küHL)解释说，攻击面大大减少了，因为你不需要包含各种依赖，因为那些都包含在容器中。

“你想从容器优化操作系统中得到的是最小的占用空间，”库尔解释道。“这意味着操作系统本身的攻击面极小。你也可以利用人们使用容器的方式，这是一个不可变的基础设施。例如，我们有一个只读文件系统。这缓解了一系列安全问题。”

接下来，Flatcar Container Linux 带来了使 CoreOS 流行的自动更新功能，其中操作系统在两个分区上运行，使其能够在一个分区上执行更新并相应地重新启动，而无需关闭系统。

自从今年早些时候 CoreOS Container Linux 正式离线以来，Kinvolk 已经看到 Flatcar Container Linux 的使用量上升，随着它的新普及，一些人希望进行更多针对云的微调和更慢的发布周期。

首先，Flatcar Container Linux Pro 将可用于 [Azure](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/kinvolk.flatcar_pro) ，预计 Google 和 AWS 将在晚些时候发布。Azure edition 将提供特定于平台的优化，如 Azure 调整的内核、对 Azure 加速网络的支持、所有 Azure GPU 启用的实例的内置驱动程序、HyperV 遥测支持和联邦信息处理标准(FIPS)加密模块。

库尔进一步解释说，Flatcar Container Linux Pro 和 LTS 将提供免费版本，在转移到 LTS 之前，这些功能通常首先出现在 Pro 中，这不仅会提供更长的支持周期，而且还会提供广泛适用的版本，应该用于内部部署。

“Pro 的某些功能肯定会进入 LTS。Pro 将开始只做云，”库尔说。“如果您在 prem 上执行此操作，LTS 版本将具有更通用的 Pro 功能。你不希望在你的裸机或本地安装上有特定于 Azure 的东西。像 FIPS 加密支持，GPU 支持，这些都是将进入 LTS 的东西，是最初将出现在 Pro 映像中的功能。”

有了 Flatcar Container Linux LTS 版，用户将获得 12 个月的发布周期，以及额外等待 6 个月更新的余地，总共可获得 18 个月的支持。这与稳定版本的免费发行版两个月的主要发布周期形成了对比。根据 Kühl 的说法，实际上是在 2018 年收购 CoreOS 和 2020 年 5 月终止生命之间的中间时期，产生了提供 LTS 版本的想法。

“一些来找我们的客户说，‘我们有点喜欢这样，因为它给了我们这种包装稳定性’”，库尔说。

直到 CoreOS Container Linux 的生命周期结束，Kühl 说，Kinvolk 主要是保持 Flatcar 的更新，但未来他们希望增加产品。

“我们在过去六个月里所做的事情证明，我们能够保持这种状态。在此之前，我们主要是跟踪 CoreOS 的变化，因为我们的保证之一是我们将成为替代品，所以我们没有试图偏离，”库尔说。“我认为 LTS 和 Pro 图像的发布表明，我们不仅有兴趣复制 CoreOS Container Linux 所做的事情，而且有兴趣扩展它。”

ds_30 de Pixabay 特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>