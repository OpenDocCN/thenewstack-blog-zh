# 教程:探索 Unix“grep”的秘密

> 原文：<https://thenewstack.io/tutorial-hunting-the-secrets-of-unix-grep/>

作为 Unix 批处理实用程序的一部分， **[grep](http://man7.org/linux/man-pages/man1/grep.1.html)** (全局正则表达式打印)是一个如此强大的搜索工具，以至于有必要查看它的所有标志和元字符，以确保您不会忽略一些非常有用的东西。事实证明，这种有用性源于早期 Unix 先驱的工作。

## **如何 *grep* 进化**

为了理解 grep 的演变，Brian Kernighan 最近在一些新的采访中回忆道，“你必须把自己放回到计算的早期 Unix 的非常非常早期”。当时，Unix 运行在一个缓慢的、低内存的 PDP-11 上——而且“如果你在将一个程序的输出放入下一个程序之前，必须完全存储它，这是有可能的，[它可能不适合](https://youtu.be/bKzonnwoR2I)。”

[https://www.youtube.com/embed/NTfOnGZUZDk?feature=oembed](https://www.youtube.com/embed/NTfOnGZUZDk?feature=oembed)

视频

这解释了为什么像 **ed** 这样的文本编辑器一次处理一行——这一传统在过去 40 年里一直流传到许多 Unix 工具中。例如， **ed** 是 **ex** 文本编辑器的前身，其中大部分最终被[并入 **vim**](/a-look-at-vim-a-text-editor-for-the-ages/) 。)

如果您编写一行 **ed** 命令来查找正则表达式**re**——在整个文档中进行“全局”搜索，然后打印每一个匹配项——您将得到…

是的，就是这样一个有用的命令，最终成为了它自己的独立工具。历史上，肯·汤普森(Ken Thompson)连夜编写了 grep 工具，帮助一位同事搜索《联邦党人文集》(Federalist Papers)的全部内容，而无需先将全部内容载入内存。

但是就像**ed**command g/*re*/p 成为一个名为“grep”的独立工具一样，grep 的一些最有用的标志最终衍生成了更多的工具。例如，有递归的 **rgrep** ，它与 **grep -r** 相同。这就像拥有超能力的 grep 它搜索每一个子目录。

然后还有 **egrep** *，*，它与 grep -E 相同，尽管 grep 手册页警告说 **egrep** “已被否决”，但是“提供它是为了允许依赖它们的历史应用程序不加修改地运行。”使用 **egrep** 的搜索不仅匹配通常的元字符(。* ^ $)而且还有 Posix 定义的一组 [(E)扩展正则表达式](https://www.regular-expressions.info/posix.html)。这让你更具体地知道你希望一个字符在你的匹配中出现多少次。

你也可以用 **grep，**做同样的数量匹配，但是你必须在字符前加一个反斜杠。

`grep 's\{2\}' filename`

使用 *egrep* 不需要反斜杠。

`egrep 's{2}' filename`

还有一种更强大的方式来丰富模式匹配:交替。“管道”字符允许您分隔一对字符，并且如果一行包含*或*字符，将进行匹配。同样， **grep** 要求您在管道字符前面加一个反斜杠——但是使用 **egrep** 您可以简单地在命令中包含它。

`grep 'z\|Z' filename`
`egrep 'z|Z' filename`

你也可以创建一个*字符组*——只有当整个组都存在时，它才被认为是匹配的。

`grep '\(even\|odd\)'`T41`egrep '(even|odd)'`

**grep** 还衍生了另一个独立工具， **fgrep** ，grep 的手册页解释说它与 **grep -F** 相同。它再次警告说 **fgrep** “不推荐使用”但是“允许依赖它们的历史应用程序不加修改地运行。”我听说它被称为“ [fast grep](https://www.ostechnix.com/the-grep-command-tutorial-with-examples-for-beginners/) ”，因为它基本上抛弃了 grep 的所有正则表达式匹配，只专注于快速查找匹配字符串。例如，grep 使用美元符号作为匹配行尾的特殊字符——因此，如果您实际上想要搜索美元符号，您必须在它前面加一个反斜杠(并在单引号中包含整个搜索字符串)。

`grep '\$' filename`

但是 **fgrep** 让你只需输入美元符号。

`fgrep $ filename`

您还可以使用 ***fgrep*** 来匹配一个点或一个脱字符号，而不必在它前面加一个反斜杠——这确实使事情更具可读性。

## 更多搜索方式

如果你的 grep 搜索给你很多“误报”，有一个内置的方法只在你的搜索模式是一个完整的单词时显示一个匹配:标志 *-w* 。例如，如果您正在查找单词“ant ”,但不想匹配包含“ant”的所有其他单词:

`grep -w 'ant' filename`

如果你想在你的搜索字符串是整行的时候只显示匹配，试试 *-x:*

`grep -x 'Only this text appears on the line' filename`

当然，还有另一种方法可以做到这一点，使用 **grep** 的 *^* 和 *$* 元字符，它们可以让你分别匹配一行的开始和结束。

`grep '^Only this text appears on the line$' filename`

因为有 *^* 和 *$* ，所以也有一个简单的方法来搜索空白行。

`grep '^$' filename`

*grep* 也支持“字符类”的匹配——如果包含括号中表示的*任一*字符，则显示一行。

`grep '[a-z]' filename`

但是也有几个方便的预定义字符集。下面是一些比较有用的。

如果你用特殊的`^`字符开始你的字符类，它会有一个新的行为:你可以匹配所有那些包含字符*而不是*的行来匹配你的字符集。

## 有趣的 Grep 技巧

这就是有趣的地方。如果你能找到你系统的“字典”目录——通常在子目录*/usr/share/dict*——有一个名为 *words* 的文件，其中英语中的每个单词都出现在单独的一行**——**总共 99171 个单词。当然，这使得解决你早报上的初级混乱变得非常容易。

`grep -x '[kriqu]\{5\}' words
quirk`

多年来，我一直使用 grep 作为获取我的目录的所有子目录列表的变通方法。

`ls -l | grep '^d'`

*ls* 上的 *-l* 标志以列出的每个文件或目录的文件权限开始每一行——当然，目录在第一个位置用 d 表示。所以 grep 命令可以搜索所有以 d 开头的行！

`drwxr-xr-x 2 username pg72253 24 Mar 8 15:11 directoryname`

这些年来，你最终会学到越来越多的技巧。当我第一次开始编程时，我会对一个特定的模式进行 grep，然后将它输入 **`wc`** 来计算有多少个匹配。

`grep 'ERROR' filename | wc`

几年后，我意识到只要用 grep**grep**就可以完成同样的事情——如果我也使用 grep 的-c 标志的话。

`grep -c 'ERROR' filename`

迟早你会想要忽略大小写——这可以通过使用 *-i* 标志来实现。

`grep 'UNIX' -i filename`

最近我了解到，你也可以通过使用 *-y* 标志来忽略大小写，grep 的 man 将其简单地描述为“过时的同义词”

`grep 'UNIX' -y filename`

但是我最喜欢的 grep 旗是*——颜色*。它的功能和你想象的完全一样:它用颜色显示匹配。这是一个特别有用的技巧的一部分，可以在 Tom Limoncelli 的 Everything Sysadmin 博客网站上找到。在一篇名为“[我每天滥用的 4 个 unix 命令](https://everythingsysadmin.com/2012/09/unorthodoxunix.html)”的文章中，他写道，“随着年龄的增长，你的视力越来越差。在文本域中查找内容变得更加困难。因此，通过使用 egrep 和它的 color 标志，他想出了一种显示整个文件的方法——同时突出显示某些关键词。因为每一行都有一个开头，这个命令将*匹配*并显示每一行——但是你只能看到你的搜索词上的高亮部分。

`cat filename | egrep --color=always '^|searchword'` 

与此同时，我每天都在滥用一些有用的标志:

*   *-n* 给出每个匹配的行号。(如果您打算直接跳到 vim 中的行号进行编辑，这就很方便了。)
*   *-h* 让您告诉 grep 停止打印匹配文本之前的文件名。

其中一个最有用的标志指示 **grep** 分别使用 *-B* 或 *-A* 打印匹配之前或之后出现的附加行(后面紧跟着要打印的附加行数)。

`grep -A2 'searchstring' filename
grep -B2 'searchstring' filename`

不要忘记 *-v* 标志，它提供了一种“相反日 grep”——打印出*和*不匹配的每一行。

你也可以指示 grep 只显示那些*不*包含匹配字符串的文件的名字——使用-L 标志或者更具描述性的——没有匹配的文件

`grep -L 'ERROR' filename
grep --files-without-match 'ERROR' filename`

我学到了很多，只是在写这个教程。这证明了 grep 有许多不同的使用方式，花些时间来确保你了解它所有隐藏的额外特性总是值得的！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>