# Docker 到底有多受欢迎？取决于你问谁

> 原文：<https://thenewstack.io/popular-docker-depends-ask/>

Docker 的使用似乎越来越多，尽管对于多快有争议。

监测初创公司 Datadog 的一项调查发现，Docker 的采用率在过去一年中增长了近五倍，而 T2 的一份 Skype 报告发现，人们对容器技术有浓厚的兴趣，但目前使用它的公司较少。

Datadog 利用了使用其云监控服务的 7000 家公司的样本数据。该报告承认，其客户“偏向‘早期采用者’和认真对待其软件基础设施的公司。”

尽管如此，该报告声称，这“可能是迄今为止已发表的最大规模、最准确的 Docker 应用综述。”

考虑到这一点，调查得出了一些有趣的发现:

*   2014 年 9 月，1.8%的 Datadog 客户采用了 Docker。一年后，这一数字为 8.3%。
*   在这一年中，Docker 的使用增长到在它所监控的 6%的主机上运行。
*   较大的公司是早期采用者。它将公司分为“采纳者”、“涉猎者”或“放弃者”。较大的公司正在做大量的涉猎，但也有更大比例的采用。
*   三分之二尝试 Docker 的公司继续采用它。
*   用户在五个月内使用的容器数量增加了三倍，即使是业余爱好者也是如此。
*   最广泛使用的 Docker 映像用于注册中心、NGINX web 服务器和 Redis 数据库。
*   采用 Docker 的中型公司在每台主机上同时运行四个容器。
*   容器的平均寿命为三天，而传统和基于云的虚拟机的平均寿命为 12 天。

“我们看到一些确凿的事实，Docker 正在被广泛和迅速地采用，”Datadog 营销总监 Alex Rosemblat 说。“我不知道是否所有声称拥有 Docker 支持的公司都能做到或做得很好，但公司都在使用 Docker，并且他们正在生产状态中使用。”

他说，Docker 用于运行新的网络规模的技术，如 NGINX、Redis 和各种数据库，这并不令人惊讶，尽管该公司确实觉得奇怪的是，无处不在的 Apache web 服务器没有进入包含最广泛的应用程序的前 10 名。他说，Rosemblat 没有关于为什么会这样的理论。

[![DockAdoption](img/90780888796f2426542a2e7146e0ee33.png)](https://www.datadoghq.com/docker-adoption/)

Docker 的采用可能会给基础设施监控市场带来一些重大变化。

“集装箱代表着需要单独监控的事物数量的数量级增长，”Datadog 报告断言。“以主机为中心而不是以角色为中心的监控解决方案很快就会变得不可用。因此，我们希望 Docker 继续推动几年前开始的云监控实践的巨变。”

与此同时，在 8 月下旬 VMworld 上进行的 Skytap 调查中，206 名受访者中只有 25%的人表示现在使用容器，但近一半的人表示他们的组织计划在未来 12 个月内采用容器。

“两年前，像 Docker 这样的容器技术在很大程度上被认为是互联网创业公司的领域，不能用于企业应用程序。现在，这些 IT 领导者中有 75%正在使用或计划部署它们。这是一个巨大的转变，”Skytap 的产品管理总监 Dan Jones 说，他将容器描述为加速应用交付的 DevOps 工具“刚刚成为焦点”。

Skype 在 VMworld 上还发现了其他有趣的使用模式。大约 58%的受访者更倾向于使用 IaaS 解决方案，46%的受访者会在尝试容器之前使用持续集成/交付解决方案来改进软件交付。

当 451 Research 在第一季度的一项调查中询问大约 1000 名高级 IT 专业人员关于他们对容器的熟悉程度和使用情况时，41%的人至少对容器有些熟悉，21%的人已经达到试点或生产使用，其中大约一半是试点。

StackEngine 在一月份进行的一项调查发现，745 名受访者中有 70%的人正在使用或评估 Docker。40%的人在 AWS 等公共云上使用，34%的人在 OpenStack 等私有云上使用。它在 QA/Test(63 %)和 Dev(53 %)中使用最多，31%的人在生产中使用或计划使用它。47%的受访者表示，中层管理人员对 Docker 产生了兴趣，24%的受访者表示基层员工做出了努力。

在 New Relic 的数据中，它跟踪的 46%的容器的寿命不到一小时。

Rosemblat 认为，也许市场变化的速度比人们能够真正衡量采用的速度要快。

的确，有这样的故事:全球金融服务公司 ING 使用 Docker 帮助[加速其持续交付流程](http://blog.docker.com/2014/12/dockercon-europe-keynote-continuous-delivery-in-the-enterprise-by-henk-kolk-ing/)并推动每周 500 次部署，投资银行[高盛](http://www.cnbc.com/2015/04/14/goldman-sachs-invests-95-million-in-docker.html)如此迷恋其与 Docker 的内部经验，以至于投资了该公司。在 DockerCon 2014 之后，Chris Dawson 为新堆栈写道，财富 500 强企业和初创公司[对 Docker 感兴趣。](https://thenewstack.io/why-you-should-care-about-docker/)

但是，如何定义收养可能会引起混乱。分析师 Chris Riley 指出了公司中的一种担心，即如果他们不说他们正在开发 Docker，他们会看起来像是落后了。

“的确，最近我接触的几乎每家公司都在某种程度上使用 Docker，而且他们‘计划’更多地使用它。但他们是如何使用它的，几乎还没有涉足，”他说。

“除了开发/测试和沙盒之外，很少有人使用它(过去六个月的 30 次采访中有三次)。即使在开发/测试中，使用量也足够小，可以由开发人员逐个处理。它仍然是一个孤立的个人工具。

“至少现在，开箱即用的 Docker 在大规模上分崩离析。它缺少(大部分)所需的管理功能，而且第三方工具市场太新了。要使 Docker 成为一款可持续的生产工具，必须解决诸如私有注册中心、配置安全、审计跟踪、发现(只需知道您配置了什么)和变更控制等问题。”

Datadog、Docker 和 VMware 是新堆栈的赞助商。

[运行集装箱起重机](https://www.flickr.com/photos/infomastern/17089055467/in/photolist-s36SPn-4LGK2-gmkcM-s36UQM-ppYzf4-hD7EEi-fs2WCj-adg96W-dcGZAo-nTNhrt-8YcDag-hD7HeX-4GVqqY-adg9Pw-8QvqVa-ee6ThD-6RbkZQ-62vTi8-5iF3Pn-5o1t5T-2NyDMe-ofRr5j-nTVXGV-cGmP7A-2NyEG8-2wZ4gM-cfavtE-7Hvwj5-4WgYF1-eP6Z2y-c7Zq8m-7L8aRj-cNJHNA-j7gdsP-52Lc3H-j7j97w-cLeUyY-2AzAVJ-89a4nD-58df1X-kKZgdV-inkvJ-2x7n1u-oS4Z9X-adg9kq-958D3A-kKYocZ-s4QLMm-9tktUm-j7gjCV)由 [Susanne Nilsson](https://www.flickr.com/photos/infomastern/) 操作，获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>