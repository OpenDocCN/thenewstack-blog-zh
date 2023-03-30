# Red Hat 为 Ceph Storage 4 带来了简单性和无服务器性

> 原文：<https://thenewstack.io/red-hat-brings-simplicity-serverless-to-ceph-storage-4/>

上周，Red Hat 推出了最新版本的 [Red Hat Ceph Storage](https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/installation_guide_for_red_hat_enterprise_linux/what_is_red_hat_ceph_storage) ，它表示，这将解决开源文件系统过去一直在努力解决的一些复杂性问题，同时还进一步提高了可扩展性，并为无服务器操作提供支持。

“我们在 Red Hat Ceph Storage 4 中所做的事情是，我们从世界各地引进 Ceph，在那里，您需要拥有博士学位才能有效地操作甚至安装和设置 Ceph。这是我们从客户那里听到的一贯说法。我们正在改善整体可管理性和安装体验，”Red Hat 混合云存储营销经理 [Pete Brey](https://www.linkedin.com/in/petebrey/) 说。

Red Hat Ceph 存储构建于 Ceph 之上，Ceph 是一个开源的 Pb 级网络文件系统，用于对象、块和文件存储。不幸的是，虽然 Ceph 可以处理极端的可伸缩性问题，但它也因其复杂性而闻名。然而，Brey 说，在这个最新版本中，Red Hat Ceph Storage 4 可以在几分钟内通过 Ansible 脚本安装，而以前需要几个小时或几天。

Brey 说，新发现的简单性只是一个开始，Red Hat Ceph Storage 4 还瞄准了它的核心价值——巨大的可扩展性。

“我们这里的一个关键价值主张是简单，但这实际上并不是最重要的价值主张。最重要的是可扩展性，”Brey 说。“这不仅仅是容量扩展，还包括在扩展容量的同时扩展性能的能力。这两件事有时是互相矛盾的；当您扩展系统时，尤其是使用传统架构时，性能通常会下降。”

Brey 举了一个公司的例子，该公司有五名存储管理员处理 20PB 的数据，并提出，对于某些系统，扩展到 100PB 可能意味着也要线性扩展您的员工。他说，Red Hat Ceph Storage 4 允许任务委派，使您不必增加员工来处理不断增长的数据存储大小。同样的员工可以处理 20PB 或 100PB。

“我们还致力于简化工作，让更高级的管理员来授权。一些更普通的任务，如更换驱动器或维护卷，一些日常的日常操作，您现在可以委托给更初级的管理员。同样，我们试图将 Ceph 从一个非常专业的领域，针对一个专业的环境，推广到更广泛的受众，”Brey 说。

在 Red Hat Ceph Storage 4 的其他新功能中，有一个统一的仪表板，可以帮助更快地发现和解决问题，一个针对多租户托管云环境中的应用程序的服务质量监控功能，以及支持 Kubernetes-native 无服务器架构的集成桶通知的引入，该架构通过容器化的无服务器平台 Knative 和 Red Hat 版本的分布式消息流平台 Kafka，AMQ 流实现自动化数据管道。

关于这最后一点，Brey 解释说，对数据桶的任何更改，无论是添加对象、删除对象还是以其他方式更改对象，系统都可以使用亚马逊 S3 API，根据发生的情况自动触发下游流程。例如，医生办公室可以在将新的 X 射线放入桶中时自动分析它，并且可以类似地自动删除个人身份信息，以便在以后的研究中使用相同的数据。

“在无服务器流程中，你几乎可以做任何你想做的事情，”Brey 说。“我们认为这实际上是一件大事。它就像一个基础架构，我们可以在许多不同类型的工作负载上进行分层。”

[https://www.youtube.com/embed/Rd9NQMtzgPY?feature=oembed](https://www.youtube.com/embed/Rd9NQMtzgPY?feature=oembed)

视频

红帽是新堆栈的赞助商。

图片来自 Pixabay 的 ArtTower。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>