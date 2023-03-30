# 了解 Golang 类型系统

> 原文：<https://thenewstack.io/understanding-golang-type-system/>

在之前的文章“从架构师的角度看 Golang”中，我们提供了对 Go 编程语言的高层次观察。在这篇文章中，我们将看看 Go 的类型系统，主要关注用户定义的类型。

类型系统是编程语言最重要的特性，它允许你组织你的应用程序数据。Go 的类型系统遵循极简主义的方法。它提供了几个内置类型，如 string、bool、int 和 float64。

Go 支持数组、切片、贴图、通道等复合类型。复合类型由其他类型组成，包括内置类型和用户定义的类型。例如，复合类型“map[string]string”表示字符串值的集合，其中每个字符串值都用一个字符串键持久化，可以用相应的键检索值。

## **带有结构的用户定义类型**

在 Go 中，结构是创建用户定义的具体类型的方法。与其他编程语言相比，struct 类型的设计是独特的。

简单地说，结构是字段或属性的集合。与其他面向对象的语言不同，Go 不提供“class”关键字。相反，在 Go 中你会发现 struct——类的轻量级版本。如果结构体的名字以大写字母开头，那么结构体类型将被导出到其他 [Golang 包](https://thenewstack.io/understanding-golang-packages/)中。与其他面向对象的语言不同，您不需要在 struct 字段上提供 getter 和 setter，因为如果字段的名称以大写字母开头，它们可以从同一个包中访问，也可以从其他包中访问。

让我们创建一个结构类型。

### **代码列表–1**

```
type  Person  struct  {
  name string
  age int
  city,phone string
}

```

在上面的代码块中，我们创建了一个名为 Person 的结构。现在，我们可以创建 Person 类型的对象，并且可以存储我们的应用程序数据。

## **创建结构类型的实例**

让我们创建一个人员类型的实例，并将值分配给字段。

### ****代码列表–2****

```
var  p  Person
p.name="shiju"
p.age=35
p.city="Kochi"
p.phone="+91-94003372xx"

```

在上面的代码块中，我们创建了一个 Person 对象，并将值逐个分配给字段。我们还可以使用 struct 文本来创建 struct 类型的实例。

### **代码列表–3**

```
p:=  Person  {
 name  :  "shiju",
 age  :  35,
 city  :  "Kochi",
 phone  :  "+91-94003372xx",  
}

```

我们通过使用 struct 文本创建了一个 Person 类型的实例。当我们使用结构文字创建结构类型的实例时，我们可以将代码分成多行，但是我们需要在最后一个赋值的末尾添加一个额外的逗号。

如果我们清楚地知道结构字段的顺序，我们可以用更短的方式创建实例。

### **代码清单–4**

```
p:=  Person  {
 "shiju",
 35,
 "Kochi",
 "+91-94003372xx",  
}

```

我们可以用一行语句创建实例。

###  ****代码清单–5****

```
p:=  Person  {"shiju",35,"Kochi","+91-94003372xx"}

```

## **用接口类型定义行为**

接口类型提供了具体类型的契约，这允许您为对象定义行为。让我们创建一个接口类型来指定 Person 对象的行为。

### **代码列表–6**

```
type  People  interface  {
  SayHello()
  GetDetails()
}

```

我们定义了一个名为 People 的接口类型，其中我们指定了两个行为——say hello 和 GetDetails。

## **向具体类型添加行为**

在代码清单 6 中，我们定义了一个接口来实现 Person 对象。让我们将这些行为实现到我们的具体类型中。

在这个示例中，我们将使用方法将接口类型 People 中定义的行为实现到 Person 类型中。在大多数面向对象的语言中，方法与类相关联，但是在 Go 中，方法与结构类型相关联。

让我们给我们的人类型添加一些行为。在 Go 中，不需要显式声明接口实现。您只需要将接口中定义的方法实现到您想要实现接口类型的结构类型中。

###  ****代码清单–7****

```
type  Person  struct  {
  name string
  age int
  city,phone string
}
//A person method
func  (p  Person  )  SayHello()  {
  fmt.Printf("Hi, I am %s, from %s\n",  p.name,  p.city)
}
//A person method
func  (p  Person)  GetDetails()  {
  fmt.Printf("[Name: %s, Age: %d, City: %s, Phone: %s]\n",  p.name,p.age,  p.city,  p.phone)
}

```

Go 中的方法只是一个用接收器声明的函数。如果要从方法中修改接收方的数据，接收方必须是如下所示的指针:

### **代码列表–8**

```
//A person method
func  (p  *Person  )  SayHello()  {
//Implementations here 
}
//A person method
func  (p  *Person)  GetDetails()  {
//Implementations here 
}

```

## **嵌入类型与成分**

Go 的类型系统不支持继承。在 Go 中，组合优先于继承，类型嵌入是实现组合的方式。许多务实的开发人员支持使用复合而不是继承。

在这个示例程序中，我们将通过将 Person 类型嵌入到新的类型中来创建更多专门的 Person 类型，用于表示 meetup 人员，如组织者、演讲者和与会者。让我们通过嵌入 Person 类型来创建代表组织者、演讲者和参与者的类型。

### ****代码清单–9****

```
type  Speaker  struct  {
  Person  //type embedding for composition
  speaksOn  []string
  pastEvents  []string
}

type  Organizer  struct  {
  Person  //type embedding for composition
  meetups  []string
}

type  Attendee  struct  {
Person  //type embedding for composition
interests  []string
}

```

在上面的代码块中，我们通过嵌入 Person 类型创建了三种新类型——组织者、演讲者和参与者。当我们将一个类型嵌入到另一个类型中时，嵌入类型的方法将有利于新的类型。因此，SayHello 和 GetDetails 方法将可用于新创建的类型 Organizer、Speaker 和 Attendee。我们的新类型还实现了 People 接口，因为 SayHello 和 GetDetails 方法在新类型上可用。我们也可以在新类型中覆盖 Person 的方法。

## **运行一个带有结构和接口的示例程序**

让我们创建代表会议的类型。

### **代码列表–10**

```
type  Meetup  struct
{
  location string
  city string
  date time.Time
  people  []People
}
func  (m  Meetup)  MeetupPeople(){
  for  _,  v  :=  range  m.people  {
  v.SayHello()
  v.GetDetails()
  }
}

```

这里，我们创建了一个名为 Meetup 的类型，其中包含了接口类型 Person 的一部分作为结构字段。因为我们将接口 People 实现为组织者、演讲者和参与者类型，所以我们可以将这些类型的实例分配到 People struct 字段中。我们在 Meetup 结构中添加了一个名为 MeetupPeople 的方法，在这个方法中，我们遍历接口类型 People 的切片，并调用方法 SayHello 和 GetDetails。

在最后的程序中，我们覆盖了演讲者和组织者类型的 GetDetails 方法，因为它们代表了比参与者更多的信息。对于 Attendee 对象，将使用 Person 的 GetDetails 方法。

这是最后一个程序:

### **代码列表–11(meetup . go)**

```
package main
import  (
  "fmt"
  "time"
)
type  People  interface  {
  SayHello()
  GetDetails()
}
type  Person  struct  {
  name string
  age int
  city,phone string
}
//A person method
func  (p  Person  )  SayHello()  {
  fmt.Printf("Hi, I am %s, from %s\n",  p.name,  p.city)
}
//A person method
func  (p  Person)  GetDetails()  {
  fmt.Printf("[Name: %s, Age: %d, City: %s, Phone: %s]\n",  p.name,p.age,  p.city,  p.phone)
}
type  Speaker  struct  {
  Person  //type embedding for composition
  speaksOn  []string
  pastEvents  []string
}
//overrides GetDetails
func  (s  Speaker)  GetDetails()  {
  //Call person GetDetails
  s.Person.GetDetails()
  fmt.Println("Speaker talks on following technologies:")
  for  _,  value  :=  range  s.speaksOn  {
  fmt.Println(value)
  }
  fmt.Println("Presented on the following conferences:")
  for  _,  value  :=  range  s.pastEvents  {
  fmt.Println(value)
  }
}
type  Organizer  struct  {
  Person  //type embedding for composition
  meetups  []string
}
//overrides GetDetails
func  (o  Organizer)  GetDetails()  {
  //Call person GetDetails
  o.Person.GetDetails()
  fmt.Println("Organizer, conducting following Meetups:")
  for  _,  value  :=  range  o.meetups  {
  fmt.Println(value)
  }
}
type  Attendee  struct  {
Person  //type embedding for composition
interests  []string
}
type  Meetup  struct
{
  location string
  city string
  date time.Time
  people  []People
}
func  (m  Meetup)  MeetupPeople(){
  for  _,  v  :=  range  m.people  {
  v.SayHello()
  v.GetDetails()
  }
}
func main()  {
  shiju  :=  Speaker{Person{"Shiju",  35,"Kochi"  ,"+91-94003372xx"},
  []string{"Go","Docker",  "Azure","AWS"},
  []string{"FOSS","JSFOO","MS TechDays"}}
  satish  :=  Organizer{Person{"Satish",  35,"Pune"  ,"+91-94003372xx"},
  []string{"Gophercon","RubyConf"}}
  alex  :=  Attendee{Person{"Alex",  22,"Bangalore"  ,"+91-94003672xx"},
  []string{"Go","Ruby"}}
    meetup:=Meetup  {
  "Royal Orchid",
  "Bangalore",
  time.Date(2015,  time.February,  19,  9,  0,  0,  0,  time.UTC),
  []People{shiju,satish,alex},
  }
  //get details of meetup people
  meetup.MeetupPeople()
}

```

在 main 函数中，这是我们示例程序的起点，我们为演讲者、组织者和与会者类型创建一个对象，然后创建一个包含三个对象的 slice 对象，并将 slice 对象分配到 Meetup 类型的 People 字段，这是 People 接口的一个切片。如果你深究一下源码 meetup.go，你就会明白 go 的接口类型的强大之处。

您可以通过在终端中输入以下内容来运行 meetup.go 程序:

去运行 meetup.go

meetup.go 的来源可从[这里](https://github.com/shijuvar/go-samples-thenewstack/blob/master/typesystem/meetup.go)获得。

## **总结**

Go 提供了一个轻量级的类型系统，通过类型嵌入来实现代码的可重用性，并促进组合而不是继承。如果类型名以大写字母开头，Go 中的类型将被导出到其他包中。结构用于在 Go 中创建用户定义的具体类型。在 Go 中，方法与结构类型相关联。Go 中的方法只是一个用接收器声明的函数，方法可以通过接收器类型调用。接口是 Go 的一个非常棒的特性，它具有强大的功能和可扩展性。当将接口类型实现为具体类型时，不需要显式声明接口类型和结构定义。相反，它会在运行时将接口类型隐式实现到您的类型中。

Shiju Varghese 是一名解决方案架构师，专门研究云计算解决方案。你可以在 https://twitter.com/shijucv 的推特上关注他。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>