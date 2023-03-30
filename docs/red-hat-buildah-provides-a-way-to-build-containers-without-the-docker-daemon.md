# Red Hat Buildah 提供了一种不用 Docker 守护进程来构建容器的方法

> 原文：<https://thenewstack.io/red-hat-buildah-provides-a-way-to-build-containers-without-the-docker-daemon/>

Red Hat 希望将守护进程从构建容器的过程中清除出去。

本周，该公司发布了其构建容器映像工具的第一个生产就绪版本，名为 [Buildah](https://github.com/projectatomic/buildah) 。等等，Docker 不是已经这么做了吗？但是红帽公司的工程师们，[和其他人](https://www.youtube.com/watch?v=qhykcC94ukg&t=1267s)，并不热衷于 Docker 所基于的客户机-服务器模型。

他们认为，这种将多种功能捆绑在一个程序中的模式可能会引入安全漏洞，并限制容器构建系统在基于 Kubernetes 的集群上的可部署性。

对于简单构建一个容器的过程，“为什么我们需要一个大的容器守护进程来在一个目录中创建内容，给它添加焦油，并用它写一些简单的 json 文件？”说[丹尼尔·沃什](https://www.linkedin.com/in/dan-walsh-a8729b2/)，红帽咨询公司软件工程师。

Buildah 命令行工具可以创建[开放容器倡议(OCI)兼容的](http://www.projectatomic.io/blog/2018/03/building-buildah-container-image-for-kubernetes/)和 Docker 容器映像，甚至使用标准的 [Dockerfile](https://docs.docker.com/engine/reference/builder/) 格式本身。它兼容所有支持容器创建的可脚本化 Linux 工具，如 **cp** 、 **make** 、 **yum** 。

Walsh 声称，去掉 [Docker 守护进程](https://docs.docker.com/engine/docker-overview/#docker-architecture)是 Buildah 的主要好处之一(命名的“Builder”来自 Walsh 浓重的波士顿口音发音“Builder”)。守护进程基本上是一个在主机系统后台运行的程序，等待某种输入。Docker 自己的基于守护进程的软件是目前最流行的构建和运行容器的方式，它可以从一个命令行处理多个任务，包括提取图像、构建图像和运行图像。

然而，在过去的几年中，通过 OCI 等人的努力，已经进行了大量的工作，将这些功能分解成独立的组件，以获得更大的控制和灵活性。

基于守护进程的方法的一个问题是安全性，即容器需要一个套接字来连接运行在主机上的守护进程。Docker 已经做了很多工作来限制容器对主机的访问，但除了批准的方式，这种进入主机的管道仍然让安全专家感到紧张不安。它允许容器对运行构建的节点拥有完全的访问权限。一旦您获得了 Docker 解决方案的访问权限，您基本上就拥有了运行 Docker 守护进程的机器的 root 权限。没有授权，”沃尔什说。

Buildah 始于 Red Hat 的[项目 Atomic](https://www.projectatomic.io/) initiative，尽管其他人也在朝着类似的目标努力。微软工程师[杰斯·弗雷泽勒](https://blog.jessfraz.com/)、[在她的业余时间](https://blog.jessfraz.com/post/building-container-images-securely-on-kubernetes/)开发了一款名为 [img](https://github.com/genuinetools/img) 的软件，这是一款“独立的、无守护进程的、无特权的 Dockerfile 和 OCI 兼容的容器映像生成器”谷歌的容器团队用 Kubernetes 创建了 [Kanikos](https://github.com/GoogleContainerTools/kaniko) 来构建容器。

Buildah 还提供了一些核心 Docker 组件所没有的特性。在构建过程中，[开发人员可以指定何时执行提交](https://www.youtube.com/watch?v=bOzJ9RJ4elU&t=1313s)，这与 Docker Build 形成对比，后者在执行 Docker 文件中的每一行后都会创建一个新的映像。这是为了加快构建速度而创建的特性，但也带来了复杂性。

“Dockerfiles 的一个经典问题是人们放入 Kerberos 密钥或不同种类的秘密来获取内容，然后这些内容被嵌入到图像中。总是有人试图找出从那张图片中删除内容的方法，”沃尔什说。“另一方面，Buildah 基本上是将 other 文件中的所有命令处理成一个单独的映像，”从而让开发人员有机会在将内容提交到映像之前清理掉不必要的内容。

Docker 还将一些工具捆绑到容器映像中，比如 YUM 和 DNF 包管理器，这些工具在初始构建后可能并不需要，并且可能会引入安全漏洞。“IT 团队可能希望他们的构建系统运行最少的流程和工具，否则，可能会引入额外的复杂性，这可能会导致系统稳定性的丧失，甚至是安全风险，”Walsh 在宣布 Buildah 1.0 发布的博客文章[中写道。Buildah 通过在构建期间临时添加外部读/写卷来解决这个需求。](https://www.redhat.com/en/blog/daemon-haunted-container-world-no-longer-introducing-buildah-10#)

就从 Docker 迁移到 Buildah 而言，所有需要做的就是在命令行和脚本中将 **docker build** 命令替换为 **buildah bud** 。请记住，Buildah 并不复制整个 Docker 命令行，尽管另一个原子项目正在做这项工作， [Podman](https://www.projectatomic.io/blog/2018/02/reintroduction-podman/) ，它也将管理运行时和推/拉功能。

沃尔什说:“我们的总体努力是将每个人目前用 Docker 做的事情分解成基本功能，并允许人们尝试和建立新的做事方式。”

这种方法也可能更有利于创建基于 GitOps 的开发工作流，开发人员根本不用担心代码的容器化。在这种情况下，每当开发人员向 git 提交一些修改后的代码时， [Kubernetes](https://kubernetes.io/) 或 [OpenShift](https://www.openshift.com/) (Red Hat 的商业版 Kubernetes)将在幕后启动一项工作，以重建包含代码的容器映像，并将其推入 CI/CD 系统进行测试，然后交付给质量保证部门或直接投入生产。全部自动(理论上)。

“如果有数百名用户签入代码，并启动数百个流构建容器，这就是我们利用 Kubernetes 编排并在容器内运行单个构建的地方，”Walsh 说。

Buildah 1.0 在 Red Hat Enterprise Linux 7.5 中有完整的产品级支持，可以通过 **yum -y install buildah** 命令获得。Buildah 还完全支持联邦信息处理标准(FIPS)，这是美国联邦政府对其计算机系统的要求。

Gartner 估计，到 2020 年，超过 50%的全球组织将在生产中运行容器化应用程序，而目前这一比例还不到 20%。

[https://www.youtube.com/embed/qhykcC94ukg?feature=oembed](https://www.youtube.com/embed/qhykcC94ukg?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>