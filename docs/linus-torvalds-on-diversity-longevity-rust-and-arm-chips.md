# Linus Torvalds 谈多样性、寿命、生锈和 ARM 芯片

> 原文：<https://thenewstack.io/linus-torvalds-on-diversity-longevity-rust-and-arm-chips/>

本周看到了 [Linux 基金会的](https://training.linuxfoundation.org/)年度[开源峰会和北美嵌入式 Linux 会议](https://events.linuxfoundation.org/open-source-summit-north-america/)的[特别虚拟版](https://youtu.be/vjKPw5FqleM?t=29%20)，该会议原定在得克萨斯州奥斯汀举行。

现在在线的活动保留了所有 230 个主题演讲(有现场问答环节)，包括与 Linux 创建者 [Linus Torvalds](https://github.com/torvalds) 和 VMware 首席开源官 Dirk Hohndel[的传统开场主题演讲的独特版本。](https://www.linkedin.com/in/dirkhohndel/)

在一次分屏远程采访中，托瓦尔兹仍然分享了他对内核开发过程的年度一瞥——但这一年不同于其他任何一年。但是对于托沃兹来说，事情真的没有改变那么多。“实际上，就在这里的这次会议，是第一次重大变革，”他告诉在家观看的虚拟观众。“我不喜欢开视频会议，在过去的四个月里，我还没有开过一次视频会议，坦率地说，这似乎真的有用，这让我感到惊讶。”

事实上，通常托沃兹是在家工作的——坐在电脑前阅读电子邮件。Hohndel 同意 Linux 社区一直以来都是基于电子邮件和远程的，很少面对面的聚在一起。这就引出了对话中最有趣的交流之一。

## 开源的多样性，新的和旧的

Hohndel 提到，在 cloud native community 和 Cloud Native Computing Foundation 中，他观察到“黑人贡献者和领导者的比例明显更高。[凯尔西·海托华](https://github.com/kelseyhightower)，[布莱恩·李尔斯](https://github.com/bryanl)，[斯蒂芬·奥古斯都](https://github.com/justaugustus)，有这么多。我不认为我在 Linux 中看到了这一点。

“仅仅是我没有看到合适的人，还是我们的种族多样性不如一些年轻的基金会，只是因为我们都是在大约 30 年前开始的？”霍恩德尔问道。

托沃兹给出了一个非常坦率的回答，首先承认“我确实怀疑你可能是对的，许多处于低级技术的人是几十年前开始的那种人，他们就是这样进入整个低级硬件接口和操作系统的……”但他的第二个反应只是“我真的不知道。”因为 Linux 社区的偏远本质，“我不和这些人见面。据我所知，内核社区的一半可能不是白人。我从来没有见过他们，我不做面对面的交流。

> “仅仅是我没有看到合适的人，还是我们的种族多样性不如一些年轻的基金会，只是因为我们都是在大约 30 年前开始的？”——德克·霍恩德尔。

“我确实知道，当谈到我一年见一次的核心维护者时，我们显然是非常同质的人群。但我甚至不知道所有的新开发商。每一次发布，我们都有一千多名开发人员。相当多，我们有 2000 多个。我不知道涉及到哪些人…

“据我所知，一些补丁是由人们正在尝试的人工智能发出的。”

## **云中的仁？**

Hohndel 指出，嵌入式 Linux 会议已经扩展到云和特定领域的技术，并询问这是否证明 Linux 本身是健康的，并扩展了它的影响范围。但是莱纳斯把这个问题引向了一个令人惊讶的方向。“在过去的十多年里，我告诉人们，不，内核不是未来——如果你正在寻找一个新的、令人兴奋的项目，也许你不应该涉足内核。”托沃兹解释说，现代操作系统的基础是对 20 世纪 60 年代所做事情的“回忆”,因此内核开发不一定是在最前沿工作。

但是当 Hohndel 引用 Torvalds 的一句名言“Linux 很无聊，内核就应该是这样的”时，Torvalds 真的叫了暂停。

“是的，我说过内核很无聊，但我真正的意思是，很多新技术应该更有趣。对我和许多其他人来说，没有什么比与硬件进行低层次的交互并真正控制正在发生的一切更有趣的了。所以不要误会我。内核不无聊。但另一方面，大多数人应该会认为它们很无聊。”

> “在过去的十多年里，我告诉人们，不，内核不是未来——如果你正在寻找一个新的、令人兴奋的项目，也许你不应该涉足内核。”——莱纳斯·托瓦尔兹

Hohndel 注意到许多 Linux 社区的领导者都已经五六十岁了，他问这个社区是否需要开始考虑代际变化。托沃兹看到了一种更微妙的情况，人们“确实倾向于留下来”，并最终转向维护和管理。“很多新人，既不是 50 岁也不是 40 岁，他们通常还在上大学，或者刚刚毕业——他们通常在做真正的工作。事实上，我们的管理人员和维护人员已经老了，开始变老，我认为，这是一个完全不同的问题。”

但是 Hohndel 仍然展望未来，问道“会不会有 30 多岁的一代人向上爬，所以会有另一波浪潮来接管？我们需要他们，对吗？”

托沃兹断然回答说:“是的。我们有足够的钱吗？没有。事实证明，很难找到维护人员。”

“维护工作很有趣，也很有挑战性，但是作为一名内核维护人员，尤其有一个缺点，那就是你必须一直呆在那里。也许不是一天 24 小时，但每天都是。你阅读邮件，回复邮件——你必须在那里。这不一定是一个非常容易进入的利基市场。”

Torvalds 反映出他们有“相当数量”的开源项目维护人员——数百人，甚至超过了许多项目的参与人数。“但与此同时，我们经常遇到的一个问题是，很难找到真正关注他人代码的人，并帮助将这些代码向上引导至我的树。我认为这是我们需要继续努力的事情…我认为这是我们在整个内核维护树中面临的主要问题之一。”

Hohndel 深入研究了这一过程的具体细节，指出 Linux 内核是用 C 语言编写的，并提出了一个异端观点，即“再也没有人用 C 语言编写软件了”。每个新项目都是用 Go 或 Rust 或另一种我从未听说过的新语言完成的。我们有可能成为 21 世纪 30 年代的 COBOL 程序员吗？”

首先，托沃兹对他的前提提出了质疑——“实际上，我认为没有人再用 C 语言写东西了。如果你看一下统计数据，我认为 C 仍然是前十大语言之一。”但更有趣的是，托瓦尔兹指出，Rust 接口(“例如”)已经是人们“积极关注的东西，特别是做驱动程序和对内核本身不是很重要的事情……”

“人们已经关注这个问题很多年了。我确信有一天会发生的。它可能不是 Rust，但它将会发生，我们将有不同的模型来编写这些类型的东西。”他承认现在是 C 或汇编，“但事情正在进行中。”尽管他也补充了一句警告。“这些事情需要很长很长的时间。你需要这样的基础设施来开始将其他语言集成到内核中，并让人们信任这些其他语言——这是一个很大的进步。”

## **一声号令**

Hohndel 还询问了上个月关于 Linus 已经[开始使用新的 AMD Threadripper 3970x](http://lkml.iu.edu/hypermail/linux/kernel/2005.3/00406.html) 系统的消息。众所周知，托沃兹喜欢办公室里完全安静——那么，他没有发现新芯片有点嘈杂吗？

Linus 指出，在一个合并窗口中，他可以收到数百个 pull 请求，“我努力做到每天 20 到 30 个，这是我的极限。”在他的旧机器上构建一个内核需要超过 15 分钟，所以他现在满足于一个更强大的机器，它仍然是安静的——至少在空闲时，当托瓦尔兹阅读他的电子邮件或回应问题时。“如果当我开始构建时，风扇真的启动时，它开始发出嗖嗖的声音，我决定如果我能让我的构建速度更快，我就能解决这个问题……现在我已经用我的新机器工作了一段时间，当我听到它在努力工作时，这让我感觉很好。”

事实上，如果有的话，他会喜欢更多。“现在我开始认为我应该选择老大哥，选择完整的 64 核和 128 个线程，只是因为那种嗖嗖的声音——越短越好。”

> “现在我已经用我的新机器工作了一段时间，当我听到它在努力工作时，这让我感觉很好。”莱纳斯·托沃兹。

托沃兹说，他已经等了很长时间，希望有一个不在云端的好的 ARM 桌面系统出现。“毫无疑问，拥有 Graviton2 的亚马逊在云中的 ARM 生态系统中做得比我们之前看到的 ARM 好得多。但是云开发并不是大多数开发人员想要做的那种开发——至少是大多数内核开发人员。你希望你面前有一台机器。”

他指出，鉴于 Linus 所做的那种计算能力，他不可避免地要坚持一个强大的桌面系统。“笔记本电脑很好，”他说，“但我只在旅行时使用。

“现在我显然没有去任何地方旅行。”

* * *

## WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>