# PHP 7 拥有双倍的性能，尽管安全问题依然存在

> 原文：<https://thenewstack.io/php-7-boasts-doubled-performance-though-security-concerns-linger/>

PHP 7，这种许多开发人员又爱又恨的脚本语言的最新版本，已经发布了，承诺会带来巨大的性能提升。

然而，这一拖延已久的版本正好及时应对了一份关于之前版本安全漏洞的严厉报告。

PHP 7 一直关注性能和内存利用率。Zend Technologies 是最初的 Zend Engine 背后的公司，它领导了 PHP 7 所基于的 PHP 下一代项目，该公司声称在不改变一行代码的情况下，现实世界应用程序的性能提高了 50%至 200%。

它受到了来自[脸书的 HHVM](http://www.zend.com/en/resources/php7_infographic) 的推动，这是一个 JIT(即时)编译器，它将 PHP 语法转换成机器码，在某些情况下拥有相当甚至更快的速度。

“最重要的是性能。大多数代码的运行速度将是以前的两倍，但也有一些例外，”PHP 开发者拉斯马斯·勒德尔夫说，他现在是电子商务网站 Etsy 的杰出工程师，“如果你花一些时间在数据库上，我们将无法让你的速度提高那么多。对于大多数人来说，他们的代码会快一倍，这意味着他们可以关闭数据中心一半的服务器，这是一件大事，尤其是对于使用 PHP 的大公司来说。实际上，他们可能不会这样做；他们将有更多的空间来添加更多的功能。”

尽管有报道称这个版本花了八年时间，但勒多夫说事实并非如此。

“我们在 PHP 5 和 PHP 7 之间有很长的延迟，主要是因为我们有一点失败的切线，试图构建 PHP6，它有一个 Unicode 核心。它太复杂，太慢，太占用内存。所以我们不得不取消它，在那几年我们发布了很多 PHP 5.x 版本。这个版本，PHP 7，花了大约两年时间，”他在谈到 20 多年前创建的脚本语言时说。

“促使我们在 PHP 7 中做出改变的事情之一是，我们正在进行 JIT，它没有给我们带来我们需要的性能改进，因为我们只是移动了太多的内存。所以我们不得不后退一步，重写代码，优化内部结构，使所有内部结构更小，内存效率更高。仅这一步就让我们的性能提高了 2 倍，这实际上有点令人惊讶。这令人印象深刻，所以我们想，‘让我们把它推出去吧’，因为我们已经准备好了，人们可以很好地利用它。”

他说，JIT 将需要一些时间，但可能会在明年推出 7.1 版或 7.2 版

phpng 分支关注的问题包括语言如何处理数据结构、数据类型和内存分配。该项目的开发人员咨询了英特尔，以更好地利用哈希线和寄存器等现代 CPU 功能。

Andi Gutmans 是 PHP 工具供应商 Zend 的首席执行官，直到被 Rogue Wave Software 收购，他在一篇关于新版本的博客文章中写道，在一个令人失望的项目上工作了 18 个月，然后又花了 5 个月来扭转局面，这是一种“英雄主义”。

“新版本让一切都飞了起来。它还消除了主要的瓶颈，这给了我们许多新的想法，我们可以继续工作，它只是越来越快，越来越快…！”他写道。

PHP 7 中的[新特性](https://secure.php.net/manual/en/migration70.new-features.php)包括标量和返回类型声明，以及 null coalesce 操作符？？以及用于比较两个表达式的宇宙飞船操作符< = >，这两个操作符都需要较少的代码来执行特定的计算。

它还带来了:

*   一致的 64 位支持
*   许多致命错误现在都是例外
*   删除旧的和不支持的 SAPIs 和扩展

在黑客新闻上有很多对 PHP 的热爱者和憎恨者，但是也有关于使用旧版本的客户需要多少支持的讨论。这可能会给他们带来问题。

“基本上，我们已经放弃了许多 PHP 4 中可用的东西，所以如果你的代码已经有 15 年了，而且从那以后你就没有碰过它，那么它很可能不经修改就无法在 PHP 7 上运行，”勒多夫说。“如果你在过去的 10 年里编写代码，比如在 PHP 5 上，几乎不会有什么变化。过去 10 年里写的任何东西都应该不加修改地运行。”

## **安全批评**

PHP 仍然被广泛使用——它在 11 月份的 TIOBE 指数中排名第六。据估计，它是 80%网站的基础，驱动着一些最流行的应用程序，包括 WordPress、Drupal、Magento 等等。

虽然 PHP 并不是唯一一个在 Veracode 的新软件安全报告中受到严厉批评的，但以前的版本受到了重创。

在过去的 18 个月中，通过对超过 50，000 个应用程序进行基于云的扫描和代码分析，他们发现 86%的用 PHP 编写的应用程序包含至少一个跨站脚本(XSS)漏洞，56%的应用程序包含至少一个 SQL 注入漏洞

用 PHP、Classic ASP 和 ColdFusion 编写的应用程序中，有五分之四未能通过 OWASP(开放 Web 应用程序安全项目)十大基准中的至少一项。在所研究的编程语言范围中。NET 和 Java 表现最好。

Veracode 的创始人兼首席技术官克里斯·威索帕尔(Chris Wysopal)告诉 [Dark Reading](http://www.darkreading.com/vulnerabilities---threats/the-programming-languages-that-spawn-the-most-software-vulnerabilities/d/d-id/1323397) :“当我看到一个漏洞时，我脑海中浮现的一件事就是‘我敢打赌那是一个 PHP 网站。’"

勒多夫说 PHP7 提供了[安全改进](https://www.techrepublic.com/article/php-7-0-boosts-speed-and-security-what-you-need-to-know/)，包括[一个过滤的非序列化函数](http://php.net/manual/en/migration70.new-features.php#migration70.new-features.filtered-unserialize)和一组简单的函数来轻松获得[加密安全随机数](http://php.net/manual/en/migration70.new-features.php#migration70.new-features.csprng-functions)。

“开发人员编写安全代码所需的一切在 PHP 中都有，”他说。“PHP 的一大优点是它的学习曲线很浅，而且有广泛的吸引力——它可以被广泛访问，这也意味着可能没有最强的科学或安全背景的人也在编写和部署潜在的不安全代码。但正是这种自由导致了一些最有趣的事情，包括 Etsy(使用 PHP)。如果只有经验丰富的开发人员能够创建动态网站，整个网络将会是一个非常无聊的地方！”

然而，一个主要的 PHP 用户，流行的博客网站[WordPress.com，最近推出了一个新的接口](http://www.wired.com/2015/11/wordpress-com-gets-a-new-face-and-joins-the-javascript-age/)，一个代号为 Calypso 的项目，它用 JavaScript 代替 PHP，用 Node.js 作为后端代码。它还计划将该技术用于其 Mac 桌面和移动应用程序。

在一篇描述这个为期 20 个月的项目的博客文章中，WordPress.com 背后的公司 Automattic 的创始人马特·莫楞威格说，“我们意识到这项技术不会把我们带到下一个十年。”

Zend Technologies 最近被 Rogue Wave Software 收购，这给 PHP 带来了各种各样的意见。

特征图片:布鲁克林的标志杆上的涂鸦贴纸。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>