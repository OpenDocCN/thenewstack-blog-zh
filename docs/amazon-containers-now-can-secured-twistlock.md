# 亚马逊集装箱现在可以用扭锁来保护

> 原文：<https://thenewstack.io/amazon-containers-now-can-secured-twistlock/>

为了增强其新推出的 Docker 容器注册表的安全性，亚马逊网络服务提供了扫描容器安全漏洞的能力，这要归功于与 Twistlock 的合作。

AWS 的 [EC2 Container Registry](https://aws.amazon.com/ecr/) 是 AWS 在 10 月份宣布的，是越来越多依靠 Twistlock 帮助用户保护其容器的云服务之一。上个月，谷歌容器注册中心[增加了](https://www.twistlock.com/2015/11/10/twistlock-is-now-available-on-google-cloud-platform/) Twistlock，Docker 也为自己的注册中心支持这项技术。

Twistlock 首席技术官 John Morello[在宣布新产品](https://www.twistlock.com/author/johnmorello/)的博客文章中写道:“许多客户已经有了多云战略，这种独立于平台的方法是跨所有云提供一致安全性的重要方式。一个 Twistlock 实例可以保护您的组织运行的所有不同云中的容器、主机和映像

Twistlock 是寻求解决容器安全问题的众多公司之一，随着越来越多基于容器的工作负载进入生产，容器安全问题越来越受到关注。CoreOS[和 Docker](https://thenewstack.io/coreos-introduces-container-scanning-for-vulnerabilities/) 都发布了自己的扫描器，它们都将容器中的内容与已知漏洞数据库进行比较。

Twistlock 的服务还会扫描漏洞，并在用户的持续集成过程中进行扫描。此外，Twistlock 还提供了[高级访问控制，](https://www.twistlock.com/product/accesscontrol/)使用由组织的基于轻量级目录访问协议(LDAP)的目录设置的权限。该服务还提供了[在操作](https://www.twistlock.com/product/runtimeprotection/)中监控容器的能力，以防范运行时发生的任何恶意活动。

“Amazon ECR 允许 Amazon 用户使用 Amazon 凭据来处理 AWS 容器注册表中的图像。Twistlock 现在还可以处理 Amazon 凭证和认证令牌。使用亚马逊凭证，无论 Twistlock 安装在哪里，你都可以指向[Twistlock]来扫描 AWS 容器注册表中的图像，”王晨曦在后续的电子邮件中写道。

要开始使用 Twistlock，用户需要安装 Twistlock 软件，该软件在一个容器内运行。该软件可在亚马逊合作伙伴网络上获得。然后导入一个 Kerberos 客户端证书到 Twistlock，这样软件就可以代理 Docker 客户端到 Docker 守护进程的流量。主机上不需要代理，被监控的容器也不需要任何额外的准备。一切都是通过 Docker 和 Linux APIs 完成的。

关于如何实现这项服务的更多细节可以在公司的网站上找到。

CoreOS 和 Docker 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>