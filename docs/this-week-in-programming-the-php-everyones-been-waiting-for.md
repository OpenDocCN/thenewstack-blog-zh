# 本周编程:人人都在等待的 PHP

> 原文：<https://thenewstack.io/this-week-in-programming-the-php-everyones-been-waiting-for/>

不知何故，我没有不尊重的意思，我想象微软作为一个整体，上周在亚马逊网络服务公司为其年度 re:Invent 用户大会进行展示时，有点畏缩。以至于 TechCrunch 的罗恩·米勒忍不住断言 [AWS 想要统治世界](https://techcrunch.com/2018/12/02/aws-wants-to-rule-the-world/)，指出“去年，AWS 宣布了令人震惊的 1400 项新功能，据说他们今年将超过这个数字。”

本周，微软与 [Microsoft Connect()上演了自己的秀；](https://www.microsoft.com/en-us/connectevent/)尽管它没有发布任何机器人或卫星即服务级别的公告，但从[开始，它们为开发者提供了大量新功能。NET Core 3 预览版](https://aka.ms/netcore3preview1)到[云原生应用捆绑](/microsoft-cnab-simplifies-container-deployment-to-distributed-applications/)到 [Azure 数据库 for MariaDB](https://aka.ms/mariadbga) 。不过，就我们的资金而言，它是围绕 Visual Studio、Azure 函数语言支持以及一些关于机器学习的公告，我们认为您可能想听听，所以我们将从那里开始。

首先，微软向[提供了 Visual Studio 2019](https://aka.ms/vs-preview) 的完整预览版，该公司在[的一篇博客文章](https://blogs.msdn.microsoft.com/visualstudio/2018/12/04/making-every-developer-more-productive-with-visual-studio-2019/)中表示，“专注于几个关键领域，如[让打开和使用存储在 g it 存储库中的项目更快](http://code.visualstudio.com/blogs/2018/12/04/rich-navigation)，[用人工智能](https://blogs.msdn.microsoft.com/visualstudio/2018/12/05/visual-studio-intellicode-supports-more-languages-and-learns-from-your-code/) (AI)(一种我们称为 Visual Studio IntelliCode 的功能)改善智能感知，并通过集成 Live Share 让与队友的协作更容易。”具体到 IntelliCode，Visual Studio 中的语言支持正在增加，随着 [C++](https://blogs.msdn.microsoft.com/vcblog/2018/12/05/cppintellicode/) 和 XAML 加入 C#，在 Visual Studio 代码支持中对于 [TypeScript/JavaScript](https://aka.ms/tsintellicode) 和 [Java](https://aka.ms/vsicjava) 加入 Python。

[https://www.youtube.com/embed/9XE8kOI5JTk?feature=oembed](https://www.youtube.com/embed/9XE8kOI5JTk?feature=oembed)

视频

对于那些喜欢无服务器的人来说，你会很高兴听到 Azure Functions 现在为 Python 和 JavaScript 开发者提供了更好的支持。随着这一宣布，Azure Functions 对 Python 和 JavaScript 的支持在公共预览版中可用，同时“Azure Functions 运行时的 [JavaScript 持久功能扩展](https://docs.microsoft.com/ga-ie/azure/azure-functions/durable-functions-install)正式可用，现已准备好用于生产工作负载。”

最后但并非最不重要的是，本周微软发布了专注于机器学习的公告，其中包括 ML.NET 0.8 的[到来和 Azure 机器学习服务](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-ml-net-0-8-machine-learning-for-net/)的[全面可用。据帖子称，ML.NET 0.8 版本“专注于增加对推荐场景的改进支持，以功能重要性的形式进行模型解释，通过预览内存数据集进行调试，以及缓存、过滤等 API 改进。”](https://azure.microsoft.com/en-us/blog/azure-machine-learning-service-a-look-under-the-hood/)[与此同时，Azure 机器学习服务](https://azure.microsoft.com/en-us/services/machine-learning-service/)希望“简化和加速构建、训练和部署机器学习模型的过程”，这似乎与 Azure 试图通过自动化来简化应用程序的构建和部署非常相似。

来自[的公告](https://azure.microsoft.com/en-us/blog/azure-machine-learning-service-a-look-under-the-hood/):“自动化机器学习使所有技能水平的数据科学家能够更快地识别合适的算法和超参数。对 PyTorch、TensorFlow 和 scikit-learn 等流行开源框架的支持允许数据科学家使用他们选择的工具。DevOps 的机器学习功能通过支持实验跟踪和管理部署在云和边缘的模型，进一步提高了生产力。所有这些功能都可以从任何地方运行的任何 Python 环境中访问，包括数据科学家的工作站。"

所以，也许还没有机器人和卫星，但微软这次肯定取得了进展。现在，对于那些对微软不是特别感兴趣的人来说，有一些过去一周的其他公告和新闻。所以，事不宜迟…

## 本周的节目中

*   你说的是 Visual Basic 吗？没错，SD Times 注意到[微软的 Visual Basic。NET 使 TIOBE 成为本月排名前五的编程语言](https://sdtimes.com/msft/microsofts-visual-basic-net-makes-tiobe-top-5-programming-languages/)，这是一种经常被认为是“为开始学习编程的人准备的玩具语言”的语言的最高排名 Java，C，Python，C++领衔当月排行榜，Visual Basic。净四舍五入前五名。据 [TIOBE Index 博文](https://www.tiobe.com/tiobe-index/)，“微软正在通过停止与 C#的共同进化策略，慢慢告别 Visual Basic。所以我认为 Visual Basic 目前的受欢迎程度迟早会再次下降。”
*   **谷歌 iOS/Android Flutter UI 工具包推出 1.0:** 这是为你的移动开发者准备的——谷歌本周宣布了 [Flutter 1.0](http://developers.googleblog.com/2018/12/flutter-10-googles-portable-ui-toolkit.html) ，这是该公司“从单一代码库为 iOS 和 Android 创建漂亮的原生体验的 UI 工具包”的第一个稳定版本。该版本的 [ProgrammableWeb](https://www.programmableweb.com/news/flutter-10-now-available-google/2018/12/04) 解释道，“Flutter 旨在解决开发人员今天面临的问题，这要求他们两次构建同一个应用程序，或者使用即插即用的代码模块，从而降低体验。这种新工具通过原生 ARM 代码为 Android 和 iOS 提供硬件加速的图形和用户界面。”除了稳定版之外，包括 Square、2Dimensions 和 [Nevercode](https://nevercode.io/) 在内的几家合作公司也宣布了配套版本，例如用于 Square 的[两个新的 Flutter SDKs、](https://squareup.com/flutter) [Flare](https://medium.com/2dimensions/flare-launch-d524067d34d8) ，一个用于创建可嵌入矢量动画的工具，以及 [Codemagic](https://codemagic.io/) ，一个用于自动构建和打包 Flutter 应用程序的工具。

[https://www.youtube.com/embed/REJDzio_h7o?feature=oembed](https://www.youtube.com/embed/REJDzio_h7o?feature=oembed)

视频

*   Rust 发布了…一些东西:我们[在二月份第一次写了 Rust 2018](https://thenewstack.io/week-programming-rusts-roadmap-epoch-release/) ，现在这一天终于到来了——Rust 团队宣布了 [Rust 1.31 和 Rust 2018](https://blog.rust-lang.org/2018/12/06/Rust-1.31-and-rust-2018.html) 。问题是，这两件事到底是什么还不清楚，以至于公告本身附带了一个解释者的博客帖子，简单地说——[Rust 2018 来了……但它是什么？](https://hacks.mozilla.org/2018/12/rust-2018-is-here/) Rust 1.31，你看，增加了“未来三年开发所需的所有突破性变化(比如增加新的关键词)，而 Rust 2018 是“某种程度上，但不是真正的”Rust 的新版本。正如 Rust 团队的林·克拉克解释的那样，“在大多数其他语言中，当一个新版本的语言出现时，任何新的特性都会被添加到这个新版本中。以前的版本没有新功能。锈版不一样。这是因为语言进化的方式。几乎所有的新功能都与 Rust 100%兼容。它们不需要任何突破性的改变。这意味着没有理由限制他们使用 Rust 2018 代码。”如果你仍然感到困惑(我们预计你可能会)，点击进入[完整的解释者](https://hacks.mozilla.org/2018/12/rust-2018-is-here/)，因为它不仅包含文字，还包含简洁的图形，以准确显示 Rust 版本的情况。
*   **你们一直在等待的 PHP:**本周我们得到了[PHP 7.3](http://php.net/releases/7_3_0.php),[带来了 C 内嵌、代码可读性和速度改进](https://www.techrepublic.com/article/php-7-3-brings-c-inlining-code-readability-and-speed-improvements-to-the-programming-language/)。根据 TechRepublic 的报道，“广泛使用的服务器端 web 开发语言的最新更新于周四发布，带来了一些新功能、现代化和适度的速度改进。对于那些在 2015 年之前由于性能问题和实现挫折而放弃 PHP 的程序员来说，7.x 分支为该语言带来了里程碑式的可用性和速度改进，7.3 版对此进行了大幅改进。”他们写道，最大的改进之一可能是包含了外来函数接口(FFI)，它允许 PHP 开发人员在 PHP 脚本中运行内联 C 代码。所以，PHP 开发人员，向前迈进，设计网页！同时，不要忘记，要像 1999 年一样[保护你的网站！](https://blog.npmjs.org/post/180765575005/securing-your-site-like-its-1999)

https://twitter.com/arlogilbert/status/1069823967786123264

特征图片:[新老股](https://nos.twnsnd.co/post/180894705470/carl-gwantry-collection-image)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>