# AWK 简介

> 原文：<https://thenewstack.io/an-introduction-to-awk/>

[](https://www.linkedin.com/in/fvendrell/)

[Francesc Vendrell](https://www.linkedin.com/in/fvendrell/)

[Francesc Vendrell 是 LogDNA 的一名现场可靠性工程师，他主要研究自动化、容器和 Kubernetes。他在西班牙加泰罗尼亚远程工作，喜欢摆弄复古电脑、烹饪和运动。](https://www.linkedin.com/in/fvendrell/)

[](https://www.linkedin.com/in/fvendrell/)[](https://www.linkedin.com/in/fvendrell/)

awk 是一个强大的工具。它实际上是一种[图灵完全语言](https://en.wikipedia.org/wiki/Turing_completeness)，这意味着你可以用它编写任何类型的程序。您可以实现经典的排序算法或更复杂的东西，如解析器或解释器。这种例子可以在 AWK 的作者写的“ [AWK 编程语言](https://archive.org/details/pdfy-MgN0H1joIoDVoIC7)”一书中找到。awk 今天仍然流行的原因，与它的通用性无关，更多的是与它在命令行中的有用性有关。

无论您是试图提取和格式化一些文本数据，还是构建一个漂亮的命令来简化您的工作， *awk* 真的可以帮助您完成工作。事实上，如果你在我们的代码库中搜索“ *awk* ，它会出现大约 520 次。

awk 是早在 1977 年由阿尔弗雷德·A·何、彼得·j·W·艾因伯格和布莱恩·K·恩尼汉创建的，当时他们在贝尔实验室工作。它是为文本处理而设计的，通常用作数据提取和报告工具。

在 Unix 的早期， *awk* 是除了 Bourne shell 之外唯一默认可用的脚本语言。令人惊讶的是，由于它的简单和强大，至今仍被许多人广泛使用。

## **基础知识**

在下面的一些例子中，我将假设输入数据来自标准输入。这就是 awk 在现实世界中的典型用法。例如:

```
# Example 1
cat my-input.txt  |  awk  '1'  # This is how to execute the code
my_super_command  |  awk  '1'  # This is how to execute the code
awk  '1'                    # This is how I will write code snippets in this post

```

我鼓励你带着开放的终端跟帖，去尝试例子，去实验，让它们失败；如果你是新手，这是获得良好学习体验的最佳方式。让我们从最基本的规则开始:

*   任何 *awk* 程序都是由一系列模式动作语句组成的。
*   在模式-操作语句中，可能缺少模式或操作。
*   如果模式丢失，该操作将应用于每一行输入。
*   缺少的操作相当于{ print }。
*   丢失的模式总是匹配的。
*   仅当模式匹配时，即模式为真时，才将动作应用于该行。

在第一个例子中，由于模式是 1，并且 1 始终为真，所以这个一行程序进一步转化为一个打印语句:

因为任何缺失的模式都是匹配的，我们也可以这样写:

这个程序是做什么的？它只是打印出每一个输入行。听起来熟悉吗？我们刚刚在 *awk* 实现了 cat！

```
# Example 2
# All of the following are equivalent implementations of 'cat'
awk  '1' # short but confusing
awk  '1 { print }'  # long and also a bit confusing
awk  '{ print }'.  # this one gets it right

```

## **向前移动**

awk 的默认字段分隔符(FS)是空格。一个输入行被划分成由 FS 定界的单个字段。我们可用的其他有趣变量如下:

*   $0:正在处理的当前记录(行)
*   $1，$2，…, $NF:记录中的单个字段
*   NR:当前记录的序号
*   NF:当前记录中的字段数
*   FS:字段分隔符；用于分隔字段的正则表达式(也可以用-F 设置)
*   OFS:输出字段分隔符；用于在输出中分隔字段的正则表达式
*   RS:输入记录分隔符，缺省情况下换行
*   ORS:输出记录分隔符，加在每条记录之后。默认情况下换行。
*   BEGIN:用于在处理任何记录之前执行语句的特殊模式
*   END:用于在处理完最后一条记录后执行语句的特殊模式

下面的例子利用了刚才描述的每一个变量。 *awk* 可以执行几乎与剪切命令相同的操作，甚至更多。例如，获取当前目录中每个文件的用户、组和文件名:

```
# Example 3
$  ls  -l  |  awk  'NR>1 { print $3, $4, $NF }'
xesco staff Documents/
xesco staff absecret/
xesco staff ansible/
xesco staff archive-upload-validate/
xesco staff authme/
xesco staff batchjobs/
[...]

```

这里我们有一个单一的模式-动作语句。图案 NR > 1 跳过第一行(总字节数)，因此不会被打印。该语句选择字段 3、4 和最后一个字段来打印它们。花一点时间来理解$NF 实际上代表什么:我们使用 NF 变量去引用(访问一个字段)。

现在，假设您想从系统中的 **/etc/services** 文件中提取一些数据。

```
$  cat  /etc/services
# The Well Known Ports are those from 0 through 1023.
# The Registered Ports are those from 1024 through 49151
# The Dynamic and/or Private Ports are those from 49152 through 65535
#
# $FreeBSD: src/etc/services,v 1.89 2002/12/17 23:59:10 eric Exp $
#    From: @(#)services    5.8 (Berkeley) 5/9/91
#
# WELL KNOWN PORT NUMBERS
#
rtmp              1/ddp    #Routing Table Maintenance Protocol
tcpmux            1/udp # TCP Port Service Multiplexer
tcpmux            1/tcp # TCP Port Service Multiplexer
#                          Mark Lottor <MKL@nisc.sri.com>
nbp 2/ddp    #Name Binding Protocol
compressnet 2/udp # Management Utility
compressnet 2/tcp # Management Utility
compressnet 3/udp # Compression Process
compressnet 3/tcp # Compression Process
#                          Bernie Volz <VOLZ@PROCESS.COM>
echo              4/ddp    #AppleTalk Echo Protocol
#                 4/tcp    Unassigned
#                 4/udp    Unassigned
rje 5/udp # Remote Job Entry
rje 5/tcp # Remote Job Entry
#                          Jon Postel <postel@isi.edu>
zip 6/ddp    #Zone Information Protocol
#                 6/tcp    Unassigned
#                 6/udp    Unassigned
[...]

```

文件格式如下:服务名端口/协议#注释。我们感兴趣的是提取每个服务的名称和协议。我们还想跳过注释行。这里的问题是默认的字段分隔符与我们想要提取的数据不匹配。幸运的是，使用 *awk，*您可以用-F:
将自己的正则表达式定义为字段分隔符

```
# Example 4
$  cat  /etc/services  |  awk  -F"[0-9]+/"  '!/^#/ { print $1, $2 }'
rtmp ddp    #Routing Table Maintenance Protocol
tcpmux udp # TCP Port Service Multiplexer
tcpmux tcp # TCP Port Service Multiplexer
nbp                ddp    #Name Binding Protocol
compressnet        udp # Management Utility
compressnet        tcp # Management Utility
compressnet        udp # Compression Process
compressnet        tcp # Compression Process
echo ddp    #AppleTalk Echo Protocol
rje                udp # Remote Job Entry
[...]

```

最后一个例子引入了一些新的结构和语法。让我们来看看:

*   -F"regex ":将字段分隔符(FS)设置为正则表达式" regex "
*   /regex/:在模式中，根据正则表达式“regex”匹配该行
*   ！表情:反转“表情”的真值

正则表达式[0-9]+/匹配一个或多个以/结尾的数字。例如，48128/无论什么都会匹配。实际上，我们将字段分隔符设置为我们想要删除的行的一部分。接下来是图案！/^#/.的！正在反转/^#/.这个表达的值这也是匹配任何以#开头的行的正则表达式。所以我们要删除以#开头的行。最后，我们打印字段分隔符之间的字段。结果几乎是我们想要的，但不幸的是，我们也得到了行尾的注释。我们可以将输出通过管道传输到另一个 *awk* 并打印前两个字段:

```
# Example 5
$  cat  /etc/services  |  awk  -F"[0-9]+/"  '!/^#/ { print $1, $2 }'  |  awk  '{ print $1, $2 }'
rtmp ddp
tcpmux udp
tcpmux tcp
nbp ddp
compressnet udp
compressnet tcp
compressnet udp
compressnet tcp
echo ddp
rje udp
rje tcp
zip ddp
[...]

```

成功了！(当然，使用内置函数 split 有一种更好的方法。在这篇文章中，我不会深入讨论内置函数，但是知道它们可以提供帮助还是很好的。)

```
# Example 6
$  cat  /etc/services  |  awk  -F"[0-9]+/"  '!/^#/ { split($2,a,"#"); print $1, a[1] }'
rtmp ddp
tcpmux udp
tcpmux tcp
nbp                ddp
compressnet        udp
compressnet        tcp
compressnet        udp
compressnet        tcp
echo ddp
rje                udp
rje                tcp
zip                ddp
echo udp
echo tcp
discard            udp
discard            tcp
[...]

```

在这种情况下，我们有两种说法。第一个使用#作为分隔符拆分$2，并将部分存储在数组 a 中，在 *awk 中，*变量是动态的，在使用前不必声明或初始化。最后，我们像以前一样打印第一个字段，但是我们打印数组 a 的第一个元素。稍后，我将向您展示一种简单的方法来消除重复的行，不管它们是否连续。

让我们看几个更简单的例子。假设你想要一个双倍空间的文件。默认情况下，awk 使用新行\n 作为输出字段分隔符(OFS)，我们可以很容易地将其更改为文件的两倍空间。下面的一行程序是等价的:

```
# Example 7
$  awk  -v  ORS="\n\n"  '{ print }' # use -v to set a variable
$  awk  'BEGIN {ORS="\n\n" } { print }'  # use a BEIGN block

```

我们可以在命令行上使用选项-v 来定义变量。在第一个例子中，我们覆盖了默认的 ORS 值，在每一行的末尾添加了一个额外的换行符。在第二个例子中，我们使用特殊的模式 BEGIN。这种模式总是在处理任何行之前进行匹配，并且可以用于执行初始化，或者如果我们实际上不关心输入的话。在这两种情况下，结果是相同的:我们得到双倍行距的文件。

在下一个例子中，我们只打印" *hello world！*“代码不需要任何输入，我们仅有的模式操作是 BEGIN。

```
# Example 8
awk  'BEGIN { print "hello world" }'

```

让我们继续前进。现在我们感兴趣的是获得一个目录中所有 YAML 文件的总字节数。这对于 *awk* :
来说很简单

```
# Example 9
$  ls  -l  |  awk  '/.yaml$/ { sum+=$5 } END { print sum+0 }'
330953

```

我知道，我本可以用 ls -l *的。yaml 和管道到 *awk* 。我所做的有一些有趣的副作用，我想让你记住。如果要过滤命令的输入或输出，除非非常必要，否则不要使用 grep | awk 或 awk | grep。您可以在一个 *awk 的*模式中使用过滤表达式/regex/来做同样的事情。这为你节省了一个额外的管道，给你一个更干净和更紧凑的表达。在本例中，我们首先过滤输入，确保只获得以. yaml 结尾的文件。对于每个文件，我们将第 5 列(字节数)累积到 sum 变量中。最后，我们使用特殊的模式 END 来打印所有输入被处理后的 sum 值。如果我们根本没有文件，我们将打印 undefined，这不是很好。这就是我们使用 sum+0 这个表达式的原因。问之前，是未定义+0 == 0。

## **最后一个例子**

在我结束之前，我想给你看一些重要的东西。下面的例子就是你所说的非常*惯用的* *awk* 一行程序。你能猜出它是做什么的吗？

```
# Example 10
awk  '!a[$0]++'

```

注意我们没有陈述，只有模式。管它呢，这种模式并不是我们目前所见的常见表情。它在做事。最后，模式所做的是过滤掉输入行，因此模式应该是真或假。我们来做一个分步执行，看看是怎么回事。

我们得到了第一行，在这一点上数组 a 是未定义的，但这对 *awk* 来说不是问题，a 被创建了。那么[$0]也是未定义的，并且[$0]的值也是未定义的。下一步是 increment bit ++，这是 undefined++和 *awk* 足够聪明，给我们一个 0 的结果。终于，我们有了！0，其计算结果为真，该行将被打印出来。很简单。下一行会发生什么？嗯，有两种可能的结果——你知道是什么吗？我已经写得太多了，所以我会让你弄清楚的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>