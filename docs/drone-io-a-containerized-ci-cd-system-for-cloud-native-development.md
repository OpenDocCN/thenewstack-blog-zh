# 无人机。IO:面向云原生开发的容器化 CI/CD 系统

> 原文：<https://thenewstack.io/drone-io-a-containerized-ci-cd-system-for-cloud-native-development/>

[Brad Rydzewski](https://www.linkedin.com/in/bradrydzewski/) 回忆起他建造[无人机](https://github.com/drone/drone)的最初灵感，他声称这是第一个开源的容器-原生 CI/CD 软件:“我想设计出所有公司可以围绕这些工具的繁文缛节。”

Rydzewski 在一家大公司工作时创造了无人机。他需要一个环境来构建、测试和部署他的代码。不幸的是，IT 部门要求他必须提交一份申请单才能获得一个基于 Jenkins 的环境，这可能需要该部门花费六个月的时间来调配资源。这不是他第一次感受到这种挫败感。

“每次我需要对环境做出改变时，我都必须开一张罚单，而且必须等上 30 或 60 天。这真的降低了我作为开发人员的速度，”Rydzewski 说。他在他工作的另一家企业公司经历了类似的困难，在那里，仅仅获得 Jenkins 插件的批准就可能需要 60 天。另一个问题是——在一个共享的环境中工作意味着他必须使用公司其他人正在使用的任何版本的 Java。

尽管问题的一部分是组织结构不能满足动态的开发环境，但 Jenkins 架构的局限性也是事实。“詹金斯是一个集中管理的系统。它并不是真正为我们作为开发人员习惯的按需云体验而构建的，”Rydzewski 说。

他说，Drone 的想法是“让开发人员只需点击一下就能构建环境”。幸运的是，就在 Docker 开始获得关注的时候，他开始构建它。Rydzewski 发现，使用容器，“开发人员真正控制并管理他们的连续交付，同时仍然给予运营团队容器提供的安全性和隔离性。”

换句话说，有了容器，你就有了自己的构建环境。你不必要求第三方来升级你的环境。无人机工作空间从 Docker 卷引导，服务(如数据库)从 Docker 合成文件创建。然后，工作空间和服务可用于管道的每一步。

Drone 同时提供持续集成和持续交付(CI/CD)，提供与 GitHub、GitLab、BitBucket 的直接连接，以及与亚马逊 Web 服务和谷歌云平台等云提供商的直接连接。每次开发人员提交代码或打开拉请求时，Drone 都会执行单元测试和集成测试，甚至将代码部署到开发、试运行甚至生产环境中。

与大多数其他 CI/CD 管道工具不同，Drone.io 可以通过自动缩放功能自动缩放以满足需求。Drone 监控一个构建队列，一个待定位置队列，因此如果有开发人员活动高峰。Drone 可以自动扩展机器，而无需开发人员等待他们的构建完成。当构建量减少时，无人机可以再次拆除服务器。

因为是集装箱包装的，无人机很容易升级。因为它是作为静态 Go 语言二进制文件提取的，所以非常紧凑。管道本身被描述为一个 YAML 文件，因此它可以被版本化。整个设置可以在本地运行，也可以在云中以相同的配置运行。

## 一支无人机部队

上个月，初创公司 Drone.io [将](https://blog.drone.io/drone-announces-official-support-for-arm/)扩展到支持 [Arm](https://www.arm.com/) 处理器架构。这意味着无人机和它通过管道发送的应用程序都可以基于 Arm 架构。

该软件的最新版本 Drone 0.9 支持 Armv7-A 和 Armv8-A 芯片架构。此外，它的许多插头都添加了 ARM 支持，可在该软件的[市场](http://plugins.drone.io/)上获得，包括 Slack、GitHub 和 Docker。

Rydzewski 承认，对 Arm 上的无人机有惊人的需求。事实上，社区甚至在该公司之前就开始了将无人机移植到 arm 的工作。“在过去的一年里，我们看到了对 Arm 的巨大需求，”他说。DIY Raspberry Pi 社区是早期的用户群，但 Arm 在无人机上的工作也扩展到了物联网和嵌入式计算，以及人工智能和机器人。

“在许多情况下，他们需要在 Arm 设备上构建和测试代码，”Rydzewski 说。无人机足够智能，可以将你的代码发送到正确的架构。

这是一个不断增长的市场:迄今为止，已经有超过 1300 亿个基于 Arm 的芯片出货，来自多家处理器制造商(Arm 本身只授权设计)。裸机云服务提供商 [Packet](https://www.packet.com/) 现在提供 100 美元的信用，以开始在 Packet 上使用带有 Armv8 服务器基础设施的无人机。

## 用例

云存储提供商 ownCloud [在对当时流行的 CI/CD 工具](https://thenewstack.io/how-drone-solved-ownclouds-continuous-integration-woes/) [Travis CI](https://travis-ci.org/) 和 [Jenkins](https://jenkins.io/) 感到极度失望后，转向了无人机。借助云服务 Travis CI Community edition，他们很难复制开发人员环境，并且升级是 Jenkins 面临的主要问题。两者都太慢了。

转向无人机使 OwnCloud 能够大幅增加可以在新功能和升级功能上完成的单元和集成测试的数量，而不增加每项工作所需的时间，从而允许该公司推出更多功能，同时保持成本稳定。该公司在开发人员密集度增加的时候将无人机扩大到 75 台或更多，但在安静的时候也缩小到少数几台服务器，为公司节省了大量资金。

EBay [也使用](https://blog.drone.io/interview-with-punit-agrawal-devops-at-ebay/)无人机，[纽约时报](https://open.blogs.nytimes.com/2017/01/12/continuous-deployment-to-google-cloud-platform-with-drone/)也是如此。事实上，Rydzewski 怀疑无人机可能在许多财富 500 强公司中，因为开发人员正在开发他们自己的副本，而 IT 部门并不知道。

Drone 属于 Apache 2 许可，由该公司管理，其管理方式类似于 Oracle 管理 MySQL 的方式。在业务源许可下，基本功能由一系列插件扩展——基本上对年收入 100 万美元的公司免费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>