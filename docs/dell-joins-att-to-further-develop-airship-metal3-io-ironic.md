# 戴尔联合美国电话电报公司进一步开发飞艇，Metal3-io，讽刺

> 原文：<https://thenewstack.io/dell-joins-att-to-further-develop-airship-metal3-io-ironic/>

戴尔技术公司已经与美国电话电报公司合作开发了许多开源技术，公司称这些技术将有助于边缘计算和 5G 部署，即[飞艇](https://www.airshipit.org/software/)平台集成软件，以及裸机配置工具 [Metal3-io](https://github.com/metal3-io) (适用于 Kubernetes)和 [OpenStack 讽刺版](https://wiki.openstack.org/wiki/Ironic) (OpenStack)。

戴尔的加入将提供一定水平的硬件专业知识，这将有助于在通往 Airship 2.0 的道路上建立势头， [Ryan Van Wyk](https://www.linkedin.com/in/ryanvanwyk) 在接受新堆栈采访时解释道。

“最终结果是，我们正在帮助加快支持[软件定义的网络]工作负载的开放式基础架构的部署。Van Wyk 说:“我们认为这是一种飞轮效应，让人们更容易部署基础设施，也让他们更容易发展他们的 SDN 生态系统。“戴尔将把一些重点放在对他们的竞争力至关重要的领域。当谈到如何管理 RAID、磁盘、服务器、BIOS 配置和硬件本身的验证，然后将其中一些内容原生集成到 Kubernetes 集群 API 时，这些内容将帮助我们进一步完成我们的使命，即能够声明基础架构，然后让 Airship go 实现这一点。这对我们来说是一个很大的补充。”

Van Wyk 指出，边缘计算和 5G 是戴尔的贡献可能产生影响的一个领域的主要例子。通过使自动化和将基础设施部署到边缘的各种硬件变得更加容易，5G 网络的部署过程变得更加容易和高效。戴尔的硬件专业知识，而不是其硬件产品，将有助于加快飞艇 2.0 的路线图。他预计该团队将在今年年底前将 RedFish 通信 API 集成到 Airship 中，明年某个时候进行硬件验证、BIOS 和 RAID 配置，预计明年年中发布 2.0 版本。

然而，在努力实现飞艇 2.0 的过程中，Van Wyk 强调了团队在采用最佳技术方面的开放思想，而不是强迫自己的解决方案。

“飞艇公司非常注重确保我们采用根深蒂固的上游项目。我们希望确保，如果某样东西是同类中最好的，我们会将其集成到飞艇中，并使其非常容易为运营商所利用。当我们开始飞艇项目时，对于如何部署一个有弹性的 Kubernetes 集群并管理它，确实没有答案，所以我们创建了名为 [Promenade](https://github.com/airshipit/promenade) 的项目，”Van Wyk 说。“从那以后，围绕着 [Kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/) 有了很多联合。虽然项目本身说你需要围绕它建立某种包装器来为企业做好准备，但在 Airship 2.0 中，我们将开始集成 Kubeadm 来取代 Promenade 的许多内容，然后围绕它做包装器，使操作者易于使用。我们非常关注如何与集群 API 集成，并利用集群 API 的本地提供者。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>