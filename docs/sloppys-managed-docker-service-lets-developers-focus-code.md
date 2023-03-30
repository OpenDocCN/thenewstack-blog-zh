# Sloppy 的托管 Docker 即服务让开发人员专注于代码

> 原文：<https://thenewstack.io/sloppys-managed-docker-service-lets-developers-focus-code/>

德国隐私法要求数据必须保存在其境内，这为德国企业和其他地方的组织提供了一个新的托管 Docker 托管服务[slapy . io](https://sloppy.io/)带来了潜在的盈利商业计划。

这家总部位于科隆的公司专注于那些希望专注于代码而不是管理服务器的企业。它的客户从自由职业者、混合集成平台 [elastic.io](https://www.elastic.io/) 这样的初创公司到[德国电信](https://www.telekom.com/en)这样的企业。

有了 sloppy.io，用户可以专注于开发；他们不必担心存储、负载平衡、更新等问题。

“如果你的容器在你的笔记本上运行，你可以在 Sloppy . io 上托管它。一切都很容易，”slapy 首席技术官兼联合创始人迈克·米歇尔说。

在解释 Sloppy 的起源时，Michel 说，当他和联合创始人 Marc Zimmermann 在日常工作之外还有一项副业，即向其他企业提供 DevOps 工具和基础设施时，他们不断遇到相同的问题:一次又一次地向客户交付 LAMP (Linux、Apache、MySQL 和 PHP/Python/Perl)和 MEAN (MongoDB、ExpressJS、AngularJS 和 Node.js)堆栈，客户有许多关于软件和服务器版本的更改请求。

“所以我们想:让我们建立一个自我供应的平台。那是在 2014 年底，我刚刚被介绍给 Docker，我立即想到，‘这将是一个游戏规则的改变，’”米歇尔说。

他说，他们在 2015 年开始构建 sloppy.io 的测试版，并在两个月内拥有了 1000 名用户。它在今年早些时候发布了 1.0 版本。第三位联合创始人 Horst Liebetrau 作为首席执行官领导着一个 10 人的团队。

他们从 Mesos/Marathon 开始，并表示他们仍然认为这是大规模运行容器的最稳定的平台。在此基础上，他们开发了 API 服务器、web UI 和 CLI，并专注于简单性。他们刚刚推出了“Clickstarters”，在部署官方 Docker 映像时，只需几次点击即可轻松启动:

它还使用 [Elastic](https://thenewstack.io/comparison-cloud-based-elasticsearch-elk-solutions/) (Elasticsearch，Logstash，Kibana，Beats)栈进行监控和日志记录，并使用 [Weave](https://www.weave.works/) 组网。

它通过 [Docker Hub](https://hub.docker.com/) 或 [Quay.io](https://quay.io/) 提供私人回购，以及一个基于 HTTP 的 RESTful API，允许你轻松挂钩其他网络服务。它支持 CI/CD(持续集成/持续部署)工具，如 [Jenkins](https://jenkins.io/) 、 [CodeShip](https://codeship.com/) 或 [Wercker](http://www.wercker.com/) 。

此外，sloppy.io 服务还提供:

*   对无限持久存储的完全读/写访问权限。
*   支持自定义 SSL 证书。默认情况下，每个项目还会收到一个*.sloppy.zone 子域，用于即时 SSL 保护。
*   实时监控。
*   版本回滚。
*   滚动部署。

“另一个好处是，我们是一家在欧洲(德国)托管业务的欧洲公司。我们的许多客户不被允许或只是不想在 AWS、Google 等网站上托管。，”米歇尔说。

越来越多的公司提供 Docker 托管服务，包括 Docker 本身、StackDock、Apcera 以及 Hyper、Jelastic 和 Arukas。上周，总部位于德国的 SUSE Linux 宣布计划在明年四月发布一个容器即服务平台作为公共测试版。

一个有趣的附带说明是，总部位于旧金山的[gravity](https://gravitational.com/)正在推销其[tele kube](http://gravitational.com/telekube/)managed Kubernetes 服务，作为软件供应商向欧洲和其他地方的客户销售的一种方式，因为当地的数据隐私法，他们通过与那里或私人环境中的主机提供商合作来实现这一目的。使用 ssh 隧道，Telekube 可以远程管理 Kubernetes 的连续部署，其创始人说。

Apcera、Docker、Mesosphere 和 Wercker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>