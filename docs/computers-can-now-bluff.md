# 知道何时弃牌:CMU 人工智能程序无限击败人类德州扑克

> 原文：<https://thenewstack.io/computers-can-now-bluff/>

我们和人工智能战斗，人工智能赢了。而在这一轮机器学习中，计算机学会了虚张声势。

在匹兹堡的 Rivers Casino，卡内基梅隆大学将其名为 Libratus 的人工智能扑克游戏程序与四名世界上最好的职业扑克玩家进行了为期 20 天的扑克比赛。Libratus，其拉丁名称的意思是“平衡的”，在大脑与人工智能比赛中击败了 Jimmy Chou，Dong Kim，Jason Les 和 Daniel McAulay。

赔率制定者倾向于人类玩家，赔率为 4 比 1 或 5 比 1。但是他们错了。[计算机科学教授和研究生博士生 Tuomas sand holm](https://www.linkedin.com/in/tuomas-sandholm-15b1045)[卡耐基梅隆大学](https://www.cmu.edu)【CMU】的诺姆布朗，Libratus 背后的大脑在赌场周围徘徊，看着他们的心血结晶稳步上升。

玩家每天花 11 个小时在屏幕上与他们的 AI 对手战斗，玩单挑、无限注德州扑克，这是一种涉及两名玩家的无限变化的扑克游戏。总共玩了 120，000 场游戏，Libratus 净得 1，766，250 美元筹码。虽然人类玩家没有用真钱下注，但这仍然是一个软件的压倒性胜利，这个软件显然教会了自己如何智胜人类对手。

“我们没有告诉 Libratus 如何玩扑克。我们给了它扑克的规则，并说‘自己学’，”布朗告诉《卫报》的记者。布朗发表了一篇论文，描述了他们是如何完成这一壮举的。

“最初的几天，我们有很高的期望，”世界级职业扑克选手 Cho 告诉 PennLive 的记者。2015 年，赵承熙所在的团队击败了桑霍尔姆的最后一次尝试[克劳迪奥·艾](https://www.pokernews.com/news/2016/03/heads-up-bots-stronger-than-humans-nlhe-never-solved-24312.htm)。

“但每次我们发现一个弱点，它就会向我们学习，第二天弱点就会消失，”他说。

这场比赛非常艰苦。每天的游戏在晚上 10 点结束后，布朗将 Libratus 连接到匹兹堡超级计算机中心的 [Bridges](http://www.intel.com/content/www/us/en/high-performance-computing-fabrics/pittsburgh-supercomputing-center-video.html) 高性能计算机，运行算法来改进其策略。早上，他会花两个小时让新增强的机器人在上午 11 点开始之前恢复运行。

## 玩游戏

在我们的游戏中击败人类是人工智能成功的黄金标准。深蓝[在 1997 年击败了国际象棋大师加里·卡斯帕罗夫](http://time.com/3705316/deep-blue-kasparov/)。IBM 的沃森[支持](https://www.theguardian.com/technology/2011/feb/17/ibm-computer-watson-wins-jeopardy) Jeopardy！2011 年，以及 2016 年谷歌的 [AlphaGo 击败围棋](https://thenewstack.io/google-ai-beats-human-champion-complex-game-ever-invented/)。

但无限注德州扑克是最后的领域。令人惊讶的是，尽管德州扑克相对容易玩，但从人工智能的角度来看，它被广泛认为是最复杂的扑克游戏。首先，一个双人游戏产生 10 ^(160) 种可能的情况。

诚然，扑克机器人至少从 2012 年就已经存在了。你可以[下载你自己的](http://www.cleverpiggy.com)或者在 Google Play 商店购买一个，但这些都是针对更简单形式的扑克。

> 迈克尔·新崎像冰山摧毁泰坦尼克号一样摧毁了仙王座。

[阿尔伯塔大学](https://www.ualberta.ca/)于 2016 年推出了“无敌”[仙王座扑克项目](http://www.washingtonpost.com/news/speaking-of-science/wp/2015/01/08/meet-cepheus-the-virtually-unbeatable-poker-playing-computer/)。 [DeepStack](https://www.technologyreview.com/s/603342/poker-is-the-latest-game-to-fold-against-artificial-intelligence/) 是由来自阿尔伯塔省、 [Charles University](https://www.cuni.cz/UKEN-1.html) 和[捷克布拉格科技大学](http://www.studyatctu.com/)的研究人员联合开发的，它玩限注德州扑克，这种扑克比无限注扑克简单得多，并且在对抗人类方面积累了良好的记录。

[仙王座第一次公开挑战](http://www.slate.com/blogs/future_tense/2015/04/13/i_beat_cepheus_the_unbeatable_poker_playing_artificial_intelligence.html)和 poker pro[Michael Shinzaki](http://pokerdb.thehendonmob.com/player.php?a=r&n=140309)只打了 100 手，Shinzaki 就像冰山推倒泰坦尼克号一样推倒了仙王座。

桑德霍尔姆之前的尝试，叫做克劳迪奥，在 2015 年输给了人类。所以他们丢弃了那台失败的计算机，并从零开始，利用学到的经验创造新的算法。为期 20 天的 120，000 手两人对决无限注德州扑克锦标赛旨在为 Sandholm 和 Brown 提供具有统计意义的数据。在经历了这样一场惨败后，这可能并不必要，但对科学来说却是必要的。

## 电脑现在可以虚张声势了

大量可能的剧本只是问题的一部分。不像国际象棋，危险！，或者 Go，无限注德州扑克被认为是一种不完美的游戏。关于游戏的当前状态，玩家没有相同的信息。这不仅仅是因为牌是未知的，而且在任何一手牌上可以下注的筹码数量都没有限制，虚张声势(本质上是隐瞒信息)是游戏的一个重要组成部分。开发人员正在为不完美的数据集编程。

那么人工智能是如何做到的呢？在比赛之前，Libratus 的算法通过在匹兹堡超级计算中心一台名为 Bridges 的新超级计算机上使用 1500 万个处理器核心小时，在数万亿场游戏中训练自己，帮助建立了一个战略。人工智能本质上没有内置或固定的策略；更确切地说，它使用一种叫做反事实后悔最小化的算法技术的变体来帮助计算策略，IEEE Spectrum 报道。

“我们不写战略，”[桑德霍尔姆在 CMU 报纸](http://www.cmu.edu/news/stories/archives/2017/january/poker-pros-vs-AI.html)上解释道。"我们编写计算策略的算法."在一封电子邮件中，桑德霍尔姆说这些算法是用 C++编写的。

布朗在 Reddit 的 [AMA 上解释说，“我们使用一种分布在大约 200 个节点上的](https://www.reddit.com/r/IAmA/comments/5qi3i9/we_are_professional_poker_players_currently/)[蒙特卡罗反事实后悔最小化(CFR](http://papers.nips.cc/paper/3713-monte-carlo-sampling-for-regret-minimization-in-extensive-games.pdf) )形式。我们还加入了一种基于后悔的剪枝的样本形式，这大大加快了计算速度。”

Libratus 算法适应[纳什均衡](https://en.wikipedia.org/wiki/Nash_equilibrium)。作为博弈理论的基础，纳什均衡本质上说，没有玩家有改变他们策略的动机。布朗在 AMA 期间分享了机器人使用 CFR 的特殊变体进行训练。在比赛之前，它只是从和自己玩扑克中学习。没有使用人手历史。

人工智能还在每手牌中参与“[残局解决](https://www.cs.cmu.edu/~sandholm/Endgame_AAAI15_workshop_cr_1.pdf)”，以确定它在最后几轮下注中承担多少风险，这一技术显然被证明是帮助人工智能占上风的决定性因素。在每天比赛结束时，Libratus 会再次连接到超级计算机上，以便进一步完善其策略。它甚至优先考虑尚未被竞争对手利用的改进。由于它和它的前辈之间的这些差异，Libratus 能够领先，即使是在无限注德州扑克的不确定性下，这种扑克允许两张隐藏的牌和无限大小的赌注。

“例如，人们认为扑克是一种非常人性化的游戏，机器人不会虚张声势。那是完全错误的。布朗解释说:“这不是要读懂你的对手，并试图判断他们是否在撒谎，而是要看牌和概率。”。

除此之外，这次失败与之前人类冠军(如围棋等无懈可击的游戏领域)的失败之间的另一个共同之处是，人类会感到疲惫，并会受到挫折的情绪影响，这反过来会影响他们的整体发挥。

“Libratus 比我们想象的要好得多。这有点令人沮丧，”Les 说，他也在 2015 年与 Claudico AI 比赛。“如果你和人类比赛输了，你可以停下来，休息一下。在这里，我们每天都要在 11 个小时里挨揍。当你不习惯经常失去时，这是一种真正不同的情感体验。”

## 那又怎样？

因此，我们有一个人工智能，它使用机器学习和 C++算法在扑克比赛中击败了一个对手。虽然 Libratus 的胜利是一个巨大的进步，但双手扑克仍然是一个受限制的世界。增加第二个、第三个或第四个玩家会让程序超负荷，所以还有很长的路要走。

那么未来我们能期待什么呢？人工智能研究人员[将他们的目光](http://www.businessinsider.com/ai-vs-humans-in-different-games-2016-11)放在征服其他复杂的战略游戏上，如星际争霸、文明，甚至角色扮演游戏如天际。仍然存在的最大挑战是创造一种适应性强的人工通用智能，它可以像人类一样相对良好地学习和掌握多种类型的游戏，而不是一种。目前，我们只知道在这种扑克变种中击败人类只是这个更大难题的另一部分。

特写:诺姆·布朗在图马斯·桑德霍尔姆的注视下观看人类玩人工智能天平。卡内基梅隆大学供图。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>