# 一个开发者如何将维基百科转变成文本冒险

> 原文：<https://thenewstack.io/one-developer-converted-wikipedia-text-adventure/>

你听说过互动小说吗？上周，[凯旺·戴维斯](http://www.kevan.org)，一位伦敦的网络开发者和游戏设计师，展示了可能是“交互式非虚构作品”的第一个实例，发布了一个基于互联网自己的百科全书的文本冒险游戏。

模仿几十年前经典文本冒险电脑游戏的界面，《[维基百科:文本冒险](http://kevan.org/wikitext/)》使用 JavaScript 创建了一个庞大的环球旅行体验，只使用来自[维基百科页面](https://www.wikipedia.org/)的描述。

戴维斯告诉 VentureBeat “我总是喜欢当你从一个新的角度看待它或者将它放入一个它并没有真正打算的框架中时，相同的数据会有多么不同的感觉。“维基百科总是一个巨大的链接兔子洞，文本冒险添加了一些不太存在的链接，这是一种偶然进入历史片段的方式，这些片段就在熟悉的东西旁边，而不会与它有任何联系。”

每次你重新加载戴维斯的网页，你会得到一个新的旅程开始地点的选择。例如，有[泡泡糖小巷](http://kevan.org/wikitext/Bubblegum_Alley)，“加州圣路易斯奥比斯波市中心的一个旅游景点，因其在小巷墙上堆积用过的泡泡糖而闻名。”或者是[大香蕉](http://kevan.org/wikitext/Big_Banana)，“澳大利亚新南威尔士州科夫斯港市的一个旅游景点和游乐园。”你甚至可以从[拥有自己的树](http://kevan.org/wikitext/Tree_That_Owns_Itself)开始你的旅程，这是一棵佐治亚州雅典的白橡树，根据当地的传说，它被授予对自己和其底部八英尺内所有土地的合法所有权。

https://twitter.com/alexhern/status/880751486132781056

据 Ars Technica(T1)报道，戴维斯有几个最喜欢的出发点值得推荐——比如 T2 普里皮亚季(T3)，乌克兰北部的鬼城，位于 1986 年被疏散的切尔诺贝利核电站附近。从那里你可以向北去废弃的[文化宫](http://kevan.org/wikitext/Palace_of_Culture_Energetik)，向东去城市的一个废弃的室内游泳池，或者向南去 Yaniv 村的[废弃的乌克兰火车站](http://kevan.org/wikitext/Yaniv_railway_station)。

但为了更愉快的冒险，我决定在迪士尼乐园开始我的想象之旅[，在那里我发现我的选择包括向北去](http://kevan.org/wikitext/Disneyland)[魔法提基室](http://kevan.org/wikitext/Walt_Disney's_Enchanted_Tiki_Room)——不出所料，这是“一个借鉴美国提基文化的伪波利尼西亚主题音乐电子动画秀。”从那里开始，下一站的选择包括“[穿越内部空间的冒险](http://kevan.org/wikitext/Adventure_Thru_Inner_Space)”和“[孟山都未来之家](http://kevan.org/wikitext/Monsanto_House_of_the_Future)”，根据它的描述，实际上在 1967 年就关闭了。

## 环球旅行

但是脚本如何决定在哪里定位它的位置呢？当用户在提示符下键入“about”时，地图会从维基百科 API[中实时调出。该脚本过滤了指定地理位置的维基百科文章——如果两个地方有相同的位置，它们会被随机放置在附近。游戏网站解释说:“如果你无法找到一个特定的地方，即使它有一篇文章，那么要么维基百科不知道它的坐标(在这种情况下，你可以通过添加它们来帮助维基百科)，要么它没有与 API 共享它们。”](https://www.mediawiki.org/wiki/API:Main_page)

戴维斯的维基百科文本冒险仍然有一些奇怪的小故障。例如，键入一个州的名称显然会将您带到其地理中心，对于许多州来说，这里并不总是有很多附近的地标可以参观。当我输入“ [go Texas](http://kevan.org/wikitext/Texas) ”时，唯一可能的行进方向是向南，到达[北部混杂的草原](http://kevan.org/wikitext/Northern_mixed_grasslands)。从那里，唯一可能的方向是……向北，到德克萨斯。

https://twitter.com/markcr63/status/881126951200731136

Ars Technica 报道称，该项目源于 2015 年为“全国小说创作月”创作一部小说的尝试，[从维基百科的 API](https://github.com/kevandotorg/nanogenmo-2015) 中提取文本。小说中的一句台词:“我们漫步到大象城堡地铁站。想象一下，当我得知它于 1890 年 7 月 25 日获得批准时，我是多么惊讶！路路通问我是否收到了一份私人法案，将提交给议会，建造 BS & WR，但我不知道。贝克鲁线似乎很方便……”

Davis [告诉 Mashable](http://mashable.com/2017/06/30/wikipedia-the-text-adventure/#R7iIYM.wogqm) “我一直很有兴趣看看还能对大型、有组织的数据集做些什么，事实上维基百科的 API 可以提供世界各地的坐标和位置摘要，这非常适合一步一步地探索。”"维基百科给出了历史事件和长期拆除的建筑的坐标，所以会有很多意外发现."

就像在文本冒险中一样，在你的维基百科页面的主题前输入“检查”也会调出更多关于你所在位置的细节。当然，它来自维基百科页面的下一段。键入“wiki”将从维基百科中调出原始页面，而键入“edit”后，页面主题将带您进入您在维基百科上编辑该页面的页面。输入“语言”会给你从维基百科的非英语版本切换到页面的指示。你甚至可以通过在主题前加上“go”来跳转到维基百科中的特定页面

因为维基百科的内容是在知识共享署名-共享许可下创建的——这允许创建衍生作品——所有的文本和图像对戴维斯的游戏都是免费的。

游戏的许多“位置”也显示一张图片——维基百科页面的主图片(除非那张图片是 SVG 文件，游戏拒绝它，因为它“总是一张无聊的地图或标志”)。显然还有一些隐藏的特征。“移动用户也可以点击摘要中的关键词，”[报道*Ars Technica*T3，“这不是很酷，但它是一个受欢迎的选择。”](https://arstechnica.com/gaming/2017/07/a-programmer-turned-wikipedia-into-a-classic-text-adventure/)

戴维斯[还告诉 Mashable](http://mashable.com/2017/06/30/wikipedia-the-text-adventure/#R7iIYM.wogqm) 有一个复活节彩蛋的小捷径“如果你知道这个神奇的单词”虽然我还没有找到它，但我确实发现，键入 1976 年原版游戏“[巨大洞穴探险](http://rickadams.org/adventure/)”——“xyzzy”——中的神奇单词会带你到游戏中的页面。

虽然旅行冒险很有趣，但“维基百科:文本冒险”不可否认缺乏行动。“这里明显缺乏雪人/牛仔/外星人引发的危险，”伦敦人开玩笑说。“但这是一种探索这座城市的可爱方式——再加上严重像素化的图像为拍摄过程增添了一些 80 年代的气息。”

大卫向 Ars 承认他从来没有添加一个明确的任务。“人们似乎对自己的探索已经有了足够的乐趣——试图从家乡遥远的角落回家，在不同城市的两个地标之间行走，或者收集特定的宝藏或奇珍异宝，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>