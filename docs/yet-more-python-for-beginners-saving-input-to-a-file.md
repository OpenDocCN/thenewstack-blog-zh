# 为初学者提供更多 Python:将输入保存到文件中

> 原文：<https://thenewstack.io/yet-more-python-for-beginners-saving-input-to-a-file/>

到目前为止，在这个关于 [Python 编程语言](https://www.python.org/)的介绍系列中，我们已经学习了一些非常酷的基本 Python 技巧。我们已经学习了[是什么让语言变得特别](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)，学习了 [Python 控制台和使用的变量](https://thenewstack.io/more-python-for-non-programmers/)，并且学习了如何接受用户的输入。

有了这些知识，我们创建了几个有趣的小程序来说明这些特性在 Python 中是如何工作的，但是这些应用程序本身除了向你的朋友和家人证明你可以学习一门编程语言之外没有做太多事情。

这一次，我们将创建一个程序，使用我们已经学过的大部分内容，添加一些新的内容，并把它们放在一起，创建一个可以接受用户输入并将其保存到文件中的程序。如果您想跟踪一系列事情，但不总是想打开文件来这样做，这可能会很方便。此外，当您在进行更高级的 Python 工作时，这是一个重要的技巧。所以这类似于高中的代数…你以后的生活中会用到。

对吗？

好吧。

不管怎样，我们继续表演吧。

我将再次在 Linux 上演示这个过程。然而，它可以在任何支持 Python 的操作系统上工作。然而，如果你在一个不同的操作系统上工作，如果事情不像预期的那样(它们应该是这样的)，你可能不得不在这里或那里进行调整。

## 写入文件

我们要一步一步来。你需要学习的第一件事是如何将数据写入文件。为此，我们必须在所谓的访问模式下打开一个文件(在 Python 中)。这有三种不同的模式:

*   只写(w)-打开文件进行写入。
*   读写(w+)–打开文件进行读写。
*   仅追加(a)-打开文件进行写入。如果文件不存在，则创建该文件。

我们将重点讨论写入和追加模式。首先，写模式。为此，我们使用了`open()`函数。假设我们要将“Hello，New Stack”写入一个名为 **text.txt** 的文件。首先，使用以下内容创建文件:

`touch text.txt`

现在可以用只写模式写入该文件。

使用以下内容创建新的 python 脚本:

`nano write.py`

我们添加到文件中的第一件事是显示我们正在以只写模式打开 text.txt 文件的行。该行将如下所示:

`file1 = open('text.txt', 'w')`

还记得什么是变量吗？我们在这里所做的是用函数定义变量 file1，该函数以写模式打开 **text.txt** 文件。然后，我们可以在文件的下两行中使用该变量。

第二行写字符串 Hello，New Stack！添加到文件中，如下所示:

`file1.write("Hello, New Stack!")`

上面的代码行使用了同一个变量(file1)，用一个新的函数(`write()`)将字符串写入文件。最后一行将关闭文件，如下所示:

`file1.close()`

所以我们完整的脚本如下所示:

```
#Open the text.txt file in write mode.
file1  =  open('text.txt',  'w')

#Write the string "Hello, New Stack!" to the file
file1.write("Hello, New Stack!")

#Close the file
file1.close()

```

记住，所有以#开头的都是注释。我们对事物进行注释，这样我们就知道代码中发生了什么。

保存并关闭文件。使用以下命令运行脚本:

`python3 write.py`

如果您查看 **text.txt** 文件的内容，您会看到它在顶部包含 Hello，New 堆栈行。如果您再次运行它，脚本会将“你好，新堆栈”替换为“你好，新堆栈！”在顶端。换句话说，我们的脚本简单地覆盖了 **text.txt** 文件中的第一行。

这很好，但是除非你只需要保存一行文本，否则这不是很实用。这就是仅追加模式派上用场的地方。所以我们稍微改一下。我们不是以只写模式打开文件 1，而是以追加模式打开它。该脚本看起来与第一个几乎相同:

```
#Open the text.txt file in write mode.
file1  =  open('text.txt',  'a')

#Write the string "Hello, New Stack!" to the file
file1.write("Hello, New Stack!")

#Close the file
file1.close()

```

发现差异？我知道你会的。

现在，如果您运行 **python3 write.py** 命令，它将追加 Hello，New Stack！到第一行的末尾。运行几次，你会得到一个类似于这样的文件:

```
Hello,  New Stack!Hello,  New Stack!Hello,  New Stack!Hello,  New Stack!

```

好转，但仍不理想。我们要做的是创建一个脚本，它会在前面的。为此，我们添加了换行符`\n`。所以现在我们的`write()`函数看起来像这样:

`file1.write("Hello, New Stack! \n")`

如果使用 write()函数运行脚本几次，text.txt 文件的内容将如下所示:

```
Hello,  New Stack!
Hello,  New Stack!
Hello,  New Stack!

```

现在让我们把它变成一个实际的应用程序，它将接受用户的输入并将输入写入一个文件。请记住，从我们以前的教程，这一节:

```
print("What is your first name?")
input1  =  input()
print("What is your last name?")
input2  =  input()

```

我们将重用它来询问用户的名和姓。当然，为了正确格式化，我们需要使用一些技巧。

我们已经为名(输入 1)和姓(输入 2)定义了变量。现在，我们必须以追加模式将它们写入文件，代码行如下:

`file1 = open('text.txt', 'a')`

接下来，我们编写变量的内容(通过用户输入的方式)并对其进行格式化，以便在名字和姓氏之间有一个空格，并且在姓氏之后有一个新的换行。如果我们不添加这些格式选项，我们的文本文件将会变成这样:

```
JackWallenOliviaNightingaleWilJackson

```

我们不希望那样。我们想要的是:

```
Jack Wallen
Olivia Nightingale
Wil Jackson

```

因此该部分看起来像这样:

```
file1.write(input1)
file1.write(" ")
file1.write(input2)
file1.write("\n")
file1.close()

```

正如你所看到的，我们在名字和新的回车符之间添加了空格。

我们的整个脚本现在看起来像:

```
#Take input from user and assign it to variables
print("What is your first name?")
input1  =  input()
print("What is your last name?")
input2  =  input()

#Open the text.txt file for appending.

file1  =  open('text.txt',  'a')

#Write the content of the variables to the text.txt file
file1.write(input1)
file1.write(" ")
file1.write(input2)
file1.write("\n")

#Close the text.txt file
file1.close()

```

当我们现在运行几次`python3 write.txt`(输入不同的名称)时，脚本将完全按照我们想要的方式写入文件。

这就对了。您已经创建了一个简单的 Python 应用程序，它接受用户输入并将其写入文件。发挥你的创造力，看看你能把它应用到多少用例中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>