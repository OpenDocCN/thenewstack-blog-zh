# Go 和 Scala 的共同点是什么，为什么 Static 正在崛起

> 原文：<https://thenewstack.io/what-go-and-scala-have-in-common-and-why-static-is-surging/>

Go(语言)和 Scala(一种[对象函数式](https://en.wikipedia.org/wiki/Multi-paradigm_programming_language) [编程](https://en.wikipedia.org/wiki/Programming_language)和[脚本语言](https://en.wikipedia.org/wiki/Scripting_language))有什么共同点？他们都越来越受欢迎。它们都是强类型语言。此外，他们还从动态语言专家那里获得了关注。

本周在 OSCON，我参加了由 Stripe 公司的 Avi Bryant 举办的“through 入门，Twitter 的高级 Scala API for Hadoop MapReduce”。会议老手可能会记得 Avi 2007 年在 RailsConf 的主题演讲。Avi 谈到了 Smalltalk 和 Ruby，这是两种绝对“动态”的语言，其中动态意味着没有输入；一切都只是一个对象，或者至少，解释器不会告诉你你的数据不适合你的函数，直到它开始运行。

思考类型的另一种方式是看另一种语言情况:静态类型的语言。用静态语言编写的程序中的数据是受类型约束的数据。把类型想象成分类。在现实世界中没有分类，你可以把一只鸭子放进一个蜂窝里。它使制作蜂箱和储存鸭子变得更容易，但是你可能会偶尔发现蜂蜜的味道很奇怪。动态语言使人们能够快速运送物品。Twitter 开始用 Ruby，自举很快；但是现在我们有 Avi 谈论他在 Twitter 期间的烫伤。Twitter 已经将其大部分架构(一个现在需要稳定而不是快速迭代的架构)转移到静态语言。

为什么静态语言会流行起来？正如 Avi 在他今天的演讲中提到的，静态语言在编译时而不是运行时抛出错误信息。当我们构建 web 应用程序的第一个版本时，我们的编写/编译/运行阶段很小:我们可能会做一个更改，点击服务器，几秒钟后就可以在浏览器中看到结果。反馈回路很小。Avi 今天的演讲是关于 Hadoop 集群计算数百万条数据记录。正如 Avi 指出的，一个“作业”可能需要 10 个小时，并且您希望在编译时(在作业提交到 Hadoop 之前)而不是在运行作业期间看到您的编程错误。静态语言不允许编译阶段的完成，也不允许你提交一个任务，直到你写了代码，并且编译器已经验证使用了正确的输入和输出。换句话说，当您将数百万条记录转换成关于鸭子和蜜蜂关系的有新闻价值的东西时，编译器知道记录应该是一排蜜蜂还是一排鸭子，如果函数是“countDucks ”,编译器不会让您继续，除非您放入其中的行来自鸭子工厂。对于 Ruby 或 Smalltalk，这种情况不会发生:这些语言在作业开始后就能判断出它是蜜蜂还是鸭子(“嘿，别对我大喊大叫，它们都有翅膀！”)，而对于 Hadoop 作业，这一时刻可能是作业开始后的第五个小时，这意味着您只浪费了五个小时。

所以，静态语言能更早地捕捉到错误。随着越来越多的工作转向大型数据集计算，我们将会看到对这些语言的更多依赖。具有讽刺意味的是，随着我们计算能力的增长，我们的数据集和日志文件也在增长。处理庞大的数据量导致了长时间运行的作业，这可以追溯到术语 job，它过去指的是“穿孔卡作业”，就像我们在计算时代看到的那样。我们在很大程度上已经忘记了编程长期运行作业的技术。静态语言为编写可靠的长时间运行的过程提供了一个入口。但是它们也让我们摆脱了困扰早期静态语言如 c 的烦人的内存管理问题。

这两种语言擅长的最后一件事是:并发性。在他的演讲中，Avi 展示了处理“爱丽丝梦游仙境”的代码。

。过滤{ word => word.length > 2 }
。filter not { word =>word . isempty }
。过滤{ word =>word . head . I supper }
。map{word = > (word，1)}
。小组
。总和
。groupAll
。maxBy{ case (word，count) = > count }

这段代码很特别，因为 Scala 和 running 可以根据它是在本地运行(在您的笔记本电脑上)还是在 Hadoop 之类的集群上运行来优化它。但是，请记住:无论在哪里运行，这些代码都不需要修改。您只需在命令行上指定一个不同的开关(–local vs–HDFS)；这是一种更安全的转换和转置方式，通过让优化编译器知道如何将作业转换到正在运行的计算引擎上。Go 和 Scala 都提供了语言级并发结构，与 Java 的线程或 Node.js 异步回调(即使使用基于 promise 的库)相比，它们非常容易使用。并发对于我们越来越多地看到的分布式计算是必要的。这些语言提供了一种简单而安全的并发方式，这也是它们越来越受欢迎的另一个原因。当你想像蜜蜂或蚂蚁一样在群体中活动时，你可以使用简单的组件和简单的工人来构建。蜜蜂才是出路，而不是鸭子。使用正确的语言，比如 Go 和 Scala。

特色图片[通过](https://www.flickr.com/photos/sugarhiccuphiccup/4529855744/in/photolist-7UhGi7-8kixfZ-73Eppv-enNKzS-iXYJvs-fopRkH-6NjKbM-4ybMuJ-8WxybG-bCgBQn-a6Ci8W-dVbbWY-4L8TL1-7z9Ti6-o9woZP-a6zS74-a6zRCg-4rTSLJ-8C47Cu-8p1R4f-815SiZ-jHetPB-6VgR8k-7zdDjL-6VgR8H-6VgKzz-2Y8FHr-c8s1fo-f6wLzz-7e3gBS-bcs3iK-bcs3h6-f6LLy5-f6LLV1-dHCgcH-bcs3kB-eGGwAB-4adTP-fveLp8-7UdXKW-7Z4m7A-4snBne-9Eo2Nq-bB7LJR-824MtD-6sfGA7-7UdYb1-bc3DtT-3eQ21k-7G8bmM) Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>