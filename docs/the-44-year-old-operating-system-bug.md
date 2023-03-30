# 44 年的操作系统漏洞

> 原文：<https://thenewstack.io/the-44-year-old-operating-system-bug/>

这个月，计算机爱好者 Foone Turing 偶然发现了一个他称之为存在了超过 44 年的 bug 这个 bug 留给他一个无法复制的文件。

作为旧电脑的爱好者，他在旧的 Windows NT 操作系统上发现了一些文件。但是很明显，他们使用了在他的新系统中“保留”的名字。“它们是完全有效的 NTFS 文件名，我在 Linux 中使用的是 NTFS 驱动器…所以今天我试图将这个 NTFS 驱动器备份到我的主 PC 上，哎呀，由于比大多数人阅读本文时更老的错误，我无法复制所有文件。”

他的发现在社交媒体上引发了一些有趣的讨论。一位用户记得这个 bug 在去年 Rust 的包管理器事件中再次出现。

一位评论者甚至有用地指出了微软程序员 Raymond Chen 在 2003 年所做的解释[，他最终写了一本名为](https://blogs.msdn.microsoft.com/oldnewthing/20031022-00/?p=42073)[The Old New Thing:Practical Development through The Evolution of Windows](https://www.amazon.com/Old-New-Thing-Development-Throughout/dp/0321440307/ref=sr_1_1?ie=UTF8&qid=1541788830&sr=8-1&keywords=Old-New-Thing-Development-Throughout)的书。“把 Wayback 的机器设置成 DOS 1.0，”陈写道。(1981 年出版)

陈记得当时当你运行编译器时，它会自动创建另外两个文件——一个带有后缀。LST 和一个后缀为. OBJ . "但是如果你不想要一个列表文件呢？编译器需要一个文件名，如果你不输入任何文件名，它会创建一个与源文件同名的文件名。所以你必须在提示符下键入一些东西，而提供“神奇文件名”的 PRN 显然甚至劫持了这个过程，让编译器把你的文件内容写到你的打印机上。“如果您想完全放弃输出，当然可以键入‘NUL’。如果你想让它出现在屏幕上，你可以输入“CON”(代表“控制台”)。

维基百科将它们称为 DOS 中的“[保留设备名](https://en.wikipedia.org/wiki/DOS#Reserved_device_names)，无论扩展名如何都不能用作文件名，因为它们被内置字符设备占用。”这在当时没什么大不了的，部分原因是 DOS 1.0 没有子目录——“只有一个目录，今天我们称之为根目录。”

但是当子目录出现时，它们还能做什么呢？神奇的文件名很快被添加到每个子目录中。甚至 22 年后，陈还写道“每个人仍然依赖他们。只需查看所有的批处理文件，这些文件可以重定向到> NUL，或者通过询问‘是否存在目录名\ nul’…”

但是这个古老的错误信息在 2018 年 11 月被 Foone Turing 重新发现后获得了新一轮的宣传。他的 Patreon 页面将他描述为“各种古怪的旧电脑/电子垃圾的收集者。”但是 Foone 显然也花了很多时间[存档旧媒体](http://foone.org/w/Digital%2520Media%2520Archiving.html)。

在他的[史诗般的 Twitter 帖子](https://twitter.com/Foone/status/1058676834940776450)中，Foone 解释了这是如何将他带入计算机历史的——以及他与陈描述的功能的第一次相遇。他最终追踪到了一种变异是如何首先进入蒂姆·帕特森的“快速而肮脏的操作系统”的，该操作系统通过加里·基尔代尔 1974 年流行的操作系统 CP/M 成为了 MS-DOS 第一版的前身——尽管在神奇的文件名后有一个冒号，“就好像它们是一个驱动器名一样”。"

然后他继续追踪这些年来这个组装车的存活情况。

这种行为从一个操作系统传到另一个操作系统。“但 Windows NT 希望与 DOS/Windows 程序兼容，”Foone 写道。“而 XP 合并了这两条线…”

所以 44 年后，“这些特殊的文件仍然有效。”

当他的 Twitter 帖子的链接出现在 Reddit 的 Windows 10 论坛上时，它吸引了超过 86 次投票，在 Reddit 的编程论坛上又吸引了 21 次投票。

当然，对于这是否真的是一个 bug——或者仅仅是保持向后兼容性的一种重要方式，还存在一些争论。

你可以在这个网址阅读 Foone 的所有推文，作为一个单独的网页[——在帖子的最后，Foone 甚至为其长度道歉。“这真的只是我太累了，漫无边际，回到家惊讶于 44 年前的一个决定引起的错误信息。”](https://threadreaderapp.com/thread/1058676834940776450.html)

“如果不清楚的话，我的意图绝不是说 WINDOWS 很烂’。总的来说，向后兼容是一件好事。事实上，我想要更多的向后兼容性，而不是更少。”

“但我只是惊讶地发现了 44 年前的一个错误，当时我正在运行 Windows 10，并从一个 USB 3.0 固态硬盘复制到另一个固态硬盘。”

* * *

## WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>