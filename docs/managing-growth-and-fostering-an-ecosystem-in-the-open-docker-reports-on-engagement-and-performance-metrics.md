# Docker 报告参与度和绩效指标

> 原文：<https://thenewstack.io/managing-growth-and-fostering-an-ecosystem-in-the-open-docker-reports-on-engagement-and-performance-metrics/>

Docker 无疑是 2014 年的增长故事。 [Andrew Clay Shafer 已经指出了](https://thenewstack.io/containers-whats-new-what-isnt-what-matters/ "Containers: whats new")Docker 的容器化如何引入了方便的默认和图像管理，这对于“技术的普及和大规模采用是至关重要的”来自惠普收购的 Eucalypt Systems 的莫滕·米科斯(rten Mickos)认为 Docker 类似于大城市的[助力车](https://thenewstack.io/marten-mickos-docker-containers-are-analogous-to-mopeds-in-a-big-city/ "Docker containers are like mopeds")(它们可能是新的热点，但你仍然需要穿防护服)，而[云计算影响者伯纳德·戈尔登](https://thenewstack.io/what-docker-does-and-does-not-deliver/ "What Docker does and does not deliver")认为，如果 Docker 能够培育一个“围绕功能的生态系统，以便 Docker 用户可以获得他们想要的所有好处”，它将“彻底改变应用程序世界”

Docker 的第一个治理顾问委员会(DGAB)上周的第一次会议反映了新堆栈在上述链接文章中涵盖的主要趋势，主要是，开源项目如何继续增加开发者的参与，同时还支持生态系统的稳定？对于新的开源项目来说，在管理预期的同时保持可伸缩性可能是一个常见的挑战，但是 Docker 需要在超高速前进的同时做到这一点。

DGAB 由 Solomon Hykes (Docker CTO)和 Docker 的其他主要维护者以及三个类别的代表组成:贡献者(过去六个月合并的非平凡拉式请求的前四名贡献者)、企业席位(Google、Rackspace、IBM 和 Red Hat)和用户(Atlassian、易贝、Spotify 和 Tutum)。

对 Docker 的接受几乎是普遍的:大型公司和新的垂直行业的初创公司，包括电子商务、媒体、生命科学和 IT SaaS/IaaS/PaaS，都在公开谈论使用 Docker。其他行业也在投资 Docker 项目，治理委员会被告知，“几乎每个主要的大型投资银行都有一个与 Docker 相关的计划正在进行中”。

## 码头工人参与度指标

虽然 Docker 于 2013 年 3 月推出，但增长达到超高速率实际上只是过去 6 个月的事情。今年 6 月举行的 DockerCon 之前的采用数据以及 10 月中旬审查的数据显示，大多数采用是新的。

总体而言，投稿人数以 44%的半年增长率增长，从 6 月初 DockerCon 时的 452 名投稿人增加到 10 月中旬的 650 名投稿人。最令人印象深刻的是容器拉动的增长率(以百万计)，这是半年内 1387%的增长率，这是 Docker 在开发人员社区中实际使用的指标。其他参与度指标(均以千计)同样令人印象深刻:

对于 DGAB，Docker 还将他们的增长率与其他开源项目进行了比较，包括 Ansible、Chef 和 Cassandra。只有 Meteor 显示了类似的优势，尽管它们的增长分布在 18 个月的时间框架内，而不是 Docker 的 6 个月的快速增长。

在 2014 年 6 月的 DockerCon 之后，Docker 的拐点也可以在其他独立整理的指标中看到。网站统计服务公司 SimilarWeb 和 Compete 都显示，2014 年 6 月以后，DockerCon 的网站流量突然持续增长，自 DockerCon 以来，SimilarWeb 估计每月平均有 380 万全球访客。

## 码头工人表演

随着开发人员的加入——特别是在不同的垂直行业中——Golden 关于支持“功能的周边生态系统”的观点对于这种转变为忠诚的开发人员社区的增长变得非常重要。

Docker 使用拉请求数据作为其核心指标，以展示其在响应用户需求方面的性能，从而能够响应 Docker 生态系统的各种功能需求。最令人鼓舞的是，社区贡献者和 Docker 的维护者关闭的拉取请求一样多(几乎完美地平分了 50.35%的拉取请求由社区贡献者关闭)。这表明一个积极参与的开源开发者社区正在围绕 Docker 真正形成。

平均而言，拉取请求保持打开状态的时间为 7.2 天。DGAB 用户代表[尼古拉·保鲁奇注意到](https://blog.docker.com/2014/11/guest-post-notes-on-the-first-docker-advisory-board-meeting/ "Nicola Paolucci's post on attending DGAB")虽然拉取请求得到了高效处理，但由于专注于高质量标准，更复杂的拉取请求可能会花费更长时间:“维护人员真的很关心干净的设计，在没有进行一些事先设计讨论的情况下，他们会谨慎地接受数万行的大幅下降。保鲁奇写道:“他们希望在重大失误发生之前，更好地促进对话。”。

## 规划未来的道路

也许 Docker 团队前进的第一步将是更好地从商业 Docker Incorporated 中描述 Docker 开源项目。根据保鲁奇的说法，一些对话继续回到寻求明确界限的问题上。因此，Docker 将建立一个独立的组织——“元团队”(Team Meta)，专注于“让项目更加有效”。团队 Meta 将负责审查拉动式请求，为工具分配资源，并使用交互式方法更新路线图，以衡量网络和存储等关键功能领域的进展。

作为 Docker 想要展示的开放文化的一部分，这个路线图将是至关重要的。API 是许多需要完成的工作的核心。无论是编排能力、通过插件的集成和定制，还是动态网络和存储，API 都被视为推进这些目标的关键机制。清晰记录的路线图将有助于用户和生态系统合作伙伴做出相应的规划(和贡献)。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/joceykinghorn/10012135796/sizes/o/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>