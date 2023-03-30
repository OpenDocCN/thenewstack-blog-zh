# Google 计算引擎现在提供自定义虚拟机规模

> 原文：<https://thenewstack.io/google-compute-engine-now-offers-custom-virtual-machine-sizing/>

谷歌计算引擎用户将不再被迫在预设的 vCPU 速度中进行选择。该公司已经正式推出了[定制机器类型](https://cloud.google.com/custom-machine-types/)，允许用户使用定制的 vCPU 和内存配置创建虚拟机。

谷歌估计，这种方法可以为用户节省高达 50%的计算成本。该公司在 11 月首次公布了测试版的服务[。](https://googlecloudplatform.blogspot.com/2015/11/introducing-Custom-Machine-Types-the-freedom-to-configure-the-best-VM-shape-for-your-workload.html)

“自从我们的[测试版](https://googlecloudplatform.blogspot.com/2015/11/introducing-Custom-Machine-Types-the-freedom-to-configure-the-best-VM-shape-for-your-workload.html)发布以来，我们已经看到客户创建了具有新的 vCPU 和内存比率的虚拟机，这些虚拟机是任何主要云提供商都无法提供的，”萨米·伊克拉姆在博客文章中写道，他是谷歌云平台[的产品经理。](https://googlecloudplatform.blogspot.com/2016/02/Custom-Machine-Types-goes-GA-saving-you-up-to-50-percent-on-compute-costs.html)

自定义机器类型提供了一种为手头的特定工作负载配置虚拟机的方法，可以根据您愿意支付的价格来平衡您需要的内存和 CPU 能力。

当用户登录谷歌云平台的计算部分时，[他们现在会看到](https://cloud.google.com/compute/docs/instances/creating-instance-with-custom-machine-type)创建基本或“定制”机器类型的选项。

一台虚拟机可以少至一个 vCPU，多至 32 个 vCPU。也可以设置内存，最高可达 6.5 [千兆字节](http://wintelguy.com/gb2gib.html)。

该公司声称，与使用标准的虚拟现成 vCPU 配置相比，尝试过这种方法的客户平均节省了 19%。

例如，托管提供商 [Wix](http://www.wix.com) 在为其媒体平台使用可变 vCPU 选项时节省了 18%。据谷歌报道，营销平台提供商 Lytics 节省了 20%到 50%的成本，电影服务 iRewind 节省了 20%的工作量。

[定价](https://cloud.google.com/compute/pricing#custommachinetypepricing)基于每分钟使用模式。vCPU 的基本价格为每小时 0.03492 美元，每 GB 内存为 0.00468 美元，并根据配置的大小呈线性变化:8 vCPU 20 GiB 内存虚拟机的成本是 4 vCPU 10 GiB 内存虚拟机的两倍。还提供基于持续使用和可抢占工作负载的折扣。

这些虚拟机类型可以与 CentOS、CoreOS、Debian、OpenSUSE、Ubuntu 以及本版本新增的 Red Hat 和 Windows 操作系统配合使用。您也可以推出自己的 Linux 发行版，并在这些可变 vCPUs 上运行。除了 GCE，Google 容器引擎和部署管理器还可以识别定制的机器类型。

通过 **gcloud** 命令行工具和我们的 API 可以创建一个定制大小的虚拟机:

|  | 

$g cloud组件 更新

$g cloud计算 实例 创建 my - 自定义-VM-自定义

 |

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>