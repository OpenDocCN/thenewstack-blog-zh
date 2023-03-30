# 开源建设者:Redis 如何颠覆数据库市场

> 原文：<https://thenewstack.io/open-source-builders-how-redis-upended-the-database-market/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

如果 [Salvatore Sanfilippo](https://twitter.com/antirez?lang=en) 要颠覆数据库市场，他至少可以体面地拥有一个数据库血统。你知道，10 年工程甲骨文或 SQL 服务器，然后他辞职去追求他的梦想，等等。但事实并非如此。桑菲利波说，当他 2009 年开始为 [Redis](https://redis.io/) [撰稿时，他还是一名数据库业余爱好者，还是数据库世界的新手。事实上，他在数据库方面的经验不足导致他违反了“好的”数据库工程的各种神圣不可侵犯的规则。](https://gist.github.com/antirez/6ca04dd191bdb82aad9fb241013e88a8)

谢天谢地。

今天，Redis 是世界上最受欢迎的数据库之一，我们都是 Sanfilippo 破坏规则的受益者。尽管依赖 Redis 的各种产品和服务上没有贴上“Redis Inside”的标签，但你很可能每天都在使用 Redis，因为优步、Instacart、Slack、Hulu、Twitter、Instagram 和更多的公司都在使用它。Sanfilippo 也不会告诉你应该如何使用 Redis。“Redis 的优势不在于我的选择，而在于应用开发者最了解它，”他说。

为了更好地理解 Sanfilippo 如何创建这个企业计算的开源主食，以及它将从这里走向何方，我与 Redis 的创始人聊了聊。

## 不需要 DBA 专业知识

在撰写 Redis 之前，Sanfilippo 已经在安全圈和其他领域声名鹊起。在安全方面，他创造了网络安全工具 hping 以及[空闲扫描](http://www.insecure.org/nmap/idlescan.html)，一种端口扫描技术。他还创造了[访问者](http://www.hping.org/visitors/)，一个博客分析器；Jim 解释器，Tcl 编程语言的小型实现；和一些设备驱动程序。简而言之，他不是无所事事。他很忙。

这种忙碌部分与他努力扩大自己的初创公司有关，具体来说，是一项名为[lloogg.com](http://lloogg.com/)的实时分析服务。Sanfilippo 努力使其与关系数据库(MySQL)一起扩展。这很有效，但他说，与应用程序的经济性相比，10，000 个用户所需的硬件数量太多了。他突然想到内存中的方法是理想的，更确切地说，他的工作负载——将数据推送到一个列表中，然后将其调整为固定大小——根本不适合关系模型。他开始建立 Redis。

创建 Redis 并不是在不同的数据库中挑选。Sanfilippo 必须从不同的角度思考底层数据模型。他最终构建了一个内存中的 NoSQL 数据库，它既是数据存储又是缓存，并在此过程中打破了各种数据库“规则”。

事实上，Sanfilippo 的方法遭到了数据库知识界的严厉批评。首先，人们指责 Redis 在内存中。他们还摒弃了 Redis 使用 [fork 系统调用](https://www.geeksforgeeks.org/fork-system-call/)在磁盘上持久化的模型，以及 Lua 脚本使用它们身体的[sha1 而不是名字](https://redis.io/commands/eval)。关于传统数据库是如何建立的，他们也许是对的。

他们对数据库未来的预测是完全错误的。

## 如何赢得朋友和影响他人

Sanfilippo 说，虽然数据库专家大多批评他的工作，但这让他可以自由地创新一种新的数据库。毫不奇怪，他选择了开放创新，因为开源一直是他的核心部分。“总的来说，我相信与他人分享东西，”他说。根据 Sanfilippo 的说法，他的职业生涯是在 18 岁时安装 Slackware 1.2.3 时开始的，他意识到里面有一个 C 编译器以及更多。“实际上，作为一名软件开发人员，我的整个故事是从开源开始的，所以对我来说，这是显而易见的方式，”他说。

但是开源不仅仅是 Sanfilippo 的许可问题。

“我确信软件是一个人类的过程，需要人们讲述故事，”Sanfilippo 说，“所以我到处讲述 Redis 的故事。”很快，人们开始接受 Redis，最初是在创业社区，后来是在成熟的企业。

虽然最初，Sanfilippo 指出，他更重视自己的自由，而不是所谓的数据库专家的帮助，但随着时间的推移，Redis 周围已经聚集了一个社区。Sanfilippo 说，10 年后，“Redis 核心肯定是许多个人之间的合作。”

这并不是说他把手从方向盘上拿开了:Sanfilippo 承认有时他很不擅长授权，以至于他仍然自己编写所有的 Redis 文档。

虽然 Sanfilippo 欢迎对 Redis 的贡献，但他说，从这个社区中，你会得到好坏参半的想法。例如，有人可能试图使用该软件解决一个不同于 Sanfilippo 希望解决的问题。此外，事实上系统软件是硬的。“你往往只能从那些大部分时间被付费撰写此类稿件的人那里获得严肃的稿件，”他说，尽管当然也有例外。他承认，为 Redis 这样一个严肃的数据库系统做贡献不是你周日早上可以放松的事情。

## 你选择

在过去的十年里，Sanfilippo 也承受着压力，他不知道 Redis 是否会成功，以及他是否有足够的资金来满足自己的需求。幸运的是，他说这些担忧自动解决了，因为 Redis 反而越来越受欢迎。今天，Sanfilippo 作为 [Redis 实验室](https://redis.com/)的一名员工，有幸将所有时间都投入到 Redis 中。

只是不要指望他会告诉你应该如何使用 Redis。

“Redis 对什么有好处不是我的选择；他解释说，每个应用程序都有自己的目标、必须提供的保证以及延迟和可伸缩性问题。Sanfilippo 说，他希望 Redis 在解决问题时被使用:无论它是一个主数据库，只是另一个数据库的索引，一些智能缓存，消息传递，或任何东西。

Sanfilippo 说，他没有为 Redis“预烤”未来，而是提供了一套积木，这样人们就可以找到创造性地组装它们的方法。Redis 也很容易修改。Sanfilippo 说:“经常通过一些改变，开发者能够让 Redis 做一些它不打算做的事情。”这很好。

Sanfilippo 并不认为自己是什么权威领袖。“我更喜欢设计新的东西并编码，”他说，如果其他人也这样做，那太好了。因为在 Redis 中，Sanfilippo 总结道，“开发者是女王还是国王——这取决于他们。”

*访问 AWS 开源博客，了解开源项目如何[申请 AWS 推广积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)。*

Redis 实验室是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>