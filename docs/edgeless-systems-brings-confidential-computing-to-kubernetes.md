# 无边缘系统为 Kubernetes 带来机密计算

> 原文：<https://thenewstack.io/edgeless-systems-brings-confidential-computing-to-kubernetes/>

德国公司 [Edgeless Systems](https://www.edgeless.systems/) 正在为云本地计算安全带来一个新的想法:[机密计算](https://thenewstack.io/confidential-computing-is-transforming-data-encryption-in-healthcare-finance/)与[星座](https://f.hubspotusercontent-eu1.net/hubfs/25442395/Constellation%20Solution%20Brief.pdf)，其 [Kubernetes](https://kubernetes.io/) 机密编排平台。

那么，你问什么是机密计算？这其实是一个简单的想法。加密一切，即使是在内存中。

正如[机密计算联盟(CCC)](https://confidentialcomputing.io/wp-content/uploads/sites/85/2019/12/CCC_Overview.pdf) 解释的那样，数据[以三种状态存在:网络中、静止和使用中。](https://confidentialcomputing.io/wp-content/uploads/sites/85/2022/01/CCC-A-Technical-Analysis-of-Confidential-Computing-v1.2.pdf)我们已经通过 HTTPS 和 SSL 等协议对数据进行加密保护。而且，我们在存储时已经加密了。这使得保护使用中的数据的第三种状态成为“新的边界”

## 像私有云一样的公共云

Edgeless 认为，通过使用 Constellation 来利用机密计算，可以隔离和运行时加密整个 Kubernetes 部署。该公司表示，这意味着，Constellation 使您能够像使用私有云一样使用公共云。

“机密计算将开创一个保护云中数据安全的新时代。机密计算先驱、Edgeless Systems 联合创始人兼首席执行官 [Felix Schuster](https://www.linkedin.com/in/felixschuster/?originalSubdomain=de) 表示:“凭借我们独特的专业知识，我们正在让这项新技术大规模应用于企业。“处理始终加密的数据(不仅是静态和传输中的数据，也包括使用中的数据)是一项艰巨的任务。”但是星座让它发生。

这解决了人们熟悉的老问题“您的数据在第三方公共云上真的安全吗？”Edgeless 声称现在是了，因为你的数据被安全地加密在云的 RAM 中。

现在，正如您所猜测的，保护和使用加密数据并不容易。Constellation 通过处理诸如机密虚拟机(VM)和工作负载的验证或证明、安全连接、密钥管理和数据加密等复杂性来解决这一问题。事实上，有了 Constellation，Edgeless 声称您“可以在不改变工具或代码的情况下，将现有的 Kubernetes 部署提升到前所未有的安全级别。”

## 在所有主要云上运行

Constellation 运行在任何支持 [AMD 的安全加密虚拟化(SEV)](https://developer.amd.com/sev/) 的云环境上。这包括所有主要的基础设施提供商，如微软 Azure、亚马逊网络服务(AWS)和谷歌云平台。

怎么会？舒斯特解释说，星座是基于该公司的开源程序 [MarbleRun](https://marblerun.sh/) 。反过来，MarbleRun 提供了一个机密的计算控制平面来部署、扩展和验证 Kubernetes 上的应用程序。它的技术使用户级代码能够分配私有内存区域，称为飞地。然后，它们可以托管机密计算虚拟机。在这里，你可以像往常一样运行 Kubernetes 和任何你喜欢的东西。

作为开发人员，您不需要担心它是如何工作的细节，也不需要修改代码来使用它。Schuster 说:“美妙之处在于，从内部来看，[一切看起来和感觉上都像普通的 Kubernetes](https://blog.edgeless.systems/founders-story-my-journey-towards-building-a-confidential-cloud-13846caccf4d) ，而从外部来看，一切都与云基础设施端到端地屏蔽开了。”

Constellation 与 AMD SEV、即将推出的[英特尔信任域扩展(TDX)](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-trust-domain-extensions.html) 和 [AWS Nitro](https://aws.amazon.com/ec2/nitro/) enclaves 合作。同样，这些细节对建造 MarbleRun 和 Constellation 的人很重要。你，使用它们的人，不需要担心它，就像你担心你的芯片的结构一样。

当然，舒斯特尔对《星座》非常兴奋。"星座最终成为大规模机密计算的正确途径."事情是这样的。我认为他是对的。如今，显然需要保护内存中的数据。Constellation 解决了这个安全需求，同时承诺易于使用和部署。关注机密计算和星座。您将很快听到更多关于这两者的内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>