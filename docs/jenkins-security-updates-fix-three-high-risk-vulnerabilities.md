# Jenkins 安全更新修复了三个高风险漏洞

> 原文：<https://thenewstack.io/jenkins-security-updates-fix-three-high-risk-vulnerabilities/>

Jenkins 已经修复了一系列漏洞，包括一个可能超过一年的漏洞，这些漏洞使其用户的内部系统面临被攻击的风险。

新发布的 [Jenkins](https://jenkins.io/) 版本解决了服务器核心和插件中的 11 个漏洞，包括三个被评为高风险的漏洞，可能导致任意代码或命令执行。

强烈建议用户升级到 Jenkins 2.84 或 2.73.2，并安装最新版本的 Swarm 和 Maven 插件，即 Swarm 插件(客户端)3.5 版和 Maven 插件 3.0 版。[的用户说话了！](https://wiki.jenkins.io/display/JENKINS/Hudson+Speaks%21+Plugin)建议插件卸载它，因为它有一个严重的安全问题，目前还没有修复。

最严重的漏洞会影响 Jenkins 核心，并可能允许拥有代理相关权限的用户在 Jenkins 主节点上执行任意外壳命令。

通过配置名为“通过在主服务器上执行命令启动代理”的启动方法，拥有创建或配置代理权限的用户可以利用该漏洞该方法可以包括在代理启动时执行的任意外壳命令。

> Jenkins 开发人员花了一年多的时间才意识到他们发布了一个易受攻击的库版本。

安全研究人员此前警告称，像 Jenkins 这样的持续集成工具开箱后安全性很差，可能会帮助黑客侵入组织。安全研究人员和渗透测试人员 Nikhil Mittal [在 2015 年的黑帽欧洲大会上展示了针对多种 CI 工具的几次攻击](https://www.infoworld.com/article/3005252/security/continuous-integration-tools-can-be-the-achilles-heel-for-a-companys-it-security.html)，包括开源工具和专有工具。他在所有这些工具中发现了默认的不安全配置和可利用的特性，这促使他将其称为持续入侵工具。

Mittal 当时警告说，CI 工具的危害通常会导致对整个网络域的管理访问，因为从 CI 机器上运行的进程中提取管理员令牌的可能性很高。他演讲的视频是[这里](https://www.youtube.com/watch?v=0H6jd5yG7_A)。

## 反应

Jenkins 开发人员现在已经将这种启动方法的使用限制为具有运行脚本权限的用户——通常只授予管理员。

“这个修复的一个已知限制是，没有运行脚本权限的用户再也不能用这种启动方法配置代理，即使启动方法保持不变，”Jenkins 开发人员在咨询中说。“Jenkins 的未来版本将把这种启动方法移到一个单独的插件中。该插件将依赖脚本安全插件来保护该字段，并恢复没有运行脚本权限的用户使用此启动方法配置代理的能力。”

Jenkins 新版本中修补的另一个高危漏洞实际上源于捆绑的 Apache Commons Fileupload 库( **commons-fileupload** )。有趣的是，这个缺陷早在 2016 年 6 月就在 Apache Commons Fileupload [中修复了。](https://mail-archives.apache.org/mod_mbox/commons-dev/201606.mbox/%3CCAF8HOZ%2BPq2QH8RnxBuJyoK1dOz6jrTiQypAC%2BH8g6oZkBg%2BCxg%40mail.gmail.com%3E)

这意味着 Jenkins 开发人员花了一年多的时间才意识到他们发布了一个易受攻击的库版本。这是一个普遍的问题，许多开发人员未能跟踪他们使用的第三方库和组件中的漏洞。

通过恶意的文件上传请求，可以利用 commons-fileupload 漏洞 [CVE-2016-3092](https://nvd.nist.gov/vuln/detail/CVE-2016-3092) 来消耗服务器的 CPU 资源，从而导致拒绝服务情况，使服务器无法为其他用户提供服务。

Jenkins core 还捆绑了一个版本的 **commons-httpclient** 库，该库带有一个在 2012 年修补的漏洞。该漏洞被识别为 [CVE-2012-6153](https://access.redhat.com/solutions/1165533) ，导致库错误地验证 SSL 证书，使流量容易受到中间人攻击。

“这个库被广泛用作 Jenkins 插件中的可传递依赖项，”Jenkins 团队警告说。例如，Maven 和 Swarm 插件也捆绑了一个过时的 commons-httpclient 版本，该版本容易受到相同缺陷的攻击。

在 Speaks 中发现了另一个高风险漏洞！插件。Jenkins 开发人员说，它允许拥有作业/配置权限的用户在 Jenkins JVM 中运行任意 Groovy 代码，有效地提升了他们的权限，使他们可以全面/运行脚本。

这个缺陷目前还没有修复，这就是为什么 Jenkins 团队已经暂停了插件的分发，并建议卸载它。

Jenkins 新版本中修补的其他漏洞是各种远程 API 中的信息泄露问题:用户、计算机、作业和队列项。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>