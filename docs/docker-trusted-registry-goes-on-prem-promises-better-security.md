# Docker 可信注册中心在本地运行，承诺提供更好的安全性

> 原文：<https://thenewstack.io/docker-trusted-registry-goes-on-prem-promises-better-security/>

周二，Docker 宣布其 Docker Trusted Registry (DTR)正式可用，该注册为 Docker 容器图像提供了一个内部注册选项。

据该公司称，2 月份推出的一个测试程序吸引了 800 多家组织，其中一半以上来自财富 500 强，为注册中心提供了宝贵的反馈。

它将注册表与其商业产品和支持服务捆绑在一起，订阅费每月 150 美元起。Docker、Amazon Web Services、IBM 和微软都可以立即提供这些解决方案。

Docker 对 1000 名用户进行了调查，以确定他们希望从公司看到什么，支持和本地注册选项是用户提到的两大服务，Docker 企业营销副总裁 David Messina 告诉 New Stack。

Docker Hub 自 2014 年 6 月开始提供，但批评者抱怨说，在那里找到的图像可能存在漏洞。事实上，初创公司 BanyanOps 已经将扫描图像作为一项业务，声称[官方存储库中超过 30%的图像容易受到安全攻击](http://www.banyanops.com/blog/analyzing-docker-hub/)，如 Shellshock、Heartbleed 和 Poodle。

在最近的一份报告中，Gartner 分析师 Joerg Fritsch 写道， [Docker 对于多租户、平台即服务类型的操作来说足够安全，但对于跨多个信任级别、安全区域或潜在敌对租户使用的 Linux 容器来说，可能需要更多的控制。](http://www.informationweek.com/cloud/infrastructure-as-a-service/gartner-gives-thumbs-up-to-docker-security/d/d-id/1318612)

随着 Docker Hub 每月接近 1 亿次拉动，Docker 在 4 月份宣布了 [Registry 2.0](https://blog.docker.com/2015/04/faster-and-better-image-distribution-with-registry-2-0-and-engine-1-6/) ，此前它使用谷歌的 Go 编程语言从头开始重写。Docker Hub 的核心技术是一个中央服务器，用于为测试和生产推送和提取图像。

为了解决一些安全问题，它使用 TLS(传输层安全性)协议来加密存储库和最终用户之间的容器。该软件还提供 Webhook 通知，可以让管理员或外部工作流引擎知道何时有人下载图像。

Docker Trusted Registry server 提供轻量级目录访问协议(LDAP)和 Active Directory 与现有认证系统的集成。它还提供了基于角色的访问控制(RBAC)和审计日志，用于授权和合规。

一月份发布的谷歌容器注册中心(T1)也已经脱离了测试阶段。存储在那里的容器图像是静态加密的，使用 Google Cloud Platform OAuth 对访问进行认证，并通过 SSL 传输。图像现在也可以存储在亚洲和欧洲。用户只需支付谷歌云存储费用。

[SUSE 周一还宣布与 Docker](http://www.prnewswire.com/news-releases/suse-elevates-docker-in-suse-linux-enterprise-server-12-300102521.html) 在 SUSE Linux Enterprise Server 12 方面建立更紧密的联系，包括经过验证的预建映像，使客户能够使用 Portus(一种开源前端和授权工具)建立私有的内部注册表。

Red Hat 已经与独立软件供应商(ISV)一起创建了一个容器认证计划，以确认特定的容器化应用程序是安全的，没有已知的漏洞，未经修改，来自已知的内容源，并在 Red Hat 基础架构上按预期工作。Red Hat 容器注册表将只存放经过认证的容器图像。它最终还将使合作伙伴和 ISV 能够托管他们自己的注册中心，用于 Red Hat 认证的容器

[CoreOS](http://www.datacenterknowledge.com/archives/2014/10/31/coreos-stand-alone-docker-container-registry-for-private-deployments/) 在 10 月份宣布了一个独立的 Docker container registry，用于私人部署，通过收购纽约初创公司 Quay.io。它最近表示正在对 Quay.io 进行改造，使其成为 Docker Hub 的更有效的竞争对手。

IBM 之前提供了托管的私有注册表，微软的 Azure 和 Tutum 等初创公司也是如此。

在周二的 DockerCon 上，微软展示了跨 Windows Server 和 Linux 的多平台分布式容器应用程序，以及对 Docker 的 Visual Studio Online 支持和新的 Azure Marketplace 体验。

“我们很高兴 Docker Trusted Registry VM image 现在可以在 Azure Marketplace 中使用，为组织提供 Docker 映像的私有存储库，”微软 Azure 的架构师 John Gossman 说。“随着我们在未来几个月内将 Visual Studio Online 与 Docker Trusted Registry 集成在一起，我们也期待着将我们共同努力的成果推向市场。”

CoreOS、Docker 和 Red Hat 是新堆栈的赞助商。

特征图片: [Franck BLAIS](https://www.flickr.com/photos/66971402@N04/ "Go to Franck BLAIS's photostream") 制作的: [Sub 收银机](https://www.flickr.com/photos/66971402@N04/7569786950/in/photolist-cwV8W7-roqGpm-35pUGM-a8y4aA-dST5CG-oE2H1D-niQRPm-8MSRFh-sQETiC-bxRRQY-rkzFmc-7sNeCk-oGrjEE-pN6nn1-pDQ471-6YVLpH-hc55Q-mu4Ehx-hsHGma-4bJhyd-sof1Mf-7B3JUK-nzqA15-6isMa-afV9TP-2LprYb-9reMj1-4Hz3H6-6dtTeL-oqawAw-rknuSp-8VHFF-5UkAUS-anBa7q-rGJewA-jR2bv4-4Gu1oJ-nEHdU1-9oneas-t6fFPo-93Vu46-8R2svU-qRzQso-pS1Dkf-g488Pj-ee9rYm-bVxpep-j4QCy8-PoUiC-bLLygx) r， [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>