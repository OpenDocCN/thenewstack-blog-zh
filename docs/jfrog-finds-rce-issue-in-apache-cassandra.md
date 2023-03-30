# JFrog 在 Apache Cassandra 中找到 RCE 问题

> 原文：<https://thenewstack.io/jfrog-finds-rce-issue-in-apache-cassandra/>

当涉及到安全的时候总是有问题。这一次，JFrog 的安全研究团队在流行的开源 NoSQL 数据库 [Apache Cassandra](https://cassandra.apache.org/) 中发现了一个远程代码执行(RCE)问题。哦，乔伊，当然有了这个 RCE，你可以阻止卡珊德拉。由于网飞、Twitter、Reddit 和数百家其他公司每天每时每刻都依赖 Cassandra 运行，这不是好消息。

好消息是，违约的卡珊德拉不会受到这种攻击。坏消息是，使用 cassandra.yaml 配置文件中的这些完全合理的 Cassandra 选项:

`enable_user_defined_functions: true`

`enable_scripted_user_defined_functions: true`

`enable_user_defined_functions_threads: false`

你的系统容易受到攻击。

## 有多糟糕？

那么，卡珊德拉 [CVE-2021-44521](https://nvd.nist.gov/vuln/detail/CVE-2021-44521) 漏洞有多糟糕呢？试试普通漏洞评分系统(CVSS) 8.4 级的不好。对于那些在家里玩的人来说，这是高的，这是真的很差的另一种说法。打开这个安全漏洞太容易了。

它通过在 Java 运行时环境(JRE)中滥用 Cassandra 的 [Nashorn](https://docs.oracle.com/javase/10/nashorn/introduction.htm#JSNUG136) 引擎来工作，JRE 是一个运行在 Java 虚拟机(JVM)之上的 JavaScript 引擎。通常，你不能通过攻击 Nashorn 来做任何事情，因为它在沙箱内工作。然而，成功的攻击可以将黑客从沙箱中解救出来，让他们运行 RCE。

其中最令人讨厌的是让用户定义的函数(UDF)运行超过分配的时间。然后，整个卡珊德拉守护进程将关闭，不仅仅是 UDF 的线程。然后，您可以通过创建一个简单的 while(true)循环来永久循环的函数，从而破坏整个数据库。

诚然，要做到这一点，攻击者首先需要有足够的权限来创建 UDF，以便能够利用这一点。但是，在上述设置下，所有用户——我重复一遍，所有用户——都可以创建和执行任意的 UDF。哦，我有没有提到所有用户意味着匿名登录也是默认启用的？所以，是的，即使是匿名用户也可能被用来进行成功的攻击。这是为什么 CVSS 评分如此之高的原因。

## 你能做什么？

那么，你能做些什么呢？还好，很多。

首先，通过将 enable_user_defined_functions 设置为 false(这是默认值)来完全禁用 UDF，可以在 UDF 没有被频繁使用时缓解这个问题。如果必须有 UDF，可以将 enable _ user _ defined _ functions _ threads 设置为 true。这也是默认值。最后，您可以——也应该——通过删除以下权限来为不受信任的用户删除创建、更改和执行函数的权限:ALL FUNCTION、KEYSPACE 中的所有函数以及用于创建、更改和执行查询的函数。我强烈建议你做最后一个。允许不受信任的用户做任何需要信任的事情，本质上是一个愚蠢的想法。

当然，您应该将您的 Cassandra 软件升级到以下版本之一，它解决了 CVE-2021-44521:

3.0.x 用户应该升级到 3.0.26

3.11.x 用户应该升级到 3.11.12

4.0.x 用户应该升级到 4.0.2

做完这些，你就可以放松，继续工作了。但是，首先，修补你的卡珊德拉软件。这里发生灾难的可能性太大了，不能把修复工作推迟到明天。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>