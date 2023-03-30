# Target 首席执行官被解雇后，公司更加关注新兴数据项目的安全性

> 原文：<https://thenewstack.io/taget-ceo-dismissal-puts-more-attention-on-security-of-emerging-data-projects/>

在影响 7000 万消费者的历史性数据泄露事件发生后，Target Corporation [宣布](http://online.wsj.com/news/articles/SB10001424052702303417104579543461881354816?mg=reno64-wsj&url=http%3A%2F%2Fonline.wsj.com%2Farticle%2FSB10001424052702303417104579543461881354816.html)解雇在该公司工作了 35 年的首席执行官 Gregg Steinhafel。你可以打赌，任何 CEO 如果没有注意到数据安全的重要性，现在肯定已经注意到了。企业——尤其是大型上市公司——将更加关注公司管理下的数据安全性。

由于大数据系统在将来自许多不同数据源的数据整合到一个位置进行存储或分析方面的作用，大数据系统对攻击者来说是一个特别引人注目的目标，因此，[会给部署它们的企业带来更大的风险](https://thenewstack.io/be-careful-what-you-ask-for-webmobile-edition/)。

尽管潜在的攻击增加，但企业级安全长期以来一直是许多大数据项目的后顾之忧，包括房间里的大象 Hadoop。Hadoop 的文件系统 HDFS 在 2008 年春天引入了一个基本的安全模型。然而，根据雅虎托管的 Hadoop 教程，HDFS 最初的许可系统从未打算提供强大的安全性:

> “从 Hadoop 0.16.1 开始，HDFS 包含了一个基本的文件权限系统。这个许可系统是基于 POSIX 模型的，但是没有为 HDFS 文件提供很强的安全性…

HDFS 权限系统旨在防止共享群集访问权限的一组用户意外损坏数据或随意滥用信息。它不是一个强大的安全模型，不能保证拒绝未授权方的访问。"

幸运的是，大数据项目开始引起人们对安全领域的更多关注。最近发布的 Hadoop 2.4.0 版本[增加了 ACL](https://issues.apache.org/jira/browse/HDFS-4685)，允许用户为指定的用户或组指定细粒度的文件权限。

Sqrrl 的 Joe Travaglini 最近对以安全为重点的产品发布进行了一项调查，调查还强调了 Hortonworks 的 HDP 2.1 中 Apache Knox 对外围安全的支持，Cloudera 在 Cloudera Search 1.2.0 中包含了索引级安全，以及 MongoDB 2.6 中的“一系列安全改进”，包括字段级编辑。

随着企业越来越关注数据安全和隐私，企业 IT 将要求他们使用的大数据产品和项目具备更多以安全为中心的功能。预计这一领域的安全相关产品发布速度将会加快。

图片来源[通过](https://www.flickr.com/photos/christinaheltonsshops/3927811730/in/photolist-6Z64zU-6Z1XWB-6Z5ZAh-9DWVdA-5YVozb-7H1n8M-aVcPc2-aVcNCT-acTso-aCQtmQ-e96NFG-6xPoPa-cofFhE-eNvzps-9CbbaL)在 Flickr 上创建共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>