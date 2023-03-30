# Python 初学者:列表

> 原文：<https://thenewstack.io/python-for-beginners-lists/>

我们的 Python 初学者教程还在继续，所以让庆祝的“万岁！”响铃出去。我们首先[向您介绍了是什么让 Python 如此特别](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)，然后我们[介绍了变量](https://thenewstack.io/more-python-for-non-programmers/)，学习了如何接受用户的输入，并发现了如何将输入保存到文件中。

我们将继续以这些教程为基础，以任何人都可以跟随的方式来做。我们的目标是帮助那些天生不是程序员的人学习一门语言，并感觉他们已经掌握了足够的语言来为他们工作。

这一次，我们将讨论列表。我们一直在使用列表。购物清单，任务清单…你知道该怎么做。但是 Python 中的列表是另一种巨大的动物……某种程度上。

Python 中的列表用于存储单个变量的多个项目。你记得变量:

在上面的例子中，我们将值“绿色”赋给了变量“颜色”然后我们可以像这样在脚本中使用这个变量:

当我们运行我们的程序时，它会打印出来:

简单。但是如果我们想要定义多种颜色呢？当然，我们总是可以这样做:

```
color1  =  "blue"
color2  =  "green"
color3  =  "red"
color4  =  "yellow"

```

要打印出这些颜色，我们可以这样做:

```
print  (color1,color2,color3,color4)

```

我们的脚本应该是这样的:

```
#Define our variables as colors
color1  =  "blue"
color2  =  "green"
color3  =  "red"
color4  =  "yellow"

#Print out a list of colors
print  (color1,color2,color3,color4)

```

你可能不会惊讶地发现，在清单的帮助下，我们可以更容易地做到这一点。让我们坚持我们的颜色。让我们用四种颜色的列表来定义颜色变量。该变量声明如下所示:

```
color  =  ['blue','green','red','yellow']

```

现在，有些事情你必须明白。你可能认为每个列表项的位置应该是蓝色= 1，绿色= 2，红色= 3，黄色= 4。理解这一点很重要，在软件开发领域，计数从 0 开始。所以我们的颜色位置是蓝色= 0，绿色= 1，红色= 2，黄色= 3。为什么这很重要？让我展示给你看。

假设你想打印出绿色。要做到这一点，您可以添加以下代码行:

所以我们的应用程序应该是这样的:

```
#Define our variable as a list
color  =  ['blue','green','red','yellow']

#Print out a color
print  (color[1])

```

当你运行那个程序时，它会打印出绿色。

我们来补充一下。假设您想要定义一个水果变量来与颜色一致。所以我们可以定义:

```
fruit  =  ['blueberry','apple','cherry','banana]

```

你知道这是怎么回事了。要打印出*青苹果*，你可以使用下面的语句:

```
print  (color[1],fruit[1])

```

我们在位置 1 打印了颜色值，在位置 1 打印了水果值。

相当漂亮。

如果我们想把所有的颜色映射到所有的水果上会怎么样？看起来应该是这样的:

```
print  (color[0],fruit[0],  color[1],  fruit[1],  color[2],  fruit[2],  color[3],  fruit[3])

```

这个脚本应该是这样的:

```
#Define our color variable as a list
color  =  ['blue','green','red','yellow']
#Define our fruit variable as a list
fruit  =  ['blueberry','apple','cherry','banana]

#Print out both variables
print  (color[0],fruit[0],  color[1],  fruit[1],  color[2],  fruit[2],  color[3],  fruit[3])

```

如果我们运行该程序(使用类似 *python lists.py* 的命令)，输出将如下所示:

```
blue blueberry green apple red cherry yellow banana

```

让我们来点小技巧。如果我们希望我们的输出看起来像这样，而不是一行输出，会怎么样呢:

```
0     color     fruit
1     blue        blueberry
2     green      apple
3     red         cherry
3     yellow     banana

```

要做到这一点，我们需要在 Python 技能上有一个飞跃，引入一个框架，叫做 Pandas。Pandas 是一个用于数据分析和操作的框架。要使用熊猫，必须安装它。我在 Ubuntu Linux 20.04 上演示，Pandas 的安装是通过以下命令完成的:

`sudo apt-get install python3-pandas -y`

一旦安装了框架，您就可以随意使用它了。要使用 Pandas，我们必须用下面一行将其导入到我们的程序中:

`import pandas as pd`

这意味着我们将使用 pd 在脚本中调用熊猫函数。我们将要使用的 Pandas 函数是 DataFrame，它允许您处理二维的、大小可变的、潜在异构的表格数据。换句话说，它使您能够更轻松地处理不同类型的数据。

还和我在一起吗？

```
So far,  the parts of our script you now understand look like this:

#Import the Pandas framework, defined as pd
import pandas as pd

#Define our color variable as a list
color  =  ['blue','green','red','yellow']
#Define our fruit variable as a list
fruit  =  ['blueberry','apple','cherry','banana']

```

到目前为止，一切顺利。现在，我们到了具有挑战性的部分。我们要做的第一件事是使用我们的 color 和 fruit 变量作为 DataFrame 函数的列来定义一个新变量。这个新变量将被称为 *df* 。记住，我们用 pd 调用 Pandas，我们使用的函数是 DataFrame。这一行看起来像这样:

```
df=pd.DataFrame(columns=['color',  'fruit'])

```

所以我们的变量是`df`，我们用`pd`调用 Pandas，我们使用 DataFrame 函数并将变量 color 和 fruit 格式化为列。

好吗？很好。

现在，我们将使用已经创建的变量为我们的列定义标签，代码行是:

```
df['COLOR'],df['FRUIT']=color,fruit

```

最后，我们用
把它全部打印出来

我们的整个程序看起来是这样的:

```
#Import the Pandas framework, defined as pd
import pandas as pd

#Define our color variable as a list
color  =  ['blue','green','red','yellow']
#Define our fruit variable as a list
fruit  =  ['blueberry','apple','cherry','banana']

#Define the df variable as formatted columns for color and fruit
df=pd.DataFrame(columns=['color',  'fruit'])
#Label our columns as color and fruit
df['color'],df['fruit']=color,fruit

#Print everything
print(df)

```

现在，当我们运行应用程序时，我们将看到预期的输出:

```
0     color     fruit
1     blue        blueberry
2     green      apple
3     red         cherry
3     yellow     banana

```

我们确实在复杂性上有了一个飞跃，你现在知道如何利用外部框架(比如 Pandas)，让 Python 变得更加有用和灵活。

你应该已经觉得自己更聪明了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>