# 了解 Golang 包

> 原文：<https://thenewstack.io/understanding-golang-packages/>

在这篇文章中，我们将看看 Go 编程语言中的包。当我们开发软件应用程序时，编写可维护和可重用的代码非常重要。Go 通过其包生态系统提供了模块化和代码可重用性。Go 鼓励你通过包来编写小的软件组件，并用这些小的包来组成你的应用程序。

## **工作空间**

在讨论 Go 包之前，我们先讨论如何在 Workspace 中组织代码。在 Go 中，程序保存在一个叫做工作区的目录层次中。工作区就是你的 Go 应用程序的根目录。工作区在其根目录下包含三个子目录:

*   **src**–这个目录包含组织成包的源文件。您将在这个目录中编写 Go 应用程序。
*   **pkg**–该目录包含 Go 包对象。
*   bin–这个目录包含可执行程序。

在开发围棋程序之前，你必须指定工作空间的位置。GOPATH 环境变量用于指定 Go 工作区的位置。

## **套餐**

在 Go 中，源文件被组织到称为包的系统目录中，这使得代码可以跨 Go 应用程序重用。Go 包的命名约定是使用我们放置 Go 源文件的系统目录的名称。在单个文件夹中，属于该目录的所有源文件的包名将是相同的。我们在$GOPATH 目录中开发我们的 Go 程序，在那里我们将源代码文件组织到目录中作为包。在 Go 包中，如果标识符名称的第一个字母以大写字母开头，所有标识符都将被导出到其他包中。如果我们以小写字母开始标识符名称，那么函数和类型将不会被导出到其他包中。

Go 的标准库附带了许多有用的包，可用于构建真实世界的应用程序。例如，标准库提供了一个“net/http”包，可用于构建 web 应用程序和 web 服务。标准库中的包可以在 GOROOT 目录的“pkg”子目录中找到。当您安装 Go 时，一个环境变量 GOROOT 将自动添加到您的系统中，用于指定 Go 安装程序目录。Go 开发者社区非常热衷于开发第三方 Go 包。当您开发 Go 应用程序时，您可以利用这些第三方 Go 软件包。

## **包主**

当您构建可重用的代码片段时，您将开发一个作为共享库的包。但是当您开发可执行程序时，您将使用“main”包来使该包成为可执行程序。包“main”告诉 Go 编译器，这个包应该编译成一个可执行程序，而不是一个共享库。包“main”中的主函数将是我们可执行程序的入口点。当您构建共享库时，您不会在包中有任何主包和主函数。

下面是一个使用 main 包的示例可执行程序，其中 main 函数是入口点。

### **代码列表–1**

```
package main

import  (
"fmt"
)
func main(){
  fmt.Println("Hello, Gopher!")
}

```

### **进口包装**

关键字“import”用于将一个包导入其他包。在代码清单 1 中，我们将包“fmt”导入到示例程序中，以便使用函数 Println。包“fmt”来自 Go 标准库。当您导入包时，Go 编译器将查找由环境变量 GOROOT 和 GOPATH 指定的位置。GOROOT 位置提供了标准库中的软件包。您自己创建的包和您导入的第三方包都可以在 GOPATH 位置找到。

## **安装第三方软件包**

我们可以使用“Go get”命令下载并安装第三方 Go 包。Go get 命令将从源存储库中获取包，并将包放在 GOPATH 位置。

终端中的以下命令将把第三方 go 驱动程序包“mgo”安装到您的 GOPATH 中，它可以在 GOPATH 目录上的项目中使用:

安装完 mgo 后，将 import 语句放入程序中以重用代码，如下所示:

```
import  (        
        "gopkg.in/mgo.v2"  
        "gopkg.in/mgo.v2/bson" 
)

```

MongoDB 驱动程序 mgo 提供了我们在上面的 import 语句中导入的两个包。

## **初始化函数**

当您编写 Go 包时，您可以提供一个函数“init ”,它将在执行开始时被调用。init 方法可用于将初始化逻辑添加到包中。

### **代码列表–2**

```
package db
import  (
 "gopkg.in/mgo.v2"
        "gopkg.in/mgo.v2/bson"
)
func  init  {
 // initialization code here    
}

```

在某些情况下，我们可能只需要导入一个包来调用它的 init 方法，而不需要调用包的其他方法。如果我们导入了一个包，并且没有在程序中使用包标识符，Go 编译器将显示一个错误。在这种情况下，我们可以使用空白标识符(_)作为包别名，这样编译器会忽略不使用包标识符的错误，但仍会调用 init 函数。

### **代码列表–3**

```
package main
import  (
        _  "mywebapp/libs/mongodb/db"
  "fmt"
  "log"
)
func main()  {
  //implementation here
}

```

在上面的示例程序中，我们导入了一个名为 db 的包。假设我们只想用这个包来调用 init 方法。空白标识符将使我们能够避免来自 Go 编译器的错误，并且我们将能够调用包中定义的 init 方法。

我们可以为包使用别名来避免包名的不确定性。

### **代码列表–4**

```
package main
import  (
        mongo  "mywebapp/libs/mongodb/db"
        mysql  "mywebapp/libs/mysql/db" 
)
func main()  {
    mongodata  :=mongo.Get()  //calling method of package  "mywebapp/libs/mongodb/db"
    sqldata:=mysql.Get()  //calling method of package "mywebapp/libs/mysql/db"  
 fmt.Println(mongodata  )
 fmt.Println(sqldata  )
}

```

我们从两个不同的地方导入了两个不同的包，但是这两个包的名称是相同的。我们可以为一个包使用一个别名，并且当我们需要调用那个包的方法时，可以使用这个别名。

## **创建和重用包**

让我们创建一个示例程序来演示一个包。在 GOPATH 中的 github.com/shijuvar/go-samples-thenewstack/packagedemo/lib"位置为包“lib”创建一个源文件“languages.go”。由于“languages.go”属于文件夹“lib”，所以包名将被命名为“lib”。在 lib 文件夹中创建的所有文件都属于 lib 包。

### **代码列表–5**

```
package lib
var languages map[string]string
func init(){
  languages=  make(map[string]string)
  languages["cs"]  =  "C #"
  languages["js"]  =  "JavaScript"
  languages["rb"]  =  "Ruby"
  languages["go"]  =  "Golang"
}
func Get(key string)  (string){
  return languages[key]
}
func Add(key,value string){
  languages[key]=value
}
func GetAll()  (map[string]string){
  return languages
}

```

在上面的程序中，我们包含了一个 init 方法，这样这个方法将在执行开始时被调用。让我们构建我们的 Go 包，以便与其他包一起重用。在终端窗口中，转到 location lib 文件夹，并运行以下命令:

go install 命令将构建包“lib ”,该包位于 GOPATH 的 pkg 子目录中。

让我们创建一个“main.go ”,用于制作一个可执行程序，其中我们希望重用包“lib”中指定的代码。

### **代码清单–6**

```
package main

import  (
  "fmt"
  "github.com/shijuvar/go-samples-thenewstack/packagedemo/lib"
)

func main()  {
  lib.Add("dr","Dart")
  fmt.Println(lib.Get("dr"))
  languages:=lib.GetAll()
  for  _,  v  :=  range  languages  {
  fmt.Println(v)
  }
}

```

在上面的程序中，我们导入 lib 包并调用 lib 包提供的导出方法。

## **源代码**

示例演示的源代码可从[这里](https://github.com/shijuvar/go-samples-thenewstack/tree/master/packagedemo)获得。

## **总结**

Go 的设计理念是将可重用的代码块构建成包，并使用这些包开发应用程序。Go 程序被组织到称为包的目录中。Go 鼓励你通过将 Go 包的各个部分组合成一个应用程序来执行软件组合。Go 包支持代码的可重用性、模块化和更好的可维护性。

Shiju Varghese 是一名解决方案架构师，专门研究云计算解决方案。你可以在 https://twitter.com/shijucv T21 的推特上关注他。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>