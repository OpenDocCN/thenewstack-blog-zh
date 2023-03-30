# 试运行:谷歌基于机器学习的“与书对话”服务

> 原文：<https://thenewstack.io/test-run-googles-machine-learning-based-talk-to-books-service/>

Google Research 最近使用机器学习来训练一个应用程序以一种非常独特的方式回答问题。它扫描了数十万本书，找出似乎能给出最佳答案的句子。它通过分析问题的*含义来做到这一点，而不仅仅是匹配关键词。这是谷歌展示处理自然语言查询的改进方法的方式。*

但是，它教会了我们关于人工智能增强应用程序的当前状态的任何东西吗？

![Semantic Experiences site logo](img/0bd3cad6800db9c84a7ea14aceed376c.png)

该公司新的“语义体验”网站[似乎在暗示](https://research.google.com/semanticexperiences/about.html)这一切都是一个巧妙的近似。“人工智能只是简单地考虑你键入的开场白，并在许多可能的回答中寻找最有可能出现的回答。”

首先，谷歌的研究人员识别了数十亿对语句，其中第二个语句对第一个语句做出回应，然后使用机器学习开发了一种算法来识别和选择(或“预测”)最佳回应——即在实际对话中接下来最有可能发生什么。其“[与书籍对话](https://books.google.com/talktobooks/)”应用程序将该模型应用于超过 10 万本书籍，找到似乎能神奇地回应用户问题语义的句子。

Engadget 称之为“人工智能中自然语言处理已经走了多远的有趣一瞥”

## 厚望

该应用程序背后的团队包括 70 岁的著名未来学家和发明家[雷·库兹韦尔](http://www.kurzweilai.net/)，他在 2012 年成为谷歌的工程总监[。“我一直致力于创造能改变人们生活的实用系统，”库兹韦尔当时说，并指出早在 20 世纪 70 年代，他就为盲人发明了第一台打印到语音的阅读机器。](http://www.kurzweilai.net/kurzweil-joins-google-to-work-on-new-projects-involving-machine-learning-and-language-processing)

“1999 年，我说过，大约十年后我们会看到自动驾驶汽车和手机等技术可以回答你的问题，人们批评这些预测不切实际。快进十年——谷歌展示了无人驾驶汽车，人们确实在问他们的安卓手机问题。

“我们很容易耸耸肩，好像这些技术一直都在，但我们真的走在加快创新的非凡轨道上，谷歌在很大程度上处于这一发展的前沿。”

本月，库兹韦尔[与谷歌研究产品经理](https://research.googleblog.com/2018/04/introducing-semantic-experiences-with.html)[雷切尔·伯恩斯坦](https://www.linkedin.com/in/rachelbernsteinsf/)共同撰写了一篇博文，解释了今天的计算机是如何更好地理解人类语言的。谷歌已经使用了一种最近开发的技术——“层次向量模型”——来[提高 Gmail 建议预填回复的能力](https://research.googleblog.com/2017/05/efficient-smart-reply-now-for-gmail.html)，他们目前正在探索其他用途。

所以就在上周——13 日星期五——谷歌研究终于在一个新的语义体验网站上展示了它的最新能力。它的口号？“理解语言的经验。”该网站上的一个[解释页面](https://research.google.com/semanticexperiences/about.html)称其为“简单的研究演示，使人工智能能够找到看起来像是对你输入的可能反应的陈述……”并补充道“你可能需要摆弄它才能最大限度地利用它。”

我是决定接受这个挑战的几个勇敢的网上冲浪者之一。

## 当你和书对话时会发生什么？

我最近读了华盛顿·欧文的《断头谷传奇》原著，以及这位作家的传记。那么，当我问:“你会如何描述华盛顿·欧文？”时，谷歌的神秘工具会如何回应呢？

"他正直、直率、勤奋、有进取心，受到汉考克县最优秀的人的广泛尊敬。"

很好——除了对乔纳森·帕克的描述，他是一本名为《俄亥俄州汉考克县历史》[的无名书中的无名之辈(这里离欧文在纽约塔里敦心爱的家很远。)](https://books.google.com/books?id=dA7VAAAAMAAJ&dq=%22Upright%20straightforward%20industrious%20and%20enterprising%20he%20was%20highly%20respected%20by%20a%20very%20wide%20circle%20of%20the%20best%20people%20of%20Hancock%20County%22&pg=PA548&v=onepage&source=ttb)

我很困惑。库兹韦尔在一篇博客文章中解释道:“语义搜索是基于搜索*的含义*，而不是关键词或短语。但它似乎错过了我在这里的意义的一个非常关键的部分。

这个工具提供了来自其他书籍的描述——显然也是其他人的描述。(例如，“[大理石人:罗伯特·李和他在美国社会中的形象](https://books.google.com/books?id=kz96tHrXIWcC&dq=%22A%20frustrated%20thespian%20he%20composed%20numerous%20historical%20dramas%20and%20wrote%20gaudy%20epic%20poems%20about%20Washington%27s%20greatness%22&pg=PA165&v=onepage&source=ttb)”和“[明尼苏达州圣保罗的钢笔画，以及老移民的传记素描](https://books.google.com/books?id=NoQUAAAAYAAJ&dq=%22He%20is%20an%20off%20hand%20humorous%20kind%20hearted%20gentleman%20and%20can%20show%20a%20record%20of%20experiences%20in%20the%20Northwest%20that%20can%20discount%20any%20other%20traveler%22&pg=PA275&v=onepage&source=ttb)。))

谷歌建议通过这个网站找到你可能想读的书——我不得不承认，我最终还是读了这本不寻常的精选书中的几段。获得这些古怪的非你所寻找的匹配让我想起了网络早期的一些意外收获——当时网络搜索有时会提供一些令人愉快的随机信息，让我感到惊讶。

我在下一次搜索中经历了同样的事情——尽管这个工具似乎表现得更好一些。

当我问:“你能从一本书中学到什么？”我从“终极丛林生存手册”中发现了一个令人惊讶的令人沮丧的回答“你可以从书中学到很多东西，但那只是讲述别人的经历，而不是了解你自己。”

该工具推荐了五本书，但没有提供节选，外加一些似乎与问题不匹配的节选。尽管当我读到《艰难的对话:如何讨论最重要的事情》中一段令人惊讶的相关摘录时，共识似乎正在形成。

"从一本书里你能学到多少关于人类互动的知识是有限的。"

我不是唯一一个玩谷歌新工具的人。网站*搜索引擎期刊*问了它一个困扰每个网络营销人员的问题:“我如何在谷歌上排名第一？”—并收到了一些[合适的回应](https://www.searchenginejournal.com/google-releases-tool-show-off-natural-language-search-capabilities/249313/)。

"在谷歌获得最高排名并没有一套最佳的比例."

“你可以把头埋在沙子里，希望谷歌奖励你更高的排名……”

但也许应用程序更擅长处理某些类型的问题。我不得不承认，当波特兰的一家报纸问网站“波特兰最美好的回忆是什么？”时，它似乎运气好得多返回的最佳结果似乎生动而恰当。

“波特兰很棒:500 名郊区朋克在跳舞，涅槃乐队在挫折中砸碎了几把吉他，泰德一如既往地沉着冷静，整个地方就像棕榈泉的弹球机，没人能碰我，这是埃弗雷特·特鲁的《[涅槃:传记](https://books.google.com/books?id=byoPYMdJ150C&dq=%22Portland%20was%20great%20500%20suburban%20punks%20dancing%20Nirvana%20trashing%20a%20fewguitars%20throughfrustration%20Tad%20thrashing%20with%20his%20usual%20aplomb%20and%20the%20whole%20place%20like%20a%20Palm%20Springs%20pinball%20machine%20that%20no%20one%20could%20touch%20me%20on%22&pg=PA171&v=onepage&source=ttb)》中的台词。

在 YouTube 上，信息系统教授詹姆斯·加斯金将其描述为“有史以来最好的文献综述工具！”表明它在一个特定的用例中非常方便——汇集学术论文的“文献综述”部分。他提出了几个合理的学术问题来证明这一点，比如“职业倦怠和离职倾向之间的关系是什么？”

[https://www.youtube.com/embed/a5Z-F9Gdv4c?feature=oembed](https://www.youtube.com/embed/a5Z-F9Gdv4c?feature=oembed)

视频

哈斯金斯在视频中解释道:“我们过去常常去图书馆整理纸质文献，这很痛苦。”。“然后我们开始使用谷歌学术，这是更好的方式，但仍然是一种在黑暗中使用关键字。现在，我们要做的就是问我们的问题…

“在这里键入它，谷歌将产生一套书籍，基本上可以指导您对研究问题的回答。”

## 在幕后

“语义体验”网站还为开发者提供了一个[页面](https://research.google.com/semanticexperiences/for-developers.html)，其中包含了关于该工具如何组装的更多细节。“这些模型是用英语语言的例子来训练的，但是同样的方法可以而且已经被用于其他语言，”该页解释说。

谷歌的博客文章提供了更多关于该应用程序实际工作方式的提示。“你可能会注意到，出名并不会让一本书排名靠前；这个实验只关注单个句子的匹配程度。

有趣的是，该网站的开发者页面还包括一个关于语言理解模型偏见的部分，警告说语言理解模型“也可以反映人类的认知偏见。”该应用程序采取了一个步骤来控制这一点:“在与书对话中，虽然我们无法手动审查 10 万册书中的每一句话，但我们使用了一个受欢迎度指标，该指标增加了专业出版社出版的书籍的比例。”谷歌也承认有更多的“偏见影响缓解”步骤可用，但没有用于与书籍交谈。“这些经历展示了人工智能的全部能力和弱点。

“有可能在这些经历中找到令人不快的联想。我们鼓励您使用反馈工具报告令人不快的联想，以便我们能够改进未来的模型……我们还没有(可能永远也不会)找到识别和减少不必要联想的完整解决方案。”

作者 Andrew Tobias 也观看了 Kurzweil 在温哥华 TED 会议上的技术展示，T4 提供了一些额外的细节。托拜厄斯总结说，这项服务“很笨重:你尝试的许多搜索都会产生超级愚蠢的结果”，但在听了库兹韦尔的报告后，“他们才刚刚开始”。会好起来的。”

重要的是要记住，结果会在半秒钟内迅速返回，这就是为什么该应用程序仅限于扫描 12 万本书。它可以很容易地扫描一百万本书，但这需要更多的时间来返回结果，“库兹韦尔告诉我们，他们知道人们不会忍受等待六秒钟。”

TED 官方博客也提到了库兹韦尔自己的一个精辟的观察，即它仍然比人类快。

"我花了*小时*去读十万本书."

* * *

# WebReduce

专题图片:俄勒冈州波特兰的鲍威尔书店

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>