# LogDNA 旨在通过机器学习使日志记录更具预测性

> 原文：<https://thenewstack.io/logdna-aims-make-logging-predictive-machine-learning/>

LogDNA 是已经拥挤的基础设施日志管理系统市场的最新参与者之一，旨在通过应用机器学习来检测 IT 问题，帮助公司采取主动的服务器日志记录方法。

该公司的创始人、连续创业家[克里斯·阮](https://twitter.com/mrchrisnguyen)和[刘辉](https://www.linkedin.com/in/leeliu)，是 2015 年冬季 Y Combinator 课程的一部分，但发现他们的项目电子商务公司 PushMarket 没有获得他们预期的牵引力。

为了从他们已经完成的工作中尽可能地挽回损失，他们决定转向并专注于他们为项目定制的日志管理技术。

Nguyen 说:“在与潜在客户交谈后，我们意识到我们已经建立了一个比原始产品更强大的内部工具。”

他们承认他们不会拥有他们想要建造的一切，首先，他们位于旧金山的公司在 2 月份发布了其最初的产品，并获得了初创客户的支持，包括 t 恤网站 [Teespring](https://teespring.com/) ，测试公司[雨林 QA](https://www.rainforestqa.com/) ，订阅市场 [Cratejoy](https://www.cratejoy.com/) ，以及建筑设备租赁网站[Equipmentshare.com](https://equipmentshare.com/)。

“我们真正建立的是这种预测智能层，”Nguyen 说。“今天的伐木都是被动的。人们与他们的日志交互的原因是因为有些东西坏了，我们知道在某个时间点，我们可以应用机器学习来说，'抬头！这是将要发生的事情，我们可以从你的日志数据中看到。"

## **注入现金**

两位联合创始人之前创建了基于位置的招聘网站 JobLoft、约会网站 cupid.com 和社交商务网站 TeamSave，后者是易贝在加拿大和英国的分类广告合作伙伴。他们的新公司最近从 Initialized Capital 和 Skype 联合创始人贾恩·塔林那里筹集了 130 万美元。

两人在 Elasticsearch 的基础上构建了他们的算法，以加快搜索速度。它运行在 AWS EC2 上。他们把他们的用户界面吹捧为“日志记录的苹果”

Nguyen 说:“我们的客户告诉我们，他们想要比竞争对手更快的搜索速度、更长的搜索保留时间、更好的界面/体验和更具成本效益的解决方案。“DevOps 工程师希望有一个解决方案，让他们能够在基础架构问题出现之前就发现问题，或者更快地解决问题，例如主动发现 DDOS 攻击、服务器停机和代码问题背后的身份根本原因。这是我们正在建设的东西。”

最初的产品侧重于聚合、搜索、跟踪和警报。根据刘的说法，预测智能层将在第四季度进行测试，并将包括一个图形功能来可视化问题。

LogDNA 允许用户从所有主机和应用程序中聚合、搜索和过滤。它提供了对常见日志格式字段的自动解析，比如 weblogs、Mongo、Postgres 和 JSON。

它提供了一个使用 web 界面或命令行界面(CLI)的直播尾巴。

“我们通过基于日志数据确定文件类型来处理解析，”刘说。“我们可以确定它是 Nginx、Apache、Ruby、Mongo、Redis 等。动态地。一旦我们知道了文件类型，我们就可以解析出不同的字段，这样我们就可以聚合和/或可视化数据。正如我们所说的，我们正在构建我们的可视化工具。”

他们发现自己过去一直在努力降低存储成本，因此希望在存储大量数据时给予客户更多的灵活性。LogDNA 有一个每月 50gb 的免费层，最高为每月 999 美元的每月 1tb 计划。

该公司在 2 月份的一篇黑客新闻帖子中受到了一些批评，该帖子是关于对传输中的数据进行加密，而不是对静态数据进行加密。刘说那是后来加上去的。

该公司计划在未来开源其技术，作为添加语言库和其他功能的一种手段。

Nguyen 承认这是一个非常拥挤的市场，他们没有所有预想的功能，但他们决定推出一个产品并建立在它的基础上。

“我们正在建立更智能的伐木方式，但这是一项长期的工作，”他说。“市场上有像 [Splunk](http://www.splunk.com) 这样专注于企业的公司，而我们专注于中小企业的利基市场。如果你看看像 [PaperTrail](https://techcrunch.com/2015/04/28/solarwinds-acquires-log-management-service-papertrail-for-41m-in-cash/) 和 [LogEntries](http://www.irishtimes.com/business/technology/ucd-spin-out-firm-logentries-acquired-by-rapid7-for-68m-1.2391425) 这样的竞争对手，他们已经被收购了，所以我不知道他们会做多少功能增强。我们希望成为这个领域下一代的下一个参与者，”他说。

虽然该公司计划增加功能，如支持 Docker，但无数竞争对手也在实现同样的目标，包括收购 Logentries 的 [Rapid7](https://www.rapid7.com/) 。【Elastic.co】、 [Graylog、](https://www.graylog.org/) Loggly、Papertrail 和 [Sumo Logic](https://www.sumologic.com/?p=8784) 都是 [Docker 日志伙伴](https://thenewstack.io/docker-partners-fill-logging-capabilities/)。

## **脱颖而出**

根据 Fixate IO 分析师 Chris Riley 的说法，机器学习是一个神奇的术语，几乎所有新兴的日志分析工具都试图将它戴上帽子。

“我会说 Sumo Logic、Splunk、log entries[和其他]都把它作为一个功能，而 Anodot 和 MoogSoft 正在把它作为他们所做的一切的关键元素，”他说。

然而，到目前为止，大多数机器学习能力仅仅是智能统计，他说。

他说，到目前为止，该公司的重点一直是基本功能——更多的存储，更好的搜索——这不会是真正的竞争优势。

“他们将面临的问题是，他们正在与开源工具竞争，如 [ELK stack](https://thenewstack.io/comparison-cloud-based-elasticsearch-elk-solutions/) 和其他允许您进行日志分析的工具。“麋鹿栈已经变得非常受欢迎——而且都是免费的，”他说。"漂亮的用户界面并不能赢得开发者的青睐."

虽然所有供应商都希望被视为一揽子日志记录解决方案，但这意味着成为“开发运维中心”或单一平台。

“但我认为这与现实相去甚远，”他说。“我还没有遇到过只使用一种日志记录解决方案的公司。而且正因为大多数球队的结构，永远都是这样。”

这个拥挤的领域让新玩家真的很难脱颖而出。

“如果我是这个领域的新供应商，我的方法会非常具体，非常适合，”赖利说。“也许他们可以比其他任何人更好地解决特定的开发堆栈，比如 Ruby 应用程序，或者，恕我直言，容器，尽管已经有很多了。它可能是具有特殊需求的特定垂直行业，例如金融服务。在金融服务中，将应用程序操作与交易相关联是一个大问题。它必须非常有针对性，非常集中。否则，他们只是在参与更好的伐木噪音。”

特征图片:[希拉·米格斯](https://www.flickr.com/photos/sheila/)的[年轮](https://www.flickr.com/photos/sheila/477734614/in/photolist-JdvRG-6KMedA-dqZ9Ci-dqZa9P-dqZiN5-3cwCEy-9dDPf-cCkQbd-zvrk9-bjnQyM-bjnQQ8-agJgDw-dqZ9qe-nrF2YR-7XFQnC-fNgMJm-51jusS-b9cgtr-9i7rec-6xUSQN-qmbUzh-bFaZMp-FPTQZC-njx6fU-516Pax-bumzeC-io3P88-rFAsRz-BnGAn-pn9EMg-bgenzV-mniV3C-aAGZqY-6Tia8Q-bK5wwp-q2kSkw-7xDU9S-mp3uxH-f2qV76-pCYRsM-34Ydj3-bvorzf-bqcnSv-dE8Ywm-bK4SCx-aVyABx-8MmSeX-4sPi8S-mnK4bT-9huvgh)，授权**下的[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)T7。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>