# 问答:本书作者安迪·格林伯格谈政府支持的黑客威胁

> 原文：<https://thenewstack.io/qa-book-author-andy-greenberg-on-government-sponsored-hacker-threats/>

几年前导致乌克兰公共基础设施瘫痪的网络攻击当时可能不会出现在许多安全团队的雷达屏幕上。然而，在过去的几年里，关于俄罗斯政府支持的沙虫黑客组织的详细证据已经出现，揭示了为什么 DevOps 团队应该保持高度警惕。

据称，沙虫黑客组织对释放 Petya、NotPetya 和其他恶意软件负责，这些恶意软件在全球范围内造成了数十亿美元的损失，其中包括美国的目标。此外，在 2016 年美国大选和其他攻击之前，俄罗斯资助了对美国民主党的黑客攻击。

同样令人担忧的是，美国政府是如何创建恶意软件的，这些恶意软件一旦泄露，也会被犯罪黑客所利用。例如，Stuxnet 被广泛报道为由美国和以色列网络特工创建，旨在阻挠伊朗在纳坦兹的核研究，后来成为用于勒索软件和其他攻击的恶意软件变种的来源。

与此同时，正如《连线》作家安迪·格林伯格在他的书《沙虫:网络战的新时代和对克里姆林宫最危险黑客的追捕》中所披露的那样，从恶意软件发布到美国政府承认网络攻击并发布补丁之间已经出现了延迟。例如，直到 10 月，美国政府才在法庭上正式承认沙虫黑客组织的存在，在美国联邦法院对其成员——俄罗斯军队情报部门的官员——提起刑事诉讼。

然而，美国政府在恶意软件传播中的参与和缺乏行动只是格林伯格书中的几个主题。这本书还对沙虫黑客组织及其在乌克兰的攻击进行了大量的研究，写得很好，也很全面。“沙虫”的关键来源是分析师和威胁事件响应者。本章还专门讨论了乌克兰对俄罗斯和北约盟友集团的地缘政治利害关系，涵盖了俄罗斯对该国内政经常进行的血腥和镇压。

格林伯格在接受《新书库》采访时谈到了平装本《沙虫:网络战的新时代和追捕克里姆林宫最危险的黑客》的发行，该书已经更新了更多关于沙虫的信息。该书的更新版本还提供了更多关于俄罗斯和美国政府创建的恶意软件攻击的见解，以及正在进行的以恶意软件为武器的国际网络战对 DevSecOps 意味着什么。

你的书给软件开发人员社区带来了什么？

这本书的核心是关于沙虫如何在乌克兰实施这些史无前例的袭击，包括两次停电袭击。当时，我对这些非常感兴趣:他们清楚地表明，这个组织愿意对民用关键基础设施进行攻击，而在世界上任何其他地方都没有人这样做。那时我开始追踪沙虫。但是，就在我发表了第一篇关于沙虫袭击的《连线》封面故事后，他们在乌克兰发布了一款名为 NotPetya 的恶意软件，这是一种自动自我传播的蠕虫，它在乌克兰和世界其他地方传播，造成了 100 亿美元的损失。人们花了一些时间才意识到 NotPetya 的规模，以及它是历史上最严重的网络攻击。它不仅与沙虫有关，而且实际上是同一伙黑客干的。

在那之前，这是一个关于乌克兰的故事，有点像是猜测，这些沙虫黑客会不会做同样的事情，他们在乌克兰和世界其他地方，如美国或西欧做了什么？但有了 NotPetya，乌克兰的网络战确实蔓延到了世界其他地方，让整个全球互联网付出了巨大的经济损失。这就是促使我写这本书的原因。

**这么说，美国政府似乎多年来一直意识到沙虫和俄罗斯政府参与了针对美国利益的网络攻击，你在书中详细描述了这一点？也许应该给政府施加更多的压力，给 IT 安全团队更多的保护和信息来保护他们的组织？**

以 NotPetya 为例可能会有帮助，因为有三种不同类型的漏洞被打包在一起，使 NotPetya 变得有效，从而允许它传播并造成如此大的破坏。一个是 [Mimikatz](https://github.com/gentilkiwi/mimikatz) ，这是一个开源黑客工具，是一个很好的例子，因为它是由【法国程序员】Benjamin Delpy 创建的工具，用于让微软修复 Windows 中的一个漏洞。因此，他成功地迫使微软使 Windows 更加安全，但他不断地用更多的黑客技术更新 Mimikatz，这些技术利用了 Windows 身份验证中的问题……微软本可以做得更多，以使这些漏洞更难被发现。基本上，一旦你在一台机器上有了立足之地，或者从内存中挖出密码，你就可以使用来转动和访问网络上的其他机器。

因此，这是微软本可以做得更多的一个方面。还有另一个方面:EternalBlue，这个泄露的 NSA 黑客工具是 NSA(美国国家安全局)拥有的秘密[零日](https://en.wikipedia.org/wiki/Zero-day_(computing))黑客技术——在那里，微软做了它能做的一切。永恒之蓝利用了 Windows 中的一个秘密漏洞。一旦发现这个工具被这个神秘的黑客组织[影子经纪人](https://en.wikipedia.org/wiki/The_Shadow_Brokers)窃取，美国国家安全局就向微软发出警告，微软也发布了补丁。问题是打补丁是一种流行病学问题，很难让每个人都打补丁，即使是非常严重的漏洞。所以，微软并没有真的做错什么。如果有什么错的话，我认为，至少部分原因在于美国国家安全局，因为它将这个零日利用秘密保持了这么长时间。即使他们帮助微软发布了一个补丁，也没有足够的时间在世界各地安装这个补丁。

因此，永恒之蓝在世界各地造成了巨大的破坏，尽管美国国家安全局努力修补它。因此，情报界存在一些错误——他们必须平衡保持零日攻击目的的需求和保护可能因使用相同秘密漏洞而受害的美国人的责任。最终,“永恒之蓝”是一个案例，它真实地展示了最糟糕的情况，即我们自己的情报机构掌握的秘密漏洞会如何反过来咬我们。

美国和其他政府应该扮演什么角色？该怪谁呢？

这要归咎于世界各地的政府未能阻止这些极具侵略性和老练的民族国家黑客做出这些事情。我们不可能真的锁上每一扇窗，锁上每一扇门，把如此先进和顽固的黑客拒之门外。我们必须努力改变他们的想法，让他们意识到他们将受到惩罚，他们将被追究责任，他们是不应该跨越的红线。我指的不是沙虫，我指的是沙虫在克里姆林宫的俄罗斯军事情报局的老板们，作为一个整体，我认为他们需要明白，他们应该感到不值得他们做这些可怕的破坏性的事情。这就是你最终如何控制这个问题。

《沙虫》的故事这本书讲述了像美国和西欧这样的西方国家的政府是如何完全无视这场正在乌克兰展开的网络战争的。沙虫发动的一次又一次袭击从一开始就应该受到谴责。沙虫在乌克兰的所作所为显然是不可接受的，它越过了我们试图在全球舞台上为可接受的黑客行为设定的每一条红线。他们肆无忌惮地攻击一个又一个民用关键基础设施，包括停电攻击，这是针对民用目标的网络战的典型行为——但没人说什么。没有哪个西方政府对沙虫说过什么，从来没有谴责过他们，从来没有实施过制裁……甚至从来没有发布过新闻稿。

<svg viewBox="0 0 68 31" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink"><title>Group</title> <desc>Created with Sketch.</desc></svg>