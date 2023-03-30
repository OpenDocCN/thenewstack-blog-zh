# HashiCorp 努力将范围扩展到开发人员工具之外

> 原文：<https://thenewstack.io/hashicorp-drives-to-expand-the-scope-beyond-developer-tools/>

根据 HashiCorp 的说法，整个 DevOps 运动一直缺少一个重要的部分，过于强调工具，而对需要开发人员、运营和安全团队作为应用交付流程的一部分共同工作的整体工作流重视不够。

联合创始人兼首席技术官[艾蒙·达德加尔](https://github.com/armon)表示:“【更快地发布软件】不仅仅是关注敏捷和提高开发人员的效率。”。

 当他们与英国的一家金融公司讨论如何协调开发和运营时，一位运营经理告诉他们，“我们能否在 5 秒内部署一个应用程序并不重要；安全团队需要六个月的时间来更新防火墙。”

这就是该公司关注工作流程的原因。

“我们认为这与工具无关，而是与开发、运营和安全团队的流程有关。如果我们能在 5 秒内完成部署，这并不重要；安全人员必须参与进来，并进行整合，”他说。

它一直将其工具集中在三个组上，包括管理开发环境的[vagger](https://www.vagrantup.com/)，构建映像的 [Packer](https://www.packer.io/) ，提供映像的 [Terraform](https://www.terraform.io/) ，连接和监控应用程序的[consult](https://www.consul.io/)，部署应用程序的 [Nomad](https://www.nomadproject.io/) ，保护应用程序和基础设施的 [Vault](https://www.vaultproject.io/) 。

“对一些人来说，看起来我们有如此广泛的工具组合，我们只是把东西往墙上一扔，看看有什么粘在一起。对我们来说，问题是，“我们如何教育人们，公司的重点是真正将应用交付过程视为一个单一的连续体？”

“我们认为这三个领域存在广泛的问题，人们对工具给予了过多的关注，而且通常只限于开发人员类别。你真的必须扩大范围，纵观整个事情，从工作流程的角度来看待这个过程，而不一定是从工具和技术的角度。有工具和技术来支持这个过程，”Dadgar 说。

## 变革的一年

对于这家成立于 2012 年、总部位于旧金山的公司来说，这是忙碌的一年。已经发展到 50 名员工；两年前它只有六个。

今年 8 月，该公司任命 VMware、GitHub 和 Hortonworks 的校友 David McJannet 为首席执行官，他最近在 Greylock Partners 担任常驻高管。联合创始人 Dadgar 和 Mitchell Hashimoto 成为联席首席技术官。

本周在 HashiConf，该公司宣布获得由 GGV 资本**牵头的 B 轮融资 2400 万美元，使其融资总额达到 3400 万美元。它还宣布了基于其开源安全软件的 [Vault Enterprise](https://www.hashicorp.com/vault.html) 的全面上市，该软件在应用程序级别实现安全。**

 **它报告称，今年上半年，每周开源下载量增长了 125%，用户群包括 Stripe、优步、Twitch、OpenAI、Pinterest 和 Capital One 等。

Dadgar 说，它还保持着一系列合作伙伴关系，包括 VMware、微软和谷歌，并集成了 800 多种不同的技术。

“我们有使用 VMware 管理 F5 负载平衡器的客户，也有在云中管理 AWS Lambda 功能的客户。这些是非常不同的世界，但他们通过相同的工作流程管理它，”他说。

诀窍是真正理解工作流挑战，并以此为基础构建核心，然后创建一个模块化的开源系统，并利用社区。

6 月，它收购了 Vektra *、*，后者提供多租户云日志记录，但也与其他日志记录供应商密切合作。

同样在今年早些时候，在所谓的[百万容器挑战](https://www.hashicorp.com/c1m.html)中，该公司测试了它认为是对其 Nomad 调度程序的[终极测试](https://www.infoq.com/articles/scaling-containers-hashicorp-nomad)。一个由 5 台 Nomad 服务器组成的集群在不到 5 分钟的时间内安排了 100 万个集装箱，速度为每秒 3750 个集装箱。

”回答是，‘你为什么会想这么做？“这是任何人都不愿做的，”达德加尔说。“然后几周后，我们接到(对冲基金)Citadel 的电话，说‘我们的工作量是那个的三倍。你能帮助我们吗？"

在本周的 HashiConf 会议上，Citadel 的凯厄斯·豪克罗夫特讲述了其在五个小时内每秒 18000 个内核和 2200 个容器的测试。

## 奥托出去了

在一年前的 HashiConf 会议上，桥本宣布[vagger 部署自动化工具已经过时](https://thenewstack.io/hashicorp-revamps-vagrant-and-retools-for-microservices/)，并任命其继任者 Otto。

Otto 构建在 vagger 之上，它会根据当时运行的系统的约束条件，为正在部署的应用程序确定最佳配置。

他称之为与流浪者根本不同的[工具，但流浪者 2.0 正在酝酿中。现在仍然如此，但上个月该公司停用了 Otto，这意味着利用 HashiCorp 的其他工具。它没有获得该公司所希望的吸引力。](https://thenewstack.io/tns-analysts-show-62-at-hashiconf-2015/)

“Otto 的开发和原型展示了以前未知的挑战。虽然这些挑战中的许多都得到了解决，但是同样多的人发现了该工具的架构限制。这是奥托设计有缺陷的最初信号，”该公司在一篇博客文章中说。

桥本说:“我们觉得这有点为时过早，而且不符合我们试图解决的问题。”。“我们仍然相信我们正在调查的问题空间，但我们不想误导用户，让他们认为我们在这个问题上投入了比实际更多的时间。我们将[的最终源代码放到了网上](https://www.ottoproject.io/)，但我们并没有积极开发它，尽管这仍然是我们坚信的一个想法。”

专题图片:[复活节岛 Ahu Tongariki](https://www.flickr.com/photos/ndecam/6214224084/in/photolist-at8wjy-ZsGTN-3zv9yf-eY69eo-nbYCxn-dFvVMA-o4jP1C-dFvQbo-48oJhE-6KRwxJ-6Bwa2Z-9QS56x-bhgKm8-ovhHKC-ZoFYi-6e1uXz-6KMpJe-6TVM2a-2vVkpu-6SQJcb-6BAjZw-6RPeQS-FCy1qP-68bZso-e6LhZK-6BJi4s-ryf8xe-bchc16-nyDj7n-5Ws9fj-ZtDCy-6RKbBZ-9SyeM8-dRMeWu-ib2U9M-n1au4J-9Sygt8-6SQaMG-6BAkGq-6SLEDc-txoQ8-6TVLez-bhgE3a-bchrj4-mnwHVw-4o1m9b-nAHZRz-6BJimA-5jABpU-9QS5fp) 作者 [Nicolas de Camaret](https://www.flickr.com/photos/ndecam/) ，授权 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**