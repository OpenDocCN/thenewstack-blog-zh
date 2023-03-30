# 本周编程:Chromebooks 能变成开发机器吗？

> 原文：<https://thenewstack.io/week-programming-dogfooding-developers-chromebooks/>

回到 2011 年初，我得到了我的第一台 Chromebook。该设备内部被称为 CR-48 ，是一种哑光黑色，具有橡胶质地。作为该设备的 60，000 名试飞员之一，我很兴奋地尝试了一下这款“纯云”设备，但很快我就失望了。如果我没记错的话，当时没有离线存储或任何类型的功能——你打开它，有一个浏览器和其他东西。我用它玩了一会儿，写了一些严厉的评论，然后迅速发给我侄女，让她在上面玩网络游戏。

几年后，你可能知道，Chromebooks 现在是功能强大的小型电脑，可以处理普通用户的许多日常需求——文字处理、网络浏览，甚至图形编辑，信不信由你。如今大多数事情都可以在网上完成。我在 2014 年初买了我的第二部 Chromebook，一直没有回头。在过去的三年里，它一直是我的主要电脑，我的旧台式机大部分时间都闲置着。

当我最近开始尝试一种新的编程语言时，我再次发现了 Chromebook 的局限性。这不是一台开发机…或者是吗？

我承认——我很快放弃了战斗，将我闲置的 Windows 桌面变成了 Linux 双引导机器，但其他人也在为那些对如何将 Chromebooks 用作开发人员机器感兴趣的人而战斗。在阅读这些账户，我的兴趣，我必须说，已经进一步更新。

本月早些时候， [Solarian 程序员](https://solarianprogrammer.com/)博客的作者决定为[发起为期两周的挑战](https://solarianprogrammer.com/2017/09/11/two-weeks-programming-chromebook-challenge/)，在接下来的两周内，他们将只使用他们的 Chromebook 和 iPhone，看看是否有可能将 Chromebook 用作通用开发机器。

事实证明，可能性是丰富的。从基于网络的在线开发工具如 [CodeAnywhere](https://codeanywhere.com/) 和 [Cloud9](https://c9.io/) 到用 Chromebook 的 Linux 发行版 [Gallium](https://galliumos.org/) 完全取代 ChromeOS，有许多方法可以将你的 chrome book 变成一台开发机器。对于他们的挑战，作者选择启用开发者模式(一些评论对此表示反对)并“通过 [Crouton](https://github.com/dnschneid/crouton) 在 chroot 中运行 Ubuntu Linux”，这允许你“并行运行 Ubuntu 和 Chrome OS”<

然而，对于那些更注重安全性的人来说，Kenneth White 详细介绍了一种方法，这种方法在保持安全性不变的同时，允许您创建自己渴望的全功能开发环境 —注意到他对经常使用的“启用开发模式”技术的厌恶:

*我在“Chromebooks for developers”上找到的几乎每一篇操作指南和博客文章，基本上都是以“启动进入开发者模式”或“安装 Debian/Ubuntu 作为主操作系统”开头的。我只想说:这是个糟糕的建议。这就好比建议朋友们越狱他们闪亮的新 iPhone。*

*显然，你可以随心所欲地使用自己的设备，但要认识到，在第一步，你将失去 Chromebook 的大部分核心安全功能，更不用说几乎会招致坏的开发习惯。就 Debian/Ubuntu(和 Crouton)而言，这很好，但你最终不会得到 Chromebook，只是一个廉价的迷你笔记本，有着古怪的驱动程序。这个练习的要点是保持平台的稳定状态，并拥有一个灵活、安全的开发环境，而不依赖特权访问。*

因此，我要对身边带着 Chromebooks 的代码骑师们说，自由吧！

## 本周的节目新闻中

*   GitHub 上的一项提议[只使用 GitHub](https://github.com/golang/go/issues/21956) 为 GoLang 做贡献，这在社区中引起了一些关注，指出“做贡献太难了”以及“Go 感觉像是一个谷歌拥有和控制的项目，不是真正的‘开源’”。
*   脸书 HipHop 虚拟机背后的团队写道，他们将把 HHVM 的未来带到 PHP 之外。正如 PHP7 将与即将被弃用的 PHP5 的兼容性决裂一样，HHVM 也将与 PHP 决裂，转而打造“一条清晰的道路，让 Hack 成为一种出色的 web 开发语言，脱离其 PHP 起源。”信息世界[提供了更多关于移动的见解。](https://www.infoworld.com/article/3226489/web-development/forget-php-facebooks-hhvm-engine-switches-to-hack-instead.html)
*   “那太令人震惊了。如果你能改变我们开发的方式，一夜之间减少 10%或更多的 bug，那是显而易见的。除非开发时间翻倍，否则我们会这么做。”——这是微软的一位工程经理引用的话，回应他的研究:T2 在 Javascript 中添加静态类型注释“可以防止提交代码中大约 15%的错误”
*   说到改进 JavaScript， [CoffeeScript 2 于本周](http://coffeescript.org/announcing-coffeescript-2/)发布，其明确目标是消除“任何与现代 Javascript 的不兼容性，这些不兼容性可能会妨碍 CoffeeScript 在项目中的使用；并尽可能保持向后兼容性。”
*   GitHub 本周公布了 [GitHub Desktop 1.0](https://github.com/blog/2437-announcing-github-desktop-1-0) ，这是去年 5 月发布的测试版的后续。[开源](https://github.com/desktop/desktop) GUI 应用程序[现在可以下载](https://desktop.github.com/)，它提供了图像差异、更快的存储库克隆等功能，并与您现有的工作环境相集成。
*   类似地， [Sublime Text 3.0](http://www.sublimetext.com/blog/articles/sublime-text-3-point-0) 也于本周发布，带来了“刷新的用户界面主题、新的配色方案和新的图标”，以及“重大的语法突出显示改进、Windows 上的触摸输入支持、macOS 上的触摸栏支持以及 Linux 的 apt/yum/pacman 资源库。”
*   IBM 本周[开源了一款支持微服务的 Java 应用服务器](https://www.infoworld.com/article/3227167/java/ibm-open-sources-a-microservices-friendly-java-app-server.html)，名为 [Open Liberty](http://openliberty.io/downloads/) ，这个消息可能会引起那些在 Java 企业工作的人的兴趣。
*   Cloudflare 和 Google Cloud 联手为应用开发者提供 10 万美元的云平台积分。初创公司可以获得最高 3000 美元的资助，2 万至 10 万美元的“特殊应用”，甚至首次使用的个人用户也可以获得数百美元的免费平台积分。
*   最后，在本周，Stack Overflow 发布了一款面向开发人员的薪资计算器，这样你就能真正知道与你的同行相比，你被低估了多少。 [Venturebeat](https://venturebeat.com/2017/09/19/stack-overflow-launches-salary-calculator-for-developers/) 提供了此次发布的所有细节。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>