# 法尔科项目:Sysdig 为安全监控而重新设计

> 原文：<https://thenewstack.io/project-falco-sysdig-reengineered-security-monitoring/>

穿越 [snort](https://www.snort.org/) 、 [ossec](http://ossec.github.io/) 和 [strace](https://linux.die.net/man/1/strace) 会发生什么？您将获得一个非常类似 Project Falco 的工具，这是一个用于检测容器化应用程序中异常活动的开源行为活动监视器。

Falco 基于 [Sysdig 项目](https://github.com/draios/sysdig)，一个开源工具(现在是[商业服务](https://sysdig.com/product/)，通过跟踪内核系统调用来监控[容器性能](https://www.safaribooksonline.com/library/view/oscon-2016-video/9781491965153/video247424.html)。Falco 没有跟踪系统调用以提高性能，而是使用相同的工具进行[异常和入侵检测](https://sysdig.com/blog/fishing-for-hackers/)。

Sysdig [在五月份启动了](https://sysdig.com/blog/sysdig-falco/)项目 Falco，到目前为止已经在 GitHub 上聚集了大约 468 位明星。

Sysdig 营销副总裁阿普勒瓦·达夫(Apurva Davé)说:“我们已经采用了内核工具的相同核心，并将其打包，使人们更容易运行和检测可疑行为。

Falco 是为“运行自己的系统和构建自己的 ops 的个人代码级人员”而构建的，但也“为希望从 Falco 获取输出并将其与其他安全和性能信息相关联的大型企业而扩展，”负责监督 Falco 的 Sysdig 软件工程师马克·斯泰姆进一步解释道。

## 行为活动监控

Sysdig 项目是几年前由 Wireshark 的联合创始人之一洛里斯·德吉奥安尼创建的，Wireshark 是一个非常受欢迎的工具，可以让管理员在数据包级别上看到网络上发生的事情。

Sysdig 被设计用来密切监视容器动作的细节。任何时候容器需要访问系统资源，比如 CPU、内存、文件访问或网络，它都会向下调用主机内核。因此，Sysdig 提供了一种在每个主机的操作系统内核中添加模块的方法，允许用户看到在该主机上执行的每个系统调用，无论是来自操作系统、容器还是容器化应用程序的调用。这样，代理可以看到容器试图做的一切。

Davé断言，当应用于安全时，这种类型的监控 Sysdig 称为“行为活动监控”。

这一想法与传统的企业安全方法不同，传统的企业安全方法是通过密码和其他身份验证机制阻止不必要的端口，从而在防火墙上阻止恶意活动。法尔科的方法是留意任何可疑的行为。

使用 Sysdig，低级别的系统调用集合被聚合成可以触发“警报”的高级“事件”库 Falco 还提供了一个规则系统，可以使用 Sysdig 生成的数据定义恶意行为，并在检测到此类行为时提醒用户。

例如，在容器中使用 Bash shell 是值得警惕的。“如果有人在容器中运行 shell，那么这可能非常可疑，因为这意味着有人在你的微服务中做通用的事情，”Stemm 说。一个在 YAML 写的警告，可能看起来像这样的:

```
rule:  shell_in_container
  desc:  a  shell running in  a  container
  condition:  container.id  !=  host and proc.name  =  bash
  output:  “Shell running in container  (user=%user.name container_id=%container.id container_name=%container.name shell=%proc.name parent=%proc.pname)”
  priority:  WARNING

```

根据[GitHub 页面](https://github.com/draios/falco)显示，该软件涵盖其他场景，如:

*   容器正在特权模式下运行，或者正在从主机装载敏感路径，如`/proc`。
*   服务器进程产生了一个意外类型的子进程。
*   意外读取敏感文件(如`/etc/shadow`)。
*   一个非设备文件被写入`/dev.`
*   一个标准的系统二进制文件(如`ls`)建立一个出站网络连接。

到目前为止，Falco 有大约 40 个用于检测安全漏洞的内置规则，它们被编码在 [YAML](http://yaml.org/) 中，并存储在 GitHub 上。用户也可以编写自己的规则。

管理员定义警报机制应该如何发送通知，以及警报应该附带哪些消息。警报是纯文本模板和可由软件填写的字段的组合，以描述特定事件。Falco 还可以与[容器编排工具](https://sysdig.com/blog/announcing-falco-0-4-0/)通信，如 [Kubernetes](/category/kubernetes/) 和 Marathon/Mesos，允许 Falco 识别编排级别的概念，如“pod”和“deployment”，因此它们可以在规则和输出字符串中使用。

管理员在另一个配置文件中指定输出通道，如电子邮件、日志或另一个程序。警报也可以发送给安全信息和事件管理系统。“在那里，我们成为这些系统之一的输入，将我们看到的事件与任何其他潜在的问题交叉关联起来，”Stemm 说。

Davé说，虽然市场上并不缺乏入侵检测工具，但 Falco 在保护集装箱化应用程序和基于微服务的应用程序的新兴市场中可能具有优势。Davé指出，大多数入侵检测设备运行在用户空间，很少直接链接到内核。

你不必安装 Sysdig 就可以使用 Falco，而且，目前，该公司还没有将 Falco 商业化。该公司的第一步是将其打造为公司的商业 DevOps 监控服务， [Sysdig Cloud](https://sysdig.com/product/) 。

Davé说:“Over strategy 就是利用内核工具的这个插入点，在您的环境中做比监控产品更多的事情。

[英特尔的 Matthew Brender 讨论遥测技术和英特尔 Snap 工具](https://thenewstack.simplecast.com/episodes/intels-matthew-brender-discusses-telemetry-and-the-intel-snap-tool)

英特尔赞助了这个故事。Sysdig 是新堆栈的发起人之一。

特征图像:NGC 6357 弥漫星云，来自[美国国家航空航天局当日天文照片](https://apod.nasa.gov/apod/ap161226.html)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>