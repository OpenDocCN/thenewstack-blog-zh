# 本周节目:考虑所有可能发生的事情

> 原文：<https://thenewstack.io/this-week-in-programming-accounting-for-all-contingencies/>

正如早期计算机科学先驱 Edsger W. Dijkstra 的名言所说，“如果调试是消除 bug 的过程，那么编程就必须是把 bug 放进去的过程。”

本周的一个故事真实地体现了编程的微妙本质，以及在试图创造出一种考虑到所有可能性的东西时所面临的困难。另一个有趣的引语，你可能以前听过，来自计算机科学先驱 Alan Perlis，说到:“有两种方法可以编写没有错误的程序；只有第三个管用。”

这个故事讲的是一个车牌为“不”的人开始收到无数来自停车场公司的罚单。事实证明，当非法停在他们停车场的车辆没有牌照时，服务员只需在表格上写下“不”，意思是“没有牌照”不幸的是，这是一个完美的字符串匹配，但结果出人意料。

[https://www.youtube.com/embed/pIBznKlIOS4?feature=oembed](https://www.youtube.com/embed/pIBznKlIOS4?feature=oembed)

视频

当然，有一些简单的方法来处理这种情况，可以防止这种错误，但是首先需要有避免这种错误的先见之明。在这种情况下，对于一个本来可以完美工作的系统来说，这是个例外。但情况不总是如此吗？

与此同时，一个类似但不完全相关的消息是，另一个故事本周流传开来，一个[赌场的豪赌者数据库通过大厅鱼缸](http://www.businessinsider.com/hackers-stole-a-casinos-database-through-a-thermometer-in-the-lobby-fish-tank-2018-4)中的温度计被盗。虽然这可能不是净化输入的情况，但它似乎属于“考虑所有可能性”的范畴——在这种情况下，连接到网络的任何东西都需要得到保护，否则它就是一个入口。我想这只是一个提醒，因为我们本周看到的一些第一新闻是以一些物联网公告的形式出现的。就这样…

## 本周的节目中

*   **Android Things 8 开发者预览版:**谷歌本周宣布了 [Android Things 发布候选版](http://android-developers.googleblog.com/2018/04/android-things-release-candidate.html)，这是该平台在即将到来的稳定发布之前的最终预览版，现在包括一个功能完整的 SDK。因此，该公司表示，在 1.0 版本发布之前不会再有突破性的 API 变化，所有变化都在[发布说明](https://developer.android.com/things/preview/releases.html)更新 [SDK 参考](https://developer.android.com/things/reference/index.html)中概述。此外，预览版还包括许多新功能，SD times[将其总结为“在发现问题时取消发布当前无线版本的能力，可视化存储布局配置，字体和区域设置管理，以及 Android Things 开发者控制台中对谷歌团队的产品共享支持。”](https://sdtimes.com/iot/android-things-developer-preview-8-launched/)
*   **微软专注于物联网的 Linux 内核:**你没看错——微软已经[构建了自己的定制 Linux 内核](https://techcrunch.com/2018/04/16/microsoft-built-its-own-custom-linux-kernel-for-its-new-iot-service/)。这些很可能是你从未想到会读到的单词(我有点惊讶)，但这是为了进入物联网游戏。[宣布](https://azure.microsoft.com/en-us/blog/introducing-microsoft-azure-sphere-secure-and-power-the-intelligent-edge/)“一种安全的端到端物联网产品，专注于基于微控制器的设备——这种设备使用微小且相对低功率的微控制器(MCU)进行基本控制或连接功能”，这是微软 [Azure Sphere](https://www.microsoft.com/en-us/azure-sphere/) 的一部分。正如 TechCrunch 所指出的，“通常，这类设备，从玩具到家用小工具或工业应用，不会经常更新，因此安全性经常受到影响。”我想这是修复那些可破解温度计的一次尝试。

[https://www.youtube.com/embed/lki7HOOkFjU?feature=oembed](https://www.youtube.com/embed/lki7HOOkFjU?feature=oembed)

视频

*   **AI DIY:**移动修补玩具和钉板套件。去年，谷歌宣布了它的 AIY 项目，本周它又加倍宣布了这个项目，有许多[的重大更新](http://developers.googleblog.com/2018/04/aiy-projects-updated-kits-for-2018.html)，BGR 说这些更新可以[帮助塑造未来](http://bgr.com/2018/04/17/google-diy-ai-kits-vision-kit-voice-kit-aiy/)。该公司的计划包括将这些套件提供给全国各地的 STEM 课程，孩子们可以使用套件中包含的新树莓 Pi Zero WH 进行语音和视觉识别。该公司还为 Android 提供了一款 [AIY 配套应用](https://play.google.com/store/apps/details?id=com.google.android.apps.aiy)以简化设置，并改进了 [AIY 网站](https://aiyprojects.withgoogle.com/)以提供更多信息。不用担心，这些套件没有年龄限制，AIY 语音套件和视觉套件都可以在塔吉特百货公司为您的父母(或只是好奇的成年人)提供。

[https://www.youtube.com/embed/Y8iQJOjw4S4?feature=oembed](https://www.youtube.com/embed/Y8iQJOjw4S4?feature=oembed)

视频

*   **GitHub 开源工具:**在 GitHub 本周发布的几个公告中的第一个，该公司宣布了[面向开源维护者的新工具](https://blog.github.com/2018-04-18-new-tools-for-open-source-maintainers/)，其中包括最小化的注释、流行项目的退役名称空间、新的拉请求需求等等。根据公告，总体意图是通过基本上帮助限制噪音和混乱来简化开源项目的维护，例如可能来自“意外和‘驱车通过’拉请求预防”的噪音和混乱。
*   **GitHub 基于 Bot 的学习实验室:**GitHub 继续努力不仅仅是一个代码存储库和版本控制工具，GitHub 本周宣布了 [GitHub 学习实验室](https://blog.github.com/2018-04-19-introducing-github-learning-lab/)，它称之为“一种经过验证的方法，可以帮助新开发人员在开始他们的软件之旅时保留更多信息并快速提升。”该应用程序使用一个机器人来引导用户通过一系列练习来学习如何使用 GitHub。在发布时，主题包括 GitHub 的介绍，使用 Markdown 进行交流，如何使用 GitHub 页面托管网站或博客，如何将项目迁移到 GitHub，以及如何管理合并冲突。
*   **Git 2.17 带来了错误修复和彩色代码:**GitHub 的最后一个版本， [Git 2.17 现在可用](https://blog.github.com/2018-04-05-git-217-released/)，它修复了一些错误和一个彩色代码功能，可以给移动的代码着色，使其更容易识别。此外，最新版本可以加快 watchman 的状态，并在存储库历史中查找对象。

*   **一个 JavaScript 标准库？**没错，据 InfoWorld 报道， [JavaScript 最终会得到一个标准库](https://www.infoworld.com/article/3268667/javascript/stdllb-roadmap-javascript-will-finally-get-a-standard-library.html)。“以[缺乏大型标准库](https://www.infoworld.com/article/3048833/open-source-tools/brendan-eich-javascript-standard-library-will-stay-small.html)而闻名，”他们写道，“在 JavaScript 标准化进程之外的第三方倡议下，JavaScript 将获得一个功能更多、规模更大的标准库。”根据这篇文章，名为 [Stdlib](https://github.com/stdlib-js/stdlib) 的开源库也将服务于 [Node.js 服务器端 JavaScript 运行时](https://www.infoworld.com/article/3257673/node-js/nodejs-roadmap-whats-next-for-the-javascript-runtime.html)，并将“提供数学、统计、数据处理和流的库集合，它将提供许多标准库所期望的实用程序。”查看这篇文章，了解“2000 多个其他函数”的更多亮点，以及 JavaScript 缺乏标准库的历史。
*   **Twilio 走向无线化:** Twilio 最终转向蜂窝，宣布[可编程无线](https://www.twilio.com/blog/2018/04/twilio-programmable-wireless-ga.html)全面上市。正如 Techcrunch 所指出的，“进入无线领域似乎一直是一个合乎逻辑的下一步，一年前，该公司就这样做了，推出了基于 SIM 卡的可编程无线服务“T21”该公司已经成为寻求添加短信、通知和呼叫等功能的开发者的宝贵工具，现在希望为物联网工作提供同样基于 API 的方法。
*   流行并不代表一切:虽然我们经常查看关于编程语言流行的各种民意调查和指数，以确定下一步该做什么——下一步该学什么，留下什么——一篇关于不受欢迎的编程语言的[可行性的博客文章](https://www.johndcook.com/blog/2018/04/17/unpopular-languages/)提出了一个简单的想法，即流行并不代表一切。“生存能力不仅仅是受欢迎程度，尽管受欢迎程度很重要，”作者写道。“更多的用户意味着更多的人去找 bug、写库、开发工具、回答问题、写教程等。但是社区规模的好处不是线性的。它经历了一种逻辑 S 曲线。对于一种语言来说，当社区足够大时，就有一个阈值大小。在这个门槛以上的某个地方，你开始遭遇收益递减。”
*   **自动化错误查找:**最后，但当然不是最不重要的，(没有什么“最后”是“最不重要的”，嗯？)一个有趣的小工具，当你得到一个编译器错误时，它可以立即获取堆栈溢出结果。名为 [rebound](https://github.com/shobrook/rebound) 的 Python 工具可以在 MacOS、Linux 和 Windows 上工作，并允许您直接从命令行获得相关的堆栈溢出结果，而不必切换到 web 浏览器。我能说什么呢？干净利落。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>