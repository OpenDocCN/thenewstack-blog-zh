# Docker 容器安全性:签名、密封和交付免受漏洞影响

> 原文：<https://thenewstack.io/3-new-security-features-docker/>

为了解决容器的一些安全问题，Docker 增加了三个新的增强功能，旨在保持开发人员的灵活性，同时保护 Docker 化的分布式应用程序。

该公司增加了使用硬件设备对容器映像进行签名、扫描容器映像的漏洞以及设置单独的用户名称空间来隔离环境的功能。总的来说，这些特性有助于使容器在安全性和策略遵从性至关重要的环境中更加可行。

该公司在本周于巴塞罗那举行的 Dockercon 欧盟会议上公布了这些功能。

## **硬件签名**

Docker 已经引入了容器图像的硬件签名，基于该公司在 6 月份引入的 [Docker 内容信任](https://thenewstack.io/docker-content-trust-can-run-containers-untrusted-networks/)。这基本上是 Docker 自有品牌的公证人实现，这是一个开放源代码系统，用于认证推向公共存储库的 Docker 图像源的有效性，并对这些图像的内容进行加密。

数字签名技术的目的是在网络的两端部署一个可靠的签名和加密系统，使网络的安全性不成问题。

基于 2009 年开始的开源项目，简称为[更新框架(TUF)](https://github.com/theupdateframework/tuf/blob/develop/docs/tuf-spec.txt) ，这个想法是，用于加密在线交换文件的密钥不应该存储在任何可以在线访问的地方。

只有原始发布者可以访问授权签署该存储库图像的密钥。如果恶意参与者试图在与存储库交换的任何时候插入更改的图像，对文件或其签名的修改将被检测为无效。

该公司已经与 Yubico 建立了合作伙伴关系，yubi co 将提供 YubiKey 4，这是一个包含根密钥的 USB 插件设备，将生成每个存储库的密钥，用于对特定存储库的 Docker 图像进行数字签名。然后，YubiKey 4 可以被锁在保险箱或其他地方，而每个存储库的密钥“是更新内容时的密钥”。Docker 企业营销副总裁 David Messina 解释说:“未来的任何签约都是通过这个存储库密钥完成的。

[![Yubikey](img/36e5a0a7143b13447189f887d13b8a05.png)](https://www.yubico.com/)

单个开发人员或开发团队将自己确立为发布者，从运营的角度来看，根据哪个团队生成了该内容，他们可以围绕该内容制定策略，以确定哪些内容可以在哪些环境中使用

为了帮助开发者开始使用这项技术，Docker 给每位 Dockercon 与会者发了一个 YubiKey，可以用来在他们自己的图片上签名。

## **安全扫描**

Docker 还推出了图像扫描和漏洞检测功能。在容器图像的每一层执行完全扫描分析，允许 Docker 与用户合作，根据他们的安全策略决定使用哪些内容。梅西纳说，Docker 还与独立软件供应商(ISV)分享结果，并努力修复漏洞。

![Solomon-Hykes-03](img/d2f1cc2d255131b0ab5da7b1b0d514b0.png)

它正在与一家未透露姓名的第三方合作，在代码级别进行扫描，并在每个图像层进行一系列测试。它与常见漏洞和暴露(CVE)进行比较，并执行其他漏洞扫描技术，然后返回给发起者，向他们提出漏洞建议。

“所有软件都有一定程度的漏洞；这就是软件的本质。我们的工作是将信息呈现给我们的消费者，那些使用 DockerHub 的人，这样他们就可以决定何时何地播放这些图片，”他说。

在会议上，Docker 引擎创建者 Solomon Hykes 强调，被扫描的 CVE 并不局限于那些为特定 Linux 发行版编译的 CVE，如 Red Hat 或 Ubuntu。

“你不需要把自己锁在 Linux 发行版中来保护你的容器，”Hykes 说。

## **用户名称空间**

Docker 引擎的 1.9 实验版支持用户命名空间，使 IT 操作能够分离容器和 Docker 守护进程级别的权限，从而按用户组为每个容器分配权限。

梅西纳说，这是 Docker 社区最受欢迎的功能之一。

名称空间提供了系统的视图，使您看起来拥有所有的资源。当你在一个集装箱内时，你甚至不知道集装箱外的任何东西是否存在，”Docker 安全总监 Nathan McCauley 在 Dockercon 欧盟会议上说。

IT 操作可以在用户组级别建立一组任何容器都可以拥有的特权。单个容器不能访问主机上的 root 用户，只有 Docker 守护进程可以。您可以设置具有不同级别的计算、网络和存储访问权限的容器。根据安全最佳实践，IT 运营部门可以将主机锁定在有限的系统管理员组中。

风险投资公司 General Catalyst 的董事总经理史蒂夫·赫罗德(Steve Herrod)最近告诉 New Stack，集装箱安全是一个热门的投资领域。

Docker 的“破碎的安全模型”是 CoreOS 在推出其替代 rkt 容器运行时大放厥词的背后原因。

英特尔推出了[透明容器](https://thenewstack.io/securing-containers-intels-clear-containers/)，这是一项旨在将全虚拟机(VM)的安全优势与容器的部署便利性相结合的技术

Red Hat 有一个包含 ISV 的容器认证程序和容器注册的认证图像。它最近还宣布了与安全公司 Black Duck 的合作，Black Duck 通过签名扫描已知的恶意代码，目的是识别可能需要用更新、更安全的版本替换的代码。

一家新公司 [Twistlock](https://thenewstack.io/twistlock-future-container-security/) ，是一个基于规则的访问控制策略系统，用于 Docker 和 Kubernetes 容器，也处理图像扫描。

Docker 还承诺在 6 月份推出的 Docker 可信注册中心[将提供更好的安全性。](https://thenewstack.io/docker-trusted-registry-goes-on-prem-promises-better-security/)

当被问及 Docker 的最新措施时，451 Research 分析师杰伊·莱曼(Jay Lyman)表示，这些措施有所帮助，“但重要的是要记住应用容器软件和产品是多么不成熟，尤其是对大型企业而言，因此要实现与虚拟机的容器对等还有很长的路要走。”

硬件级容器映像签名；图像扫描和漏洞检测；他说，审计和治理功能主要面向企业 IT 运营团队，较少面向开发人员，这表明 Docker 与更多对合规性和安全性感兴趣的企业有联系。

Docker 是新堆栈的赞助商。

图片:Docker 创造者 Solomon Hykes，在 2015 年欧盟 Dockercon 展会上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>