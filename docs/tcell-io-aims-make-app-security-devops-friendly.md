# tCell.io 旨在让应用安全对开发者更加友好

> 原文：<https://thenewstack.io/tcell-io-aims-make-app-security-devops-friendly/>

安全初创公司 [tCell.io](https://www.tcell.io/) 从免疫系统中获得灵感，提供它所谓的“应用免疫”——让应用程序能够保护自己。

它将它认为最好的运行时应用程序安全保护(RASP)和 web 应用程序防火墙(WAF)技术与基于云的分析相结合，以提供对应用程序行为的实时监控并查明实际违规行为。

Okta 前产品负责人兼 Blue Coat 技术总监首席执行官 [Michael Feiertag](https://www.linkedin.com/in/mfeiertag/) 和 Splunk 前工程副总裁 [Boris Chen](https://www.linkedin.com/in/boris-chen-4b118a1/) 合作开发了一种安全方法，与 DevOps 更快交付软件的方法协同工作。

基于他们自己对阻碍交付的文化和工具的体验，“我们决定专门为试图尽可能快地创新的团队和公司建立一些新的东西。并帮助安全团队支持更快速的创新，帮助他们变得更加安全。

“[这是]而不是，'嘿，在你发布这个软件之前，我需要运行这个代码分析'或'在你发布这个软件之前，我需要做这个设计审查'或'在你发布这个软件之后，我将把一堆网络设备放在适当的位置，我不会让你去 AWS '我们需要一个解决方案来提高安全性，并帮助所有团队以他们需要的方式工作。”

## 工作流程的一部分

如何在生产环境中保护应用程序或 web 服务？这是最基本的问题，菲尔塔格说。

总部位于旧金山的 tCell 就像一个免疫系统，在应用程序运行时提供对应用程序发生的事情的洞察力，以识别攻击者并防止对应用程序的破坏。

他说，在开发产品的过程中，他们没有关注现有的安全工具，而是关注开发人员和运营团队喜欢的工具，如[app dynamics](https://www.appdynamics.com/)和[New Relic](https://newrelic.com/)。

他们提出了一些要求:

*   它必须有一个自然的部署模型，以便开发、运营和安全团队能够协同工作。
*   该软件必须是高度可脚本化的、轻量级的，并且应该在部署应用程序的任何地方运行。
*   它应该使用您已经在使用的工具，所有已经到位的自动化工具，与您的应用程序一起部署。

以容器为例，它的轻量级代理是容器内应用的一部分。他说，建造、运行和监控这些容器的所有自动化都不会改变。

该系统透明地扩展，从单个测试系统扩展到数百个全球分布的节点。

客户包括[约翰·缪尔健康](https://www.johnmuirhealth.com/)，Sophos，生命科学软件厂商 [Veeva](https://www.veeva.com/) 和人力资源平台 [Zenefits](https://www.zenefits.com/) 。

[https://www.youtube.com/embed/UIh-yTtMPw0?feature=oembed](https://www.youtube.com/embed/UIh-yTtMPw0?feature=oembed)

视频

## 应用程序、服务器、浏览器

该架构将轻量级代理放在应用服务器、web 服务器和浏览器中。如今，40%的代码是运行在浏览器内部的 JavaScript。他说，这一切都连接到一个云平台，这个平台可以从那些代理那里获取上下文信息，并看到比你从网络层看到的更多的东西。

最近，它把它的 [web 服务器代理](https://www.tcell.io/2017/09/introducing-web-server-agents/)添加到它的 JavaScript、Java、Ruby、Python、Node.js 和。Net 来抵御 OWASP 十大攻击，如跨站点脚本、SQL 注入、跨站点请求伪造等。

传感器监控:

*   请求处理和路由
*   认证和会话管理
*   数据库访问
*   操作系统访问
*   包装装载
*   响应生成

传感器收集相关数据，包括生成请求、控制器和实际命令，从而有可能区分实际入侵和攻击企图。

至少，在实施点，检测包括添加日志和策略检查。没有代码或跟踪分析或其他测试行李。策略保持轻量级并在内存中执行。根据一份公司白皮书，这些策略使 tCell 在繁忙的系统上保持低于 4%的性能开销，并且通常更低。

它使用专有的数据分析平台，支持基于流的近实时事件处理分析，以及对时间不太敏感的分析的批处理。

它帮助客户建立最佳实践安全策略，例如[内容安全策略](https://www.w3.org/TR/CSP/)，这是一个可接受的第三方内容的 web 标准白名单，可以上传到浏览器。

一旦检测到问题——无论是实际的入侵还是仅仅是一次尝试——用户会直接收到通知，他们可以用沙箱保护或阻止攻击。他们可以使用策略来设置阻止，比如说，“不要让这个应用程序运行 shell 命令”——这是在大规模的 [Equifax 漏洞](https://www.usatoday.com/story/tech/news/2017/10/03/equifax-ex-ceo-faces-questions-why-its-internal-controls-failed/725756001/)中黑客用来访问服务器的[战术](https://arstechnica.com/information-technology/2017/09/massive-equifax-breach-caused-by-failure-to-patch-two-month-old-bug/)，据菲尔塔格称。

该公司增加了 webhooks 等集成，事件响应供应商如[德米斯图拉](https://thenewstack.io/demisto-applies-chatops-security-incident-management/)、[page duty](https://www.pagerduty.com/)，协作应用 [Slack](https://slack.com/) 等。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>