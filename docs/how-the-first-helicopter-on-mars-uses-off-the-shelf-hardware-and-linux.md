# 火星上的第一架直升机如何使用现成的硬件和 Linux

> 原文：<https://thenewstack.io/how-the-first-helicopter-on-mars-uses-off-the-shelf-hardware-and-linux/>

据《科学美国人》报道，近 50 艘宇宙飞船已经被送往火星。据说这是我们所知的唯一一个完全由机器人居住的星球。

但是这个月，随着人类继续探索，不屈不挠的漫游者着陆，开源爱好者欢呼火星也成为 Linux 走向世界统治的第二个星球。开源操作系统是一个项目的关键部分，该项目可能成为有史以来第一架从火星表面起飞的飞机。

这是一个鼓舞人心的巨大复杂工程的例子，它承载着人类最好的技术，也承载着人类最好的希望。

[https://www.youtube.com/embed/gAoxsUYn00E?feature=oembed](https://www.youtube.com/embed/gAoxsUYn00E?feature=oembed)

视频

## 火星的风

这项任务已经为[带来了有史以来第一份来自火星](https://www.nasa.gov/press-release/nasa-s-mars-perseverance-rover-provides-front-row-seat-to-landing-first-audio)的声音录音。根据美国宇航局的一份新闻稿，“在 60 秒记录的大约 10 秒钟内，可以听到几秒钟的火星微风，以及火星车在表面运行的机械声音。”周四，美国宇航局分享了毅力号火星车特殊桅杆安装的变焦相机 [Mastcam-Z](https://www.planetary.org/outreach/mastcam-z-partnership) 的现场镜头，该相机不仅可以生成彩色图片，还可以生成 3D 和立体图像。

但是坚忍号火星车还搭载了一位特殊的乘客——一个被美国宇航局命名为“独创性”的小型飞行机器人。现在，美国国家航空航天局[将](https://www.nasa.gov/feature/jpl/nasa-s-mars-helicopter-reports-in)描述为“附在坚持号火星车的腹部”,它将在接下来的一两个月里留在那里，同时火星车[寻找合适的地点将其放下。“它的身体有一盒纸巾那么大，”IEEE Spectrum](https://mars.nasa.gov/technology/helicopter/) 的[解释道，重量只有 1.8 公斤(不到 4 磅)。虽然美国国家航空航天局估计“坚持不懈”任务的成本为 24 亿美元，但只有 8000 万美元用于“创新”直升机(另有 500 万美元用于运营)。](https://spectrum.ieee.org/automaton/aerospace/robotic-exploration/nasa-designed-perseverance-helicopter-rover-fly-autonomously-mars)

但是美国国家航空航天局的喷气推进实验室自豪地称其为“人类送往另一个星球的第一架飞机”上周六，直升机向火星轨道飞行器报告说[它在着陆](https://mars.nasa.gov/news/8867/nasas-mars-helicopter-reports-in/)中幸存下来，并像预期的那样使用部分充电的电池运行，就像它在毅力漫游者上的基站一样。

毅力最终会变得自主——在某种程度上。地球到火星的通讯可能需要至少 4 分钟——或长达 21 分钟，这取决于行星在其轨道上特定点的距离。因此，当它的重要时刻到来时，独创性将通过分析自己的下方地形图像以及来自自己传感器的数据(如它的行驶速度)来保持其预编程的飞行路径，而无需任何来自地球的实时输入。IEEE Spectrum 采访了美国宇航局喷气推进实验室火星直升机操作团队的负责人蒂姆·坎汉姆，他解释说“几十个特征被逐帧比较，以跟踪相对位置，从而计算出方向和速度，这就是直升机导航的方式。”

虽然如果一个传感器坏了，“直升机真的有一个响应，那就是采取最后传播的状态，并试图着陆，然后告诉我们发生了什么，并等待我们处理它。”

![NASA on YouTube - Mastcam-Z event on Thursday (edge of the crater delta) cropped pic](img/10a326ab3c03cfefce2cc97b3b655057.png)

虽然火星的重力大约是地球重力的三分之一，但直升机的设计者还必须做出调整，以适应稀薄的火星大气——密度仅为地球的 1%。美国国家航空航天局的一篇博客文章[解释说](https://solarsystem.nasa.gov/news/472/10-things-mars-helicopter/)尽管直升机的坚硬叶片足足有 4 英尺宽(约 1.2 米)，“在每分钟 2800 转的速度下，它的旋转速度大约是地球直升机的 10 倍。”美国宇航局还指出，直升机“在火星大气中盘旋的每一秒钟都需要 360 瓦的电力”(相当于 6 个灯泡所需的电力)。但是大部分来自直升机太阳能电池阵列(位于旋翼叶片上)的能量将仅仅用于保暖。

美国宇航局网站[补充道](https://www.jpl.nasa.gov/news/nasas-mars-helicopter-reports-in)“如果独创性能熬过它在火星上的第一个刺骨的夜晚——那里的温度低至零下 130 华氏度(零下 90 摄氏度)——这个团队将继续在另一个世界进行飞行器的首次飞行。”

## Linux 板载

但是对计算机爱好者来说更有趣的是:坚持依赖于 Linux。

“据我所知，以前没有人使用过 Linux，肯定是在以前的漫游者上，”Canham [告诉 PC 杂志](https://www.pcmag.com/news/linux-is-now-on-mars-thanks-to-nasas-perseverance-rover)。据该杂志报道，即使是毅力漫游者也在使用风河公司专有的 VxWorks 操作系统，该系统也用于过去的一些漫游者——但坎汉姆告诉他们，他们需要 Linux 才能与骁龙 801 板一起使用。“这绝对是 Linux 的胜利。”

它还使用了 F(发音为“F Prime”)，这是一个 JPL 生产的“组件驱动框架，能够快速开发和部署太空飞行。”F Prime 可通过 GitHub 库获得，该库列出了它的组件，包括“一个将飞行软件分解成具有良好定义接口的离散组件的架构”和“一个提供核心功能如消息队列和线程的 C++框架”(尽管也有几个 Python 依赖)。

坎汉姆告诉 IEEE Spectrum，“这是一种开源的胜利，因为我们正在运行开源操作系统和开源飞行软件框架——如果你有一天想自己做这件事，你可以从货架上购买商业部件。”

## 高风险，高回报

美国宇航局认为这项任务是“高风险、高回报的技术展示”，根据其创作的一部令人印象深刻的动画:

[https://www.youtube.com/embed/vnH4yD0s8QM?feature=oembed](https://www.youtube.com/embed/vnH4yD0s8QM?feature=oembed)

视频

该机构主要只是想回答一些基本问题:比如它能在火星大气中起飞——以及它能成功着陆。根据美国宇航局的说法，如果它仍然可行，他们将尝试“最多四次以上的飞行”——每次飞行[比上一次](https://solarsystem.nasa.gov/news/472/10-things-mars-helicopter/)更远一点。美国国家航空和宇宙航行局预计“飞行时间长达 90 秒，每次飞行距离近 980 英尺(300 米)，距离地面约 10 到 15 英尺。”

但坎汉姆向 IEEE Spectrum 暗示，30 天内的首次飞行可能只是开始。“根据前三个的速度，我们可能有一周左右的时间来尝试一些更具异国情调的东西。”

然而，另一份美国宇航局的简报指出，它也展示了小型化飞行技术的实用性——缩小的机载计算机和电子设备减轻了负载。“由于独创性被归类为技术演示，JPL 愿意接受更多的风险，”坎汉姆向 IEEE Spectrum 解释道。“所以我们基本上走出去，使用了许多现成的消费类硬件。”坎汉姆补充说，尽管关键的航空电子部件是抗辐射的，但它使用的是普通的手机级惯性测量单元，其处理器板只是高通的手机处理器骁龙 801。

“但具有讽刺意味的是，因为它是相对现代的技术，它比火星车上搭载的处理器强大得多……因为我们需要它，坎汉姆说。”我们的导航回路以 500 赫兹的频率运行，以保持对我们正在飞行的大气层的控制。最重要的是，我们正在捕捉图像和分析特征，并以 30 赫兹的频率逐帧跟踪它们。"

坎汉姆告诉该网站，它使用的是他们从开源硬件网站 SparkFun Electronics 在线购买的激光高度计。NASA 的一个网页上解释说“这种相机和你的手机相机一样好”。配备了 1300 万像素的相机，“工程师们将试图拍摄大量的好照片。”

美国宇航局指出，毅力号还为[携带了一个特殊的标语牌，上面有 10，932，295 个名字](https://mars.nasa.gov/news/8634/109-million-names-now-aboard-nasas-perseverance-mars-rover/)，“通过电子束印刷在三个指甲大小的硅片上”

但是也许这次任务的精神最好地被[抓住了，一条特殊的信息](https://mars.nasa.gov/resources/25646/mars-decoder-ring/)美国宇航局用降落伞的颜色进行编码，减缓了登陆艇降落到火星表面的速度。降落伞的橙色部分代表二进制代码中的 1，而黄色部分代表 0。(于是字母“A”就变成了黄色-黄色-黄色-黄色-黄色-黄色-橙色。)

信息是什么？降落伞外环的颜色为美国宇航局位于加州帕萨迪纳的喷气推进实验室的 GPS 坐标编码。但是内环编码了 1889 年西奥多·罗斯福演讲中的一句话，这句话后来成为 JPL 的官方座右铭。

"勇敢面对强大的事物"

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>