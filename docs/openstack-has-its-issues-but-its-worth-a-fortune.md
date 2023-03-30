# OpenStack 有它的问题，但它值一大笔钱

> 原文：<https://thenewstack.io/openstack-has-its-issues-but-its-worth-a-fortune/>

本月早些时候发布的 OpenStack [用户调查](https://superuser.openstack.org/articles/openstack-user-survey-insights-november-2014/)显示了这个项目的弱点，以及为什么使用它的客户变得依赖供应商。这些问题跨越 OpenStack 的不同方面，在巴黎 OpenStack 峰会的 [Kilo 设计峰会](https://wiki.openstack.org/wiki/Summit/Kilo)上进行了详细讨论。用户痛点的全部细节可以在[这里](https://etherpad.openstack.org/p/kilo-summit-ops-pain)找到。

不管怎样，顾客还是源源不断:

“OpenStack 市场正在蓬勃发展，451 Research 预测到 2018 年将达到 33 亿美元，”451 Research 的研究总监 Michael Cote 在最近为 Rackspace 发布的新闻公告中表示。“这种增长是由公共云和私有云的使用推动的，私有云得到了企业的极大关注。这些公司对云的敏捷性优势感兴趣，但也希望采用单租户、私有云部署模式。

以下是来自 Cote 的更多内容，他几乎做到了:

> 通常，他们还会寻求帮助来启动和运行云，然后持续管理云。

OpenStack 被认为是“开源的”，但它的模型旨在使供应商成为用户体验不可或缺的一部分。这产生了许多问题，这些问题是由架构本身以及如何管理 OpenStack 引起的。以下是用户最近发现的一些最普遍的问题。

## 一键安装

OpenStack 是计算、映像、存储和网络等各种项目的组合。但 OpenStack 是一种可插拔的模块化架构，这使得一键安装过程只能限制用户的选择。有各种各样的供应商正在销售 OpenStack，只需在他们的秘方上点击一下，就可以让那些想要易用性的人使用。但是使用供应商有一个警告。它把你锁在他们的解决方案里，而且可能不是开源的。

## 证明文件

OpenStack 文档需要改进。例如，对用户评论的分析表明，文档问题是第二大棘手问题。为 OpenStack 定义网络的 Neutron 项目排在第一位。为了解决他们的问题，用户转向供应商的支持文档来解决他们的问题。OpenStack 的改进只有在核心贡献者更多地参与文档团队并让他们了解最新变化的情况下才会发生。每个新版本都有新的特性和变化，大多数时候是开发人员有知识将它们添加到文档中。

## 升级

OpenStack 仍然无法通过一键安装过程升级其所有组件。例如，用户可能需要备份数据库，然后在新版本中重新安装。这造成了一个缓慢而痛苦的过程，也迫使客户将系统拆卸下来。这是客户在现代云服务中永远不会遇到的问题。升级还需要相当多的专业知识，这意味着客户经常外包，以确保更新顺利进行。

## 长期版本支持

各种电信公司和服务提供商都在寻求对 OpenStack 的长期支持。他们对当前每六个月更新一次的流程不满意。它会消耗大量资源，因为升级总是意味着停机、备份系统以及安全性等其他问题。然后，他们必须将其全部集成回自己的系统中。

这个问题只会变得更糟。OpenStack 已经开始反对或停止对旧版本的支持。例如，哈瓦那不再受支持。OpenStack 版本 [wiki](https://wiki.openstack.org/wiki/Releases) 只显示了 Icehouse 正在获得安全支持。旧版本要么已经过时，要么已经过时。如果您在数据中心内运行数百万台虚拟机，这将使升级变得非常困难。我们将看到 OpenStack 基金会是否会制定路线图来实现同样的目标。另一方面，长期支持意味着减缓整个项目的开发速度。

## **太多厂商**

当 OpenStack 开始时，批评者称它是一个没有供应商的科学项目。但是时代变了。批评者现在说，供应商已经挤满了 OpenStack，使其发展缓慢。事实上，这些供应商意味着更多的企业希望参与 OpenStack 来构建他们的开放式单租户私有环境。这些客户是 OpenStack 的贡献者，但严重依赖供应商来实现具有开源味道的专有解决方案。

特色图片 [via](https://www.flickr.com/photos/jeffbelmonte/8228640/in/photolist-Jb67-f8zVad-8puuqx-7x2iNZ-8uLv7W-zEkF-htS3C8-csUyaj-bfhhVi-mijeGX-fFq6Lr-5AmsfM-mguBzV-5AqdWf-7aiE9W-c7FqBN-x2e1U-7GJBKH-5MY3iq-8putCp-8pxBCE-bAjNG7-8pust2-89yQS7-5G1b1C-89vASe-5RRPxs-bNTXHM-pzFUXQ-8puprR-8pxDRo-6r8HMR-5tRRkz-aekw1N-dzm6TZ-axrZv2-5jRras-8purhr-aoECdY-mdknBv-8pup2p-9ZzDZD-8pupSi-4Ld4pq-oUETEo-pz5kFS-pRhCUH-pRwnyi-72Kz7s-8UaXX) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>