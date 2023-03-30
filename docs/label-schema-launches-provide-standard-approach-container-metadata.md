# 标签模式:一种新的容器元数据标准方法

> 原文：<https://thenewstack.io/label-schema-launches-provide-standard-approach-container-metadata/>

[](http://www.microscaling.com)

 [利兹·赖斯

利兹·赖斯是 Microscaling Systems 的首席执行官，也是 MicroBadger 的开发者之一。她在网络协议和分布式系统以及 VOD、音乐和 VoIP 等数字技术领域拥有丰富的软件开发、团队和产品管理经验。当不创业和写代码的时候，Liz 喜欢在天气比她的家乡伦敦更好的地方骑自行车。](http://www.microscaling.com) [](http://www.microscaling.com)

现在有了一个新的容器元数据社区标准，参与者来自 Puppet、Mesosphere、Microscaling Systems、Container Solutions、Weave、Cloud66、Tigera 等。标签模式的[候选版本将于周五在伦敦的](http://label-schema.org/rc1/)[集装箱营地](https://container.camp/)发布。

该计划的灵感来自于 Puppet 的 Gareth Rushgrove，他指出了关于容器的额外元数据的用处。Docker 已经提供了向任何容器图像添加任意键-值对的标签指令，而 Label Schema 旨在通过在社区中就一些公共数据达成一致的标准来构建这个指令。

如果工具匠们就构建参考、联系信息和使用说明等公共数据的标签达成一致，这将避免用户在想要使用不同工具的组合时不得不重复数据。

该规范虽然还处于草案阶段，但已经有一些人接受了。在 Microscaling Systems，我们已经通过使用标签模式格式标签的 MicroBadger 工具检查了 125 幅公共图像，这里有几个例子。

你能用标签做什么？嗯，你可以直接做的一件事就是过滤你的 Docker 图片。下面是一个查询特定供应商提供的所有图像的简单示例:

```
     docker images  --filter  "label=org.label-schema.vendor=&lt;vendorname&gt;"

```

当多个工具支持相同的标签时，事情变得有趣多了。例如，构建工具可以自动添加版本标签，然后可视化和日志记录工具可以自动将该版本信息包含在它们的输出中——所有这些工具都不需要知道其他工具的存在。

[规范是一个候选版本](http://label-schema.org/rc1/)，代表所有的维护者，我们渴望得到评论和贡献——我们甚至更渴望听到使用通用标准的工具。你可以在 GitHub 的[标签模式上提出问题或请求，我们也有一个](https://github.com/label-schema/label-schema.org)[邮件列表](https://groups.google.com/forum/#!forum/label-schema)欢迎你加入。

Docker 和 [Mesosphere](https://d2iq.com/) 是新堆栈的赞助商。

通过像素的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>