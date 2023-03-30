# 教程:挖掘 Bash 命令历史的潜在力量

> 原文：<https://thenewstack.io/tutorial-tap-the-hidden-power-of-your-bash-command-history/>

上个月，我写了一篇关于使用管道组合一系列 Unix 命令的文章。但是有些时候，你甚至不需要*管道来将一系列精心选择的命令转换成强大而方便的自制实用程序。*

这当然给了我一个机会来讲述一个关于我的第一份编程工作的最喜欢的荒诞故事——以及我最终开发的疯狂的鲁布·戈德堡式的解决方案。

把它当成一封新手写给另一个新手的指导性的信。

![Rube_Goldberg's 'Self-Operating Napkin' (cropped) - Originally published in Collier's, September 26 1931 (public domain via Wikipedia)](img/90bcacc4add7e2e931803accbd064aa6.png)

作为 Perl 程序员的第一年，我一直提醒自己 Perl 创始人拉里·沃尔的口头禅——程序员的三大美德是[懒惰、急躁和傲慢](http://threevirtues.com/)。不幸的是，当时我只知道少数几个 Unix 命令——没有一个命令完全符合我的要求。

例如， **echo** 命令重复在它之后输入的任何文本。我只是从来没有发现它特别有用，因为它似乎总是麻烦多于它的价值。当然， [**echo**](http://man7.org/linux/man-pages/man1/echo.1.html) 对于给输出添加装饰很方便。

``echo "--------------------------" ; date ; echo "--------------------------"
--------------------------
Thu Feb 28 01:25:46 UTC 2019
--------------------------`` 

但是如果你不得不首先在中输入*所有这些装饰，你并没有真正节省时间。*

我真正想要的(而不是 **echo** )是一个命令，让我回到我正在做大部分工作的那个深层子目录。比…短的东西

``cd ~/subdirectory/subdirectory/subdirectory/subdirectory/subdirectory``

是的，有一个命令可以让你变回上次使用的目录。

``cd -``

但不幸的是，我使用了三个 T21 目录——似乎总是需要切换回我最后一次没有使用的目录。

所以日复一日，年复一年——好吧，总是那些小事让你抓狂，直到你不可避免地开始寻找替代品。让事情变得更加困难的是，我与其他开发人员共享这些目录，并对留下任何额外的脚本感到不安，这些脚本可能会使更改目录变得更容易。

但最终，我想出了一个完美的新手解决方案。

在这一路上的某个地方，我知道了**！**是您进入 Bash 的“历史替换”命令的门户，可以替换任何最近输入的以感叹号后的字符串开头的命令。很明显，只需输入**就可以再次执行整个命令！**及其首字母。

然后，我让第一个命令成为我从未在其他任何事情上使用过的命令: **echo。**

``echo; cd ~/directory/subdirectory/subdirectory/subdirectory/subdirectory``

所以只要我想，只要输入这两个字符，我就可以变回那个目录。

``!e``

程序员谈论[重载一个函数](https://en.wikipedia.org/wiki/Function_overloading)(或者一个方法)——基本上，创建一个子程序的不同版本，如果有额外的参数，它们会有不同的行为。我告诉自己，我发明了一些全新的东西:我重载了一个*命令。*现在我终于可以像对待 vi 一样对待 bash 了——一系列一个或两个字符的命令触发了强大的响应，做了我需要的一切。

很快我就把我新发现的能力应用到工作流程的其余部分…

例如，我的主管坚持让我检查我编写的任何 Perl 代码的语法——当然，这个命令还涉及到另外一长串子目录。

``perl -I/home/davidc/perl/lib -wc filename``

由于文件名总是在变化，这将更难自动化。但并非不可能…

显然，我必须得到那个不断变化的文件名。但是在关闭一个文件之后，我可以运行 history 命令，然后使用 [**tail**](http://man7.org/linux/man-pages/man1/tail.1.html) 只提取最后两个命令——最后一个是我键入我的 *history* 命令，但是它之前的一个是编辑文件的命令。

``history | tail -2
496 2019-02-28 02:11:01 vi filename.pm
497 2019-02-28 02:11:59 history | tail -2`` 

使用稍微长一点的命令可以把它精简到所有重要命令的文件名(使用 [**头**](http://man7.org/linux/man-pages/man1/head.1.html) )。)

``history | tail -2 | head -1
496 2019-02-28 02:11:01 vi filename.pm``

文件名总是在第五块文本中——当然，我可以使用 **[awk](http://man7.org/linux/man-pages/man1/awk.1p.html) 提取它。**

``history | tail -2 | head -1 | awk -F " " '{print $5}'
filename.pm`` 

幸运的是，有一个 Unix 命令— [**xargs**](http://man7.org/linux/man-pages/man1/xargs.1.html) —它可以神奇地将输出转换成下一个 Unix 命令的参数。在我的例子中，下一个命令将是那个复杂的语法检查 perl 指令。

``history | tail -2 | head -1 | awk -F " " '{print $5}' | xargs perl -I/home/davidc/perl/lib -wc``

瞧啊。现在，如果我需要检查我刚刚编辑的文件的语法，我有一系列命令可以立即完成。同样，我可以通过在*后输入第一个字符来运行整个系列的命令！*

``!h
filename.pm syntax OK``

真正疯狂的是。起初，似乎只有当我从未使用过另一个以字母 *h* 开头的命令时，这才会起作用。但后来我意识到，当然，还有另一个解决办法。不一定是字母 h 。我可以编造一个不存在的命令——比如说`zarkfum`——这样我就可以对一个不常用的字母使用相同的技巧。

``zarkfum; history | tail -2 | head -1 | awk -F " " '{print $5}' | xargs perl -I/home/davidc/perl/lib -wc``

现在，每当我键入这两个字符时，整个系列的命令就会出现。

``!z
-bash: zarkfum: command not found
filename.pm syntax OK`` 

(尽管最终，我添加了一个屏幕清理命令——只是为了避免收到无休止的提示，说 zarkfum 不是一个真正的命令。)

``zarkfum; clear ; history | tail -2 | head -1 | awk -F " " '{print $5}' | xargs perl -I/home/davidc/perl/lib -wc``

有更干净、更简单的方法吗？大概吧。但是作为一名 Perl 程序员，我已经记住了 Perl 语言的官方格言:“有不止一种方法可以做到这一点。”

在未来的几年里，在现实世界中，在令人麻木的重复工作流中，我发现很容易一遍又一遍地使用相同的少量 bash 命令。但当其他程序员分享他们自己最喜欢的技巧时，我总是学到很多东西。也许分享我自己的第一个有用的命令集可以教给别人一些有用的东西。

也许有一天，他们会把它们结合成自己疯狂的鲁布·戈德堡式的解决方案。

毕竟，可能性真的是无穷无尽的，这也是我热爱程序员工作的一部分。而且不止我一个人这么想。就在今天下午，我重读了 Unix 的 Perl 老人页，当我看到它的最后一条注释仍然提醒读者 Perl 的座右铭是“有不止一种方法可以做到这一点”时，我笑了。

但是也多加了一行。

"猜测还有多少是留给读者的练习."

专题图片:斯特罗姆-马斯滕·冯·曼海姆(维基百科)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>