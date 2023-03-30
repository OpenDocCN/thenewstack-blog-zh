# 东京 OpenStack 的 TNS 制造商:来自大帐篷的智慧

> 原文：<https://thenewstack.io/tns-makers-openstack-tokyo-canonical-ubuntu-project-midokura-ibm/>

对于 OpenStack 来说，2015 年是成长的烦恼之年，从本周的东京 OpenStack 峰会来看。对 OpenStack 的兴趣持续增长，尤其是在企业中。但是这个社区也发现自己需要[为自己的未来做出艰难的决定。](https://thenewstack.io/openstacks-future-sparks-frank-debate-tokyo-summit/)

OpenStack 董事会成员[罗布·希施菲尔德](https://twitter.com/zehicle)在本周的会议上接受采访时告诉 New Stack 创始人亚历克斯·威廉姆斯说:“过去，我们有点战略性地认为 OpenStack 将主宰世界，创造彩虹和独角兽，[但]现实是用户做出了很多选择，我们必须战略性地考虑我们如何适应这一点。”。

除了希施菲尔德，Williams 还在会议上与来自 Canonical、Midokura 和 IBM 的主要 OpenStack 玩家进行了交流。我们在 [Simplecast](https://thenewstack.simplecast.com/) 上发布了采访的音频记录，因此您可以收听活动:

## Anand Krishnan，Canonical

Krishnan 是 Canonical 的云运营执行副总裁。与 Williams 一起，Krishnan 谈到了容器如何简化应用程序部署，强调了企业级解决方案需要简单易用，而不考虑所呈现的用例。

“Docker 下的 Ubuntu 可能是其他操作系统的七倍，”Krishnan 吹嘘道。

Krishnan 指出，随着越来越多的技术加入 OpenStack，越来越多的 OpenStack 被企业采用。OpenStack 已经成为主流企业级应用。考虑转向 OpenStack 解决方案的组织的主要顾虑是需要能够在生产中运行的服务，这些服务具有稳定性和可扩展性，能够轻松处理和平衡流量负载。Krishnan 认为 OpenStack 技术未来的发展方向是关注简单性和易用性。

[Canonical](http://www.canonical.com/) 提供一项名为 [Autopilot](http://www.ubuntu.com/download/cloud/install-openstack-with-autopilot) 的服务，为 OpenStack cloud 带来了自我管理的水平。自动驾驶围绕金属即服务[ [MaaS](http://maas.ubuntu.com/) ]锚定，将裸机变成一个功能节点。这意味着应用程序可以请求裸机节点，否则它们将需要虚拟机。Autopilot 还包括 Canonical 的 [JuJu](https://jujucharms.com/) 中的服务监控，它可以允许用户的应用程序随后部署在选定的目标云上。

[Anand Krishnan，Canonical:在东京 open stack](https://thenewstack.simplecast.com/episodes/anand-krishnan-canonical-at-openstack-tokyo)

## 《典范》的达斯汀·柯克兰

Ubuntu Cloud 产品经理兼策略师 Dustin Kirkland 在与 Williams 的谈话中表示，Canonical 正在向 Docker 中运行微服务的方向转变。他指出，编排和监控大规模的容器是一个尚未完全解决的挑战，并指出 Docker“构建、运行、部署”功能的简单性应该如何引起当今软件开发人员的共鸣。

Kirkland 指出，在容器中使用微服务时，容器编排层仍然存在有趣的问题。一个棘手的问题是选择使用 IPv4 还是 IPv6，因为使用容器联网涉及大量的端点。

> “IPv6:尽快实现目标。当支持大量容器时，您将需要它”——Canonical 的 Dustin Kirkland。

为了帮助解决这个问题，Canonical 创建了粉丝覆盖(Fan overlay ),这是一个 IPv4 bandaid，给用户时间迁移到 IPv6。Canonical Fan overlay 有一种独特的方式，可以使任何两个容器通过网络与任何其他容器进行对话。它在内核级创建了一个 fan 桥，处理从一个容器到另一个容器的 IP 流量。

使用 Fan overlay，容器端点地址和主机内核处理包装和解包，而不需要分布式数据库或一致协议。

[达斯汀·柯克兰，Canonical: At OpenStack 东京](https://thenewstack.simplecast.com/episodes/dustin-kirkland-canonical-at-openstack-tokyo)

## 丹尼尔·伯格和拉尔夫·贝特曼，IBM

在这个演讲中，IBM 云工程师 Daniel Bateman 和 IBM 高级技术人员 Ralph Bateman 描述了 IBM 如何努力为 IBM Bluemix 开发一套平台服务，包括使用 Docker 容器和全定义微服务的服务。

IBM 最近发布了基于某些标准和 OpenStack 等开放技术的改进的 VM 服务。这允许客户为他们自己的应用程序运行本地 OpenStack 云，通过 IBM Bluemix 公开。IBM 继续对其注册中心进行改进，为客户提供一个多租户模型，以实现真正的高可用性。Bluemix 还允许客户为他们自己的组织创建他们自己的名称空间，因此他们可以在不同区域之间推送和拉取他们的图像，而不必更改他们的整个名称空间。

[拉尔夫·贝特曼和丹尼尔·伯格，IBM: At Open Stack 东京](https://thenewstack.simplecast.com/episodes/ralph-bateman-and-daniel-berg-ibm-at-open-stack-tokyo)

## 亚当·约翰逊，米多仓

Midokura 是一款网络虚拟化工具，旨在帮助日本市场上运行公共云的企业。在 Midokura 开发的时候，云服务器通常运行在传统的物理网络上，而不是自动化系统上。

Midokura 的创始人亚当·约翰逊指出，计算需求已经虚拟化，而当时网络供应需要数周才能完成。为了解决这个问题，Midokura 团队在担任亚马逊网络服务的负载平衡服务和 DynamoDB 数据库服务的工程师时，开发了这个软件。“我们从亚马逊构建分布式系统中学到了什么，并将其应用于软件定义的网络，或者更具体地说，用于网络虚拟化覆盖，”约翰逊说。

[亚当·约翰逊，米多仓:东京](https://thenewstack.simplecast.com/episodes/adam-johnson-midokura-at-openstack-tokyo)的 OpenStack

## 拉肯公司的罗布·希施菲尔德

罗布·希施菲尔德除了 OpenStack 董事会的职责之外，还是 RackN 的创始人兼首席执行官，他与 Williams 谈论了 OpenStack 的未来，包括董事会希望如何定义新项目的发展。

希施菲尔德指出，技术社区已经决定让更多的项目进入，这带来了新的问题需要解决。让更多的项目进入 OpenStack 将创建一个更广泛的生态系统，并对供应商产生更大的影响，因为社区将不得不在基于云的生态系统中拥抱其他平台，并意识到用户可以在云平台中进行选择。

希施菲尔德强调，OpenStack 社区必须有足够的成熟度来处理这一问题，因为是 OpenStack 的用户将想法带到平台上，供开发人员研究和解决。希施菲尔德希望，随着[大帐篷向前推进](https://www.openstack.org/summit/vancouver-2015/summit-videos/presentation/the-big-tent-a-look-at-the-new-openstack-projects-governance)(“大帐篷”是 OpenStack 对其生态系统治理的简称)，OpenStack 董事会将继续拥抱社区，并进一步澄清 OpenStack 在云中的角色。

“我们必须鼓励我们的生态系统，”希施菲尔德说。例如，如果 Rackspace 这样的供应商除了 OpenStack 之外，还想与 AWS 和微软 Azure 合作，那么“社区必须成熟到可以说这是 Rackspace 的正确答案，因为他们的用户告诉他们，他们想使用所有平台。”

希施菲尔德希望 OpenStack 首先是一个开发者社区，还是一个消费基于云的解决方案的用户社区。最后，希施菲尔德指出，OpenStack 开发者和社区成员必须明白，一些云软件不在 OpenStack 项目空间中，客户和品牌仍然可以使用 OpenStack 服务和其他产品。

[罗布·希施菲尔德，RackN: At OpenStack Tokyo](https://thenewstack.simplecast.com/episodes/rob-hirschfeld-rackn-at-openstack-tokyo)

IBM 和 Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>