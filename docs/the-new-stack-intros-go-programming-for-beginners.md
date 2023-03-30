# 面向初学者的 Go 编程

> 原文：<https://thenewstack.io/the-new-stack-intros-go-programming-for-beginners/>

编者按:编程语言的流行程度可以根据各种标准来定义，正如最近在 New Relic 网站上发表的一篇文章所探讨的那样。例如，帖子引用 Go 作为 web 开发的编程语言的趋势。

对我们来说，Go，也称为 golang，是更有趣的编程语言之一，因为它在代表新一代松散耦合应用程序和基础设施的应用程序中的使用。 [Docker](https://thenewstack.io/a-great-introduction-to-docker-and-where-its-all-going/ "A Great Introduction to Docker, and Where It’s All Going") ，[云代工厂](https://thenewstack.io/docker-on-diego-cloud-foundrys-new-elastic-runtime/ "Docker on Diego, Cloud Foundry’s New Elastic Runtime")， [CoreOS](https://thenewstack.io/its-beta-time-for-coreos-the-linux-distro-for-massive-server-deployments/ "It’s Beta Time For CoreOS, The Linux Distro For Massive Server Deployments") ，[数字海洋](https://thenewstack.io/haproxy-still-an-arrow-in-the-quiver-for-those-scaling-apps/ "HAProxy Is Still An Arrow in the Quiver for Those Scaling Apps") …这些公司都做出了要去的承诺。

对我们来说，新的堆栈在许多方面代表了探索技术新思维的一种方式。创新的多样性和速度意味着它在某些时候对我们所有人来说都是新的。考虑到这一点，我们将推出一系列新的堆栈技术介绍。首先，我们请班加罗尔的一名工程系学生 Kartik Nayak 写下他对初学者指南的看法。所以，在这里，你去，新的堆栈介绍:初学者指南去。干杯。亚历克斯。

![go muscat](img/7272939ac1d5c8af780ece9674220c44.png)

Go 最初由 Google 开发，是一种静态类型语言，语法松散地来源于 C 语言，增加了垃圾收集、类型安全、一些动态类型功能、额外的内置类型(如可变长度数组和键值映射)以及一个大型标准库。

**创建人:**

Go 最初于 2007 年在谷歌开发，并于 2009 年 11 月发布。目前的稳定版本是 1.3 版。

**查看时间的用法:**

![go progress](img/bcf010d0baad5a3cfd9177004cc79bff.png)

资料来源:http://talks.golang.org/2014/hellogophers.slide

**为什么去？**

***围棋就像一个更好的 C，来自那个没给你带来 C++的家伙*”—Ikai Lan**

 ****围棋的特点:**

*   语法和环境采用模式。
*   快速编译时间。
*   远程包管理。
*   在线软件包文档。
*   内置并发原语。
*   接口来替换虚拟继承。
*   类型嵌入以替换非虚拟继承。
*   编译成静态链接的本机二进制文件，没有外部依赖。
*   简单的语言规范。
*   大型内置图书馆。
*   轻型测试框架。

## **围棋语言**

### 类型

#### **整数**

整数是没有小数部分的数字。与我们不同，计算机使用二进制表示法。Go 的整数类型有: *uint8，int8，uint16，int16，uint32，int32，uint64，int64* 。

8、16、32 和 64 告诉我们每种类型使用了多少位。

另外，*字节*是 *uint8* 的别名，是 *int32* 的*符文*。

还有 3 种机器相关的整数类型: *uint、int 和 uintptr* 。它们依赖于机器，因为它们的大小取决于您使用的架构类型。

```
var  x  int  =  404
var  y  uint32  =  234242

```

#### **浮点数**

浮点数可以定义为带有小数部分的数字，或者更一般地称为实数。

Go 有两种浮点类型: *float32* 和 *float64*

Go 也有两种复数类型:*复数 64* 和*复数 128*

```
var  x  float64  =  34.23
var  y  complex64  =  3  +  2i

```

#### **琴弦**

字符串是用于文本表示的固定长度的字符序列。

Go 中的字符串可以使用双引号“Hello World”或反引号`Hello World`来创建。

双引号不能包含换行符，但允许特殊的转义序列，如 *\n* 和 *\t* 。

可以使用 *+* 符号连接字符串。

使用 *len( < string > )* 函数可以获得字符串的长度。

使用索引，可以获得字符串的单个字符。

```
var weird string  =  "weird string"
a  :=  `Hello to all`

```

#### **布尔型**

布尔是一种特殊的 1 位整数类型，用于表示真或假。

可用于布尔运算的逻辑运算符有:

#### **变量**

Go 中的变量使用 *var* 关键字初始化，然后后跟变量名和变量类型。

```
var  x  int
var  y  string  =  "Hello world"

```

你也可以用更短的方式初始化变量。

这里的数据类型是内部分配的。

也可以使用赋值运算符声明常量，Go 中的数值常量是高精度值。

```
const  y  =  "Hello world"
const Pi  =  3.14

```

#### **回路和控制结构**

**为**

For 循环的使用就像在 C 和 Java 中一样。

```
for  i  :=  0;  i  &lt;  10;  i++  {
  fmt.Println("The value of i : ",  i)
}

```

或

```
for  i  !=  0  {
  fmt.Println("The value of i :",  i)
}

```

关键字 *range* 也可用于对一系列值进行排序

```
a  :=  [  ]int{4,  3,  1,  7,  3,  9,  2}
for  _,  i  :=  range  a  {
  sum  =  sum  +  i
}

```

**如果**

If 语句也类似于 C 和 Java 中的语句。

```
if num  %  2  ==  0  {
  fmt.Println("Even")
}  else  {
  fmt.Println("Odd")
}

```

#### **开关**

Switch 语句以关键字 *switch* 开始，后面是多个 cases。

```
switch  i  {
  case  0  :  fmt.Println("Zero")
  case  1  :  fmt.Println("One")
  case  2  :  fmt.Println("Two")
  case  3  :  fmt.Println("Three")
  case  4  :  fmt.Println("Four")
  case  5  :  fmt.Println("Five")
  case  6  :  fmt.Println("Six")
  case  7  :  fmt.Println("Seven")
  case  8  :  fmt.Println("Eight")
  case  9  :  fmt.Println("Nine")
  default  :  fmt.Println("Unknown Number")
}

```

### **阵列、切片和图谱**

#### **阵列**

类型*【n】T*是类型 *T* 的大小为 n 的数组。

```
var  a  [10]int  
x  :=  [5]float64  {
  34,
  63,
  56,
  84,
  23,
}

```

#### **切片**

切片是数组的一段。切片的长度是不固定的。切片的创建是通过 *make* 命令完成的。

#### **地图**

映射是键值对的无序集合。也称为关联数组、哈希表或字典，映射用于通过相关的键查找值。

```
var  x  map[string]int
x["Hello"]  =  1

```

#### **功能**

使用关键字 *func* 定义函数，后跟函数名、参数和返回值。

```
func say_hello()  {
  fmt.Println("Hello From the function")
}

```

如果结果参数已命名，则不带参数的返回语句返回变量的当前值

```
func details(a  []int)  (x,  y  int)  {
  x  :=  len(a)
  y  :=  cap(a)
}

```

#### **多种退货类型**

Go 支持多种返回类型。

```
func calculate(a,  b  int)  (sum,  prod int)  {
  sum  :=  a  +  b
  prod  :=  a  *  b
  return sum,  prod
}

func main()  {
  a,  b  :=  calculate(3,  4)
}

```

#### **可变函数**

函数可以接受 0 到特定数据类型的未定义变量。

```
func total(args  ...int)  (sum int)  {
  sum  :=  0
  for  _,  i  :=  range  args  {
  sum  =  sum  +  i
  }
  return sum
}

```

#### **关闭**

考虑下面的例子

```
func main()  {
dog  :=  func()  {
  fmt.Println("Woof!")
}
  dog()
}

```

这里我们实际上是在给一个变量赋值。

同理。

```
func increm()  func()  int  {
  x  :=  0
  return func()  int  {
  x  =  x  +  1
  return  x
  }
}

func main()  {
  y  :=  increm()
  fmt.Println(y)
  fmt.Println(y)
}

Output  :
1
2

```

这里，func *increm* 返回一个类型为 *func() int* 的 func，它仍然引用 func 主体之外的变量 *x* 。这就是所谓的闭包函数。

#### **指针**

指针，是的指针！Go 有指针，但是没有指针运算。

```
x  :=  5
y  :=  &amp;x
fmt.Println(*y)

Output  :
5

```

*y* 指向 *x* ，使用 *** 运算符获得 *y* 的值。&运算符用于获取变量的地址。

*新的*操作符用于为指针变量分配内存。

```
x  :=  new(int)
*x  =  9
fmt.Println(*x)

Output  :
9

```

### **结构、方法和接口**

#### 结构

结构是包含命名字段的用户定义的数据类型。结构基本上是 Go 中的一个对象，上面有数据类型和方法。

```
type  dog  struct  {
  breed string
  age int
  owner string
}

type  cow  struct  {
  age int
  farm string
}

rocky  :=  dog  {  "Lab",  5,  "Roy"  }
bigcow  :=  cow  {  age  :  3,  farm  :  "Donalds"  }
fmt.Println("Dogs age is : ",  rocky.age  )
fmt.Println("Cows age is : ",  bigcow.age  )

```

我们使用*类型*和*结构*关键字来声明结构。使用点运算符访问结构的各个元素。

#### **方法**

假设，我们想知道狗/牛说了什么，我们可以在给定的结构上定义一个方法来执行特定的任务，在我们的例子中就是说话。

```
func  (d  dog)  speak()  string  {
  return  "Woof"
}

func  (c  cow)  speak()  string  {
  return  "Moo"
}

```

有了这个你现在可以使用:

```
fmt.Println(dog.speak())
fmt.Println(cow.speak())

Output  :
Woof
Moo

```

在这里，函数 speak 分别接受狗和牛的类型，并根据类型返回一个字符串。

#### **接口**

接口基本上是方法的集合。让我们在函数 *speak* 上定义一个接口。

```
type  Speaker  interface  {
  speak()  string
}

```

因此，任何拥有名为 *speak* 的方法的类型都会自动满足扬声器接口。

因此我们可以。

```
var  a  Speaker
a  :=  dog  {  "Lab",  5,  "Roy"  }
fmt.Println(a)
a  :=  cow  {  age  :  3,  farm  :  "Donalds"  }
fmt.Println(a)

Output  :
{Lab  5  Roy}
{3  Donalds}

```

在 Go 界面中得到隐式满足，这是该语言最好的特性之一。

让我们举一个例子， *Println* 函数采用一个接口，该接口包含一个类型为 *String() string* 的方法

为*狗*类型定义我们自己的方法，我们可以按照最适合我们的方式打印数据。

```
func  (d  dog)  String()  string  {
  return fmt.Sprintf("The dog is %s, it is currently %d years old and belongs to %s",  d.breed,  d.age,  d.owner)
}
b  :=dog  {  "Lab",  5,  "Roy"  }
fmt.Println(b)

Output  :
The dog is Lab,  It is  5  years old and belongs to Roy

```

因为 dog 有一个 *String* 函数，而 *Println* 所取的接口需要一个 *String* 函数，所以我们满足那个接口。

### **并发**

Go 通过 goroutines 和通道为并发性提供了丰富的支持。这是该语言的亮点之一。

#### **Goroutines**

Goroutines 可以被描述为与其他函数同时运行的函数。它们在 *go* 关键字之后被调用。当调用该函数时，它会并发运行，而其余的代码会在不等待该函数完成的情况下执行。*主*函数是一个隐式的 goroutine。

```
func foo(n  int)  {
  for  i  :=  0;  i  &lt;  n;  i  =  i  +  2;  {
  fmt.Printf("%d : %d ",  n,  i)
  time.Sleep(time.Milliseconds *  50)
        }
}  

func main()  {
      for  i  :=  0;  i  &lt;  10;  i++  {
            go  f(i)
    }
 var input string
 fmt.Scanln(&amp;input)
}

```

现在该函数打印出不同 goroutines 的所有 no，因为它们是同时运行的。sleeper 确保特定的例程在下一次迭代之前等待 50 毫秒，这给了其他例程运行的时间。

#### **频道**

对于并发函数的相互通信，我们使用通道。频道必须在使用前创建，使用 *chan* 关键字。让我们创建一个类型为*字符串*的通道。

```
var  c  chan string  =  make(chan string)

```

让我们考虑一个小例子

```
func sender(c  chan string)  {
 for  {
              c  &lt;-  "Hello"
 }
}
func receiver(c  chan string)  {
 for{
                fmt.Println(

```

此处*发送器*函数连续向 *c* 通道发送字符串，接收器函数连续打印从该通道接收的值。

函数原型还可以限制进出通道的数据流的方向。

让我们更换*发送方*和*接收方*功能

```
func sender(c  chan&lt;-  string)
func receiver(c  &lt;-chan string)

```

处理通道时，还有一个*选择*选项，其作用类似于选择准备好的通道的开关语句。

## **最后的话**

要继续学习围棋，请看一下官方文档，我推荐这个教程。

我也经历了在 go 上举行的各种 Gophercons 的会谈，明年我将参加印度的 Gopeherconf。

看看 Go 代码是如何组织的，以及测试框架是如何在 Go 中使用的。学习使用自动代码格式化工具 *gofmt* 和自动文档生成器 godoc。

## **参考文献**

Kartik Nayak 是印度班加罗尔的一名工程系学生。不上大学的时候，可以看到他在学习 linux 内核和编码。也沉迷于休闲摄影。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**