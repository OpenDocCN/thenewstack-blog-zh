# 3 个不可变的操作系统:Bottlerocket、Flatcar 和 Talos Linux

> 原文：<https://thenewstack.io/3-immutable-operating-systems-bottlerocket-flatcar-and-talos-linux/>

[](https://www.siderolabs.com/)

 [他现在是 Sidero 实验室的首席执行官。](https://www.siderolabs.com/) [](https://www.siderolabs.com/)

对于那些不知道的人来说，不可变操作系统最近越来越受欢迎。不可变操作系统是这样一种系统，其中部分或全部操作系统文件系统是只读的，并且不能被改变。

不可变的操作系统有很多优点。它们本质上更安全，因为许多攻击和利用依赖于写入或更改文件。此外，即使发现了漏洞，坏人也无法更改磁盘上的操作系统(这本身将阻止依赖于写入文件系统的攻击)，因此重新启动将清除任何驻留在内存中的恶意软件，并恢复到未被利用的状态。

不可变系统也更容易管理和更新:操作系统映像不打补丁或更新，而是自动替换(在一个操作中，保证完全完成或完全失败——没有部分升级！

不可变系统也可以宣称比传统的操作系统更稳定，仅仅是因为消除了许多给系统带来不稳定性的因素——其中大部分是人为的。没有一个系统管理员可以“只改变一个设置就能解决问题”——这会带来不可预见的影响，直到几个小时后才被发现。(我做过系统管理员。)没有部分完成的地形或傀儡会让系统处于奇怪的状态…

在工作站方面，有一些方法可以实现不可变的操作系统，比如 [rpm-ostree](https://coreos.github.io/rpm-ostree/) 。这种方法试图在操作系统中创建不变性和基于映像的部署，但是在顶层构建了一个灵活的文件系统架构，因此包仍然可以由 RPM 管理和更新。

在服务器端，特定于容器的操作系统之间存在一系列不变性。所有都支持基于映像的操作系统更新，根本没有软件包管理器。一些操作系统，如 [Flatcar Linux](https://www.flatcar.org/) 将 */usr* 设为只读，但允许公共运行时修改，如动态加载内核模块，覆盖 systemd 配置。

[Bottlerocket](https://aws.amazon.com/bottlerocket/) ，来自[亚马逊 Web 服务](https://aws.amazon.com/?utm_content=inline-mention)，在/root 分区中添加只读，默认禁用 SSH 访问(可以在特权容器中运行)。Bottlerocket 确实允许内核模块加载到旧版本中，但是已经切换到只允许使用 Bottlerocket 映像密钥签名的模块——bottle rocket 附带的那些模块。

来自 Sidero Labs 的 Talos Linux ，将不可变的概念更进一步。它是另一个操作系统，具有完全不可变的文件系统和用于管理的完整 API，与 Bottlerocket 不同，它完全删除了 SSH 和控制台访问，可以在任何运行 Kubernetes 的地方运行——所有云提供商、裸机、虚拟化系统，甚至可以在 Docker 内和 Raspberry Pis 等 SBC 上运行。Talos Linux 还要求内核模块使用与构建内核时相同的密钥进行签名——因为这个密钥是短暂的，所以它使得内核完全是静态的和不可变的。

当然，和所有事情一样，不可变操作系统固有的优点也是它们的弱点。并非所有系统都需要运行相同的工作负载、固件和软件包。如何定制一个不可变的操作系统来适应各种各样的应用？

Flatcar Linux 具有较少的不可变特性(例如，根文件系统是可写的，节点支持 SSH)，它通过 [Ignition](https://www.flatcar.org/docs/latest/provisioning/ignition/) 项目(通常与 Afterburn 结合使用)解决了这个问题，该项目在节点第一次启动时运行，可以修改文件系统、添加文件、配置用户和其他操作。这类似于使用 Puppet、Chef 等工具的典型 Linux 工作流(除了它在第一次引导时只能运行一次)。

类似地，Bottlerocket 使用引导容器的概念来自定义节点运行的方式。这些容器在节点启动后由 *systemd* 执行，可以访问根文件系统和主机设备。它们可以在每次启动时执行，或者只在第一次启动时执行。这些容器的顺序是不确定的。因此，引导容器实际上不受文件系统不变性的约束——这在某种程度上降低了不变性的安全性。

## 系统扩展

Talos Linux 是完全不可变的，必须采用更严格的方法来修改节点。Talos Linux 使用了一个叫做[系统扩展](https://github.com/talos-systems/extensions)的概念。它可以在保持操作系统完全不变性的同时工作，因为它要求在节点安装或更新期间设置此类扩展。为了使系统扩展上的任何更改生效，必须在节点上重新安装 Talos Linux。

这鼓励(事实上，强制执行！“牛不是宠物”的概念，因为为了通过系统扩展添加或改变节点，磁盘的内容将被擦除和替换。在安装/重新安装期间，系统扩展容器镜像将作为 *squashfs* 镜像存储在 *initramfs* 中；在引导期间，它们覆盖在 Talos Linux *squashfs* 根文件系统之上，使用只读 *squashfs overlayfs* 挂载。所有文件系统(Kubernetes 数据的/ *var* 除外)此后都是不可变的。

系统扩展的概念保持了文件系统的不变性，同时允许节点加载不同的功能，例如特定的固件，或者用于进一步隔离容器的 [gVisor](https://github.com/google/gvisor) 。

这些允许修改不可变系统的不同方法具有不同的优势，但允许用户选择适合他们的方法:从以熟悉的方式管理系统(例如使用 *rpm-ostree* ，或使用 SSH)到新的范例，例如由 Talos Linux 实现的范例，其中没有 SSH，所有的管理都由 API 完成，并且安全性是最重要的——需要学习一种管理系统的新方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>