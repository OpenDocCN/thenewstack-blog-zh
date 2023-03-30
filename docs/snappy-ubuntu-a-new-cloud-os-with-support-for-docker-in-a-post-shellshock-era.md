# Snappy Ubuntu，后 Shellshock 时代支持 Docker 的新云操作系统

> 原文：<https://thenewstack.io/snappy-ubuntu-a-new-cloud-os-with-support-for-docker-in-a-post-shellshock-era/>

新的[分布式和微服务应用生产环境](https://thenewstack.io/reactive-frameworks-microservices-docker-and-other-necessities-for-scalable-cloud-native-applications/ "Microservices and other necessities for scalable cloud native applications")为开发架构创造了新的需求。对于操作系统来说尤其如此，无论是在开发人员的笔记本电脑上创建代码，还是在世界各地无数机器和服务器上部署的操作系统，每个都运行一个微服务，连接成为最终用户体验的分布式应用程序。

红帽发布了[项目原子](https://www.projectatomic.io)，而 [CoreOS](https://coreos.com) 继续创造新的功能和服务来吸引新的应用环境，特别是支持需要容器化服务的开发者。

现在，Canonical 发布了一个基于云的操作系统， [Snappy Ubuntu](http://www.ubuntu.com/cloud/tools/snappy) 作为“Ubuntu 的新风格”,非常适合新的堆栈开发人员。以下是 Canonical 创始人马克·舒托沃尔斯的 [take](http://www.markshuttleworth.com/archives/1434) on it:

[https://www.youtube.com/embed/BlcTDz9ogug?feature=oembed](https://www.youtube.com/embed/BlcTDz9ogug?feature=oembed)

视频

快速系统将 Ubuntu 的每个部分保存在一个单独的只读文件中，并对每个应用程序做同样的事情，舒特尔沃斯在他关于 Ubuntu 核心新风格的帖子中写道。

通过这种方式，开发人员可以提供他们需要的一切，以确保他们的应用程序完全按照他们的意图运行，我们可以采取措施保持各种应用程序相互隔离，并确保更新总是完美的。当然，这意味着 apt-get 不会工作，但这没关系，因为开发人员可以重用 deb 来制作他们漂亮的应用程序，核心系统与任何其他 Ubuntu 系统完全相同——服务器或桌面。

Ubuntu Cloud Solutions 产品经理兼策略师 Dustin Kirkland 说:“Snappy Ubuntu 对构建大型新系统的新学科很有吸引力。Kirkland 指出网飞是这种新的微服务架构的主要例子。

柯克兰说，网飞采取了一种非常不同的方式来创造它的服务。网飞的开发人员使用数百台服务器，每台服务器运行一点服务，而不是两台单一的服务器。Snappy Ubuntu 支持这种环境。它非常小，非常高效，只有最低限度的运行，它能够在最少的服务中断下进行大规模更新。

Ubuntu 背后的公司 Canonical 指出了 Snappy Ubuntu 的两个关键特性:事务更新和对 Docker 容器的支持。

## 交易更新

Snappy 吸取了 Ubuntu 两年来为手机托管操作系统“风味”的经验，即需要在不中断最终用户体验或要求他们手动更新到新版本的情况下将更新推送到手机的固件中。

在后 Shellshock 时代，事务性更新有望被应用程序开发行业所接受。 [Shellshock](https://thenewstack.io/responding-to-shellshocks-chaotic-impact-on-new-stack-ecosystems/ "Shellshock's impact on ecosystems") 曝光了很多基于 Linux 和 Mac 架构的系统。用户开始担心手动更新将意味着系统在一段时间内仍会受到威胁，因为架构师和其他负责服务器维护的人无法检查安全风险并更新可用的补丁。

Snappy 旨在通过在整个网络中自动更新来避免这种手动负担。

“Shellshock 是影响 Linux 和 Mac 机器的严重安全漏洞的一个例子，”Kirkland 说。“Snappy 处理更新的方式在大规模推出此类修复时要高效得多。当我们在 Ubuntu Mobile 进行开发时，我们看到了电信公司在确保大规模有效推出更新时面临的问题。

“Snappy Ubuntu 是一种更有效的大规模更新机制，并以事务方式进行更新。它通过测试，然后 Snappy Ubuntu 能够注意到新图像何时可用。当消费者选择进行更新时，更新会立即批量完成，而不是一路单独更新软件包。”

## 码头支持

柯克兰很清楚，Snappy 是管理 Dockerized 应用程序的理想操作系统，其他容器服务将在稍后添加:
“Docker 是 Ubuntu Snappy 的一个奇妙载体，拥有非常丰富的图像库。任何可以在 Docker 中运行的东西都可以在一个简洁的 Ubuntu 环境中运行，我们从第一天起就将这一点融入其中。”

柯克兰指出，敏捷的 Ubuntu 操作系统是 Docker 服务生态系统的桥梁。应用程序在容器中运行。你在 Docker 里面运行的任何东西都可以在 Snappy 里面运行。”

Snappy Ubuntu 能够与 Docker 一起使用是 Canonical 希望 Snappy 能够满足开发者需求的一个重要组成部分，开发者是该产品的主要受众。Snappy 还使用 Docker-esque 类型原则来加速 Snappy 打包软件的新方法，而不会给开发人员造成太多的混乱，即使软件打包系统是一种新方法:

“Snap packages 是一个从零开始的打包系统，它建立在最新、最棒的流程之上，现代开发人员通过这些流程向消费者提供他们的应用程序。它使开发人员能够快速地将他们的软件打包交付。与学习 debian 打包的细节相反，我们是在与 Docker 容器或 java jar 文件相同的原则上构建的。这是一个 zip 文件:非常简单。我们有一系列打包工具，从 GitHub 中的源代码开始，编译一个可以在 Snappy 运行的任何地方运行的应用程序。”

Snappy Ubuntu 映像也可以在虚拟机和私有云环境中运行。“我们将让开发人员在一个带有 vagger 的 [VirtualBox 上以 100 兆的速度运行。](http://docs.vagrantup.com/v2/virtualbox)它也将在微软 Azure 中可用，然后它将在谷歌计算引擎和亚马逊网络服务中可用。它也可以在私有云环境中的 OpenStack 上运行，”Kirkland 证实道。

在测试版中，柯克兰确信这只是这个精彩故事的开始:“这是开始，而不是结束。它将展示我们为构建这个适用于云和服务器实例的神奇系统付出了多少努力，”柯克兰说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>