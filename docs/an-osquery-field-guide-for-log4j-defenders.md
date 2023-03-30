# Log4J 防御者的 Osquery 现场指南

> 原文：<https://thenewstack.io/an-osquery-field-guide-for-log4j-defenders/>

[](https://www.linkedin.com/in/seshupasam/)

 [塞舒·帕萨姆

塞舒·帕萨姆是 Uptycs 的首席软件架构师。](https://www.linkedin.com/in/seshupasam/) [](https://www.linkedin.com/in/seshupasam/)

Log4Shell 漏洞已经迅速成为过去十年中最严重的漏洞之一。自公开披露以来，维权者在事件响应和补救上投入了无数时间。我们在 [Uptycs](https://www.uptycs.com/) 最近发表了 [一篇博文](https://www.uptycs.com/blog/remediating-log4j-using-osquery-a-quick-reference-guide-of-tables-and-actions) ，介绍了一些有用的 osquery 表，以帮助调查、补救和/或利用检测周期应对 Log4j 漏洞。

在本帖中，我们分享了一组在开源版本的 [osquery](https://osquery.io/) 操作系统查询工具上运行的查询，以及其他有用的验证和修复技术。

## **日志 4 外壳简介**

当前的漏洞特别危险，因为受影响的应用程序不需要面向互联网；只要用户提供的输入到达易受攻击的应用程序并被日志库处理，该应用程序就易受攻击。这意味着作为 HTTP 头或 HTTP 正文的一部分发送的精心编制的字符串可能允许攻击者远程执行代码(RCE)。如果攻击者成功危及应用程序的安全，RCE 可以让攻击者拥有完全的命令和控制权限。

那么，哪些库容易受到攻击，哪个版本有补丁呢？

易受攻击:

*   log4j (1.x)是一个遗留库。即使它有自己的 [漏洞](https://snyk.io/vuln/maven:log4j:log4j@1.2.17) ，都没有这么严重。
*   log4j-core jar 文件来自 [log4j2](https://logging.apache.org/log4j/2.x/) 库中有易受攻击的类。
*   log4j-core-2.0-beta9.jar 或更高版本易受攻击。

最新版本:

*   log4j-core-2.12.4.jar(适用于 JDK7)和 log4j-core-2.17.1.jar(适用于 JDK8 和更高版本)

## 我应该收集哪些库存和信息？

在了解哪些资产受到了潜在影响时，我们需要快速收集信息和环境清单。我们建议调查开发、试运行、测试和生产机器以及云虚拟机、容器和无服务器应用程序。为了进一步扩展 osquery 的功能，维护者还可以使用 [cloudquery](https://www.uptycs.com/blog/use-cloudquery-and-osquery-to-simplify-your-cloud-monitoring) 和 [kubequery](https://www.uptycs.com/blog/kubequery-brings-the-power-of-osquery-to-kubernetes-clusters) ，这是 Uptycs 维护的两个开源工具，用于从云基础设施和 Kubernetes 集群获取相关数据。

应该考虑的其他资产是内部注册/回购、注册的容器、带有构建工件的 blob 存储和员工机器。

## **应该找什么？**

在前面提到的例子中，我们建议寻找关于 Java 供应商软件、易受攻击的 Java 应用程序以及与 log4j 版本 1 和 2 相关的所有工件的信息。

### 运行在主机上或主机上的容器中的 Java 进程

```
SELECT *
FROM processes
WHERE name LIKE  'java%'

```

### 受影响的 JDK/JRE 版本

```
SELECT *
FROM deb_packages
WHERE name LIKE  '%jdk%'
       OR name LIKE  '%jre%';

SELECT *
FROM rpm_packages
WHERE name LIKE  '%jdk%'
       OR name LIKE  '%jre%';

```

### formatMsgNoLookups=true

请注意，更改此设置并不能完全修复漏洞。Log4j-core 应该升级到 2.17.1。

**具有 JVM 属性的进程-dlog4j 2 . formatmsgnolookups = true**

```
SELECT *
FROM processes
WHERE cmdline LIKE  '%-Dlog4j2.formatMsgNoLookups=%'

```

**环境变量为 LOG4J _ FORMAT _ MSG _ NO _ LOOKUPS = true 的进程**

```
SELECT *
FROM process_envs
WHERE key  =  'LOG4J_FORMAT_MSG_NO_LOOKUPS'

```

**获取设置了 LOG4J_FORMAT_MSG_NO_LOOKUPS 环境变量的所有 docker 容器**

```
SELECT *
FROM docker_containers
WHERE env_variables like  '%LOG4J_FORMAT_MSG_NO_LOOKUPS%'

```

### 寻找易受攻击的 log4j2 核心

**命令行中存在易受攻击的 log4j2 内核的进程**

```
SELECT *
FROM processes
WHERE cmdline LIKE  '%log4j-core%'
       AND cmdline NOT LIKE  '%log4j-core-2.17.1%'

```

**Java 进程打开的具有易受攻击的 log4j2-core 的进程**

```
SELECT *
FROM process_open_files  o
JOIN processes  p
USING  (pid)
WHERE <a  href="http://p.name/"><span class="s1">p.name</span></a>  LIKE  'java%'
        AND  o.path LIKE  '%log4j-core%'
       AND  o.path NOT LIKE  '%log4j-core-2.17.1%'

```

### 在所有打开的 Jar/War/Ear 文件中查找 JndiLookup。

请注意，根据打开的文件数量，这可能是一个开销很大的查询。此外，这可以检查 jar/超级 jar/阴影 jar，但在检查 log4j-core-2.17.1 jar 时不能正常工作。

```
SELECT *
FROM yara
WHERE count  &gt;  0
  AND sigrule  =  'rule class { strings: $cls = "JndiLookup" condition: $cls }'
  AND path IN  (SELECT path
                FROM process_open_files
                WHERE path LIKE  '%._ar')
   AND path NOT LIKE  '%log4j-core-2.17.1%'

```

### 更多事件表

您可以使用以下事件表来帮助识别与 Java 进程 post exploit 相关的活动。

`--    process_file_events`

`--    process_events`

`--    socket_events`

## 如何验证我的修复？

### 正在验证 JndiLookup.class 是否已删除

您需要确保这个类不再被您的应用程序加载。

**对于每个 Java 进程，如果****jps****可用:**

```
for  i  in  `jps  |  grep  -v  Jps  |  awk  ‘{print  $1}’`;  do jcmd  $i  GC.class_histogram  |  grep  -q  JndiLookup  &amp;&amp;  {  echo  “PID  $i  MIGHT be vulnerable”;  };  done

```

### 验证版本升级

您可能还想验证您是否已正确升级到修复版本。为此，您可以:

*   获取进程打开的所有 jar/war/war/jmod 文件的清单。
*   对于进程打开的每个文件，检查它是否是或包含易受攻击的 log4j2-core jar。
*   持续进行验证，以避免由于自动伸缩、旧的构建工件等原因而部署易受攻击的应用程序。

在收集你的资产清单后，还有很多事情要做。其他安全团队应该考虑实现一个 WAF 来阻止用户输入中的 jndi 或 ctx 字符串。EDR/XDR 团队应该监视由 Java 进程产生的进程，并监视出口流量。

Uptycs 威胁研究团队 [最近发布了一些关于 log4j 的后果的研究](https://www.uptycs.com/blog/log4j-vulnerability-aftermath) ，并继续狂热地工作以提供对漏洞利用的进一步观察。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>