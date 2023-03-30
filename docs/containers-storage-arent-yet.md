# 集装箱和存储:为什么我们还没有到达那里

> 原文：<https://thenewstack.io/containers-storage-arent-yet/>

尽管“泡沫容器编排系统”的供应商保证，持久存储在可预见的未来仍将是容器的拦路虎，IBM 容器倡导者 James Bottomley 在上月于波士顿举行的 Linux Foundation Vault storage 会议上说。

目前，容器的有状态存储的一个主要障碍是，在当前的 Linux-y 架构下，无法将外部存储系统使用的文件系统用户 ID (fsuid)与容器内创建的用户 fsuid)相协调。它们不能以既安全又可维护又不丧失系统或系统管理员的一致性的任何方式进行协调。

Linux 内核社区*已经*伸出了援助之手，通过创建[超级块用户名称空间](https://lkml.org/lkml/2016/7/26/297)，尽管超级块用户名称空间没有提供完整的解决方案，并且容器公司仍然必须做大量的工作来将他们自己锁定在一个稳固的基于 Unix 的安全模型中。

## 名字游戏

Linux [用户名称空间](http://rhelblog.redhat.com/2015/07/07/whats-next-for-containers-user-namespaces/)的工作方式是关键。Bottomley 断言，容器安全性依赖于用户名称空间，这是公认的常识，但这只是部分事实。默认情况下，安全系统应该将某人锁在系统之外。名称空间实际上做了相反的事情:它们为用户提供了增强的特权。

![](img/da0d2df5aefcb181ba9e3a8303357291.png)

在用户命名空间内允许用户进行某些根操作，而在用户命名空间外则不允许。例如，您可以[从一个名称空间中运行 mount 命令，但是不能作为一个普通用户](https://blog.hansenpartnership.com/unprivileged-build-containers/)。

用户名称空间基本上完成了从一组外部 uid 到内部 uid 的映射。外部 uid 是内核为用户看到的。内部 uid 是容器内部的用户所看到的。

在 Bottomley 看来，试图将两个世界结合在一起导致了一些扭曲的用法。容器编排系统通常必须在根目录下运行(这就是 Bottomley 将大多数编排系统描述为“有毒”的原因)。

Bottomley 说:“我们在用户名称空间方面遇到的许多错误和问题都是通过这种使用增强解决的。”例如，权限提升漏洞的发生是因为一些网络实用程序函数位于名称空间中。(他也没有对 Docker 的用户名称空间的[实现说好话，直到 Docker 1.10 才添加，并且在他看来做得如此“糟糕”。)](https://success.docker.com/KBase/Introduction_to_User_Namespaces_in_Docker_Engine)

所以默认情况下，用户命名空间操作是特权操作。运行[非特权容器](https://thenewstack.io/quest-build-unprivileged-container/)是这个行业的一个目标，尽管特别是在云部署的情况下，“我们还远远没有达到那个水平，”Bottomley 说。

将容器写出到存储器的一个重要问题是，存储系统有它们自己的 uid，即上面提到的 fsuid，它主要对应于分配给其用户的内核 uid。是内核将 uid 翻译成 fsuids。容器中的 Root 用户的 uid 为 0，但是内核会将其转换为容器所有者的 uid，比如 1000，uid 1000 也是 fsuid 记录的内容，系统中的每个人都会看到该用户的 uid(除了实际用户，实际用户仍然会看到 uid 0)。

到目前为止一切顺利。但是共享容器在这里呈现了真正的困境。通过像 [Docker Hub](https://hub.docker.com/) 这样的服务，分享是容器的大部分价值主张。Bottomley 说:“这对于运行非特权容器和标准图像来说是一个很大的问题。“如果我们都为不同的根值写出了容器图像，那么在某个地方将会是一片可怕的混乱。”

人类牺牲，狗和猫生活在一起，集体歇斯底里，就像比利·穆雷[可能会说的](https://www.youtube.com/watch?v=JmzuRXLzqKk)。

任何植入容器的操作系统都需要拥有 uid 0 的根才能运行。但是在当前未改变的设置下，容器内以任何方式接触文件系统的任何操作都将得到一个权限拒绝错误。“我会在这张图片上看到所有这些 id，因为我没有它们的映射，”他说。

所以！容器需要特权。然而，赋予容器真正的根用户——而不是用户名根用户——会让企业感到紧张，因为如果有人能够突破容器，他们将拥有主机的完全根用户。或者，即使由于某些错误配置，他们只能访问某个外部目录，他们仍然可以对该目录中的所有内容进行根级别的破坏，删除文件等等。

理想情况下，我们需要一种在内核和文件系统之间传输用户空间 uid 信息的方法，消除将 root 用户交给容器所带来的风险。

10 月份发布的 [Linux 4.8](https://kernelnewbies.org/Linux_4.8) 带来了一个潜在的解决方案，包含了超级块用户名称空间(通常以其变量名而闻名:s_user_ns)，由 Red Hat 软件工程师 [Eric Biederman](https://www.linkedin.com/in/eric-biederman-89b3792/) 创建。s_user_ns 将容器用户名称空间中的 uid 保留到 fuid 空间中。“这使我能够安全地执行文件和修改特权映像上的文件，”Bottomley 说。

然而，s_user_ns 有一个非常严格的限制，即它只能在[超级块](http://www.linfo.org/superblock)上使用，这是文件系统的基本分配单位，Bottomley 解释道。容器，为了发挥它们的魔力，需要被[绑定挂载](http://unix.stackexchange.com/questions/198590/what-is-a-bind-mount)，这复制了一个目录树。然而，绑定挂载通常不能用超级块分配来完成。

Bottomley 自己的解决方案是 [ShiftFS](https://lwn.net/Articles/687354/) ，简单地说，它允许绑定到超级块。如果您不需要共享映像，那么您可以使用您自己的权限，但是对于“如果我想创建一个文件系统映像并与其他人共享”，则需要一种类似 ShiftFS 的方法。

这种方法存在安全隐患。由于能够以 root 用户的身份编写任何文件系统，因此必须严格控制这种机制，为此所做的工作仍然必须完成。“但是，嘿，你们都信任你们的容器编排人员，对吗？会出什么问题？”博顿利说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>