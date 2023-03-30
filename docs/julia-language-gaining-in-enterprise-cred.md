# 茱莉亚语言赢得企业信任

> 原文：<https://thenewstack.io/julia-language-gaining-in-enterprise-cred/>

Julia 编程语言最初是为数学和科学工作负载设计的，随着在中国的迅速采用，它正在一系列企业用户中获得转变。

它最有趣的一个用例:伯克利实验室的 [Celeste 项目](https://www.nextplatform.com/2017/11/28/julia-language-delivers-petascale-hpc-performance/) ，旨在为可见宇宙中的恒星和星系编目所有的望远镜数据。其基于 Julia 的应用程序对 1.88 亿颗恒星和星系进行了 80 亿参数的变分贝叶斯推理分析，仅在 15 分钟内处理了 178 万亿字节的数据。

在最近的[编程语言排名](https://redmonk.com/sogrady/2018/08/10/language-rankings-6-18/)中，Redmonk 分析师 [Stephen O'Grady](https://redmonk.com/team/stephen-ogrady/) 评论了它在过去四个季度的稳步增长，并将其称为值得关注的语言之一。

朱莉娅[于 2009 年在麻省理工学院开始了](https://julialang.org/blog/2012/02/why-we-created-julia)的研究项目，[由计算机科学家](https://www.reddit.com/r/IAmA/comments/97jdb9/weve_spent_the_past_9_years_developing_a_new/)[杰夫·贝赞森](https://github.com/JeffBezanson)、[斯特凡·卡尔平斯基](http://karpinski.org/)、[病毒沙阿](https://www.linkedin.com/in/viralbshah/)和麻省理工学院教授[艾伦·埃德尔曼](http://math.mit.edu/directory/profile.php?pid=63)创建。它作为一家公司被剥离出来，并于 2012 年向公众推出。Julia Computing 公司的首席技术官和联合创始人之一基诺·费舍尔(Keno Fischer )表示，大约在 2015 年，商业用户，尤其是金融服务行业的用户，开始询问它对他们独特工作负载的适用性。

“他们来找我们，希望确保它是稳健的，”他说。

就在这个月，开源项目发布了 Julia 1.0 的[版本](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/57UM5PBFxH763KI2q7632H1fgg/AQyB9QmL4ZrIp3VtRv1R892Q)，Fischer 说，在发布之前的几年里，他们一直在确保健壮性、稳定性和提供企业用户期望的可用性保证的能力。

Fischer 说，虽然传统上，编程语言在高性能和高生产率之间提供了一个艰难的权衡，但它的创造者希望它速度快，并且易于使用。

他解释说，速度快的语言是由计算机科学家设计的，这些人接近硬件，知道如何最大限度地利用硬件。易于使用的语言是由用户、统计学家和科学家设计的。

“朱莉娅团队的优势在于同时拥有这两种人，”他说。

其结果被描述为提供了 C++和 Java 的速度，以及 Python 和 r 的高水平生产率、简单性和易用性。

## 多重调度

菲舍尔说，就创意而言，它最接近于多年前苹果公司开发的迪伦 T1。应用方面，和 Matlab，R，SAS 或者 Python 差不多。它专注于科学界的数学和线性代数能力，除了它被设计成对那些来自科学背景的人来说“不可怕”的编程。

其核心原理是[动态多重调度](https://docs.racket-lang.org/multimethod/index.html)，其中函数或方法可以基于运行时类型或其他一些属性被动态调度[。](https://en.wikipedia.org/wiki/Dynamic_dispatch)

费舍尔是这样解释的:

如果我在代码中写 A + B，在动态语言中，A 和 B 可能是很多东西——数字、矩阵、字符串、数据库对象——各种复杂的东西。但是 plus 的意思是上下文同时依赖于 A 和 B，如果 A 和 B 都是数，你就把它们加在一起。但如果 A 是一个数，B 是一个矩阵，就没那么简单了。寻找最佳的执行方式被称为多重分派。

“这是一种非常适合表达数学概念的范式，”费舍尔说。“然后通过优化过程，我们从这些模型分派声明中提取静态类型信息，并使用这些信息来优化代码，就像静态编译器一样。”

Julia 依赖于一个复杂的类型系统。

“Julia 有非常丰富的类型概念，你可以在运行时选择……最重要的是，这些是你可以操作的语言中的一级对象，”他说。“你可以把它们传来传去，你可以转换它们，你可以对它们进行操作，你可以对它们进行注释。这些字体是茱莉亚最深思熟虑和最关键的创新之一。”

回到直观和静态路径语言，他解释说，“你不能把静态语言变得更快，应用到传统动态语言的原因是动态语言没有足够的静态信息来利用这些技术。这是一个关键的事情，为什么在朱莉娅中不是这样，因为类型系统。类型系统允许我们静态地推理 Julia 程序的行为，将这些信息提供给编译器，让它快速生成代码。”

## 在中国很大

700 多名志愿者为 1.0 版本做出了贡献。其特点包括:

[https://www.youtube.com/embed/1jN5wKvN-Uk?feature=oembed](https://www.youtube.com/embed/1jN5wKvN-Uk?feature=oembed)

视频

它在发布后的两周内在 140 多个国家被下载，其中 34%的茱莉亚下载 T2 页面的独立访问者来自中国。

Julia 正被用于驱动[自动驾驶汽车](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/NdpaLIf2Hp2VpcZ4TK892g9g/AQyB9QmL4ZrIp3VtRv1R892Q)、[机器人](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/LwxQ763APdeBky892FOzqNdtRA/AQyB9QmL4ZrIp3VtRv1R892Q)、 [3D 打印机](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/tEnDilUDpem64IJkHxsTwA/AQyB9QmL4ZrIp3VtRv1R892Q)以及在[精准医疗](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/wT7637FsWCt82CXSzk4Jvn8g/AQyB9QmL4ZrIp3VtRv1R892Q)、[增强现实](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/APY7kPNfStDUFzJ17892t7Wg/AQyB9QmL4ZrIp3VtRv1R892Q)、[基因组学](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/uuBPKrVVg763ycPRkj2yCkyg/AQyB9QmL4ZrIp3VtRv1R892Q)、[能源交易](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/3sxMhZu3V892UljlBkAyh4Bw/AQyB9QmL4ZrIp3VtRv1R892Q)、[机器学习](https://newsletter.juliacomputing.com/sendy/l/sb5nVGtyyfItaxsCiD3Xtg/BUiLoVTFf892DUr7T4Xp64Fg/AQyB9QmL4ZrIp3VtRv1R892Q)、金融风险管理和太空任务规划中的应用。它被用于政府机构，包括联邦航空管理局，美联储和其他机构；贝莱德、英杰华、花旗银行、美国银行等金融服务公司；包括谷歌、亚马逊、脸书和优步在内的硅谷公司。

Julia Computing 公司在 Julia Pro 中提供了受支持的 Julia 版本，以及针对金融服务、数据库和时序工作负载等的特定产品。菲舍尔说，它将在未来几个月整合其产品。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>