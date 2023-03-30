# Canonical 最新的 Ubuntu 核心版本专注于边缘安全

> 原文：<https://thenewstack.io/canonicals-latest-ubuntu-core-release-focuses-on-edge-security/>

Canonical 发布了 Ubuntu Core 20(T1)，这是针对边缘部署优化的最新版本的容器化操作系统。这一最新版本重点关注边缘部署的一个特殊痛点，即安全性，引入了一些功能，包括安全引导、全磁盘加密，以及一些旨在提供安全设备恢复的初步举措。

除了安全功能，Ubuntu Core 20 还推出了一项名为 [Smart Start](https://ubuntu.com/core/smartstart) 的咨询服务，该公司称之为“智能事物即服务”，旨在帮助公司将围绕物联网(IoT)部署的想法付诸实践。

Canonical 公司 Ubuntu Core 的产品经理[加莱姆·加贺](https://twitter.com/galemkayo?lang=en)提供了从智能咖啡机到智能城市的例子，他说他们有很多客户带着好主意来找他们，但不确定如何或从哪里开始。他说,“聪明起步”就是要消除创新障碍。

“许多公司都有关于智能设备的想法，他们想创新，但他们缺乏实施这些项目的知识，”加贺说。“我们提供建筑、工程和走向市场方面的帮助。我们正在构建他们部署设备所需的基础设施，以在固定的时间表内以固定的价格大规模维护设备，从而真正扫清创新道路上的一切障碍。”

Ubuntu Core 从一开始就抱着简化边缘部署的想法，从之前的 [Ubuntu Snappy](https://thenewstack.io/snappy-ubuntu-core-powering-microcontrollers-to-microservices/) 和 Ubuntu 8.10 server[Just full Operating System(JeOS)](https://www.suse.com/products/susestudio/features/jeos.html)发展而来。Ubuntu 核心操作系统的每个部分，一直到内核、文件系统和引导加载程序，都被容器化，然后在 [SnapD 守护进程](https://github.com/snapcore/snapd)上运行。加贺说，这种容器化的方法使 Ubuntu Core 成为部署到各种硬件上的理想选择，你可能会在边缘和创建智能设备时遇到这种情况。

“容器化方法使支持不同的硬件变得更加容易，因为如果你想在新硬件上构建物联网设备，你只需要改变包含内核的容器和包含启动资产的容器，”加贺说。“然后你可以重复使用所有其他的东西。容器方法使得支持更加可组合。”

安全性是边缘部署的另一个特别棘手的问题，因为潜在的不良行为者通常可以物理访问设备，Ubuntu Core 20 主要通过添加安全引导和全磁盘加密功能来解决这一问题。

安全引导可防止此类不良行为者实际访问设备并安装受损的引导加载程序或其他恶意软件，从而威胁您网络的完整性。加贺解释说，安全引导通过“验证引导链中的每一个软件”并检查它们是否来自设备制造商，来防止这种情况发生。否则，设备将无法启动。同样，全磁盘加密可以防止在现场实际接触设备的人访问设备上的数据。

至于安全设备恢复，加贺说，他们已经“通过提供恢复系统迈出了第一步”，他们希望在下一个版本中使其可以远程管理。完全启动后，该功能将使用户能够安全地将设备远程恢复到其默认配置，这意味着任何受损设备都可以恢复在线，而不必直接在现场访问。

展望未来，加贺表示，Canonical 计划增加实时功能，以满足智能工厂和汽车应用等不断增长的需求。除此之外，他认为“微云”的出现是 edge 特定操作系统的一个重点领域。

“我们认为边缘云，或我们所说的‘微云’，正处于接管的边缘，而像 Microk8s 这样的 Ubuntu Core 和 Kubernetes 发行版非常适合这些类型的用例——部署在零售店、工厂或高速公路上的小型云，用于智能城市应用程序，运行 Ubuntu Core 来实现安全性，并在其上运行 Microk8s Kubernetes 来协调容器，”加贺说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>