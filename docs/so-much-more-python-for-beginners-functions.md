# 给初学者更多的 Python:函数

> 原文：<https://thenewstack.io/so-much-more-python-for-beginners-functions/>

我们又回到了[我们关于](https://thenewstack.io/python-for-beginners-lists/) [Python](https://www.python.org/) 的系列对于初学者来说，你可能无法完全掌握。好吧，这并不完全正确，因为你已经准备好进行下一步了。

这一次，我们将创建一个实际上可以做一些有用的事情的应用程序。这是什么神奇的应用？一个计算器。没错，这是一个方便的小工具，可以帮助你做加减乘除运算。在离开学校大约十年后，你可能需要这样一个应用程序。

暂时忽略你的智能手机。记住，这都是以教育的名义。

无论如何，这个小应用程序是学习两个非常重要的编程特性的好方法……函数和`if else`语句。

## 什么是函数？

简单地说，函数是一组相关的语句，它们被放在一起执行一个特定的任务。函数的语法如下所示:

*def 函数(参数):* *【语句(S)】*

其中:

*   函数是函数的名称。
*   参数是将值传递给函数的自变量。
*   语句是构成函数功能方面的比特。

理解所有语句必须有相同的缩进很重要，否则代码会出错。因此，包含多个语句的函数可能如下所示:

*def 函数(参数):* *statem ENT1* *statem ENT2* *statem ENT3*

缩进可以是制表符，也可以是空格，但是不能在一个代码块中混合使用这两种形式。

## 什么是 if else 语句？

If else 是一个条件语句，如果表达式为真，则运行一组语句，如果表达式为假，则运行另一组语句。

这样想:

```
num  =  3

if  (num  &gt;=  0):
       print("The number is zero or positive")
else:
       print("The number is negative")

```

我们已经将 num 设置为 3，所以它大于 0，这意味着它将打印出第一条语句。但是，如果我们将 num 设置为-5，它将打印出第二条语句。

因此，我们可以写出 if else 语句，如下所示:

如果数字大于或等于 0，则为正，否则为负。

现在，让我们将这两个很酷的特性用于我们的计算器。

## 创建函数

我们必须做的第一件事是编写我们的函数。使用以下内容创建新文件:

`nano calculator.py`

我们将创建四个函数，分别用于加、减、乘和除。

我们用 def(定义)开始每个函数。所以我们的第一个函数是加法，看起来像这样:

所以我们告诉 Python 我们正在定义一个函数，这个函数的名字是 add，我们的变量将是 x 和 y。我们以:，结束，因为这告诉 Python 这个函数还有更多的功能。该函数的最后一行是:

这告诉 Python 把 x 和 y 加在一起。所以我们的完整函数看起来是这样的:

```
def add(x,  y):
      return  x  +  y

```

就是这样。现在我们创建其余的函数，它们看起来像这样:

```
def add(x,  y):
     return  x  +  y

def subtract(x,  y):
     return  x  -  y

def multiply(x,  y):
     return  x  *  y

def divide(x,  y):
     return  x  /  y

```

接下来，我们将使用一些你已经学过的东西，print()语句。我们这里要做的是让用户在加、减、乘或除之间做出选择。用户不知道的是，他们正在我们创建的功能中进行选择。这部分看起来是这样的:

```
print("Select A Type of Calculation.")
print("1.Add")
print("2.Subtract")
print("3.Multiply")
print("4.Divide")

```

我要用 *while* loop 向你扔一个曲球。只要条件为真，就会执行一组语句。我们为什么需要这个？在我们的例子中，用户只能选择 1、2、3 或 4。如果他们打 5 呢？在这种情况下，我们的程序需要知道如何处理它。因此，如果用户键入 5，这意味着不满足 while 条件，它将通知他们输入无效，并要求他们做出另一个选择。所以我们的 while 循环有两个语句。第一个以
开始循环

```
while True:
     choice  =  input("Make your choice(1/2/3/4): ")

```

我们根据用户的输入设置选择变量，他们只能从四个有效选项中选择。如果用户输入一个有效的数字，while 循环将允许程序继续下一阶段。如果用户输入一个无效的数字，while 循环将跳转到它的 else 语句，即:

```
else:
print("Invalid Input")

```

else 语句将把它踢回到 while 循环的开始，并给用户另一个机会。

好的，我们的用户输入一个有效的数字，while 循环允许程序继续运行。下一阶段使用`elif`关键字，这意味着如果前面的条件不为真，那么尝试这个条件。

我们现在要做的是要求用户输入要执行的数字。我们首先要做的是通过用户的首选(1。补充，2。减去，3。相乘，4。Divide)到下一段语句。这是通过
完成的

```
if choice in  ('1',  '2',  '3',  '4'):
       num1  =  float(input("Enter first number: "))
       num2  =  float(input("Enter second number: "))

```

我们还用`float(input())`为 num1 和 num2(用户将输入)定义变量。float 函数将存储在字符串或整数中的数字转换为浮点数(带小数点的数字)。所以 2 会转换成 2.0。

接下来，我们有 if else 语句，它接受变量 choice 并将其传递给语句，如果 choice 等于 1，它会将数字相加，如果 choice 等于 2，它会将数字相减，如果 choice = 3，它会将数字相乘，如果 choice 等于 4，它会将数字相除。该部分如下所示:

```
if choice  ==  '1':
       print(num1,  "+",  num2,  "=",  add(num1,  num2))

elif choice  ==  '2':
       print(num1,  "-",  num2,  "=",  subtract(num1,  num2))

elif choice  ==  '3':
       print(num1,  "*",  num2,  "=",  multiply(num1,  num2))

elif choice  ==  '4':
       print(num1,  "/",  num2,  "=",  divide(num1,  num2))

```

注意双“==”。这实际上意味着平等。

每条语句将打印 num1 变量的值，后面跟着根据用户选择的运算符(+、-、*、/)。然后，它将打印出适当的操作符，并在其后跟随 num2 变量的值。然后，根据用户的选择，每条语句的最后一部分作用于 num1 和 num2。

应用程序的最后一部分询问用户是否想要运行另一个计算，看起来像这样:

```
# check if user wants another calculation
# break the while loop if the answer is no
next_calculation  =  input("Let's do next calculation? (yes/no): ")
if next_calculation  ==  "no":
break

```

如果用户键入 yes，程序将重新开始，否则将结束。

所以我们完整的 Python 脚本看起来是这样的:

```
def add(x,  y):
     return  x  +  y

def subtract(x,  y):
     return  x  -  y

def multiply(x,  y):
     return  x  *  y

def divide(x,  y):
     return  x  /  y

print("Select A Type of Calculation.")
print("1.Add")
print("2.Subtract")
print("3.Multiply")
print("4.Divide")

while True:

     # Accept input from user
     choice  =  input("Make your choice(1/2/3/4): ")

     # check if choice is one of the four options
     if choice in  ('1',  '2',  '3',  '4'):
         num1  =  float(input("Enter first number: "))
         num2  =  float(input("Enter second number: "))

         if choice  ==  '1':
             print(num1,  "+",  num2,  "=",  add(num1,  num2))

         elif choice  ==  '2':
             print(num1,  "-",  num2,  "=",  subtract(num1,  num2))

         elif choice  ==  '3':
             print(num1,  "*",  num2,  "=",  multiply(num1,  num2))

         elif choice  ==  '4':
             print(num1,  "/",  num2,  "=",  divide(num1,  num2))

         # check if user wants another calculation
         # break the while loop if the answer is no
         next_calculation  =  input("Let's do next calculation? (yes/no): ")
         if next_calculation  ==  "no":
           break

     else:
         print("Invalid Input")

```

保存并关闭文件。然后，您可以使用以下命令运行计算器:

`python3 calculator.py`

享受简单数学的新鲜味道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>