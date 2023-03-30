# 容器安全、未经验证的图像和 Docker 漏洞

> 原文：<https://thenewstack.io/container-security-unverified-images-and-docker-vulnerabilities/>

[集装箱安全，未经验证的图片，以及码头工人漏洞](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities)

容器只是在最近才开始成为持续集成和交付(CI/CD)的主流。这对于开发者自治和个人所有权来说是很棒的，但是安全性呢？虽然 Docker 和 Kubernetes 是这种快速容器采用的主要驱动力，但这两个编排器允许任何人轻松部署代码，这可能会给安全性带来危险。这些是开源平台的事实是否让它更安全或更不安全？

最重要的是，用户对容器安全性了解多少？

这是 New Stack 创始人亚历克斯·威廉姆斯(Alex Williams)在 [DockerCon](https://www.docker.com/dockercon/) 与 [InfoSiftr](https://infosiftr.com/) 运营高级副总裁 [Tianon Gravi](https://twitter.com/tianon) 以及[ticket master](https://twitter.com/Noah_Abrahams)Kubernetes 工程师诺亚·亚伯拉罕斯坐在一起时提出的一些问题。

5 月底，在 Docker 容器引擎的所有版本中发现了 [Docker 符号链接竞争漏洞](https://thenewstack.io/docker-symlink-race-vulnerability-could-allow-unauthorized-data-access/)，该漏洞为攻击者提供了一种进入主机本身或该主机管理的任何其他容器的方法，不仅可以读取文件，还可以修改文件。

亚伯拉罕斯认为安全性是一种被动、主动和追溯性的东西。

“拿 Docker Hub 这样的东西来说，‘哦，那是基于出处的。“这是基于图像的存储方式。那就更被动了。我不会从主动安全的角度考虑这个问题。我会从已经做过的事情的角度来考虑这件事，我不会以应有的尊重来看待这件事，”他说。

在安全方面，我们总是需要积极思考。我们总是需要学习。

Gravi 指出，没有多少人在谈论 May 的 Docker 攻击如何涉及 Github 令牌。这意味着 Symlink-Race 漏洞可能会危及您的源代码。

他说，这意味着攻击可以“修改 Github 库的设置，添加一个新的部署令牌，如果他们不主动审计他们的访问，几个月内都不会有人注意到。”

Gravi 说，也许因为这个漏洞没有一个令人难忘的名称和图标(如“心脏出血”)，人们不理解这次攻击的严重性。他说你必须再次确认你已经主动更换了你的令牌并更新了你的密码。

对话继续谈论云服务提供商的日益成熟，他们应该很快就会注意到不规则的行为，如更新以前没有使用过的不同类型的令牌，并标记代码更改。

另一方面，亚伯拉罕斯指出，标签是可变的——“因为它是 Docker 环境中标签概念的固有属性”——这使得[使用加密哈希](https://docs.docker.com/engine/swarm/secrets/)——如果它与图像不匹配，Docker 将拒绝它——成为当前标记攻击的最可靠方式。

Gravi 将其提升到了一个新的水平，并表示，如果他特别依赖某个特定的 Docker 映像，他将尝试接管对它的维护，因此他是映像生命周期的负责人。当然，他承认，这对于更大的组织来说是不可扩展的。

Gravi 和 Abrahams 都认为人多好，这使得他们认为开源是容器的未来。亚伯拉罕斯接着预测，那些传统上专注于攻击取证的入侵防护公司将朝着主动实时了解容器中发生的事情的方向发展。他继续说，这些公司中的每一家都将专注于一个特定的领域，然后有望与更广泛的覆盖范围进行合作和整合。

Gravi 对此表示赞同，他说，“我认为给他们的安全供应商打电话说，‘嘿，你们在开源上做什么？你如何推动社区向前发展？“你是如何让我们所有人变得更好的，”"

[https://www.youtube.com/embed/MZMGIVjKBew?feature=oembed](https://www.youtube.com/embed/MZMGIVjKBew?feature=oembed)

视频

### 在这个版本中:

[1:58:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=1:58) 客户对集装箱安全了解多少。
[4:51:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=4:51) 如何更具预防性？
[10:41:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=10:41) 整理问题。
[14:05:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=14:05) 开源安全。
[19:43:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=19:43) 对主要平台提供商的要求？
[25:41:](https://thenewstack.simplecast.com/episodes/container-security-unverified-images-and-docker-vulnerabilities?t=25:41) 探讨如果有事发生，责任在哪里。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>