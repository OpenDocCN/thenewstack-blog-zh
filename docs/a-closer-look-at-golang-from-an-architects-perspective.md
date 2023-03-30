# 从建筑师的角度看戈朗

> 原文：<https://thenewstack.io/a-closer-look-at-golang-from-an-architects-perspective/>

编者按:在以前的文章中，我们已经仔细研究了围棋。在这篇文章中，Shiju Varghese 从一个建筑师的角度来看 Golang，展示他认为不同寻常的语言的各个方面。

世界上的一切都在进化，计算机编程语言也是如此。在过去的五年里，我们看到了 Clojure、Rust、Julia 和 CoffeeScript 的出现，它们都代表了应用程序开发的转变。

Go 是一种新的编程语言，它不是从 C#和 Java 等现有编程语言发展而来的，也不是从它们那里借鉴来的。Go 根本无视编程语言理论。如果您来自 C# 5.0 或 Java 8.0 背景，并希望成为一种功能更丰富的语言，您将会失望。Go 不关注学术理论和学术思想，而是关注在云、分布式和并发计算环境以及系统编程上构建下一代应用程序的现实实践。

从事 C#语言研究已经超过十年，当我以一种清新务实的心态看待这种语言时，我对 Go 的设计感到非常兴奋。

我将向您提供 Go 的高级视图，然后重点介绍 Go 的类型系统和并发支持，这是该语言最独特的特性。

## 具有更高生产力水平的静态类型语言

Go 是一种静态类型、垃圾收集、本机编译的编程语言，就基本语法而言，它主要属于 C 语言家族。Go 为它的轻量级类型系统提供了一个富有表现力的语法，并发性是语言级别的一个内置特性。Go 提供了与 C 和 C++相当的性能，同时提供了快速开发。

如果您来自静态类型语言，那么您已经知道这种语言在性能和可维护性方面的强大功能。在保持 Go 作为静态类型语言的同时，它提供了动态类型语言的生产力，这要归功于 Go 惊人的简单语法和语言设计。你可以说 Go 是一个生产力很高的现代 C。如果你来自动态类型语言，Go 将解决你的性能和可维护性问题，同时保持生产力。

像 C 和 C++一样，Go 编译成本机代码，这样我们就不需要 CLR 和 JVM 这样的环境来运行 Go 应用程序。当您通过 Docker 之类的应用程序容器分发应用程序时，这会给您带来很多好处。

Go 编译器的另一个优点是编译程序非常快。这在编译大型应用程序时尤其有用。

### **简洁的语言和实用的设计**

如果你深入观察 Go 的设计，你会惊讶于它务实、简单、极简的做法。例如，如果名称以大写字母开头，Go 的类型将被导出到其他包中。以小写字母开头的类型不会导出到其他包，并且访问将受到同一个包的限制。

Go 的功能非常有限，但它不会影响您的工作效率，因为它包含了构建大型应用程序所需的所有功能。Go 的类型系统非常简单，遵循实用的设计，提供代码可重用性、生产力和可扩展性。

### **围棋式系统很牛逼**

如果你来自其他编程语言，试着用一种新鲜的思维来看待 Go，这样你就可以体验 Go 语言设计的强大和实用设计。Go 不提供 class 关键字，它的面向对象不同于其他面向对象编程语言。如果你正在寻找类似于 Go 中类的东西，你会找到 Go 的类型 struct。Go 不支持其类型系统中的继承，但支持类型的组合。如果你是一个务实的开发者，而不是学者，那么继承之上的组合会让你兴奋。

如果要将接口实现为结构类型，不需要显式实现接口类型和结构类型定义。相反，您只需要将接口中定义的方法实现到结构类型中。

这里有一个示例，演示了带有接口和结构的 Go 类型系统。它还探讨了类型组合的类型嵌入。

#### 代码清单–1

```
package main
import  "fmt"

type  People  interface  {
  SayHello()
  ToString()
}

type  Person  struct  {
  name string
  age int
  phone string
}

//A person method 
func  (p  Person  )  SayHello()  {
  fmt.Printf("Hi, I am %s, %d years old\n",  p.name,  p.age)
}
//A person method 
func  (p  Person)  ToString()  {
  fmt.Printf("[Name: %s, Age: %d, Phone: %s]\n",  p.name,p.age,  p.phone)
}

type  Student  struct  {
  Person  //type embedding for composition
  university string
  course string
}
type  Developer  struct  {
  Person  //type embedding for composition
  company string
  platform string
}
//Developer's method overrides Person's SayHello
func  (d  Developer)  SayHello()  {
  fmt.Printf("Hi, I am %s , %d years old, developer working on %s for %s\n",
  d.name,d.age,d.platform,d.company)
}
func main()  {
  alex  :=  Student{Person{"alex",  21,  "111-222-XXX"},  "MIT","BS CS"}
  john  :=  Developer{Person{"John",  35,  "111-222-XXX"},  "Accel North America",  "Golang"}
        jithesh  :=  Developer{Person{"Jithesh",  33,  "111-222-XXX"},  "Accel North America",  "Hadoop"}
        //An array with People types 
  peopleArr  :=  [...]People{alex,  john,jithesh}
        //Iterating through the array of People types and call methods.
  for  n,  _  :=  range  peopleArr  {
  peopleArr[n].SayHello()
  peopleArr[n].ToString()
  }
}

```

在上面的示例代码中，我们首先用两个方法声明一个名为“People”的接口类型——say hello 和 ToString。我们创建一个结构类型 Person 并添加两个方法，SayHello 和 ToString。不像 Java 和 C#，你不需要明确地声明你将实现一个接口到一个类型中。

在 Java 中，我们必须执行以下操作来实现接口:

#### 代码清单–2

```
public  class  Person  implements People{
//implementations here
}

```

在 C#中，我们必须执行以下操作来实现接口:

代码清单–3

```
public class Person  :  People{
//implementations here
}

```

在 Go 中，不需要显式声明接口实现，你只需要将接口中定义的方法实现到你想要实现它的结构类型中。这种简单的设计在以高效的方式构建松耦合系统时会给你带来很多好处。

在定义了结构类型“Person”之后，我们将类型“Person”嵌入到结构类型“Student”和“Developer”中。在 Go 中，组合是优于继承的方式，而类型嵌入是实现组合的方式。当您构建复杂的面向对象系统时，使用组合而不是继承的设计方法会给您带来很多实际优势。因为我们将类型 Person 嵌入到类型“Student”和“Developer”中，所以在类型“Person”中定义的方法将自动对类型“Student”和“Developer”可用。你可能会觉得这像是继承，但这是真正的作文，比继承有很多优势。我们还为类型“Developer”重写了 SayHello 方法。在 main 函数中，这是代码清单 1 中示例程序的入口点，我们创建一个 People 接口类型的数组，并分配一个“Person”对象和两个“Developer”对象，最后遍历数组并调用方法。

```
alex  :=  Student{Person{"alex",  21,  "111-222-XXX"},  "MIT","BS CS"}
john  :=  Developer{Person{"John",  35,  "111-222-XXX"},  "Accel North America",  "Golang"}
jithesh  :=  Developer{Person{"Jithesh",  33,  "111-222-XXX"},  "Accel North America",  "Hadoop"}

//An array with People types

peopleArr  :=  [...]People{alex,  john,jithesh}

//Iterating through the array of People types and call methods.

for  n,  _  :=  range  peopleArr  {
peopleArr[n].SayHello()
peopleArr[n].ToString()
}

```

如果你深入研究我们在代码清单-1 中演示的代码示例，你就会明白 Go 的类型系统的强大之处。与许多现有的编程语言相比，Go 的类型系统是 Go 的独特和最引人注目的特征。

我们将在接下来的关于 Go 的文章中探讨类型系统的特性。

### **并发性是语言级别的内置特性**

我们的计算机在过去的十年里不断发展。过去，我们针对具有单个 CPU 内核的计算机进行编程。但是今天，我们的服务器有 32 个、64 个、128 个和更多的 CPU 内核，但是我们仍然使用在只有单核机器可用的时代设计的编程语言和技术。如今，大多数编程语言通过库和框架提供对并发的支持，但不是在核心语言级别。在 Go 中，并发是核心语言中的一等公民。Go 引入了 Goroutines，它允许您并发运行函数。您可以使用通道在 Goroutines 之间通信和传递值。Goroutines 和 Channels 是 Go 的重要特性，可以让您以更安全、更高效的方式利用应用程序中的并发性和并行性。一些 Go 的标准库使用 Goroutines 内置了并发性。例如，为 http 编程提供支持的标准库“net/http”使用 Goroutines 同时处理传入的请求。

### **Go 套餐**

像 Go 的其他特性一样，包也提供了简单性。Go 程序被组织到称为包的文件目录中，这使得代码可以跨 Go 应用程序重用。我们可以使用 import 关键字导入 [Go 包](https://thenewstack.io/understanding-golang-packages/),这可以让您在应用程序中重用代码。在代码清单 1 中，我们从标准库中导入了一个包“fmt”。通过简单地使用 import 语句，我们可以从内置的标准库和 GOPATH 中导入包，GOPATH 是本地机器中的 Go 项目根目录。我们可以在终端使用“Go get”命令安装第三方 Go 包。

与 NPM、NuGet 和 RubyGems 等其他包管理系统不同，Go 并没有为 Go 包提供一个集中的存储库。Go 包管理系统是为现代场景设计的，在现代场景中，开发者通过 Github 上的存储库共享源代码。

终端中的以下命令将在您的 GOPATH 中安装一个第三方包“mgo ”,该包可以在 GOPATH 目录上的项目中使用。

去找 gopkg.in/mgo.v2

安装第三方包后，只需将 import 语句放入您的程序中，以便重用代码，如下所示:

```
import  (
  "gopkg.in/mgo.v2"
  )

```

### **总结**

令人惊讶的是，Go 是一种简单的编程语言。Go 的类型系统通过类型嵌入支持代码的可重用性，类型嵌入促进了组合而不是继承。在 Go 中，并发是核心语言中的一等公民，让您为现代计算环境构建高性能应用程序。Go 是为分布式、并发和云计算环境构建应用程序的绝佳语言。

Shiju Varghese 是一名解决方案架构师，专门研究云计算解决方案。他目前是 Accel Frontline 的技术架构师。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>