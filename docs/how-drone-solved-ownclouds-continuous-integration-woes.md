# 无人机如何解决 ownCloud 的持续集成困境

> 原文：<https://thenewstack.io/how-drone-solved-ownclouds-continuous-integration-woes/>

在采用[无人机](https://github.com/drone/drone)之前，云存储提供商 [ownCloud](https://owncloud.org/) 在持续集成和交付方面处于“黑暗时代”，ownCloud DevOps 工程师 [Thomas Boerger](https://github.com/tboerger) 断言。

在此之前，公司的前进势头已经停止了太多次，因为开发团队清理了旧的 Jenkins jobs，或者等待几天来完成 Travis CI 测试集。

ownCloud 的解决方案架构 Patrick Jahns 说:“这令人沮丧，因为测试没有完成，一个功能发布不得不被推迟。本周在德国汉堡举行的[集装箱日](https://containerdays.io/)会议上，两人展示了他们使用无人机的经验。

他们指出，转向无人机让该组织清理了许多困扰公司的 CI 问题。该软件的自动扩展功能使该公司能够大幅增加可以在新功能和升级功能上完成的单元和集成测试的数量，而不增加每项工作所需的时间，从而使该公司能够推出更多功能，同时保持成本稳定。

ownCloud 以促进“开源协作”为使命，是一项共享和同步文件的在线服务。它建立在一个开源软件栈之上，包括 PHP、JavaScript、JavaScript、Elastic、memcached 和 Redis。

云服务由 GitHub 上的 1800 个存储库构建而成。直到最近，该公司一直通过社区(免费版) **[Travis CI](https://travis-ci.org/)** 托管服务以及公共和本地版本的 [Jenkins](https://jenkins.io/) 持续集成(CI)软件的组合来运行其开发管道。

Travis CI 运行了基于 DAV 的测试，如 Litmus，以及特定于 PHP 的测试和 [Selenium](https://www.seleniumhq.org/) 测试。多个 Jenkins 实例(公共的和云中的)针对用户可能部署的内容运行代码的单元测试，包括不同版本的 PHP、各种数据库和存储接口，如 Swift、Ceph 和 Samba。詹金斯还进行了 T21 的测试。

## 四面受敌

Boerger 指出，ownCloud 是一家预算仍然很少的成长型公司，这两种 CI 工具都遇到了限制，他将无人机引入了 ownCloud(他现在管理无人机名称空间)。

使用 Travis CI，开发人员会遇到某些东西在开发中可以工作，但在生产中却不行的情况。由于没有办法用插件来扩展 Travis CI，Travis CI 很难满足公司自己的特定需求。开发人员也经历过超时，通常是由于测试的复杂性。由于他们需要运行大量的作业，一项作业可能需要几天才能完成。

诚然，ownCloud 只使用 Travis CI 的免费版本，它不提供为额外吞吐量付费的能力。但 ownCloud 不想为高级版本付费，因为需要完成的工作量会使其成本过高。

柏格指出，詹金斯有自己的一套问题。升级 Jenkins 是件苦差事，因为每次升级都会破坏作业配置。詹金斯是磁盘空间的贪婪者。使用的一个实例运行在具有 32 个内核和 128 GB RAM 的专用机器上，它仍然需要定期重置。随着 ownCloud 转向容器，这个问题变得更糟:Jenkins 在容器被使用后不清理它们。“詹金斯不是为 Docker 有效载荷制造的，”Boerger 说。

和 Travis CI 一样，Jenkins 对于 ownCloud 的快节奏开发周期来说太慢了。

## 进入无人机

Jahns 解释说，Drone 是一个开源的容器原生 CI 系统。工作空间从 Docker 卷引导，而服务(如数据库)是从 Docker 合成文件创建的。然后，工作空间和服务可用于管道的每一步。“这都是自包含的，”Jahns 说:克隆步骤在容器中完成，构建步骤在容器中完成，发布步骤在容器中完成。

因为是集装箱包装的，无人机很容易升级。因为它是作为静态 Go 语言二进制文件提取的，所以非常紧凑。管道本身被描述为一个 YAML 文件，因此它可以被版本化。整个设置可以在本地运行，也可以在云中以相同的配置运行。对于每个测试，ownCloud 可以简单地提取容器，或者在没有合适的环境下创建一个容器。“无论你测试什么环境，你都可以把它作为一个可以测试的定义好的栈，交给你的开发者来测试，”Jahns 说。

对于一个接口来说，Drone 建立在 Docker Compose 之上，因此熟悉容器的开发人员很快就会熟悉它。它还提供了很多可扩展性:它可以轻松地与 GitHub(以及 GitLab 等其他存储库)集成，并且通过插件，可以直接发布到云提供商，如 Amazon Web Services 和 Google Cloud Platform。

## **准备好稳走**

最初，ownCloud 推出了无人机和其他 CI 工具，使用 Ansible 来管理设置。该公司从几个测试工作负载开始，但很快扩大了业务。随着团队学习如何使用无人机，他们给软件增加了越来越多的负载。最终，他们完全停止使用特拉维斯 CI 和詹金斯。

无人机最棒的地方在于它能够轻松扩展。因为提供公共服务，该公司必须针对每个可能的用户配置测试其代码，这一数字还在急剧增长。无人机的创造者 Bradley Rydzewski 也在开发软件，根据需求自动调整无人机的大小。它可以根据需求调配更多的节点，当工作完成时，这些节点就会退役。然而，它仍然是一个实验性的功能，只支持少数云提供商。

Boerger 和 Jahns 向观众展示的图表最好地展示了 ownCloud 在这项技术上的优势。它显示了每次构建的测试时间量如何随着无人机的采用而急剧增加——每次构建 30，000 分钟——即使每次构建的等待时间*基本保持不变，*大约 9 小时的构建时间，45 分钟的测试结果。

[![](img/c78a52e0914665418225b27e7d418f95.png)](https://storage.googleapis.com/cdn.thenewstack.io/media/2018/06/ab567d08-droneci-01.jpg)

虽然持续集成工具为更快的开发周期铺平了道路，但容器化和云原生计算正在展示进一步自动化运营的方式。他们的收益被折回 CI/CD 工具产生的速度。无人机等软件展示了这种协同作用的巨大可能性，这种可能性仍然存在。

专题图片:Thomas Boerger(左)和 Patrick Jahns 在 ContainerDays。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>