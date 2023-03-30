# CLI:使用 Go 进行命令行编程

> 原文：<https://thenewstack.io/cli-command-line-programming-with-go/>

CLI 或“命令行界面”是用户在命令行上与之交互的程序。Go 已经成为 CLI 开发的一个非常受欢迎的选择，因为它通过编译成静态二进制文件而缺乏部署依赖性。如果您编写了一个依赖于安装的 CLI，您就会知道这有多重要。

在本帖中，我们将介绍使用 Go 创建 CLI 的基础知识，以及这样做所需的标准库包。

## **自变量**

大多数 CLI 程序都希望有一些 CLI 参数形式的输入。程序参数在 Go 中作为一段字符串处理:

检索当前运行程序的名称

```
package main

import  (
    "fmt"
    "os"
)

func main()  {
    // Program Name is always the first (implicit) argument
    cmd  :=  os.Args[0]

    fmt.Printf("Program Name: %s\n",  cmd)
}

```

这个程序在 code/example1 目录下。您可以使用以下命令构建并运行它:

您应该会看到下面的输出:

### **确定传入程序的参数数量**

要找出传入了多少个参数，可以用参数的长度减去 1(记住第一个参数总是你的程序名)。或者，您可以通过使用操作系统来扩充切片。Args[1:]简单地说:“给我一个新的子片，从索引 1(不是 0)开始，到片的结尾。”

```
package main

import  (
    "fmt"
    "os"
)

func main()  {
    argCount  :=  len(os.Args[1:])
    fmt.Printf("Total Arguments (excluding program name): %d\n",  argCount)
}

```

运行这个。/example2 将导致总参数(不包括程序名):0

带着这个跑。/example 2–foo = bar 将导致总参数(不包括程序名):1

### **枚举参数**

这里有一个快速浏览当前参数的方法

```
package main

import  (
    "fmt"
    "os"
)

func main()  {
    for  i,  a  :=  range os.Args[1:]  {
        fmt.Printf("Argument %d is %s\n",  i+1,  a)
    }

}
Running the program with  ./example3  -local  u=admin  --help results in:
Argument  1  is  -local
Argument  2  is  u=admin
Argument  3  is  --help

```

### **国旗包**

到目前为止，我们已经研究了如何在一个非常基础的层次上看待一个程序的论点。在这个层次上询问它们并将它们分配给变量以在我们的程序中使用将是非常麻烦的。这就是[标志包](https://golang.org/pkg/flag/)的用武之地。

```
package main

import  (
    "flag"
    "fmt"
)

func main()  {
    var port int
    flag.IntVar(&amp;port,  "p",  8000,  "specify port to use.  defaults to 8000.")
    flag.Parse()

    fmt.Printf("port = %d",  port)
}

```

我们做的第一件事是声明我们将有一个 int 类型的标志，默认值为 8000，并使用文本来帮助用户理解我们对该标志的意图。

要让 flags 包填充您定义的标志，您需要调用 flag。Parse()。

不带任何参数运行该程序将导致 port = 8000。这是因为我们告诉标志包，如果没有任何东西传入端口，应该使用默认值 8000。

一起跑步。/example 4–p =9000 导致端口= 9000。

作为奖励，flag 包免费为我们提供“程序使用”输出。如果我们逃跑。/example 4–帮助我们获得:

的用法。/example4:
-p=8000:指定要使用的端口。默认为 8000。

### **旗帜。Args()**

许多 CLI 程序同时采用标志和“非标志”参数。旗帜。Args()将返回不考虑标志的参数。

```
package main

import  (
    "flag"
    "fmt"
)

func main()  {
    var port int
    flag.IntVar(&amp;port,  "p",  8000,  "specify port to use.  defaults to 8000.")
    flag.Parse()

    fmt.Printf("port = %d\n",  port)
    fmt.Printf("other args: %+v\n",  flag.Args())
}

```

用运行这个程序。/example5 -p=9000 foo=10 -bar 将导致:

port = 9000
其他参数:[foo=10 -bar]

一旦遇到任何不是以连字符开头的参数，标志包就会停止寻找标志。因为 foo=10 不是以连字符为前缀的标志，所以它和它后面的所有内容(包括-bar)都将被视为非选项标志。

这种区别使得 command [flags]子命令[subflags]样式的应用程序可以轻松构建。

### **无效的标志参数**

Go 是一种强类型语言，所以如果我们试图将任意字符串传递给 int 标志，它会让我们知道。

```
package main

import  (
    "flag"
    "fmt"
)

func main()  {
    var port int
    flag.IntVar(&amp;port,  "p",  8000,  "specify port to use.  defaults to 8000")
    flag.Parse()

    fmt.Printf("port = %d",  port)
}

```

运行这个程序。/example6 -p=foo 导致:

flag -p: strconv 的值“foo”无效。ParseInt:解析“foo”:无效语法
用法。/example6:
-p=8000:指定要使用的端口。默认为 8000

标志包不仅告诉我们哪里做错了，而且还打印出默认用法。

### **旗帜。用法**

flag 包公开声明了一个用法函数变量，允许我们把它重新赋给任何我们想要的函数，从而允许我们有自定义的用法输出。

```
package main

import  (
    "flag"
    "fmt"
    "os"
)

func main()  {
    flag.Usage  =  func()  {
        fmt.Printf("Usage of %s:\n",  os.Args[0])
        fmt.Printf("    example7 file1 file2 ...\n")
        flag.PrintDefaults()
    }
    flag.Parse()
}

```

运行这个程序。/example 7–帮助结果:

的用法。/example7:
example7 文件 1 文件 2 …

### **获取输入**

到目前为止，我们一直从我们的 CLI 输出，但一旦程序启动就不接受输入。我们可以用 fmt.Scanf.
通过 stdin 进行一些基本的输入捕获

```
package main

import  "fmt"

func main()  {
    var guessColor string
    const favColor  =  "blue"
    for  {
        fmt.Println("Guess my favorite color:")
        if  _,  err  :=  fmt.Scanf("%s",  &amp;guessColor);  err  !=  nil  {
            fmt.Printf("%s\n",  err)
            return
        }
        if favColor  ==  guessColor  {
            fmt.Printf("%q is my favorite color!",  favColor)
            return
        }
        fmt.Printf("Sorry, %q is not my favorite color.  Guess again.\n",  guessColor)
    }
}

```

### **蟾蜍。扫描仪**

而 fmt。Scanf 对于获取一些简单的输入非常有用，我们很多时候一次需要一整行。

```
package main

import  (
    "bufio"
    "fmt"
    "os"
)

func main()  {
    scanner  :=  bufio.NewScanner(os.Stdin)
    for scanner.Scan()  {
        line  :=  scanner.Text()
        if line  ==  "exit"  {
            os.Exit(0)
        }
        fmt.Println(line)  // Println will add back the final '\n'
    }
    if err  :=  scanner.Err();  err  !=  nil  {
        fmt.Fprintln(os.Stderr,  "reading standard input:",  err)
    }
}

```

这是一个基本的 echo 程序。要退出程序，请键入 exit。

## **一个基本的 cat 程序**

你们很多人都用过卡特彼勒。我们将把我们在这篇文章中学到的大部分内容放在一起，构建一个非常基础的 cat 版本。

```
package main

import  (
    "flag"
    "fmt"
    "io"
    "os"
)

func main()  {
    flag.Usage  =  func()  {
        fmt.Printf("Usage of %s:\n",  os.Args[0])
        fmt.Printf("    cat file1 file2 ...\n")
        flag.PrintDefaults()
    }

    flag.Parse()
    if flag.NArg()  ==  0  {
        flag.Usage()
        os.Exit(1)
    }

    for  _,  fn  :=  range flag.Args()  {
        f,  err  :=  os.Open(fn);  
        if err  !=  nil  {
            panic(err)
        }
        _,  err  =  io.Copy(os.Stdout,  f)
        if err  !=  nil  {
            panic(err)
        }
    }
}

```

### **救命！**

正如我们在上面已经提到的，如果您没有显式定义帮助参数，那么它们就是隐式定义的:

-h
–h
-帮助
–帮助

以上都将触发使用，并且根据您初始化标志解析器的方式，可能会导致您的包出错退出。另请注意，长格式和短格式的参数在标志包中被同等对待。

## **总结**

正如您所看到的，在使用 Go 构建 CLI 时有很多选项。在这篇文章中，我们只涉及了基础知识。我建议阅读以下资料，以获得更深入的知识:

## **附加命令行库**

有几个第三方库可以帮助简化 cli。我建议你看看它们是否也能满足你的需求。

[科里](https://twitter.com/corylanou) [蓝鸥](https://twitter.com/corylanou)是一位经验丰富的软件开发人员，拥有二十多年的经验，以及两年半的生产 [Go](https://golang.org/) 经验。他目前是 gSchool 的首席教练，在那里他教授围棋，并领导当地的丹佛围棋聚会，被恰当地称为丹佛地鼠

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>