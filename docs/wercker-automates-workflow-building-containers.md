# Wercker 自动化了构建容器的工作流程

> 原文：<https://thenewstack.io/wercker-automates-workflow-building-containers/>

为了理解 [wercker](http://wercker.com/) 服务如何自动化开发和部署周期，我们可以看看 Pivotal 的 Cloud Foundry Solutions (PCFS)如何将该技术作为其系统的一部分来帮助新开发人员快速启动和运行。

[Wercker](http://wercker.com/) 协调一堆 Docker 工具来运行一个名为 [Pivotal Elastic Zones (PEZ)的云资源虚拟售货机。](https://github.com/pivotal-pez/pezconsole)

PEZ 让员工迅速行动起来。团队成员可以下载 wercker [命令行界面](http://wercker.com/cli/) (CLI)并立即访问开发环境，在那里他们可以使用基础设施即服务、裸机和其他云资源在本地或云中启动、测试和部署微服务。这个堆栈包括 Golang、Ruby、Python 和 Spring Framework。

该团队还使用 wercker 自动编译培训文档，而不是手动收集各种截图、幻灯片、视频和文本。

使用一个简单的 YAML 配置，wercker 使开发人员能够在一个设置好的环境中，通过一个通过/失败步骤的集合，建立自动流水线来构建 Docker 容器。它支持三种类型的管道:开发、构建和部署。可以通过 wercker 平台或 CLI 进行部署。

Wercker 成立于 2012 年，已融资 790 万美元，最近一次是在 1 月份的 450 万美元 A 轮融资。首席执行官 Micha Hernández van Leuffen 解释说，该公司的发展源于他在加州大学旧金山分校的论文和他在一家机构从事的自动化流程工作。OpenStack 的前联合创始人、首席技术官安迪·史密斯(Andy Smith)是该公司的联合创始人。

Wercker 是位于阿姆斯特丹的 2012 年创业孵化器项目 Rockstart Accelerator 的一部分。

Wercker 最初专注于 LXC 集装箱。

“我们从用户那里收到了很多问题——你支持 Erlang 吗？你支持 Scala 吗？因此，对我们来说，开放平台，让人们创建自己的 LXC 容器是有意义的。这一切都发生在 Docker 之前，”van Leuffen 解释道。

“我们还在管道方面开放了平台。管道是一组任务、构建任务或部署任务。我们让用户设置他们自己的步骤，所以你可以设置一个松弛通知或者一个设置你的测试的步骤。有各种各样的舞步。

“当 Docker 出现时，它似乎非常适合我们，因为我们正在创建定制的 LXC 容器，所以我们转向了 Docker 和 CoreOS，并重建了我们的部分基础设施，以支持 Docker 成为一等公民。我们在 2015 年 4 月推出了这项服务。整个目标是建立一个以容器为中心的平台，用于自动化微服务和应用的开发。”

然后，该服务允许部署到各种云平台，从 Heroku 到 AWS 和 Rackspace。去年 12 月，它还在 Bitbucket 中添加了 Wercker YAML 浏览器。

van Leuffen 说，Wercker 使用 CoreOS 作为 Linux 发行版，现在 CoreOS 的容器运行时 [rkt 已经可以生产了](https://thenewstack.io/coreos-container-runtime-rkt-reaches-1-0/)，wercker 也会支持它。

“我们与容器无关。如果出现另一种容器格式，我们很乐意支持，”van Leuffen 说。

“一端是调度程序和 Linux 发行版，如 CoreOS，另一端是开发人员工作流。我们帮助您开发、构建这些容器，并将其部署到 Kubernetes、Mesosphere 和其他编排平台的调度程序中。”

作为其最近资金公告的一部分，它还开源了其 CLI，允许开发人员在他们的笔记本电脑上使用 Docker 容器。现在[是 GitHub](https://github.com/wercker/wercker) 上的一个开源项目，该软件可以在 Linux 和 OSX 上运行。

该公司的产品目前作为云服务提供，尽管 wercker 正在开发一种企业产品，也将允许内部使用。“我们一开始是一个[软件即服务]产品，如果你愿意，我们希望以 SaaS 式的方式提供企业产品，使安装和设置过程无缝，”van Leuffen 说。

Wercker 与像[shipped](https://thenewstack.io/shippable-speeds-code-production-front-line/)、 [Drone](http://blog.drone.io/) 和 [CloudBees](https://www.cloudbees.com/) 这样的公司竞争，尽管 van Leuffen 说一些 DevOps 工具还没有进入 Docker 领域以提供自动化功能。

“一些公司将某些功能拼凑在一起，而不是拥有一个自动化所有任务的解决方案，”他说。

Docker 和 Pivotal 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>