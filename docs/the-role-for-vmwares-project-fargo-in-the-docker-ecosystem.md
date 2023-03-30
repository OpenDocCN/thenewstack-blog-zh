# VMware 的 Project Fargo 在 Docker 生态系统中的角色

> 原文：<https://thenewstack.io/the-role-for-vmwares-project-fargo-in-the-docker-ecosystem/>

编者按:VMware 的 Project Fargo 使用分叉机制快速克隆虚拟机。它仍处于起步阶段，但已经引起了观察者的注意，他们开始探索它的用途及其在 Docker 生态系统中的作用。

VMware 的[项目 Fargo](http://blogs.vmware.com/cto/vmware-docker-better-together/) 在 8 月的 VMworld 上宣布，但几乎没有什么细节，该项目是在虚拟桌面和容器的背景下谈论的。如果它成功了，那么 Fargo 可能是企业获得虚拟机的安全优势以及容器的速度和可移植性的方法。

> 与此同时，这可能会让 VMware 利用一系列根深蒂固的客户和关系，为 Docker 的生态系统设立一个企业关卡。

自从去年 3 月发布以来，Docker 一直很活跃，很多人都在问“虚拟机和容器之间有什么区别？”对于一家销售虚拟机和管理虚拟机的工具的公司来说，转向容器可能会造成严重的破坏。当然，这种情况并不是在虚拟机和容器之间的简单选择，许多容器将在虚拟机中运行，这推动了 VMware 和 Docker 当前“更好地在一起”消息背后的思考。

VMware 现有的虚拟基础架构是否是运行 Docker 的最佳虚拟机环境并不重要。这一信息似乎是针对已经是 VMware 客户的企业，让他们相信，在涉足 Docker 领域时，他们不必做任何改变。一旦这些企业决定大规模部署，迫在眉睫的问题是容器不能提供与虚拟机相同程度的隔离和保护。简单来说，容器不包含。

Project Fargo 旨在提供一种两全其美的方法——一种轻量级虚拟机，看起来和感觉上都像一个容器(并且可以被 Docker 工具视为一个容器)。据 [VMware 首席技术官 Ben Fathi](https://www.youtube.com/watch?v=hP48ucnPQnY&t=69m30s) 称，结果将是虚拟机“更快，内存占用越来越小，启动更快”。他接着说，该项目应该提供“虚拟机的亚秒级可用性”，这“将使容器更快，在某些情况下比裸机更有效”。

VMware 已经研究 Fargo 背后的技术好几年了。这种被命名为“VMfork”的方法就像操作系统中的进程分支一样，创建一个正在运行的虚拟机的克隆。在其开发过程中，它的目标是将虚拟桌面基础架构(VDI)作为一种快速调配用户环境的手段。因此，切换到 Linux 服务器环境绝非易事。

VMware 的优势在于 Docker 的开放性。从 0.9.0 版本开始，Docker 的工具链和底层容器机制之间通过一个名为 libcontainer 的 API 提供了一个可插拔的接口。这可以用来支持各种容器类型(除了 Docker 自己的实现)，包括 LXC、OpenVZ 和 chroot。原则上，VMware 只需插入 API，就万事大吉了。在实践中，一旦运行时库被分散在一系列虚拟机上，而不是在单个内核的管理下，实现相同的内存和存储优化可能会很棘手。

如果 VMware 成功交付基于 Fargo 的产品，那么奖励可能会相当丰厚——能够在 Docker 生态系统上采用“构建和交付”方面，同时提供更好的“运行”方法，并且企业愿意为此开出支票。

Chris Swan 是 CohesiveFT 的首席技术官，主要负责产品开发和产品交付。Swan 先生之前在瑞银担任客户体验首席技术官，负责所有地区和业务部门的网络和移动产品的战略和架构。在 UBS，Chris 还是安全 CTO 的联席主管，主要负责身份管理、访问控制和数据安全。Chris 代表瑞银担任开放数据中心联盟(ODCA)指导委员会的董事。在加入瑞银之前，他是伦敦一家科技投资银行的首席技术官，该银行运营一个纯云 IT 平台。

特色图片[通过](https://www.flickr.com/photos/hjmediastudios/7883634326/in/photolist-d1DFPL-4nJA8m-d3E2hw-4PifQX-nCM2w1-7VyufJ-7J48A-pkbhk6-d3E24Y-5vFF78-vDJsg-4kDoz-6pGyNi-oLGRfM-5mony4-pkbhsF-pkcXCk-5aKwDN-6FYrTU-okV1om-6RWmna-jj9AUq-86Qp8C-97VeVN-41Hhfs-kPSwsc-kjDsmh-53WShr-kjBEm2-kPRFFB-4UqE9Q-kPTG5Y-jjc5DG-4w9mPV-7z6YYq-5Jjsdp-mKc7Wa-65xDev-DMLmm-4ptLUH-9tDpaU-b9tm3e-9vaFGm-dqRb5r-qmmYM-7Rx9sr-bDfNmb-8K2J1X-4yFRkM-qrCrn) Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>