# Equifax 数据泄露显示了不及时打补丁的危险

> 原文：<https://thenewstack.io/equifax-data-breach-shows-perils-not-patching-timely-manner/>

Equifax 最近宣布的[数据泄露事件暴露了近一半美国人口的社会安全号码和其他个人信息，这是该公司未能及时为 Apache Struts 安装安全补丁的结果。](https://www.nytimes.com/2017/09/07/business/equifax-cyberattack.html)

美国三大信用监测机构之一的 Equifax 公司[于 9 月 7 日宣布了这次泄密事件](https://www.equifaxsecurity2017.com/)。当时，该公司表示，攻击者在 5 月中旬通过一个“网站应用程序漏洞”闯入，直到 7 月 29 日才被发现。

周三，该公司在其网站上发布了一个更新，澄清“该漏洞是阿帕奇 Struts [CVE-2017-5638](https://nvd.nist.gov/vuln/detail/CVE-2017-5638) ”这是 Apache Struts 组件中的一个远程代码执行漏洞，名为 Jakarta Multipart parser，[在 3 月 7 日发布的 Struts 2.3.32 和 Struts 2.5.10.1 中修补了这个漏洞。](https://cwiki.apache.org/confluence/display/WW/S2-045)

> 从 3 月 7 日到 5 月中旬，两个多月来未能部署一个关键的安全补丁，反映了 Equifax 的安全实践存在严重问题。

Apache Struts 是一个基于 Java 的 web 应用程序开发框架，在企业环境中非常流行。

在最初的违规声明发布后的几天里，有未经证实的说法称被利用的漏洞存在于 Apache Struts 中。这些指控可以追溯到金融服务公司 Baird 的股票研究部门发布的一份报告。

Baird 分析师在报告中表示，“我们的理解是，EFX [Equifax]保留的主要通过消费者互动生成的数据是通过 Apache Struts 漏洞(即，据信没有被攻破的核心数据库)被攻破的，”但没有说明这些信息的来源。

这造成了一点混乱，因为 Apache Struts 开发人员[在 Equifax 违规声明发布前几天刚刚发布了另一个关键远程代码执行漏洞的补丁](https://thenewstack.io/critical-vulnerability-apache-struts-puts-thousands-web-applications-risk/)。该漏洞位于该框架的 REST 插件中，并被识别为 [CVE-2017-9805](https://cwiki.apache.org/confluence/display/WW/S2-052) 。

Apache Struts 项目管理委员会(PMC)周六发布了一份公开声明，以解决声称 Struts 漏洞——可能是 CVE-2017-9805——可能导致 Equifax 违规的报告。委员会借此机会解释了该项目的开发实践和安全响应程序。

继周三 Equifax 确认攻击者实际上利用了一个旧漏洞后，阿帕奇软件基金会[发布了一份新声明](https://blogs.apache.org/foundation/entry/media-alert-the-apache-software)，其中写道:“该漏洞于 2017 年 3 月 7 日修补，当天就宣布了。总之，Equifax 数据受损是由于他们未能及时安装所提供的安全更新。”

从 3 月 7 日到 5 月中旬，两个多月来未能部署一个关键的安全补丁，反映了 Equifax 的安全实践存在严重问题。更糟糕的是，CVE-2017-5638 [的补丁在 3 月份被广泛攻击](http://blog.talosintelligence.com/2017/03/apache-0-day-exploited.html)，这些攻击利用该漏洞在服务器上安装勒索软件和其他恶意程序。媒体报道了这些攻击，安全公司发出了警报。

为了保证 web 应用程序和服务器的安全，Apache Struts PMC 为 Struts 用户提供了以下建议:

1.  了解你的软件产品中使用了哪些支持框架和库，以及哪些版本。跟踪影响这些产品和版本的安全公告。
2.  *建立一个流程，以便在支持框架或库因安全原因需要更新时，快速推出软件产品的安全补丁版本。最好是考虑几个小时或几天，而不是几周或几个月。我们意识到的大多数违规行为都是由于未能更新软件组件造成的，而这些组件在数月甚至数年内都是易受攻击的。*
3.  任何复杂的软件都有缺陷。不要在假设支持软件产品完美无缺的基础上构建您的安全策略，尤其是在安全漏洞方面。
4.  *建立安全层。在面向公众的表示层(如 Apache Struts 框架)后面有单独的安全层是一个很好的软件工程实践。对表示层的入侵不应该授权访问重要的甚至所有的后端信息资源。*
5.  *监控对公共网络资源的异常访问模式。现在有很多开源和商业产品可以检测这种模式并发出警报。我们建议将此类监控作为业务关键型网络服务的良好操作实践。*

同样值得注意的是，本月早些时候修补的 REST 插件漏洞已经被利用，安全研究人员已经观察到利用它的攻击。如果您现在还没有更新您的 Struts 部署，请尽快更新。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>