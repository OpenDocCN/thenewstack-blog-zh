# 在 Go 中构建 Web 服务器

> 原文：<https://thenewstack.io/building-a-web-server-in-go/>

go([Golang.org](https://golang.org/ "Golang.org"))是一种系统编程语言，在其标准库中提供了标准的 HTTP 协议支持，这使得开发人员可以很容易地构建并快速运行 web 服务器。同时，Go 为开发者提供了很大的灵活性。在这篇文章中，我们列出了在 Go 中构建 HTTP web 服务器的几种方法，然后分析了这些不同的方法如何以及为什么在 Go 中都能完美工作。

在我们开始之前，我假设你有关于如何编写 Go 代码的基本知识，你理解 HTTP 并且知道什么是 web 服务器。然后，我们可以从 HTTP web 服务器版本中著名的“hello world”示例开始。

最好先看效果，再解释细节。创建一个名为`http1.go`的文件，将以下代码复制并粘贴到该文件中:

```
package main

import  (
  "io"
  "net/http"
)

func hello(w  http.ResponseWriter,  r  *http.Request)  {
  io.WriteString(w,  "Hello world!")
}

func main()  {
  http.HandleFunc("/",  hello)
  http.ListenAndServe(":8000",  nil)
}

```

在终端中，执行命令`go run http1.go`，然后打开浏览器，访问`http://localhost:8000`。你会看到`Hello world!`出现在你的屏幕上。

那是怎么发生的？在 Go 中，任何可运行的包都必须命名为`main`，这里我们有一个 main 函数和一个 hello 函数。

在主函数中，我们从包`net/http`中调用了函数`http.HandleFunc`来注册另一个函数为 handle 函数，在本例中就是 hello 函数。该函数接受两个参数。第一个是`string`类型的模式，这是您想要匹配的路由，在本例中是根路径。第二个参数是带有签名`func(ResponseWriter, *Request)`(【https://gowalker.org/net/http#HandleFunc】)的函数。如您所见，我们的 hello 函数有完全相同的签名，因此我们可以将它作为参数传递。下一行我们调用了`http.ListenAndServe(":8000", nil)`函数来监听端口为 8000 的本地主机。暂时忽略`nil`参数。

在 hello 函数中，我们有两个参数。一个带有类型`http.ResponseWriter`及其对应的响应流，实际上是一个接口类型。第二个是`*http.Request`及其对应的 HTTP 请求。我们不必使用所有的论点。就像在 hello 函数中一样，如果我们想要浏览器中的响应字符串`Hello world!`，那么我们只使用`http.ResponseWriter`。`io.WriteString`是一个帮助函数，让你将一个字符串写入一个给定的可写流。在 Go 中，我们称之为`io.Writer`接口。这不是这里的重点，所以知道它对我们有用就够了。

这个例子稍微复杂一点:

```
package main

import  (
  "io"
  "net/http"
)

func hello(w  http.ResponseWriter,  r  *http.Request)  {
  io.WriteString(w,  "Hello world!")
}

func main()  {
  mux  :=  http.NewServeMux()
  mux.HandleFunc("/",  hello)
  http.ListenAndServe(":8000",  mux)
}

```

在上面的例子中，我们不再使用函数`http.ListenAndServe`中的`nil`。相反，用一个类型为`*ServeMux`的变量来代替它。正如你可能猜到的，这个例子做的和前面的例子完全一样，但是我们使用变量`mux`来注册句柄函数，而不是直接从`net/http`包注册。底下是怎么回事？嗯，你可以直接在包级注册句柄函数的原因是因为`net/http`在包内有一个默认的`*ServeMux`，现在我们在这里定义了自己的函数。

为了使这个例子更加复杂，请看下面的代码:

```
package main

import  (
  "io"
  "net/http"
)

func hello(w  http.ResponseWriter,  r  *http.Request)  {
  io.WriteString(w,  "Hello world!")
}

var mux map[string]func(http.ResponseWriter,  *http.Request)

func main()  {
  server  :=  http.Server{
  Addr:    ":8000",
  Handler:  &amp;myHandler{},
  }

  mux  =  make(map[string]func(http.ResponseWriter,  *http.Request))
  mux["/"]  =  hello

  server.ListenAndServe()
}

type  myHandler  struct{}

func  (*myHandler)  ServeHTTP(w  http.ResponseWriter,  r  *http.Request)  {
  if  h,  ok  :=  mux[r.URL.String()];  ok  {
  h(w,  r)
  return
  }

  io.WriteString(w,  "My server: "+r.URL.String())
}

```

为了证实您的猜测，这次我们再次做同样的事情，在屏幕上显示`Hello world!`字符串。然而，我们不仅定义了`*ServeMux`，还定义了类型为`http.Server`的变量 server。至此，您应该知道为什么我们能够直接从`net/http`包运行和服务 HTTP 服务器了。是的，它在包中也有一个默认的服务器。我们在这里看到的新东西是我们定义的类型`myHandler`和它的方法`ServeHTTP`。在静态编程语言中，如何从标准库中定义一个自定义类型并在未修改的函数中使用它？道理很简单。`Handler`是一个接口，只需要实现一个签名为`func(w http.ResponseWriter, r *http.Request)`([https://gowalker.org/net/http#Handler](https://gowalker.org/net/http#Handler))的方法，必须命名为`ServeHTTP`。类型`myHandler`有接口期望的方法，所以我们很好。

你可以看到我们的代码是如何改变的，但目的是一样的。不要忘了亲自尝试这三个例子，然后做一些改变，看看这种改变如何表现。希望你喜欢！

**[陈嘉桦](https://www.linkedin.com/in/jiahua-chen-86218a81/)** 是一个地鼠，web 应用开发者，编码爱好者，视频课程制作者，勤奋的家伙，Go Walker，Gopm，Gogs 和 Macaron 的创造者。他还是 51CTO 学院、网易云课堂和 UCAI 的认证教师。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>