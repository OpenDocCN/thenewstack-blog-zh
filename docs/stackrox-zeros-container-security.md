# StackRox 提供了容器安全性的细粒度视图

> 原文：<https://thenewstack.io/stackrox-zeros-container-security/>

根据提供专注于容器的安全技术的初创公司 [StackRox](https://www.stackrox.com/) 的说法，随着 DevOps 团队构建和部署更快、分布式、可扩展和可移植的应用程序，IT 安全工具需要反映这种生产速度。

“我们认为保护需要以与应用程序相同的方式运行。他们需要使用相同类型的构建模块，并以与这些应用相同的方式提供安全性，”StackRox 产品副总裁[魏连当](https://www.linkedin.com/in/weiliendang/)在接受采访时说。

近三年来，其团队一直致力于 Docker 和 Kubernetes、机器学习和 DevOps 工具的安全平台，以提供一种新的方法来保护容器免受威胁。

传统上，单点解决方案一直专注于堆栈的一个方面，即网络、主机或对 API 的服务调用。但是因为容器是如此短暂，它们可能已经消失很久了，没有留下任何信息来进行法医分析。据该公司称，StackRox 可以在最精细的层次上查看任何类型的集装箱活动。

“无论组件是瞬间扩展几个数量级、跨云(公共云或私有云)移动，还是依赖完全自动化的生命周期，都需要持续一致地应用安全性。这需要将安全性构建到将应用粘合在一起的‘结缔组织’中——它必须是微服务结构本身的一部分，”Dang 在一篇关于其新技术的[博客帖子](https://www.stackrox.com/post/2017/07/introducing-stackrox-a-modern-security-platform-for-the-microservices-age/)中写道。

StackRox 为容器提供自适应威胁保护，包括端点检测和响应(EDR)、web 应用防火墙(WAF)和入侵防御系统(IDS)/入侵防御系统(IPS)保护，所有这些都在同一产品中。

StackRox 软件持续监控数百万个信号，包括系统调用、网络流量和 Docker 事件。它允许用户组织和可视化他们的容器环境，并可以自动执行或手动执行操作。

该技术作为一组基于容器的微服务[与客户的容器化应用](/category/microservices/)一起部署和运行。Dang 说，它的运行方式与部署任何其他应用程序的方式相同。

## 增强的可视性

这家总部位于加州山景城的公司成立于 2014 年。

联合创始人 Sameer Bhalotra 曾是谷歌于 2014 年收购的 T2 公司的首席运营官，并担任白宫网络安全高级主管，以及参议院情报特别委员会(SSCI)的技术和网络安全负责人。他的合作伙伴阿里·戈尔山(Ali Golshan)共同创立了硅谷恶意软件防御公司[cy hort](https://www.cyphort.com/)，并领导该公司的产品战略、研究和技术计划，包括威胁研究实验室。

它刚刚在红杉资本(Sequoia Capital)牵头的首轮融资中筹集了 1400 万美元。

“众所周知，开发人员不会改变他们编写代码的方式来提高安全性。因此，安全产品创建了“控制点”，在这里可以应用安全策略。对帕洛阿尔托来说，是网络流量；对于 Okta 来说，是身份；对于 Skyhigh 来说，就是云流量。如今的不同之处在于，应用程序被写成了‘微服务’……，”红杉资本(Sequoia Capital)的合伙人 Aaref Hilaly 在一篇[帖子](https://www.linkedin.com/pulse/stackrox-reinvention-security-microservices-aaref-hilaly?published=t)中写道，他解释了为什么要投资 StackRox。

“这意味着，第一次有可能将控制点转移到应用程序本身。通过预先收集数据——来自容器的系统调用、Docker 事件数据等。—现在，安全团队可以获得比以前更大的可见性和对应用程序内部的控制。从某种意义上说，安全团队现在可以通过监控和管理应用程序组件之间的信息流来将安全性构建到应用程序环境中。如果做得好，它将消除对其他控制点的需要—如果您可以将安全层置于应用程序本身的核心，为什么还要有 web 应用程序防火墙(WAFs)或入侵检测系统(IDS)呢？”

StackRox 的特性包括:

*   **带指纹识别的容器自动发现:**它自动发现您环境中的每个容器，并应用指纹识别技术来轻松发现已知和恶意容器。
*   **高级网络可视化:**容器网络的实时详细、交互式可视化，实时显示容器、微服务和应用程序之间的连接。
*   **多种机器学习模型检测各种威胁。**
*   **自动-** **调优:**随着应用程序的不断发展，StackRox 会根据应用程序和环境的变化进行动态调整，无需用户干预。
*   **预配置的数据过滤器**可以轻松聚焦最有意义的数据。或者你可以创造你自己的。
*   ****攻击类型和技术库**基于各种威胁媒介的异常或恶意行为模式。**

 **安全团队可以控制所呈现警报的特殊性以及呈现警报的格式，以最适合他们的响应工作流。

用户可以设置自动操作，如阻止未经授权的 Docker 命令，隔离或暂停受损或流氓容器。

在 TechCrunch [的一篇文章](https://techcrunch.com/2017/06/28/the-next-generational-shift-in-enterprise-infrastructure-has-arrived/?ncid=mobilenavtrend)，[中，纽约市企业技术风险投资基金 Work-Bench 的风险合伙人迈克尔·亚姆尼茨基](https://twitter.com/ItsYamnitsky)谈到了正在进行的涉及人工智能的世代转变。

他表示，变革性的新公司将通过智能系统(SOI)提供价值，该系统将领域专业知识与来自多个来源的数据和机器学习相结合。

他列举了新的安全初创公司，包括 Twistlock、Aqua Security、StackRox、Signal Sciences 和 tcell.io，它们正在向这一领域发展。

他说，实现这一目标将需要跨平台的智能和采用开放平台架构，应用程序开发人员可以在此基础上建立一个生态系统。

特征图片:[容器](https://www.flickr.com/photos/jumilla/14403331148/in/photolist-nWLQxE-njSrwT-an9FYm-iYjsv-iEoK39-iYjss-9at6Z7-bW3NeL-o4RkR-6rJaN3-e7BQt-28rg3L-8LXD1-TvqJmB-2UrVHv-VjiSN1-pnSzL-2UrYz4-2Us2tK-Eeqeo-85HX8j-V9GHEo-nS6Sax-SGpPT3-V9GK1j-3EK4k-U3mP5E-Vdfttu-GjMFdK-fs2WCj-4LGK2-a3NYdi-hD9cR2-rF6SGG-o9rBXe-2AzAVJ-dcGZAo-89kD1f-r8PNMA-WAsqHf-aoHuTF-boaQy8-u8Bei-VFjkSN-He19d1-UHodd1-6YXYGU-7YmaKY-FXpFZ-4U7q5f)由 [Jumilla](https://www.flickr.com/photos/jumilla/) 提供，在 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**