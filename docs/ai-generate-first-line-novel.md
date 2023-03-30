# 人工智能能生成小说的第一行吗？

> 原文：<https://thenewstack.io/ai-generate-first-line-novel/>

我们是否正在接近这样的一天，即机器能够在“人类”领域(如创造性艺术)超越我们？如果你给一个复杂的神经网络适当的训练集，它最终能写出一部小说的第一行吗？

事实证明，还没有。

詹妮尔·谢恩已经开始探索类似的其他问题，通过摆弄神经网络。谢恩的方法很简单。“我所要做的就是给神经网络一个长长的例子列表，它会尽最大努力教会自己生成更多类似的例子，”她在一篇帖子中解释道。在所有愚蠢行为的背后，有一些高性能的技术，她在[接受 Next Web](https://thenextweb.com/artificial-intelligence/2017/11/02/novel-approach-to-ai-wages-war-on-writers-block/) 采访时说。

*我正在使用一个叫做 [char-rnn](https://github.com/karpathy/char-rnn) 的开源神经网络框架，由 Andrej Karpathy 在 [Torch](http://torch.ch/) 中编写。人们使用各种各样的奇特方法来使神经网络更好地理解和生成句子和段落。我没有使用这些，只是一个机器学习算法，它学习一个字母一个字母地拼写单词，而不知道它们是什么意思。*

TheNextWeb 总结道，“所以也许这不是奇点。”

但乐趣的一部分是挑选一些看起来像是人类独有的东西。“通常在我的实验中，我会给神经网络一个不公平的数据集——比如油漆颜色，”[谢恩写道](http://aiweirdness.com/post/167343465812/the-neural-network-meets-its-match-fish)“它尽了最大努力，但最终会出现一些非故意的怪异，比如一种被称为臭豆的褐色，或者一种被称为爸爸的亮蓝色。”

当然，另一半乐趣是在她的博客上分享可笑的结果[。例如，给定一个包含 37，265 个鱼名的数据集，神经网络尽最大努力](http://aiweirdness.com/)[生成自己的](http://aiweirdness.com/post/167343465812/the-neural-network-meets-its-match-fish)。上周谢恩训练它学习 224 首迪士尼歌曲的第一句歌词。但是这个月谢恩把她的注意力转向了最人性化的努力之一:写小说。Shane [在她的网页上开玩笑说:“当你面对一个空白页面时，有时很难开始。”。"我想看看能不能训练一个计算机程序来帮忙。"](http://aiweirdness.com/post/167049313837/a-neural-network-tries-writing-the-first-sentence)

“事实证明，她不能，”Geek.com 打趣道。

首先，很难找到足够的数据来训练神经网络。在搜索小说的第一行后，谢恩只找到了几百行，而“理想情况下，我需要几千行。”否则，神经网络会建议与其训练数据几乎相同的新的第一行，或者笨拙地将两行粘贴在一起，进行一些奇怪的调整。它一度让人联想到一部小说，以史努比最喜欢的开头语开始，但以詹姆斯·乔伊斯(James Joyce)的《尤利西斯》(Ulysses)的第一行结尾，还随意添加了一些词语。

*`"It was a dark and stormy night; the rain fell in torrents — except the station steps; plump Buck Mulligan came from the stairhead, bearing a bowl of people."`*

在《尤利西斯》中，勃克·穆利根拿着“一碗肥皂沫，上面交叉放着一面镜子和一把剃刀。”(尽管不可否认，如果碗里装满了*人*会有趣得多)。但是谢恩对神经网络产生的新奇开口并不满意。"大多数没有多大意义，而且/或者明显是名句的混搭."

虽然其中有几个很奇怪很尖锐。

*`"It was a wrong number that struggled against the darkness."`*

*`"The sky above the present century had reached the snapping point."`*

*T3*

几周后，谢恩承认“事情进行得不太顺利。”她发现还有一个网站提供额外的 900 个小说开头句子:布尔沃-利顿小说竞赛要求参赛者为一部小说写出最差的开头句子。(例如，“这是一个关于爱、痛苦、失去和救赎的故事，也是一只狒狒阿米莉亚的故事。”)

谢恩的判决。“无济于事。”她以新颖的开头结尾，比如…

*`"It was a dark and stormy night and the secret being a silver-backed gorilla."`*

绝望中，她求助于互联网——或者至少，求助于她网站的读者和她在 Twitter 上的追随者。是的，她让网上的陌生人发来他们最喜欢的小说的第一行——甚至是他们自己写的业余小说的第一行。她的神经网络能从人类志愿者提供的众包数据集中为一部小说精心打造一个令人信服的开头吗？

或者，网络上的人类会简单地用他们对科幻小说的异常的亲近感淹没它吗？

谢恩耐心地等到月底，甚至在感恩节前一周花了一个完全不同的实验——训练她的人工智能网络根据 2237 种馅饼食谱的名称产生馅饼的名称。但很快就回到了人工智能生成的小说，或者至少，收集了足够的数据，为她的神经网络提供了足够的训练集。

幸运的是，在这个阶段，她得到了朋友们的一点帮助:

很快，有用的提交开始涌入…

与此同时，另一群人聚集在互联网的另一部分。周四，在午夜钟声敲响的时候，384，126 名有抱负的小说作家标志着“全国小说写作月”的结束，这是第 18 次尝试在 30 天内只用人类的智慧创作一部快速小说。谢恩选择了同一个重要的日子来最终公布她自己的实验结果。她的读者已经从小说中获得了额外的 11，135 行。

"伙计们，你们让我和神经网络如此快乐."

结合用户提交的第一行和她已经有的 900 行，Shane 创建了一个包含 10，096 行小说的强大训练数据集。听起来更乐观，她写道，“第一个结果显示，如果不是承诺，那么至少是数据集中大量“*我的小马”*故事的证据。”

*`"...an of the the all stood ponyville at es that ev the."`*

但最初的结果总是有点粗糙，谢恩报告说，在训练更长时间后，神经网络“很快取得了一些进步，偶尔会产生语法正确的句子，只要它非常短。”

*`"It was an hour of the night."`*

*T2*

在通过训练集进行几次迭代后，它变得更像人类。或者至少，谢恩写道，“它最终学会了如何以谈论天气开始一本书——尽管并不总是成功。”

*`"The night is like a wounded carpets from the Crumzon."`*

*`"The sky was dead."`*

谢恩报告说，训练持续不断，最终，许多台词“几乎说得通……尤其是最短的。”

*`"I am not a king."`*

*`"The sky has gone."`*

*`"The sun was coming."`*

*`"The night was over."`*

实验结束时，她得出结论，人工智能生成的第一句台词“实际上相当有趣。我可能会读这些书。”

*T4*

*`“I am forced to write to my neighbors about the beast.”`*

*`"The sun was probably for his wife."`*

*`"I am a story that was not a truth."`*

但是在这个过程中，她有了一个有趣的发现:她并不是唯一一个试图利用科技写小说的人。在过去的几年里，全国小说创作月一直伴随着一个重叠的事件:“全国小说创作月”一个极客社区一直在 GitHub 知识库上分享他们的计算机生成小说[，谢恩忍不住加入了这一乐趣。](https://github.com/NaNoGenMo/2017)

所以，最后，她关于电脑生成的小说台词的帖子以一个情节转折结束。“这个项目是我参加全国小说创作月的*作品，这意味着我创作了 14 万字的第一行……”*

令人惊讶的是，它的某些部分实际上是可读的。

*`On the end of April, that was a large little boy before the mast. The book was nothing but stars, and the earth was hard to breathe. The day was enveloped in the year 1874.`*

谢恩(和她的追随者)现在终于可以见证他们邪恶合作的结果。

那么，当你将机器学习技术、众包和人类幽默感结合起来时，会发生什么呢？

当被要求写下它永远无法完全理解的东西时，神经网络仍然会带来一些令人愉快的惊喜。

当然，有一些小故障，但它们显然是由人类恶作剧引起的。

这个实验似乎是成功的，即使它没有把人类引向完美的机器生成的小说。

因为至少它给了我们在黑暗中迷失的可怜的小马，这是最有人情味的礼物。

笑声。

* * *

# WebReduce

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>