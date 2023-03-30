# Python 初学者:如何从文件中读取文本

> 原文：<https://thenewstack.io/python-for-beginners-how-to-read-text-from-a-file/>

从初学者的角度来看，我们带来了更多 Python 的优点。本系列的目标是让 Python 语言易于学习和使用。到目前为止，我们已经了解了[数据类型](https://thenewstack.io/python-for-beginners-data-types/)、 [range()函数](https://thenewstack.io/python-for-beginners-the-range-function/)、[和/或运算符](https://thenewstack.io/python-for-beginners-and-or-operators/)、[函数](https://thenewstack.io/so-much-more-python-for-beginners-functions/)、[将输入保存到文件](https://thenewstack.io/yet-more-python-for-beginners-saving-input-to-a-file/)、[python 控制台](https://thenewstack.io/more-python-for-non-programmers/)和[是什么让 Python 变得特殊](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)。所有这些条目应该加在一起，以帮助您理解 Python 的基础知识以及一些基本的编程概念。

我希望你已经明白的一件事是 Python 是多么容易学习，以及它是多么有用。有了足够的技巧和创造力，你可以让这种语言做很多事情。

我想向您介绍 Python 的另一个非常方便的特性，即打开和读取外部文件的能力。这是一个非常容易理解的概念，应用它可以真正帮助你成长为一名 Python 程序员。

但是用 Python 读取文件有什么含义呢？你能用它做什么？

比方说，你创建一个小程序，从一个文件中读取数据，并把它保存为一种信息数据库。使用这样的应用程序，您只需要编辑源文件，然后将更多条目添加到 save-to 文件中。

但是这是怎么做到的呢？

## 你需要什么

与本系列的所有文章一样，您需要安装 Python(可以在 Linux、macOS 或 Windows 上使用)。我将在 Ubuntu Linux 上演示，但是您需要改变的只是用于创建新文本文件的工具。

## 介绍 open()和 close()函数

从文件中读取数据的方法由 open()和 close()函数处理。打开文件后，您可以应用已经学习过的其他概念(比如 for 循环或 print()函数)。

我们同时使用 open()和 close()函数，因为如果我们不使用 close()函数，我们打开的文件将保持打开状态，这可能会导致以后出现问题。

首先，我们将学习如何使用 open()函数读取并打印出包含莎士比亚十四行诗 145 的文件内容。首先，让我们用以下命令创建一个名为 sonnet.txt 的文件:

`nano sonnet.txt`

在该文件中，粘贴以下内容:

爱情亲手做的嘴唇发出声音，对我说“我恨”
*为她而憔悴；* *但当她看到我的惨状时，* *直在她心里大发慈悲来了，* *丁池那曾经甜蜜的舌头* *被用来给予温柔的厄难，* *又教它这样从新去迎接；* *【我恨】她把它改成了结尾，* *它就像温柔的白昼* *跟随着黑夜，谁像一个魔神* *从天堂飞向地狱；* *‘我恨’从恨中挣脱她扔了，* *又救了我一命，说‘不是你’*

保存并关闭文件。

现在，我们将创建一个 python 脚本来读取该文件的内容，然后在终端中将它们打印出来。使用以下内容创建新的 Python 脚本:

`nano read_in.py`

首先，我们用下面一行打开 sonnet.txt 文件进行阅读:

`myfile = open(“sonnet.txt”)`

接下来，我们将使用 for 循环打印文件，一次一行。那个循环是这样的:

```
for line in myfile:

      print(line)

```

我们的整个脚本看起来是这样的:

```
#Open the sonnet.txt file for reading
myfile  =  open(“sonnet.txt”)

#Use a for loop to print the text
for line in myfile:
    print(line)

```

保存并关闭文件。使用以下命令运行 Python 脚本:

`python3 read_in.py`

您应该在输出中看到十四行诗的每一行。

我们还应该注意的一件事是关闭该文件(只是为了安全)。我们可以使用 close()函数来关闭该文件，代码行如下:

`myfile.close()`

所以，现在我们的脚本看起来是这样的:

```
#Open the sonnet.txt file for reading
myfile  =  open(“sonnet.txt”)

#Use a for loop to print the text
for line in myfile:
    print(line)

#Close the file
myfile.close()

```

## 如何读取输入并将其写入另一个文件

让我们更进一步。我们现在要做的是读取 sonnet.txt 的内容，并将其写入 poem.txt。

`nano write_out.py`

在脚本的第一部分，我们将打开第一个文件(sonnet.txt)进行读取，并以追加模式打开第二个文件(poem.txt )(因为我们可能不想覆盖文件中已经存在的内容。

那行看起来像这样:

`with open('sonnet.txt','r') as firstfile, open('poem.txt','a') as secondfile:`

所以我们将 sonnet.txt 定义为 firstfile，poem.txt 定义为 secondfile。我们现在可以使用 for 循环从 firstfile 读入每一行，然后将其追加到 secondfile。脚本的这些行看起来像这样:

`for line in firstfile:secondfile.write(line)`

我们的整个脚本看起来像这样:

```
# Open our files for reading and writing
with open('sonnet.txt','r')  as firstfile,  open('poem.txt','a')  as secondfile:

     # Read in the content from firstfile
     for line in firstfile:

              # Append the content to secondfile
              secondfile.write(line)

```

保存并关闭文件。

使用以下命令运行脚本:

`python3 write_out.py`

该命令将很快完成，您应该会在脚本所在的目录中找到一个名为 poem.txt 的新文件。poem.txt 的内容应该与 sonnet.txt 的内容相匹配。如果您再次运行该脚本，您会发现它在第一行的末尾附加了完整的十四行诗。继续运行它，让我们继续追加文本。

另一方面，如果您不想追加，您可以打开 secondfile 进行写入(这将覆盖 poem.txt 中的原始内容),代码如下:

`with open('sonnet.txt','r') as firstfile, open('poem.txt','w') as secondfile:`

我们已经将 a(表示追加)更改为 w(表示写入)。现在，无论你运行多少次脚本，poem.txt 中只会有一个十四行诗的副本。

这就是使用 Python 从一个文件中读取文本并将其写入另一个文件的方法。这个技巧将在很多 Python 应用程序中派上用场。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>