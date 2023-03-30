# ShiftLeft 将安全重点转移到分析应用程序，而不是对威胁做出反应

> 原文：<https://thenewstack.io/shiftleft-shifts-security-focus-applications-not-reacting-threats/>

如果您可以放弃试图跟上每一个即将到来的安全威胁，而是在代码级别保护您的应用程序，会怎么样？

这就是总部位于加州圣克拉拉的初创公司 ShiftLeft 的想法，该公司专注于在构建时和运行时提供安全性。

首席执行官[马尼什·古普塔](https://www.linkedin.com/in/manishgupta00/)说:“我们正在开发一个针对每个应用程序每个版本的微代理，不是通过响应威胁，而是通过了解该应用程序版本的安全需求。

他解释说，在收缩包装软件时代，客户别无选择，只能提供外围安全——防火墙、入侵检测、防病毒、web 应用程序防火墙——因为他们无法访问专有源代码。在安全行业的 15 年中，最近在 [FireEye](https://www.fireeye.com/) ，他每天看到大约 100，000 个新的恶意软件，在开发团队每天发布多次软件的环境中，对威胁做出反应是没有意义的。

与此同时，组件的组装——一点点定制代码、一些开源软件和第三方库——为将错误和代码缺陷整合到应用程序的多个版本中提供了更多机会。

## 双管齐下的方法

ShiftLeft 结合了对源代码和软件运行时行为的分析。

在构建时，ShiftLeft 首先确定公司所说的应用程序的“安全 DNA ”,并创建一个在运行时使用的自定义安全代理来保护应用程序的特定版本。这个“DNA”包括软件做什么，使用的开源软件，漏洞，它如何使用敏感数据和编码错误。

“如果你知道微服务不会派生一个流程，如果在生产中它开始派生一个流程，我们就知道它被利用了。我们可能不知道是什么威胁导致了它，但通过源代码了解应用程序，然后监控与源代码相关的生产环境行为，我们可以知道应用程序何时被利用或未知漏洞何时被利用来利用，”Gupta 说。

与 Jenkins、Travis CI 或 Circle CI 等 CI/CD 工具一起使用时，它是一个插件或命令行界面。构建完成后，它获取与项目相关的外部依赖项，组成一个归档文件，并将其与组织 ID 和令牌元数据一起上传到 ShiftLeft 云中的网关服务器。从网关服务器到 ShiftLeft 核心系统的所有数据都用组织的私钥加密和签名。

微代理是一个 JAR 文件，它使用一个命令附加到部署，该命令包括 JAR 路径和发送运行时事件和警报的 ShiftLeft 网关服务器地址。

如果使用 Chef、Puppet 或 Ansible 之类的部署配置工具，请使用配置文件中的命令来提供应用程序。微代理在运行时监控应用程序，并通过 ShiftLeft 代理将事件和指标发送到 ShiftLeft 网关服务器，shift left 代理是一个 Linux 可执行文件，可以安装在大多数 Linux x64 位发行版上。

例如，如果您有一个 1.3 版本的应用程序，初始扫描在代码中发现了 10 个问题，开发人员，无论出于什么原因，可能只修复了其中的 6 个问题，这就变成了 1.3.1 版本。古普塔解释说，公司将两个版本都投入生产并不罕见。那么 ShiftLeft 将保护 1.3 版中的 10 个问题，并且只保护 1.3.1 版中剩下的 4 个问题。

“它知道每个版本中有什么问题，以及这些问题在源代码的哪一行。如果你在 AWS 上的虚拟机中部署你的应用程序，当它启动时，微代理知道第一个问题在第 23 行，所以它在那里检测自己，第 98 行有第二个问题，所以它在那里检测自己，等等，”他解释说。

在[的一篇博客文章](https://blog.shiftleft.io/shiftleft-notes-on-a-journey-b0de00aea408)中，联合创始人兼首席技术官[切坦·科尼基](https://www.linkedin.com/in/conikee/)解释说，一个仪表板从安全的角度映射了应用程序的流程。然后，可以将基于策略的逻辑应用于流程，以跟踪:

*   所有输入和输出
*   流根处的输入验证
*   随着应用程序的发展，添加了新的流程
*   流边缘的输出编码
*   应用程序中的加密实践
*   应用程序中如何使用敏感数据

他说，该软件会随着你的代码随着时间的推移而变化，识别潜在的漏洞，你的应用程序中的敏感数据泄漏，并对负漂移发出警报。

它与云基础架构、虚拟机、容器和裸机无关。10 月份首次亮相的初始版本支持 Java，包括 Oracle JVM 1.6+和 OpenJDK 1.6+等流行的 Java 运行时。该公司计划在未来几个月内支持 JavaScript 和 Golang。

特征图片: [**Christiaan Colen**](https://www.flickr.com/photos/christiaancolen/) 的 [Linux 密码文件](https://www.flickr.com/photos/christiaancolen/21133467186/in/photolist-ycuxvU-59814t-7ZaHVm-ycuxEG-inZDzP-597Zn8-59cbDu-RZqfKq-fw1RmQ-CuCPLA-6jw2p5-84xCWK-dH4Kzp-6jw2mU-TyLyVy-qqxTVm-5PrWqf-8TnkqM-hSZkHk-fw1Rmd-87jJcQ-fw1RjQ-2bPm7-igjcMa-2bRe4-nzu)，在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>