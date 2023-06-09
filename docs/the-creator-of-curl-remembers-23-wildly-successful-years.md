# Curl 的创建者记得 23 年非常成功的岁月

> 原文：<https://thenewstack.io/the-creator-of-curl-remembers-23-wildly-successful-years/>

[Daniel Stenberg](https://daniel.haxx.se/) 是无处不在的 [cURL](https://curl.se/) 数据传输实用程序的原创者、长期维护者和首席开发者，该程序最初只有 300 行 C 代码，后来发展成为详细的数据传输库中超过 172，000 行代码，在全球数十亿个应用程序中使用。

本月，在 curls 的 23 周年纪念日，他回顾了一生快乐发展的时光。

在瑞典斯德哥尔摩南部的赫丁格市(Stenberg 以支持商业 curl 为生)，Stenberg 在[的一篇周年博客文章](https://daniel.haxx.se/blog/2021/03/20/curl-is-23-years-old-today/)中写道，libcurl“随着时间的推移已经发展成为事实上的互联网传输 API。”

“今天，在它 23 岁生日的时候，这仍然是我如何看待我在 curl 上的工作的主要焦点和我在这里要做的事情，”他写道。

经过几十年的改进，它的各种库现在支持超过 26 种不同的传输协议，并支持许多定制。(举个例子，curl 现在可以用 43 个不同的 TLS 库构建。)其被广泛认可的地位使其成为各种应用程序的首选组件，这些应用程序在其生命周期的某个时刻需要可靠地传输数据，Stenberg 写道，curl 捆绑在顶级发行版和操作系统中(包括 Mac OS X 和 Windows 10，以及 iOS、Android 和各种 Linux 发行版)。

但是这仅仅是开始，Stenberg 指出。几个主要的应用程序(包括 YouTube、Skype、Instagram、Spotify 和网飞)都捆绑了自己独立的 curl 版本，这意味着许多智能手机实际上都安装了多个 curl。Curl 还用于任天堂 Switch、Xbox 和索尼 PS5 等游戏机，以及顶级视频游戏，包括《侠盗猎车手 V》、《堡垒之夜》和《红色死亡救赎 2》。它甚至出现在 Roku 和 Apple TV 这样的机顶盒中，所以 Stenberg 估计它出现在“大约 5 亿台电视中”

他还统计了来自主要品牌的至少 22 种不同的“智能汽车”,这些汽车使用 libcurl 与汽车来回传输数据。你也可以在物联网设备中找到 cURL，包括打印机、智能手表、媒体播放器和医疗设备——所以 Stenberg 估计安装了 cURL 的设备总数超过 100 亿。

甚至在你考虑到它也在大多数互联网服务器中使用，并且是 PHP 的默认传输引擎之前…

但是，尽管花了一点时间来承认它最终在哪里结束，Stenberg 也分享了一些关于这一切是如何开始的有趣的一瞥。他网页上的另一篇简介甚至分享了他在 20 世纪 80 年代初在朋友的 Commodore 64 上第一次发现“计算机的乐趣”的回忆。“我在 Basic 中输入数据集，我们在他那里急切地阅读了一些最早的 C64 杂志，从那以后我就迷上了。”

## 一个年轻程序员的肖像

14 岁的斯滕伯格和他的弟弟比约恩省吃俭用，以便在 1985 年购买他们的第一台 Commodore 64。但在学习了基本编程语言后不久，他意识到所有酷的东西都是用汇编语言编写的，并加入了制作短小精悍的视听节目的繁荣的[演示亚文化的一部分。“这是我开始用业余时间编程的时候。每天长达几个小时。](https://en.wikipedia.org/wiki/Demoscene)

“这是我从未停止过的事情，自从…”

斯坦伯格申请了大学——直到命运的安排，他接受了 IBM 的一份工作。在那里，他第一次接触了 Unix 和 C 编程语言——主要是通过阅读各种 Unix 工具的文档手册页来学习——最终，Stenberg 成为了一名全职 C 开发人员，后来成为了一名嵌入式系统顾问。

但是，他和一个朋友一起为 Amiga 构建了一个文本编辑器，以及一个专用的、受 Emacs 启发的脚本语言，他用它来驱动 IRC 聊天频道上的一个机器人——这是一个决定性的项目，curl 最终由此诞生。Stenberg 想让人们查询这个机器人，将价格从一种货币转换成另一种货币。他找到了在线工具“httpget”(最初由 Rafael Sagula 在巴西创建)来执行定期查询，Stenberg 记得，随着时间的推移，他“或多或少地成为了 httpget 项目的领导者”——这个项目他更名了几次，因为它的功能演变成了他今天仍在维护的软件。“当时做的一些小而迅速的决定，后来对我的生活产生了重大影响并塑造了我的人生。从那以后，卷发就成了我的主要爱好之一——当然，从几年前开始，这也是我的一份全职工作。”

![creenshot of Daniel Stenberg announcing new version of curl - next release](img/647e84af107b2ed7dafaf039a6c2ae14.png)

虽然 curl 作为命令行工具仍然很受欢迎，“我当然怀疑会有一些程序和系统能够从将 curl 的强大功能应用到它们的应用程序中获益，而将 curl 作为一个库将会实现这一点。”

到 1998 年，它的网站吹嘘这个工具已经被下载了“超过 300 次”“对于这个项目和工具，我从来没有任何征服世界的想法或蓝天般的愿景。我只是想让它能更好、更快、更可靠地进行互联网传输，这就是我努力实现的目标。”Stenberg 记得早期的时候，curl 只有 2200 行代码和 7 个贡献者。即使在六年之后，贡献者的总数也不到一百。

但是现在，他自豪地领导着一个蓬勃发展的志愿者开发人员社区——超过 2300 人在项目的整个生命周期中贡献了代码。

## 做大

大约在 2004 年，Stenberg 向瑞典的互联网基金会申请资助，以“在 curl 上有一些集中的开发时间”，后来又从 Adobe 那里得到了一些资助，将 SFTP 的支持带给 curl。从那以后，它一直很强大，现在有了赞助和捐款的支持。(尽管他最近转发了一个似乎是视觉隐喻的东西。)

curl 网站现在每月提供 15.6TB 的数据。

多年来，有 2348 名贡献者，Stenberg 在他的博客文章中写道，以及 6787 个错误修复。这么多年过去了，他仍然对贡献者社区心存感激——也许将它视为早期程序员价值观的回声。“我使用了这么多开源软件，我想和其他开源作者一样酷，”Stenberg 在 2019 年的一篇堆栈溢出帖子中回忆道。“由于它是开源的，数以千计的人在过去的几年里帮助了我们，并改进了产品、文档、网站和项目的几乎所有其他细节。”

临近其 23 周年纪念日，Stenberg 在推特上发布了[关于 curl 的 23 个不同的统计数据](https://twitter.com/bagder/status/1372156259546193920)。

本月早些时候，Stenberg 的作品获得了 GitHub 的特别表彰。他们给 Stenberg 邮寄了他自己的 2020 年 GitHub 贡献图——用 3D 打印机转换成钢铁雕塑。“你的辛勤工作、关心和关注没有被忽视，”他们在一封附带的信中写道，并补充说，这座雕塑“讲述了一个只有你才能真正理解的个人故事……”

![](img/68a220ff5c14634ed4f80b6c54d2acce.png)

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>