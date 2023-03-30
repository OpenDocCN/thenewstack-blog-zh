# Python 初学者:何时以及如何使用元组

> 原文：<https://thenewstack.io/python-for-beginners-when-and-how-to-use-tuples/>

Python 是一种[非常强大和灵活的编程语言。对于初学者来说，它也是最好的语言之一，因为它不仅简单易学，不需要复杂的编译器，相反，它使用解释器来运行程序。所以你不用写程序，编译它，运行它…你只需简单地写它，运行它。](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)

在大多数情况下， [Python](https://www.python.org/) 很容易掌握。我们已经介绍了从文件中读取文本的[、](https://thenewstack.io/python-for-beginners-how-to-read-text-from-a-file/)[范围函数](https://thenewstack.io/python-for-beginners-the-range-function/)、[数据类型](https://thenewstack.io/python-for-beginners-data-types/)，以及围绕这种用户友好语言的许多其他概念。

但并不是每个概念都那么容易理解。一个这样的想法是元组。一个[元组](https://www.w3schools.com/python/python_tuples.asp)是一个可以保存多个条目的单个变量。尽管一旦你理解了这个特性的作用，使用起来还是很简单的。像 Python 集合、列表和字典一样，元组是内置的数据类型，但比其他选择更快。

也就是说，让我们学习什么是元组，以及如何编写/使用它们。

## 什么是元组？

用最简单的术语来说，Python 元组类似于一个[列表](https://thenewstack.io/python-for-beginners-lists/)，这是定义多个变量的一种简单方式。

所以不要像这样定义你的变量:

```
color1  =  "blue"
color2  =  "green"
color3  =  "red"
color4  =  "yellow"

```

然后你可以像这样打印出变量列表:

```
print  (color1,color2,color3,color4)

```

这很好，但是有了清单就容易多了。为了得到同样的效果，颜色列表应该是这样的:

```
color  =  ['blue','green','red','yellow']

```

然后你可以像这样打印出这个列表

```
<i>print  (color[0],  color[1],  color[2],  color[3])</i>

```

使用列表可以更容易有效地定义相似的变量。

与列表类似，元组是使用括号声明的值的集合。所以代替这个列表的是:

```
names  =  ['Olivia',  'Nathan',  'Bethany',  'Jacob']

```

我们这样格式化元组:

```
names  =  ('Olivia',  'Nathan',  'Bethany',  'Jacob')

```

除了[] vs()的明显用法，元组和列表还有什么区别？简单地说，你可以改变列表中的元素(一旦它们被赋值)，而对于元组，你不能。

想从 Python 解释器的角度来看区别吗？在安装了 Python 的计算机上打开终端窗口，并使用以下命令访问控制台:

`python3`

类型:

`names_l = ['Olivia', 'Nathan', 'Bethany', 'Jacob']`

现在，键入:

`names_t = ('Olivia', 'Nathan', 'Bethany', 'Jacob')`

好的，现在输入:

`print(type(names_l))`

按下键盘上的回车键，您应该会看到:

`<class 'list'>`

类型:

`print(type(names_t))`

按下键盘上的回车键，您应该会看到:

`<class 'tuple'>`

到目前为止，对于程序员来说，这种差别是很小的。使用元组而不是列表的一个关键是列表不能在字典中使用(因为列表是可变的)。

等一下。你说的这本字典是什么？Python 字典类似于列表，因为它是数据的集合。字典是关联数组的 Python 实现，使用键值对，如下:

```
NBA_TEAM  =  {

...  'Indiana'  :  'Pacers',

...  'Boston'  :  'Celtics',

...  'Los Angeles'  :  'Lakers',

...  'Milwaukee'  :  'Bucks'

...  }

```

然后你可以像这样打印出字典:

`print (NBA_TEAM) `

## 元组的类型

您可以使用四种不同类型的元组。首先，有一个空元组，它是这样写的:

`empty_tuple = ()`

打印出那个元组(用命令 *print(empty_tuple)* )，您将只看到作为输出的 *()* 。

下一种类型的元组是整数元组，如下所示:

`integer_tuple = (1, 2, 3)`

打印出这个元组，您应该会看到:

`(1, 2, 3)`

接下来，我们有一个混合数据类型的元组，可能如下所示:

`mixed_tuple = (0, "Hello", 1.2, "World!")`

打印出该元组，您应该会看到如下内容:

`(0, 'Hello', 1.2, 'World!')`

最后，我们有嵌套元组，它是元组中的元组，看起来像这样:

`nested_tuple = ("aardvark", [0, 1, 2], (2, 1, 0))`

如您所料， *print(nested_tuple)* 的输出将类似于:

`('aardvark', [0, 1, 2], (2, 1, 0))`

## 访问元组元素

这就是元组变得有点棘手的地方。让我们像这样创建一个基本的元组:

```
tns_tuple  =  ('N',  'e',  'w',  'S',  't',  'a',  'c',  'k')

```

现在，发出命令:

`print(tns_tuple[0])`

您应该看到打印出来的是:

`N`

记住，在 Python 中，计数从 0 开始，所以 N 在元组中的 0 位置。

当你想索引一个嵌套的元组时，事情变得有点棘手。让我们创建下面的嵌套元组:

```
n_tuple  =  ("kubernetes",  "cloud native",  [8,  6,  7,  5,  3,  0,  9])

```

让我们访问嵌套元组中的各种元素。因为这是嵌套的，所以我们有效地创建了三个元组:

```
tuple  0  =  kubernetes
tuple  1  =  cloud native
tuple  3  =  8,  6,  7,  5,  3,  0,  9

```

如果我想打印出元组 0 中的元素 3(即“kubernetes”中的字母“e”)，我可以发出以下命令:

`print(n_tuple[0][3])`

我所做的是告诉 Python 解释器打印出第一个元组(元组 0)中第三个位置的值。

我们还可以通过所谓的切片来访问元组中的一系列项。这是通过使用:字符来完成的。让我们回到我们的基本元组:

```
tns_tuple  =  ('N',  'e',  'w',  'S',  't',  'a',  'c',  'k')

```

为了打印出前三个元素，我们可以这样做:

`print(tns_tuple[0:3])`

该命令将打印出:

`('N', 'e', 'w')`

要打印出最后五个元素，命令应该是:

`print(tns_tuple[3:8])`

上面的命令会打印出来:

```
('S',  't',  'a',  'c',  'k')

```

我们可以对元组使用连接和重复。连接是用+运算符完成的，如下所示:

`print(('T', 'h', 'e') + ('N', 'e', 'w') + ('S', 't', 'a', 'c', 'k') )`

串联元组的输出如下所示:

```
('T',  'h',  'e',  'N',  'e',  'w',  'S',  't',  'a',  'c',  'k')

```

我们可以像这样用*操作符重复:

`print(("The New Stack",) * 3)`

上述命令的输出将如下所示:

```
('The New Stack',  'The New Stack',  'The New Stack')

```

最后，元组的另一个真正方便的特性是计数和索引项目的能力。让我们回到我们的基本元组(增加了一点):

```
tns_tuple  =  ('N',  'e',  'w',  'S',  't',  'a',  'c',  'k',  'R',  'o',  'k',  's')

```

假设您想要计算元组中有多少个 k。可以这样做:

`print(tns_tuple.count('k'))`

上述命令的输出将是 *2* ，因为元组中有两个 k。但是那些 k 洞的位置呢？让我们来看看:

`print(tns_tuple.index('k'))`

啊，我们遇到了一个问题。上面的命令将打印出 7 并停止。它不会继续索引。这是因为 *tuple.index* 正是为此而设计的。

为了找到第二个实例，我们不得不使用一些诡计，比如:

```
i  =  tns_tuple.index('k')
tns_tuple.index('k',  i  +  1)

```

应该打印出来:

这就是你对 Python 元组的介绍。请务必回顾本系列的其余部分，并继续关注新的堆栈，了解更多 Python 的优点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>