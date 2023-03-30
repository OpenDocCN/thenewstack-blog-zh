# 本周编程:晚安，亲爱的 Python 2.x

> 原文：<https://thenewstack.io/this-week-in-programming-goodnight-sweet-python-2-x/>

终于到了告别 Python 2.7 的时候了，Python 2.7 将于 2020 年 1 月 1 日正式死亡。嗯，几乎完全正式死亡。

对于那些一直在关注的人来说， [Python 时钟](https://pythonclock.org/)在工作了近五年后，已经全线倒数到零，它是在 Python 2.7 采用新的生命终结期限时创建的。最初，该语言将于 2015 年到期，但[获得了延期](https://hg.python.org/peps/rev/76d43e52d978)“以澄清 Python 2.7 的状态，并减轻那些还不能迁移到 Python 3 的用户的担忧。”点开那封邮件，你会发现这一天已经过去了很久很久。

现在，回到官方和非官方死亡的部分。Python 2.7 已经正式死亡，但是我们还没有看到它的终结。根据来自 [Python 软件基金会](https://www.python.org/psf/)的[声明](https://www.python.org/psf/press-release/pr20191220/)，最后一个主要版本 2.7 将于 2020 年 4 月发布(与 [PyCon](https://pycon.org/) 同时发布)，然后 Python 2.x 的所有开发都将停止。该基金会进一步解释了五年的延迟，写道“Python 3 中更严格的文本模型正在强制解决参考解释器和标准库以及迁移的库和应用程序中非平凡的 Unicode 处理问题”，并且延长是为了给人们足够的时间进行迁移。所以，是的，从进一步开发的角度来看，Python 2.x 已经死了，尽管我们仍然会看到一个最终版本，对于那些使用像 Red Hat Enterprise Linux 这样的系统的人来说，在地毯被正式从你脚下拉出来之前，你还有[多一点时间。](https://access.redhat.com/solutions/4455511)

但是，移植到 Python 3.x 的进展如何呢？这取决于你问的是谁。

JetBrains 已经进行了几年的 Python 开发者调查，显示 Python 2.7 的使用持续下降，2017 年仍有 25%的人坚持使用 2.7 [，2018 年](https://www.jetbrains.com/research/python-developers-survey-2017/#python-3-adoption)有 16%的人继续使用[，2019 年](https://www.jetbrains.com/research/python-developers-survey-2018/#python-3-adoption)只有 13%的人继续使用[。但也许这些数字被接受调查的观众扭曲了一点，因为两个月前 StackOverflow 的一篇博客文章采用了不同的方法，得出了完全不同的结果。相比之下，StackOverflow 问](https://www.jetbrains.com/lp/devecosystem-2019/python/)[为什么迁移到 Python 3 需要这么长时间](https://stackoverflow.blog/2019/11/14/why-is-the-migration-to-python-3-taking-so-long/)，而不是问人们他们正在使用什么版本，他们看一些关于 Python 包库 [PyPI](https://pypi.org/) 的下载数据。这些数字也显示了下降，但讲述了一个不同的故事:

“尽管 Python 3 已经成为社区的主导版本至少一年了，但 PyPI 的最新单个包下载统计显示，2019 年 9 月的所有包中至少有 40%是 2.7 下载。诚然，这比年初的 60%有所下降，但考虑到离停产只有几个月的时间，这一数字仍然很大。”

如果你仍然没有实现飞跃，不管你是 13%(还是 40%)的 Python 用户，你可能想要查看一下[官方移植指南](https://docs.python.org/3/howto/pyporting.html)——许多项目已经[承诺](https://python3statement.org/)放弃 Python 2.x 支持。我，我只是希望生命的正式终结可能意味着我可以再给我的 Python 教程[一次机会](/this-week-in-programming-like-riding-a-bicycle/)，也许这次能通过设置。

现在，关于编程世界的新闻，这里有两个周中假期，几乎没有什么新闻。因此，相反，我们带给你一点点年度总结和来年的预测。不客气首先，这里是谷歌 2019 年的开发者综述:

[https://www.youtube.com/embed/DQGSZTxLVrI?feature=oembed](https://www.youtube.com/embed/DQGSZTxLVrI?feature=oembed)

视频

## 本周的节目中

*   **2019 年最佳应用编程接口:**接下来是 [ProgrammableWeb 的](https://www.programmableweb.com/)年度年终系列，查看其“2019 年点击最多、分享最多和谈论最多的应用编程接口”，涵盖广泛的类别，包括[广告](https://www.programmableweb.com/category/advertising)、[客户关系管理](https://www.programmableweb.com/category/customer-relationship-management)、[内容](https://www.programmableweb.com/category/content)、[印刷](https://www.programmableweb.com/category/printing)、[产品](https://www.programmableweb.com/category/products)、[目录](https://www.programmableweb.com/category/catalogs)、 [](https://www.programmableweb.com/category/catalogs) [发货](https://www.programmableweb.com/category/shipping)，[条形码](https://www.programmableweb.com/category/barcodes)，[评分](https://www.programmableweb.com/category/ratings)，[定制](https://www.programmableweb.com/category/customization)，[调查](https://www.programmableweb.com/category/surveys)， [SEO](https://www.programmableweb.com/category/seo) ，[推文](https://www.programmableweb.com/category/tweets)，以及[订婚](https://www.programmableweb.com/category/engagement)。 这里没有太多要解释的-每篇文章都根据这些指标看了每个类别的顶级 API，并对 2019 年 API 类中最好和最聪明的 API 进行了相当全面的审视。如果这对你来说还不够，该网站还提供了基于 Twitter 流量的 2019 年[十大 API 文章](https://www.programmableweb.com/news/top-10-api-articles-2019-based-twitter-traffic/brief/2019/12/31)，所以看看吧。

*   **预测和回顾:**至于对未来一年的预测， [InfoQ 提供了 2019 年的回顾](https://www.infoq.com/articles/infoq-2019-retrospective/)，触及了我们在这里谈论的许多话题——量子计算、WebAssembly、Java、。NET、DevOps 等等——这是[的一部分，一个更大的文章、视频、等等的集合](https://www.infoq.com/software-architecture-trends-2020/)，所有的主题都是回顾 2019 年和展望 2020 年。与此同时，SDTimes 跳上了预测列车，发布了对 2020 年的[软件稳定性预测，这是那些](https://sdtimes.com/softwaredev/software-stability-predictions-for-2020/)[可爱的预测文章之一](https://sdtimes.com/softwaredev/software-predictions-for-2020-from-around-the-industry/)，它收集了一堆最有可能由公关人员撰写的预制报价，并看看 [Gartner 的 2020 年十大趋势](https://sdtimes.com/softwaredev/gartners-top-10-technology-trends-for-2020/)。甚至还有看[2020 年](https://sdtimes.com/softwaredev/what-software-will-be-built-in-the-new-decade/)会写什么软件，好像会和 2019 年大不相同。接下来，PaktPub 调查了 2020 年的 10 家科技初创公司，它们将帮助世界构建更具弹性、更安全、更可观察的软件，这份名单包括一些你在新堆栈的页面上也见过的名字——launch darylly、NS1 等等。最后，就这些事情而言，亚马逊网络服务回顾了自己在 2019 年对开源的贡献。

*   所以你想在 2020 年学习？撇开水晶球和怀旧不谈，我们来看看新年的另一个方面——决心。不幸的是，我们现在都听说过“新的一年，新的我”，开发者和准开发者似乎也不例外。每个人都在承诺学习一门新语言，HackerNews 似乎是提供建议的地方，因为过去一周有几个热门话题触及了学习的话题。所以，如果你计划学习[机器学习](https://news.ycombinator.com/item?id=21924298)或者只是想弄清楚一些[计算机科学基础](https://news.ycombinator.com/item?id=21919465)，这些线程是一个很好的起点。

Amazon Web Services 和 NS1 是新堆栈的赞助商。

专题图片:“巨浪”，葛饰北斋(1830-32)，纽约大都会艺术博物馆。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>