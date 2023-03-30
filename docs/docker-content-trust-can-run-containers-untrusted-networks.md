# Docker:有了内容信任，你可以在不可信的网络上运行容器

> 原文：<https://thenewstack.io/docker-content-trust-can-run-containers-untrusted-networks/>

在 6 月的 DockerCon 大会上，Docker，Inc .向开发人员介绍了其开源系统公证人[，该系统用于认证推送至公共存储库的 Docker 图像来源的有效性，并对这些图像的内容进行加密。今天早上，该公司发布了自己的品牌公证人实现，称为 Docker 内容信任。](http://www.cmswire.com/information-management/docker-engineer-our-containers-are-secure/)

Docker 的目标是部署一个签名和加密系统，它在网络的发送端和接收端都非常可靠，以至于中间的网络安全不再是问题。

> Docker 安全负责人迪奥戈·莫尼卡在接受《新堆栈》采访时说:“我们获得的一个好处是，我们不需要依赖任何可信的通信手段，Docker 最终用户就可以安全地下载和验证这些内容。这实质上是我们现在提供的一个巨大保证，这是以前没有的。”

## 信任的两把钥匙

内容信任实际上是 Docker 品牌的公证人。使用的基本框架是 2009 年开始的开源项目，简称为[更新框架(TUF)](https://github.com/theupdateframework/tuf/blob/develop/docs/tuf-spec.txt) 。TUF 不是一个通用的软件更新工作流，而是一个更新系统(在公证人的情况下，是存储库)的工作流，它实现了加密，作为阻止攻击的一种方式。

TUF 的基本原则之一是，用于加密在线交换文件的密钥不应该存储在任何可以在线访问的地方。Content Trust 将通过两层密钥系统来实现这一原则，这种系统使用针对 Docker 存储库的每个存储库的密钥，并保持在线，可能在持续集成系统上，与用于创建每个存储库的密钥并保持离线的根密钥分开。Mónica 在接受新堆栈采访时表示，Content Trust 的这一实现版本仍将推出。

[![Docker security lead Diogo Monica](img/39af907aace228213f2d2f247ac88352.png)](https://thenewstack.io/wp-content/uploads/2015/08/150622-DockerCon-20-Diogo-Monica.jpg) “根密钥实际上可以保存在 USB key 中，存储在保险箱或银行中——一个安全的存储位置，”莫妮卡解释道，“因为只有在创建新的存储库密钥时才需要它。”

在恶意行为者试图将伪造的 Docker 图像注入到利用内容信任的储存库中的情况下，安全主管继续说，只有原始发布者应该能够访问被授权为该储存库签署图像的密钥。如果恶意参与者试图在与存储库交换的任何时候插入更改的图像，对文件或其签名的修改将被检测为无效。

从 DockerCon 上提出的建议中得到启示，信息安全专业人员希望看到绿色的保证复选标记(由，[哦，我不知道，某个记者](http://www.cmswire.com/information-management/docker-engineer-our-containers-are-secure/?pageNum=2)提出的建议)，当无效检测出现在存储库中图像名称旁边时，它会将绿色的“GO”标记变为红色。

每个存储库密钥的密钥轮换过程发生得足够快，以至于使用旧版本密钥伪造内容的恶意尝试也将触发无效。莫尼卡说:“现在，你将真正得到保证，内容是你能得到的最新内容，因为 Docker 内容信任实际上给了你数据新鲜度的保证。实际上，在有些攻击中，攻击者主要向用户提供有效的内容，但这些内容已经过时。内容信任让您能够抵御这些“冻结攻击”"

当然，所有这些都假设恶意攻击者永远不会同时获得两组密钥。在这种情况下，某种新形式的密钥管理工具难道不是必要的吗？

Docker 告诉我们，根密钥实际上是离线的，这一事实使得密钥管理软件的问题变得毫无意义。它能做什么，提醒你你把根钥匙放在哪个抽屉或壁橱里了吗？这可能就像密码维护者一样愚蠢，让任何自称斯科特 m 富尔顿三世的人通过提供他祖父的名字来找回他忘记的密码。

在恶意行为者确实获得了每个存储库的密钥的副本的情况下——可能通过盗窃存储该密钥的设备——物理根密钥，例如[Yubico FIDO 密钥](http://www.fierceenterprisecommunications.com/story/yubico-puts-fidos-second-authentication-factor-your-pocket/2014-12-17)，可以用于生成新的每个存储库的密钥，该密钥自动使所有早期版本无效。

## 烤的还是栓上的？

关于软件开发人员应该在多大程度上关注安全问题，在容器化领域内外都有相当多的讨论。从历史上看，平台供应商认为，如果平台能够正常工作，开发人员就不需要关心安全问题。栅栏的另一边是每个被 Windows XP 体验烧伤的人，他们对 Vista 及其继任者过于怀疑，以至于不遵守微软的安全准则。

分布式应用程序目前在 Docker 中的工作方式让一些人想起了他们早期使用 DCOM 等系统的经历，在这些系统中，程序组件相互信任，因为注册中心告诉他们要这样做。鉴于关于 Docker 网络未来的新讨论，一些人在问，更广泛的社区中的开发人员是否会承担在最底层为 Docker 定义安全架构的任务。

目前，根据 Docker 营销副总裁 David Messina 的说法，Docker 的答案是否定的。

> “对于开发人员来说，通常在他们的工作流程中，安全性是一种事后的想法，”Messina 说。“在这种情况下，他们不必考虑安全性，但它嵌入在我们向他们提供的模型中。”

迪奥戈·莫尼卡向我们强调，关于安全性，“使用这种软件的开发人员并没有考虑到这一点。他们可以构建图像，可以提取图像，并且可以继续正常操作，而不会注意到 Docker 内容信任实际上是在验证所有这些签名并为它们执行所有这些复杂的操作。从发布者的角度来看，将会有一个新概念，这基本上是一个需要这些密钥来操作的数字签名方案的功能。”

Docker 是新堆栈的赞助商。

专题图片:[MMIX(2009 年你可以提高摄影水平的十件事)](https://www.flickr.com/photos/pagedooley/3155475669/in/photolist-vFzU1x-jgYViU-5NQCYV-uJoyX6-dGL2HN-vEEyiy-vFBmKT-uJnQNr-uJnF1a-vCX6Ws-voFcPC-voERMo-uJcbyb-vCWmd5-uJnbrg-jVxCqB-voF4oG-vFA4mg-voCcZA-uJmZgF-voLofi-uJo1qc-bSfMp-9GaueZ-dYxuRV-vCU29C-voCPFy-vFfmrn-vCVqAA-voEKgC-vFesoV-vEDGS9-voLcs6-rPYMNw-4yMYWW-dGL2wW-my59wp-voErKW-vEF6ML-Hd1XE-D6LLP-4dgkeH-4yHHgB-4yMX91-4yMWvQ-k36zt)[凯文·杜利](https://www.flickr.com/photos/pagedooley/)。由 2.0 在知识共享 [CC 下发布。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>