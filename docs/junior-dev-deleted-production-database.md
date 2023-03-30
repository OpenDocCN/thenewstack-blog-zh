# 删除生产数据库的初级开发人员

> 原文：<https://thenewstack.io/junior-dev-deleted-production-database/>

上周，一位匿名的年轻程序员登录了 Reddit 论坛，讨论计算机科学职业问题，并将他工作的第一周浓缩为一个令人回味的故事:“[在工作的第一天意外破坏了生产数据库，并被告知离开，此外，首席技术官告诉我，他们需要法律介入，我有多糟？](https://www.reddit.com/r/cscareerquestions/comments/6ez8ag/accidentally_destroyed_production_database_on/)

据《华盛顿邮报》报道，这位自豪的年轻程序员获得了大学学位，然后收拾行装准备去一个全国各地的新工作，做一名初级软件开发员。在一家拥有 100 多名员工和 40 多名开发人员的公司，这是他的第一个非实习职位，你可以想象对工作的第一天抱有很高的期望。

“不幸的是，我搞砸了，”他写道。

> [在工作的第一天，意外地破坏了生产数据库，并被告知离开，此外，首席技术官告诉我，他们需要让法律部门介入，我有多倒霉？](https://www.reddit.com/r/cscareerquestions/comments/6ez8ag/accidentally_destroyed_production_database_on/?ref_source=embed&ref=share)来自[cscarerier 提问](https://www.reddit.com/r/cscareerquestions/)

由于无处可去，开发者转向了 Reddit 的“CS 职业问题”论坛。可怜的开发人员形容自己“困惑”和“恐惧”他不知道自己能否保住这份工作。然后，他做了任何有压力的年轻开发人员都会做的事情——出去喝一杯。

醒来后——大概是有点宿醉——他登录 Reddit，发现他的帖子已经超过 23，000 次投票，4，500 条评论和无数条私信。他的故事很快成为论坛有史以来最受欢迎的话题，获得的支持票数是第二大热门话题的七倍。

这是一个令人震惊的支持展示，普遍的反应似乎是整个行业的同情集体表达。

Yorick 后来分享了一些额外的观点。“对于许多公司来说，有些事情直到成为问题才变得重要，这很不幸……我个人认为创业文化强化了这一点:建立 MVP、销售销售等比建立可持续的东西更重要。”

Yorick 的评论引发了一个鼓舞人心的例子，展示了极客社区是如何对待诚实承认错误的。“原来是你！？！！！你们能如此坦诚真是太好了。随着你在 youtube 上的恢复努力，这是一个爆炸。继续好好打！”

Yorick 甚至得到了与最近高调的数据删除混乱有关的人的回应:

“嗨，今年早些时候不小心攻击了 GitLab.com 的数据库的家伙…”另一条回复写道。“这不是你的错……公司方面有太多的危险信号……”其中一个危险信号是公司的备份没有工作，表明它们没有经过*测试*，他称之为“我们在 GitLab 遇到的同样问题，至少现在工作了。”(GitLab 确实有备份，但是晚了 6 个小时。)

一个自称系统工程师的网名为 CoffeeSippingBastard 的 Redditor 提醒初级开发人员，当时亚马逊的维护程序[从生产服务器](https://aws.amazon.com/message/680587/)删除了负载平衡数据:“我记得的最后一件事是——盖伊还在那里。”

这引发了对亚马逊回应的有趣分析。“他们写了一份 COE(错误纠正报告),详细说明了发生这种情况的原因(使用 5 个为什么来找出每个原因的真正‘底部’),写下了具体的立即行动，并包括了学到的经验教训(例如，在没有第二双眼睛通过 CM 流程批准您的更改的情况下，不要在任何地方对 prod 进行直接更改)…该报告以草稿形式发送给几乎整个公司进行审查和评论。他们会发表评论。很多。质疑事物是他们的一种文化习惯。对于亚马逊的所有错误，最好的部分是当有人搞砸了，团队和公司只关注如何让它不再发生。

"人类的错误是集体的失败，而不是个人的。"

另一条评论补充道，“我公司的逻辑是，除非你是一个巨大的重复错误……为什么要解雇一个最了解发生了什么的人？解雇那家伙不会破坏你的程序。他开始创建一个流程文档，这样就不会再发生了。”

同样的同情情绪一再被表达。“你做得对，”另一位 Reddit 用户写道。“你弄错了。你承认那是什么，那就是你。”

一位首席技术官评论道:“这恰恰凸显了他们的无能。这不是你的错……但在某种程度上，你应该感到幸运，因为你已经不在那里了。听起来你会在那里学到一些非常坏的习惯。”

当科技新闻网站 The Register 进行了一项民意调查，询问[谁应该被解雇](https://www.theregister.co.uk/2017/06/05/dev_accidentally_nuked_production_database_was_allegedly_instantly_fired/)时，高达 99%的受访者认为初级开发人员无罪，另外 43%的人投票认为不应该解雇任何人；“这给所有人敲响了警钟。”

尽管 10%的人希望解雇负责备份维护的人，另外 45%的人投票解雇首席技术官。

黑客新闻上的[高层回应也没有对该公司表示同情。“对不起，但是如果一个初级开发人员在遵循您的文档的同时，通过在他的 _local_ dev 环境中运行一个脚本，就可以让您的产品](https://news.ycombinator.com/item?id=14476538)[数据库系统](https://thenewstack.io/category/data/)泡汤，那您只能怪自己。为什么您的 prod 数据库甚至可以从他的本地 env 访问？你的其他保安是什么样子的？我打赌是瑞士奶酪。”

或者，正如其他人所说，“他们的技术是什么， *Jenga？*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>