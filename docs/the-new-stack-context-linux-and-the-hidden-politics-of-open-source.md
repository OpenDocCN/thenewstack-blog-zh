# 新的栈环境:Linux 和开源的隐藏政治

> 原文：<https://thenewstack.io/the-new-stack-context-linux-and-the-hidden-politics-of-open-source/>

即使在开源软件的世界中，源代码对所有人都是透明的，关于代码未来的重要决定有时也是在没有完整解释的情况下做出的。

欢迎来到[新的堆栈环境](https://thenewstack.io/podcasts/context)，在这个播客中，我们将讨论云计算领域的最新新闻和观点。本周，我们与 New Stack 的 Linux 记者[杰克·沃伦](/author/jack-wallen/)聊天，他定期为我们撰写教程文章，报道最新的 Linux 和安全新闻。我们聊到了来自 Linux 首席维护者 Linus Torvalds 最近关于 ZFS 文件系统的评论，以及 Red Hat 最近决定从 Red Hat Enterprise Linux 发行版中撤出 Docker 软件，用它自己的 Podman 软件取代它。

[Linux 与杰克·沃伦的开源隐藏政治](https://thenewstack.simplecast.com/episodes/linux-and-the-hidden-politics-of-open-source-w-jack-wallen)

正如 Wallen 在他的帖子中所提到的，Torvalds 拒绝将任何改变合并到他的 Linux 内核中，这将集成 ZFS 文件系统，理由是许可证不兼容。但他似乎也助长了对这项技术更普遍的不信任，Canonical [在其最新的 Ubuntu 发行版中包含了这项技术。“不要用 ZFS。就这么简单，”托瓦尔兹写道。“我觉得，它总是比其他任何东西都更流行，而许可问题只是让它对我来说不可行。”](https://thenewstack.io/how-to-create-and-destroy-zfs-snapshots-on-ubuntu-19-10/)

这个决定背后是否有更多的原因，是技术原因(ZFS 不尊重指导 Linux 开发的 OSI 七层模型)还是政治原因(甲骨文对代码的所有权)？Wallen 说，这很难讲，我们只是根据分散在开源世界的“面包屑”来做出自己的决定。

同样，Wallen 指出，Red Hat 没有在其 Red Hat Enterprise Linux 中包含 Docker 是一个奇怪的决定，这将要求 Docker 用户在 RHEL 维护他们自己的 Docker 程序，而没有 Red Hat 的实质性升级和维护服务的支持。我们推测可能的原因。注意:在这段播客录制完成后，Red Hat 发言人给我们发了一封电子邮件，称“我们发现我们的客户群希望将容器运行时生命周期嵌入到操作系统中，或者与 OpenShift 一起交付。”

然后在节目的稍后部分，我们讨论了该网站上最近的一些播客和新闻故事，包括关于 Kubernetes 安全的[新生状态的对话，云原生计算基金会的新 bug 赏金计划以](/real-data-for-a-proper-kubernetes-security-review/)[改善所说的 Kubernetes 安全](/cncf-bug-bounty-program-shines-a-light-on-the-darker-corners-of-kubernetes/)，Equinix 购买[数据包](https://www.packet.com/)[以改善其裸机配置的边缘服务](https://thenewstack.io/equinix-purchases-packet-to-bring-bare-metal-provisioning-to-the-edge/)，最后是 MariaDB 的分裂分析/交易数据库服务，该公司称之为“云原生”

《新书库》的编辑和营销总监利比·克拉克(Libby Clark)在 TNS 创始人兼出版商亚历克斯·威廉姆斯(Alex Williams)和 TNS 执行主编乔布·杰克逊(Joab Jackson)的帮助下主持了这一集。

Amazon Web Services、Cloud Native Computing Foundation、Linux Foundation、OpenShift、Oracle 和 Packet 都是新堆栈的赞助商。

来自 Pixabay 的 congerdesign 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>