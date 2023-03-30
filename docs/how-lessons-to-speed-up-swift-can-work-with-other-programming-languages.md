# 提高 Swift 速度的课程如何适用于其他编程语言

> 原文：<https://thenewstack.io/how-lessons-to-speed-up-swift-can-work-with-other-programming-languages/>

Udemy online academy 最近发布了一个加快 Swift 学习的 10 大技巧，我在这里深入探讨了其中的 5 个，但是是在更广泛的背景下，包括其他编程语言，而不仅仅是 Swift。

## 1.使用类型推理

更好的编程语言有更短更简单的语法，使得源代码更容易阅读和理解。比如 Java，虽然很流行，但是没有类型推断。当你声明一个变量时，你必须指定它的类型，即使你赋了一个初始值。使用类型推断增加了代码的可读性。

下面的例子来自 GitHub 上的 AWS SDK for Java。有类型推断的语言有 ML、OCaml、F#、Haskell、Scala、D、Clean、Opa、Rust、Swift、Visual Basic(9.0 起)、c#(3.0 起)和 C++11。[谷歌碳](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/)太新了，还处于实验阶段，不包括在内。

在 Java 中，它是:

```
AWSRequestMetrics awsRequestMetrics  =  executionContext.getAwsRequestMetrics();

```

在 C#中是这个更短的版本:

```
var awsRequestMetrics  =  executionContext.getAwsRequestMetrics();

```

ide 需要能够从右边推断出类型，当然，你只能在有值要赋值的时候使用类型推断。如果你声明更少的未初始化变量，你会有更少的错误。

## 2.值类型通过复制传递

从 C 语言开始，许多编程语言都通过将值类型复制到函数中来传递值类型。值类型通常是简单的类型，比如整型**和浮点型**。相反的类型是引用类型，比如字符串和对象的实例。引用类型通常是 32 位长(在 32 位架构上),指向(或引用)别处的一块内存。

当您将值类型变量传递给函数调用时，如下面的 C 示例所示，变量 **b** 中的值通过复制传递给变量 **a** 。在函数 **dodouble()** 内部， **a** 中传入的值乘以 2，所以值为 20。但是，外部变量 **b** 保持不变，在打印结果中仍然是值 10。

```
#include &lt;stdio.h&gt;

int dodouble(int  a){
  a  =  a  *  2;
  return  a;
  }

  int main()  {
 int  b=10;
 printf("b=%d b*2= %d",b,dodouble(b));
 return  0;
  }

```

## 3.使事物通用化

编程的原则之一就是 d . r . y——不要重复自己。一种方法是使用泛型(也称为模板)。假设你有一个函数可以对**int**进行排序。您没有编写一个几乎相同的函数来排序 **floats** ，而是将它转换成一个通用函数，可以处理任何可排序的类型。然后你调用一个特定类型的函数，比方说一个浮点数组，只要有可能比较同一类型的两个元素，它就不管类型如何对它进行排序。

这个例子适用于任何值类型 **T** ，并使用 **BubbleSort** 对数组 **arr** 进行排序。 **where T : IComparable** 将它的使用限制在实现 **IComparable** 的类型 **T** 上。您可以通过添加一个方法 int **CompareTo(T t)** 将此与此进行比较，并根据比较结果是小于、等于还是大于，返回 **-1** 、 **0** 或 **1** ，从而将此添加到任何类型中。在这个例子中， **BubbleSort** 被调用了两次，分别在一个整型数组和一个浮点型数组上调用一次。这些都有隐式的 **CompareTo** ，不需要指定。

通常情况下，我不会使用冒泡排序，因为它是低效的，但它可以用来说明这一点。

```
    class  Program  
    {
        static void Swap(ref  T  x,  ref  T  y)
        {
            T  t  =  y;
            y  =  x;
            x  =  t;
        }

        public static void BubbleSort(  T[]  arr)  where  T  :  IComparable
        {
            for  (var  i  =  0;  i  &lt;  arr.Length;  i++)
            {
                for  (int  j  =  0;  j  &lt;  arr.Length  -  1;  j++) 
                { 
                    if  (arr[j].CompareTo(arr[j  +  1])  &gt;  0)
                        Swap(ref arr[j],  ref arr[j  +  1]);
                }
            }
        }

        static void Main(string[]  args)
        {
            int[]  vals  =  {98,  65,  1,  2,  8};
            float[]  valf  =  {9.8f,  2,  3f,  0.0f,  10.7f,  12.5f};
            BubbleSort(vals);
            BubbleSort(valf);
            foreach  (  var val in vals  )
            {
                Console.WriteLine(val);
            }
            foreach  (var val in valf)
            {
                Console.WriteLine(val);
            }
        }
    }

```

## 4.代表缺乏价值:期权

Swift 有一种非常简洁的方式来处理可以为空的引用类型和不能为空的值类型。它允许您用枚举值包装这两种类型，称为可选的。其他一些编程语言支持类似的概念。Java 有基本类型的包装类，C#有可空类型。C# (6.0)的下一个版本对可空类型进行了类似 Swift 的检查。

```
    List lines  =  ParseSourceCodeFile("Program.cs");
    return lines?.Count  ??  0;

```

这个读入文件 **program.cs** 。如果失败，可能是因为文件被锁定或不存在，那么变量行将为空，空合并操作符**？？**将返回 **0** 。

它简化了语法，消除了对 null 的检查，使编程稍微更像函数。

## 5.元组

Swift、Java、C#、Lisp、Python 等语言都支持元组。元组是相同或不同类型的值的有序集合。在 C#中，它是一个类，但与类不同的是，字段没有命名。它也不像列表，因为字段不是同一类型。

常见的用法是从函数调用中返回一个二元组，其中一个元素是错误代码，另一个是计算值。或者一个元组可以保存一个数据集，其组成部分代表单独的字段。在 C#中，有一个到七个值的预定义构造函数，第八个参数可以容纳更多的元组，理论上可以容纳任意数量的元组，尽管有点笨重。

在许多语言中元组是不可变的，尽管在 Swift 中您必须使用 **let** 而不是 **var** 来指定它为只读。

## 结论

这些编程技巧都适用于 Swift，但都是从现有的编程语言中提取的。通常情况下，掌握了一种编程语言，其他的就更容易了，因为你只是在填补空白。

专题图片:[瑞安·麦基](https://www.flickr.com/photos/ryan_mckee/)的《奥卡拉国家森林霍普金斯大草原[星迹》获得](https://www.flickr.com/photos/ryan_mckee/8566451925/in/photolist-e3ZiGZ-5DT9MZ-2MqBKX-nMH6ZM-nw7yPY-nxqyyb-xidLr-njaC1m-nMmcHM-61cX15-rhwijY-m4tjYp-nvsjDt-rLbaUs-nj9pCN-crwV8y-bvGxVF-qPhKaA-nBWZAv-niuzBc-8Dcrc7-8nrYBy-kCMJXv-a9tSqx-97Mf1q-rxaFn-cwiigy-61G3v7-8zLS4h-FGv3Y-61G39m-9huw5r-rvQoTD-gT6pn-nMN8H3-aum88m-eZMn6a-gopPwm-3QuztU-83ip7N-nHEVtP-rMjajk-8zzUsB-dYwoTT-8jDT2a-5nrizV-nvwnrV-8FXB5w-o5eLSK-dSzePd) [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>