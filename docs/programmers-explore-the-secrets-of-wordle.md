# 程序员探索 Wordle 的秘密

> 原文：<https://thenewstack.io/programmers-explore-the-secrets-of-wordle/>

随着“文字热”席卷互联网，程序员、数学爱好者和各种各样的书呆子决定加入其中——他们释放了创造力的爆发。

每天，[简单却突然流行的游戏](https://www.powerlanguage.co.uk/wordle/)给玩家六次机会猜一个五个字母的单词——每次突出他们猜对的字母(以及那些在正确位置的正确字母)。一月早些时候，[最近刚从训练营毕业的汉娜·帕克](https://www.linkedin.com/in/hannahpark1000/)，创造了一个[单词游戏克隆](https://wordle.hannahmariepark.com/)作为教育练习(使用流行的工具如 React、TypeScript 和 Tailwind)。

然后，一位伦敦的数据科学家/物理学家， [Richard Mann](https://twitter.com/richardajmann) (与 Imogen Mann 一起)想到了一个版本，玩家可以猜测数学方程中的数字和运算符，而不是字母。

他们分叉了 Park 的代码(在一个个人理财应用的联合创始人/首席技术官 Marcus Tettmar 的帮助下，创建了 Nerdle。“我们认为玩数字和玩字母一样有趣，”游戏的信息页面解释道。“看你同意不！”

但是他们并不是唯一想把游戏变得更有技术含量的人。本周早些时候，在英国诺里奇，一位名叫[詹姆斯·利弗西](https://www.linkedin.com/in/james-livesey-01742b1ba/)的 18 岁程序员创造了 [Bytle](https://jamesl.me/bytle/) ，这是一个玩家试图猜测的游戏——你能相信吗？—一个无符号 8 位整数。

问题是玩家的输入必须是正常的以 10 为基数的数字，最好是 0 到 255 之间的数字。但是在显示八个绿色和黄色方框之前，每个猜测都被转换成二进制(现在，这八个方框只表示 8 位中哪一位是正确的)。

开发人员 Ian Ross 和 Colin M. Saunders 甚至创建了一个 Python 模块，可以与本土机器人进行 Wordle 对抗——他们在 botfights.ai 上挑战开发人员在 1000 词比赛中测试他们的创作[。](https://botfights.ai/)

## 寻找答案

但是其他程序员正在尝试创建 Wordle 解算器。得克萨斯州 Colleyville 的开发人员 Christian Genco 开发了一个令人印象深刻的多功能[单词解算器](https://www.wordlesolver.com/)，它也可以让玩家输入他们猜测的单词，然后[显示](https://twitter.com/cgenco/status/1479585434455977987)剩余的每个可能的单词。(单击您猜测中的字母，将颜色改为绿色或黄色。)

它还会计算出你最有可能的下一个猜测——排除剩余单词最多的选择。当他的工具[只用了三次猜测就解决了第 203 号谜题时，Genco 兴高采烈地在 Twitter 上发布了“哈哈哈，太棒了”。](https://twitter.com/cgenco/status/1479912775153602561)

Genco 的 Wordle Solver 也可以用来根据你自己的猜测来重放游戏，只是为了看看你有多接近或者有多远。

但是很快，这支 Wordle 解决者大军遭遇了他们的黑暗分身，不止一个开发者尝试了一种叫做“邪恶 Wordle”的变种

“ [Absurdle](https://qntm.org/wordle) ”的创作者“承诺自己的 AI”是高度回避的，需要真正的努力才能迫使游戏放弃有用的信息，并将其逼入死角。”(“如果你喜欢荒谬，试试 [HATETRIS](https://qntm.org/files/hatetris/hatetris.html) ，我的俄罗斯方块对抗版。”)

其他开发人员也实现了类似的猜测回避算法。“每次你猜的时候，我都会查看符合你所有猜测的所有可能的 5 个字母的单词，并选择产生最可能单词的匹配模式，”由程序员 [Ravi Parikh](https://www.linkedin.com/in/raviparikh2) 创建的 [Evil Wordle](https://swag.github.io/evil-wordle/) 页面说道，他是内部应用程序构建平台 Airplane.dev 的联合创始人。“我的目标是最大限度地增加找到单词所需的猜测次数。”

最近黑客新闻上的帖子发现解决方案的构建者[分享了](https://news.ycombinator.com/item?id=29862597) [关于他们的单词解决程序如何处理这些邪恶的单词改变克隆体的故事](https://news.ycombinator.com/item?id=29864418)！

> 我们都坚持的不破坏日常生活的社会契约，稍稍恢复了我对人性的信心。
> 
> —莎拉·贝西(@莎拉·贝西)[2022 年 1 月 25 日](https://twitter.com/SarahBessey/status/1485795898315575297?ref_src=twsrc%5Etfw)

周四，CNET [报道](https://www.cnet.com/news/new-much-more-evil-wordle-challenges-you-to-tackle-two-words-at-once/)一个名叫[古伊列梅·托沃斯](https://www.linkedin.com/in/gtows)的游戏开发者创造了一个“新的、更加邪恶的”克隆体，名为[多尔德](https://zaratustra.itch.io/dordle)，其中的解决方案是两个五个字母的单词，并排在一起，玩家试图猜出这两个单词(仍然只猜一个五个字母的单词)。

游戏网站 Kotaku [将](https://kotaku.com/wordle-games-like-clones-twitter-word-absurdle-lewdle-d-1848414806) Dordle 描述为“一个只会带来痛苦和悲伤的噩梦，所以只有擅长猜词的人应该试试这个，除非你喜欢被一个视频游戏所拥有。”

但 Kotaku 也称衍生产品是“聪明人为了好玩而乱搞时会发生什么的杰出例子……这些游戏可以根据他们的喜好简单或复杂，随着时间的推移，可能会变得越来越奇怪。

“我很兴奋地想看看接下来集体意识中会涌现出什么样不可思议的猜字游戏。”

## 如果沃尔多是一座城市

其他开发者也在尝试构建一个更好的 Wordle。 [Hello Wordl](https://hellowordl.net/) 复制了原始游戏的机制，但在谜题顶部添加了一个滑块，将单词(和你的猜词)的长度扩展到 11 个字母。

有人甚至创造了一种变体，他们称之为“[填字游戏:数独遇上单词游戏](https://crosswordle.vercel.app/?daily=1)”，这是一个令人惊讶的难题，你试图填写一组猜测，从而产生一个单词——包括每个黄色或绿色方框的适当字母。

与此同时，一些开发者已经把他们的努力集中在把 Wordle 的快乐带给世界的其他地方。现在有版本[使用](https://www.jiconway.com/vertl/) [意第绪语](https://greenwichmeanti.me/wordle/)和[希伯来语](https://wordleheb.web.app/)单词，还有一个版本中[是挪威语](https://www.fiveletters.xyz/no/five)。

再看久一点，你会发现至少有两个版本的[使用了](https://motle.fac3.org/)法语[词汇](https://wordle.louan.me/)，外加两个版本的[使用了丹麦语词汇](https://ordlek.github.io/ordlek/dansk/)——包括域名[wrdle . dk](https://w%C3%B8rdle.dk/)的一个。有[荷兰语](https://woordle.nl/)，[葡萄牙语](https://term.ooo/)，[瑞典语](https://ordlek.github.io/ordlek/)，[芬兰语](https://sanuli.fi/)，[罗马尼亚语](https://cuvantul.github.io/cuvantul)，甚至还有一个[保加利亚语](https://wordle-bg.ggerganov.com/)的版本。

在 Twitter 上，有很多关于 Wordle 释放更多意想不到的创造力的精彩故事。科技教育专业人士劳拉·蒂尔顿最近[在推特上](https://twitter.com/tiltondata/status/1485621258008117257)说她一直在用谷歌数据工作室创建游戏中最常用字母的可视化。计算机图形艺术家朱利安·格兰德正在将他的积木[转换成奇特的三维图像](https://twitter.com/glanderco/status/1481701089724538889)。

Twitter feed 试图使用微软的 Paint 将其猜测转化成漫画。英国和爱尔兰现代音乐学院计算机音乐设计的助理讲师大卫·麦克法拉尼声称他已经建造了一个单词音序器“可以把你的结果变成音乐”

一名开发人员甚至创建了一个网页，将带有 Wordle 的无剧透色块的推文变成游戏 Townscraper 中的彩色摩天大楼。

## 永无止境的乐趣

最后，也许在技术头脑中有一些原始的东西将整个 Wordle 现象视为另一个新的玩具来拆开和探索。

另一个以新方式审视游戏的人是 Kaggle 的首席技术官兼联合创始人本·哈姆纳(Ben Hamner)，他曾被谷歌的子公司 T2 形容为“数据科学家的 AirBnB”。周四，哈姆纳宣布，他已经找到了一种方法来确定单词[，只需咀嚼人们在推特上分享的所有黄色/绿色/灰色方块](https://www.kaggle.com/benhamner/wordle-1-6)。

“自从我开始收集 Twitter 数据(Wordle 210-222)以来，这个方法每天第一次尝试就生成了正确的 Wordle 答案！”哈姆纳在博客上写道。

尽管他们发现一些推文比其他的更有用…

但是，也许科技社区的真实面目在史蒂文·克拉沃塔的故事中最闪亮，他在 18 岁时制作了另一款完全不同的应用程序——他也将其命名为 Wordle。四年后的这个月，它的下载量出人意料地飙升，根据 Cravotta 的 Twitter 账户，在短短一周内突然吸引了超过 200，000 次下载。

这个故事有一个快乐的结局。Cravotta [联系了现已流行的游戏 Wordle 的实际创作者 Josh Wardle](https://twitter.com/powerlanguish/status/1482007797437014020%20) ，Cravotta 承诺将这笔钱捐给慈善机构——具体来说，是一个名为 [Boost 的辅导/指导项目！西奥克兰](http://boostoakland.org/index.html)。

是的，Wordle 有一些不太受启发的变体。Slate 上最近的一篇[文章提到了其他山寨版本——比如一个被称为](https://slate.com/culture/2022/01/wordle-game-creator-wardle-twitter-scores-strategy-stats.html) [Sweardle](https://www.sweardle.com/) 的带有亵渎成分的版本——还有一个游戏的讽刺[单字母版本](https://edjefferson.com/letterle/)(允许辅音)当然需要更长的时间来解决。

但是为了得到官方的回应，Slate 还追踪了 Wordle 的创始人[沃德尔](https://www.linkedin.com/in/joshwardle)，他是 Reddit 和 Pinterest 的前软件工程师，从去年 12 月开始担任纽约艺术集体 MSCHF 的软件工程师。

沃德尔说，所有的克隆人都让他内心感到温暖和满足。

“作为一个创作东西的人，看到人们被你创作的东西如此激励，以至于他们想要即兴创作，这太棒了，”他说。“这让我感觉很好。”

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>