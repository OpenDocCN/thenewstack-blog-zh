# 开放容器倡议为注册中心创建了一个分发规范

> 原文：<https://thenewstack.io/open-container-initiative-creates-a-distribution-specification-for-registries/>

本周,[开放容器倡议](https://www.opencontainers.org/)启动了它的第三个开放项目——分发规范项目。该计划的目标是为托管容器映像的注册中心提供一组共享的[需求](https://github.com/opencontainers/tob/blob/master/proposals/distribution.md)。根据 [Docker 注册版本 2](https://docs.docker.com/registry/) ，新项目没有设定完成的时间框架。

OCI 的第三个项目将由 Docker 的 Derek McGowan 和 Stephen Day 以及 Red Hat 的 Vincent Batts 负责。目前，该项目作为平台整体的一组目标以及 Docker 注册表中的经验教训而存在。

“OCI 已经存在 2.5 年了。当我们第一次开始时，整个事情都是为了在容器技术出现时围绕它们创建标准，”云本地计算基金会首席运营官 Chris Aniszczyk 说。“首先，我们从运行时规范开始，然后是围绕图像布局，最后社区最近决定分发是标准化的好事情，因为大多数市场都采用 Docker 的注册表 API 进行图像分发。”

Aniszczyk 说:“许多注册中心已经通过大型云提供商实现了 Docker 的注册 API，尽管出现了一些小问题，一些提供商没有完全实现规范，或者没有正确地实现多架构镜像。这是一个很好的机会来标准化已经在行业中广泛使用的东西。"

OCI 分发规范项目的维护者、Docker 的高级软件工程师 Day 说，该规范将允许第三方在兼容的注册中心之上构建分发层，确保供应商能够在增值方面而不仅仅是在实现方面进行竞争。

“我们不是在建立一种新的格式。我们采用现有的形式，并把它原样引入 OCI，”戴说。“我们已经从第一个大的 pull 请求开始了这个过程，该请求将现有的 Docker Registry HTTPv2 API 规范导入其中，然后我们将从那里开始。这意味着实现该协议的现有设备也能很好地实现 OCI 功能。

他接着说，该规范“为不同的系统集成商留下了许多细节。您可以在此基础上构建安全的分发模型。它为图像定义了一个非常好的分发模型子集，这样使用类似技术的人可以直接互操作，并且可以围绕签名和验证进行竞争，或者可以在此基础上建立其他分发模型，”Day 说。

该项目的主要要求之一是确保图像的安全性。由于注册中心提供了一个单一的位置，整个组织都可以从这个位置获取它的容器映像，所以注册中心是黑客的完美目标。像 Yum 和 apt-get 这样的传统包管理系统不能完全胜任跨映像确保企业级安全性的任务。

为此，Day 说发行规范项目从 git 得到了启示:该项目使用一个文件的加密散列作为该文件的唯一标识符。这也允许多个注册中心通过相同的唯一 ID 共享文件，并验证图像没有被篡改。如果有，标识图像的散列将不同于注册中心共享的散列。

云本地计算基金会和 T2 红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>