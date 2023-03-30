# Docker 提供 Docker 扩展，Docker 桌面 Linux 版

> 原文：<https://thenewstack.io/docker-delivers-docker-extensions-docker-desktop-for-linux/>

![](img/9555984d94d923c5e5c763944683ef97.png)

斯科特·约翰斯顿

Docker 为其产品组合增加了新的组件，帮助开发人员在 Docker 桌面上寻找和添加工具，并帮助开发人员在基于 Linux 的系统上工作。

在其 [DockerCon 2022](https://docker.events.cube365.net/dockercon/2022) 虚拟会议上，Docker 宣布了 [Docker 扩展](https://www.docker.com/blog/docker-extensions-discover-build-integrate-new-tools-into-docker-desktop/)和[Docker Linux 桌面](https://www.docker.com/blog/the-magic-of-docker-desktop-is-now-available-on-linux/)。由不同的合作伙伴构建的 Docker 扩展为开发人员省去了安装、配置和管理新工具的苦差事。

Docker 首席执行官 Scott Johnston[告诉新堆栈:“我们有一群合作伙伴，他们构建了一个扩展工具集，开发人员可以在 Docker Desktop 中发现，并预先配置了智能默认值。“所有的安全问题都已解决，开发人员只需点击一下，就可以设置好工具，然后继续使用他们的应用程序，而不必去谷歌寻求指导，去堆栈溢出，问问题，找到依赖关系，并处理所有这些问题。”](https://www.linkedin.com/in/scottcjohnston/)

## SDK 和工具

Johnston 说，Docker 已经在扩展技术上工作了大约一年，并在过去的三个月里与一组封闭的合作伙伴和一小部分开发人员用户进行了私下预览。

该公司已经创建了一个[扩展 SDK](https://docs.docker.com/desktop/extensions-sdk/) ，合作伙伴和用户自己可以使用它来创建这些扩展。

Johnston 说:“非常有意地，我们为用户提供的工具和 SDK 是同一个工具，用于构建应用程序容器映像。因此，结果是他们可以打包并分发他们的扩展，就像他们分发他们的应用程序容器映像一样。所以今天，你会在 Docker 桌面的仪表板中看到扩展市场，这些扩展实际上正在 Docker Hub 上分发和提供。”

Docker 扩展的其他好处包括改进开发人员的工作流程和工作效率，增加和扩展 Docker Desktop 的功能，以及使用扩展 SDK 定制 Docker 桌面体验的能力。

“VMware 和 Docker 有着共同的愿景，即通过提供快速、安全地构建和运行应用程序所需的工具，实现高效的开发人员体验。VMware Tanzu Community Edition 作为 Docker 扩展的可用性为团队提供了在 Docker Desktop 上构建容器化应用的机会，Docker Desktop 是一个适合学习者和用户的开发人员友好的 Kubernetes 平台。“Docker 扩展的便利性和灵活性极大地改善了开发人员的体验，允许他们利用 Tanzu Community Edition 等新工具，而不会中断开发工作流程和工作效率。”

## 生态系统建设

Johnston 表示，14 个发布合作伙伴已经发布了 Docker 扩展，包括 JFrog、Red Hat、Snyk 和 VMWare。其他有扩展的公司有 Ambassador、Anchore、AquaSec、EverX、Layer5.io、Okteto、Portainer、SUSE/Rancher、Tailscale 和 Uffizzi。

[企业管理协会](https://www.enterprisemanagement.com/)的分析师[托尔斯滕·沃尔克](https://www.linkedin.com/in/torstenvolk/)说:“增加‘类似应用商店’的开发者体验听起来的确是一个有趣的价值主张。“帮助开发人员释放他们在不得不处理与选择、构建、测试和管理应用程序堆栈相关的主题之间丢失的“另外 50%”的生产力，是一个很好的解决方法。”

Docker 扩展允许开发人员基于一组标准构建块将他们的环境组合在一起，而不必弄清楚每项技术的来龙去脉。同时，Volk 声称，这使企业 IT 部门能够从安全性和合规性的角度控制这些技术的配置。

然而，“尽管这似乎是一个可靠的价值主张，但更大的问题是 Docker 是否能为这 14 家供应商赢得足够的吸引力，以真正投资于这种关系，以及 Docker 是否能吸引更多的合作伙伴，”他说。“与此同时，Red Hat、SUSE、VMware 和其他公司都在致力于在自己的平台上开发类似的开发工具。”

Constellation Research 的分析师 Holger Mueller 表示，随着 Docker 的扩展，Docker 已经迈出了保持相关性的关键一步——无论是在其合作伙伴生态系统还是平台中。

“前者是关键，因为没有一个 AppDev 平台可以提供 NextGenApps 创建所需的所有内容，所以创建 Docker 扩展是至关重要的一步，允许开发人员留在 Docker 中，但利用第三方合作伙伴来提高开发速度，”他说。

## 新的使用案例

与此同时，Johnston 表示，Docker 不仅推动了当前专注于应用现代化和微服务的计划，还通过其对无服务器、 [WebAssembly](https://thenewstack.io/webassembly-the-future-of-cloud-native-distributed-computing/) 、 [Web3](https://thenewstack.io/web3-stack-what-web-2-0-developers-need-to-know/) 等的支持，推动了未来的计划。

虽然“Linux 容器是(Docker)今天的面包和黄油，但围绕 WebAssembly、Web3、加密应用程序和无服务器的用例正在出现，”他告诉 New Stack。“扩展将使开发人员能够将它应用到这些新的用例中，这是我们在一家不到 200 人的公司中无法独自完成的。”

Johnston 说，Docker Hub 创造了应用程序容器映像的“寒武纪大爆发”。“现在，Docker Hub 上有 1400 万张图片，我们预计会出现寒武纪大爆发和 Docker 扩展的良好浪潮，由合作伙伴、顾问和最终用户自己开发，他们会找到集成工具的好方法，并希望与社区的其他人分发和共享这些工具。”

## Docker 桌面 Linux 版

除了 Docker 扩展之外，Docker 还发布了 Docker Desktop for Linux，为 Linux 带来了 Docker Desktop 的生产力优势。在此之前，Docker Desktop 只对使用 Mac 和 Windows 工作站的开发者开放。

“Linux 支持对 Docker 桌面很重要，因为它打开了大约 25%的软件开发者使用 Linux 作为他们的开发机器，”Volk 说。

为了提高开发人员的工作效率，Docker Desktop for Linux 预打包了 Docker Compose、Docker CLI 和 Kubernetes 等工具，简化了该工具的安装和更新过程。

“将 Docker 平台扩展到 Linux 是另一个关键步骤——因为它增加了对一个非常受开发者欢迎的平台的支持，”Mueller 说。

Johnston 说，将 Docker 桌面引入 Linux 是 Docker 去年收到的用户最多的请求之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>