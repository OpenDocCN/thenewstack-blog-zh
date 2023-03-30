# Docker 将桌面连接到 Azure，Visual Studio

> 原文：<https://thenewstack.io/docker-wires-desktop-into-azure-visual-studio/>

随着今年的虚拟 [DockerCon](https://docker.events.cube365.net/docker/dockercon/) 于周三拉开帷幕， [Docker](https://www.docker.com/) 公布了与 [Visual Studio Code](https://code.visualstudio.com/) 、 [Docker Desktop](https://www.docker.com/products/docker-desktop) 和[Azure Container Instances](https://azure.microsoft.com/en-us/services/container-instances/)(ACI)的集成，据说这将为开发者提供一种直接从 Docker CLI 登录 Azure 的方式。

“早在一月份，我们就开始了一项新战略，旨在帮助开发人员和开发团队构建和发布应用程序。该战略的一个关键部分是帮助参与生态系统，而不是试图用 Docker 之外的代码从头开始构建每个新功能，[Docker](https://www.linkedin.com/in/justingraham/)产品副总裁 Justin Graham 说，“客户希望与市场上最好的解决方案集成，我们希望实现这一点。”

Graham 称这种整合是“我们与微软合作关系的重大扩展”，他说这不仅会将本地开发环境与 Visual Studio 代码联系起来，还会与 Azure 运行时联系起来，尽管他没有说明这是通过 Visual Studio 代码扩展还是其他方式。新功能预计将于 2020 年下半年推出。

集成将允许开发人员直接从 Docker CLI 登录 Azure，触发自动设置 ACI 云容器服务环境，然后从本地上下文切换到云上下文来运行应用程序。该集成还让开发人员首次在云容器服务中无缝地调用完全兼容 Docker 的命令，并通过共享持久的协作云开发环境，提供通过 Docker Hub 共享工作的能力。

然而，格雷厄姆没有详细说明该功能是否会扩展到[微软最近更名的 Visual Studio Codespaces](https://devblogs.microsoft.com/visualstudio/introducing-visual-studio-codespaces/) 或其 GitHub 提供的替代产品 [GitHub Codespaces](https://github.com/features/codespaces/) 。

Graham 解释说，这种集成“目前纯粹是为了 Visual Studio 代码”。

“开发人员将在本地安装 Visual Studio 代码和 Docker Desktop，他们很快就能在 Node、Python、.并通过 Compose 规范和 Docker CLI 利用该功能，不仅可以构建和开始使用，还可以通过 Docker CLI 打包和部署生成的容器化应用程序到 ACI，”Graham 解释道。

有关更多信息，DockerCON Live 2020 将于 5 月 28 日开幕，相关会议包括:

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>