# Docker 收购了 Kitematic，这是一个用于 Mac OS 的容器管理 UI，并计划用于 Windows 版本

> 原文：<https://thenewstack.io/docker-snaps-up-kitematic-a-container-management-ui-for-mac-os-with-plans-underway-for-a-windows-version/>

Docker，Inc .周四宣布收购 2013 年夏天推出的 Mac OS 开源容器管理 UI 的初创公司 Kitematic ，这又是一个表明服务器平台格局正在被戏剧性地重新描绘的信号。在接受 New Stack 采访时，Kitematic 的联合创始人肖恩·李表示，他和他的团队计划充分利用 Docker 的投资，为 Windows 开发新版本的用户界面。

“在我们的 GitHub repo 上，我们已经有了的开源路线图，”李告诉我们。“在短期内，我们的目标是 Windows，让 Kitematic 在 Windows 上运行，并让它从 Docker hub 中提取[的私人图像。”](https://docs.docker.com/docker-hub/)

根据 Kitematic 的路线图，私人图像功能计划在本月推出。Kitematic UI 到 Windows 的移植定在 5 月或 6 月。

用于 Mac OS 的 Kitematic 的最新发布版本是 0.4.5 版，直到 v. 0.5.10 的预发布版本也在进行中。在撰写本文时，Kitematic 已经积累了 2610 个 GitHub 星点。

Kitematic 旨在与 Oracle 的 VirtualBox 配合使用，后者可以说是在个人设备上托管虚拟机的最广泛分布的平台。虽然 VirtualBox 自己管理的虚拟机通常是带有客户端操作系统或虚拟服务器的虚拟 PC，但 Kitematic 使 VirtualBox 能够直接从其软件包中运行 Docker 容器。

无障碍的便携性是 Docker 突然获得巨大成功的关键。虽然容器化技术实际上已经存在了几年(许多人认为 Google 工程师开发了第一个全功能的实现)，但几乎就在 Docker 将其实现作为基于云的软件部署的 PaaS 平台的一部分进行部署之后，容器就从业余爱好项目转移到了临界质量。

现在，支持 Docker 开源项目的组织实际上已经脱离了 PaaS 业务，他们正忙于处理自 FORTRAN 以来数据中心技术中最大的突然变化。但这项最新投资表明，Docker 足够谨慎，也关注其生态系统的客户端，这有助于使专门为容器设计软件的开发人员能够在测试环境中本地部署这些软件。

Docker 企业营销副总裁大卫·梅西纳(David Messina)在回答我们关于未来几个月我们是否会在任何与 Docker 相关的活动中看到肖恩和 Kitematic 的问题时说:“肖恩将被锁在他的办公桌上开发产品。”

Messina 可能只是打个比方，但从与他的交谈中可以明显看出，Docker 组织对 Kitematic 的激进路线图印象深刻，并有兴趣确保该组织坚持下去。

“Docker 项目的主要目标是为开发者创造工具，并继续从中受益，”Messina 说。“因此，如果你看看采用 Docker 的障碍，开箱即用的体验已经被确定为一种重要的东西，如果我们想扩展它，那就太好了。如果你看看这对更广泛的生态系统的好处，使用 Docker 的人越多，对生态系统中围绕 Docker 构建差异化技术的每个人都越好。”

梅西纳接着说，Docker 不仅仅将 Kitematic 视为一种技术，而是一个个人团队。在公司存在的这个阶段，最熟悉该工具的开发人员是更广泛社区的成员。随着 Docker 成为一家公司——为了在别人之前管理席卷全球的容器新现象，它必须成为一家公司——它必须将这种 DNA，如 Messina 所称，带入组织中。

随着 Docker 的生命周期超加速，它可能没有时间等待内部专业知识的增长。

周四的公告保持了 Docker 重要里程碑的快速发展。就在上周，[该组织获得了 SocketPlane](https://thenewstack.io/docker-acquires-sdn-technology-startup-socketplane-io/) 的专业知识，SocketPlane 为 Docker 容器开发了一个网络层，可以绕过基于硬件和基于软件的网络控制器。在此前一周， [Docker 发布了 Docker Machine](https://thenewstack.io/orchestration-toolkit-release-aims-prove-dockers-commitment-flexibility-community-ecosystem/) 来自动化容器的供应，以及 Docker Swarm 来管理跨多个数据中心集群的容器供应。

Kitematic 实际上是利用 Docker Machine 作为编排工具，把 Mac 做成 Docker 主机。随着即将到来的从云中提取存储库的能力，Kitematic 可能很快就会成为首批主要工具之一，用户可以通过它直接从云中连接、供应和运行真正的虚拟应用程序，而无需安装。

未来几周的一个重大事件是微软在芝加哥举行的 Ignite 会议，在会上，微软的两位摇滚明星——Azure 技术研究员马克·鲁西诺维奇和 Windows Server 首席架构师杰弗里·斯诺弗——承诺[将披露 Docker 相关的新功能](http://www.cmswire.com/cms/information-management/microsoft-confirms-dramatic-refactoring-of-windows-server-028300.php)。细节暂时保密。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/charlietakesphotos/145332439/in/photolist-dQSgH-cCkuvo-7UKYHk-L2FcZ-6MsdEw-4KMbDw-6tZ4tF-vRjZd-5RDHA1-f9NeQY-pbzWna-do97f3-qmQu1S-f9xZHH-9Ho1Ku-6ANxE-q9SrrW-f9NdFE-eeZCj1-6Mm8n7-7EbFFU-c51Z8G-dhC37r-a3TwBq-eh1o17-bVPmfk-6JnqTA-cWvCPL-bj1bm-4LEscp-f9NeC7-ntkuEL-cwtdg-7qVue-5ArmUR-9NLLJe-b7sAFv-5uQNGe-fs6Nyr-qeaxP-3rZaf-8CJpBm-7CMtAW-8JiMSN-7AfmZN-7V1qrk-8somLy-dfSgcb-cwtdi-4Chc42)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>