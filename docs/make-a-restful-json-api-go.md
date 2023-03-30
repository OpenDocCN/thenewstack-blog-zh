# 在 Go 中制作 RESTful JSON API

> 原文：<https://thenewstack.io/make-a-restful-json-api-go/>

在这篇文章中，我们不仅会讨论如何使用 Go 来创建一个 RESTful JSON API，还会讨论好的 RESTful 设计。如果你在过去曾经使用过一个没有遵循好的设计的 API，那么你最终会写出糟糕的代码来使用一个糟糕的 API。希望在这篇文章之后，你会对一个行为良好的 API 有更好的理解。

## 什么是 JSON API？

在 JSON 之前，有 XML。既使用了 XML 又使用了 JSON，毫无疑问 JSON 是明显的赢家。我不打算深入讨论 JSON API 的概念，因为它在[jsonapi.org](http://jsonapi.org/)上已经有很详细的介绍了。

## 一个基本的网络服务器

RESTful 服务首先从根本上是一个 web 服务开始。这是一个非常基本的 web 服务器，它通过简单地输出请求 url 来响应任何请求:

```
package main

import  (
    "fmt"
    "html"
    "log"
    "net/http"
)

func main()  {
    http.HandleFunc("/",  func(w  http.ResponseWriter,  r  *http.Request)  {
        fmt.Fprintf(w,  "Hello, %q",  html.EscapeString(r.URL.Path))
    })

    log.Fatal(http.ListenAndServe(":8080",  nil))

}

```

运行这个例子将在端口 8080 上启动一个服务器，并且可以在 [http://localhost:8080](http://localhost:8080/) 上访问

## 添加路由器

虽然标准库带有路由器，但我发现大多数人对它的工作原理感到困惑。我在我的项目中使用了一些第三方路由器。最值得注意的是，我使用了来自 [Gorilla Web Toolkit](http://www.gorillatoolkit.org/) 的 [mux 路由器](http://www.gorillatoolkit.org/pkg/mux)。

另一个流行的路由器是 Julien Schmidt 生产的，名为[http outer](https://github.com/julienschmidt/httprouter)。

```
package main

import  (
    "fmt"
    "html"
    "log"
    "net/http"

    "github.com/gorilla/mux"
)

func main()  {

    router  :=  mux.NewRouter().StrictSlash(true)
    router.HandleFunc("/",  Index)
    log.Fatal(http.ListenAndServe(":8080",  router))
}

func Index(w  http.ResponseWriter,  r  *http.Request)  {
    fmt.Fprintf(w,  "Hello, %q",  html.EscapeString(r.URL.Path))

```

要运行这个示例，您现在需要执行以下命令:

这将从 GitHub 的“github.com/gorilla/mux”中检索 Gorilla Mux 包

上面的例子创建了一个基本的路由器，添加了 route /你现在还会注意到，在我们可以请求[http://localhost:8080/foo](http://localhost:8080/foo)之前，它成功了。因为没有定义路由，所以现在不再有效。只有 [http://localhost:8080](http://localhost:8080/) 将是有效的响应。

## 创建一些基本路线

现在我们已经有了路由器，是时候创建更多的路由了。

假设我们要创建一个基本的 ToDo 应用程序。

```
package main

import  (
    "fmt"
    "log"
    "net/http"

    "github.com/gorilla/mux"
)

func main()  {

    router  :=  mux.NewRouter().StrictSlash(true)
    router.HandleFunc("/",  Index)
    router.HandleFunc("/todos",  TodoIndex)
    router.HandleFunc("/todos/{todoId}",  TodoShow)

    log.Fatal(http.ListenAndServe(":8080",  router))
}

func Index(w  http.ResponseWriter,  r  *http.Request)  {
    fmt.Fprintln(w,  "Welcome!")
}

func TodoIndex(w  http.ResponseWriter,  r  *http.Request)  {
    fmt.Fprintln(w,  "Todo Index!")
}

func TodoShow(w  http.ResponseWriter,  r  *http.Request)  {
    vars  :=  mux.Vars(r)
    todoId  :=  vars["todoId"]
    fmt.Fprintln(w,  "Todo show:",  todoId)
}

```

我们现在已经增加了两个端点(或路线)

这是 Todo 索引路由:http://localhost:8080/todos

这是 Todo 显示路由:http://localhost:8080/todos/{ Todo id }

这是 RESTful 设计的开始。

请密切注意最后一条路由，我们在该路由中添加了一个变量，名为 todo id:http://localhost:8080/todos/{ todo id }

这将允许我们向路由传递 id，并使用正确的记录进行响应。

## 基本模型

既然我们已经有了路由，那么是时候创建一个基本的 Todo 模型来发送和检索数据了。在 Go 中，一个结构通常会作为你的模型。许多其他语言使用类来实现这个目的。

```
package main

import  "time"

type  Todo  struct  {
    Name      string
    Completed bool
    Due time.Time
}

type Todos  []Todo

```

注意，在最后一行我们创建了另一个类型，称为 Todos，它是 Todo 的一个片段(有序集合)。您将很快看到这在哪里变得有用。

## 发回一些 JSON

现在我们有了一个基本模型，我们可以模拟一个真实的响应，并用静态数据模拟 TodoIndex。

```
func TodoIndex(w  http.ResponseWriter,  r  *http.Request)  {
    todos  :=  Todos{
        Todo{Name:  "Write presentation"},
        Todo{Name:  "Host meetup"},
    }

    json.NewEncoder(w).Encode(todos)
}

```

目前，我们只是创建了一个静态的 Todos 片段并发送给客户端。现在，如果您请求 http://localhost:8080/todos，您应该会得到以下响应:

```
[
    {
        "Name":  "Write presentation",
        "Completed":  false,
        "Due":  "0001-01-01T00:00:00Z"
    },
    {
        "Name":  "Host meetup",
        "Completed":  false,
        "Due":  "0001-01-01T00:00:00Z"
    }
]

```

## 更好的模型

对于任何经验丰富的老手来说，你已经发现了一个问题。虽然听起来无关紧要，但大写键并不是 JSON 的惯用做法。这是你解决这个问题的方法。

```
package main

import  "time"

type  Todo  struct  {
    Name      string    `json:"name"`
    Completed bool      `json:"completed"`
    Due time.Time  `json:"due"`
}

type Todos  []Todo

```

通过添加 struct 标签，你可以精确地控制你的结构将如何被封送到 JSON。

## 好吧，我们得把这个分开！

在这一点上，项目需要一点重构。我们在几个文件里有太多的事情要做。

我们现在将创建以下文件，并相应地移动代码:

*   main.go
*   handlers.go
*   routes.go
*   todo.go

### Handlers.go

```
package main

import  (
    "encoding/json"
    "fmt"
    "net/http"

    "github.com/gorilla/mux"
)

func Index(w  http.ResponseWriter,  r  *http.Request)  {
    fmt.Fprintln(w,  "Welcome!")
}

func TodoIndex(w  http.ResponseWriter,  r  *http.Request)  {
    todos  :=  Todos{
        Todo{Name:  "Write presentation"},
        Todo{Name:  "Host meetup"},
    }

    if err  :=  json.NewEncoder(w).Encode(todos);  err  !=  nil  {
        panic(err)
    }
}

func TodoShow(w  http.ResponseWriter,  r  *http.Request)  {
    vars  :=  mux.Vars(r)
    todoId  :=  vars["todoId"]
    fmt.Fprintln(w,  "Todo show:",  todoId)
}

```

### Routes.go

```
package main

import  (
    "net/http"

    "github.com/gorilla/mux"
)

type  Route  struct  {
    Name        string
    Method      string
    Pattern string
    HandlerFunc http.HandlerFunc
}

type Routes  []Route

func NewRouter()  *mux.Router  {

    router  :=  mux.NewRouter().StrictSlash(true)
    for  _,  route  :=  range  routes  {
        router.
            Methods(route.Method).
            Path(route.Pattern).
            Name(route.Name).
            Handler(route.HandlerFunc)
    }

    return router
}

var routes  =  Routes{
    Route{
        "Index",
        "GET",
        "/",
        Index,
    },
    Route{
        "TodoIndex",
        "GET",
        "/todos",
        TodoIndex,
    },
    Route{
        "TodoShow",
        "GET",
        "/todos/{todoId}",
        TodoShow,
    },
}

```

### Todo.go

```
package main

import  "time"

type  Todo  struct  {
    Name      string    `json:"name"`
    Completed bool      `json:"completed"`
    Due time.Time  `json:"due"`
}

type Todos  []Todo

```

### Main.go

```
package main

import  (
    "log"
    "net/http"
)

func main()  {

    router  :=  NewRouter()

    log.Fatal(http.ListenAndServe(":8080",  router))
}

```

## 更好的路由

作为重构的一部分，我们创建了一个更加通用的 routes 文件。这个新文件现在利用一个结构来包含关于路由的更详细的信息。具体来说，我们现在可以指定操作，如 GET、POST、DELETE 等。

## 输出网络日志

在分割路线文件时，我还有一个不可告人的动机。您很快就会看到，现在用额外的功能来装饰我的 http 处理程序变得非常容易。

让我们像大多数现代 web 服务器一样，从注销 web 请求的能力开始。在 Go 中，标准库中没有 web 日志包或功能，所以我们必须创建它。

我们将创建一个名为 logger.go 的文件，并添加以下代码:

```
package main

import  (
    "log"
    "net/http"
    "time"
)

func Logger(inner http.Handler,  name string)  http.Handler  {
    return http.HandlerFunc(func(w  http.ResponseWriter,  r  *http.Request)  {
        start  :=  time.Now()

        inner.ServeHTTP(w,  r)

        log.Printf(
            "%s\t%s\t%s\t%s",
            r.Method,
            r.RequestURI,
            name,
            time.Since(start),
        )
    })
}

```

这是围棋中非常标准的习语。实际上，我们将把我们的处理程序传递给这个函数，然后这个函数将把传递的处理程序与日志和计时功能包装在一起。

接下来，我们需要在我们的路由中使用 logger 装饰器。

## 应用记录器装饰器

为了应用装饰器，当我们创建路由器时，我们将简单地通过更新我们的 NewRouter 函数:
将我们所有的当前路由包装在其中

```
func NewRouter()  *mux.Router  {

    router  :=  mux.NewRouter().StrictSlash(true)
    for  _,  route  :=  range  routes  {
        var handler http.Handler

        handler  =  route.HandlerFunc
        handler  =  Logger(handler,  route.Name)

        router.
            Methods(route.Method).
            Path(route.Pattern).
            Name(route.Name).
            Handler(handler)
    }

    return router
}

```

现在，当您请求 http://localhost:8080/todos 时，您应该会在控制台上看到类似这样的日志:

```
2014/11/19  12:41:39  GET  /todos   TodoIndex        148.324us

```

## 这个路由文件太疯狂了…让我们重构一下

既然 routes 文件已经变大了一点，让我们把它分成以下几个文件:

### routes . go–redux

```
package main

import  "net/http"

type  Route  struct  {
    Name        string
    Method      string
    Pattern string
    HandlerFunc http.HandlerFunc
}

type Routes  []Route

var routes  =  Routes{
    Route{
        "Index",
        "GET",
        "/",
        Index,
    },
    Route{
        "TodoIndex",
        "GET",
        "/todos",
        TodoIndex,
    },
    Route{
        "TodoShow",
        "GET",
        "/todos/{todoId}",
        TodoShow,
    },
}

```

### Router.go

```
package main

import  (
    "net/http"

    "github.com/gorilla/mux"
)

func NewRouter()  *mux.Router  {
    router  :=  mux.NewRouter().StrictSlash(true)
    for  _,  route  :=  range  routes  {
        var handler http.Handler
        handler  =  route.HandlerFunc
        handler  =  Logger(handler,  route.Name)

        router.
            Methods(route.Method).
            Path(route.Pattern).
            Name(route.Name).
            Handler(handler)

    }
    return router
}

```

## 承担一些责任

现在我们有了一些很好的样板文件，是时候重新审视我们的处理程序了。我们需要更负责任一点。我们将首先通过添加两行代码来修改 todo index:

```
func TodoIndex(w  http.ResponseWriter,  r  *http.Request)  {
    todos  :=  Todos{
        Todo{Name:  "Write presentation"},
        Todo{Name:  "Host meetup"},
    }

    w.Header().Set("Content-Type",  "application/json; charset=UTF-8")
    w.WriteHeader(http.StatusOK)
    if err  :=  json.NewEncoder(w).Encode(todos);  err  !=  nil  {
        panic(err)
    }
}

```

现在有两件事正在发生。首先，我们发送回我们的内容类型，并告诉客户端期待 json。第二，我们显式地设置状态代码。

Go 的 net/http 服务器会试图为我们猜测输出内容的类型(然而它并不总是准确的)，但是因为我们确实知道类型，我们应该总是自己设置它。

## 等等，我的数据库在哪里？

显然，如果我们要创建一个 RESTful API，我们需要一个存储和检索数据的地方。然而，这超出了本文的范围，所以我们将简单地创建一个非常粗糙的(不是线程安全的)模拟数据库。

创建一个名为 repo.go 的文件，添加以下内容:

```
package main

import  "fmt"

var currentId int

var todos Todos

// Give us some seed data
func init()  {
    RepoCreateTodo(Todo{Name:  "Write presentation"})
    RepoCreateTodo(Todo{Name:  "Host meetup"})
}

func RepoFindTodo(id int)  Todo  {
    for  _,  t  :=  range  todos  {
        if  t.Id  ==  id  {
            return  t
        }
    }
    // return empty Todo if not found
    return  Todo{}
}

func RepoCreateTodo(t  Todo)  Todo  {
    currentId  +=  1
    t.Id  =  currentId
    todos  =  append(todos,  t)
    return  t
}

func RepoDestroyTodo(id int)  error  {
    for  i,  t  :=  range  todos  {
        if  t.Id  ==  id  {
            todos  =  append(todos[:i],  todos[i+1:]...)
            return nil
        }
    }
    return fmt.Errorf("Could not find Todo with id of %d to delete",  id)
}

```

### 将 ID 添加到待办事项

现在我们有了一个“模拟”数据库，我们正在使用和分配 id，所以我们必须相应地更新我们的 Todo 结构。

```
package main

import  "time"

type  Todo  struct  {
    Id        int `json:"id"`
    Name      string    `json:"name"`
    Completed bool      `json:"completed"`
    Due time.Time  `json:"due"`
}

type Todos  []Todo

```

### 更新我们的 TodoIndex

为了使用这个数据库，我们现在需要通过修改下面的函数来检索 TodoIndex 中的数据:

```
func TodoIndex(w  http.ResponseWriter,  r  *http.Request)  {
    w.Header().Set("Content-Type",  "application/json; charset=UTF-8")
    w.WriteHeader(http.StatusOK)
    if err  :=  json.NewEncoder(w).Encode(todos);  err  !=  nil  {
        panic(err)
    }
}

```

### 发布 JSON

到目前为止，我们只输出了 JSON，现在是时候接收和存储一些 JSON 了。

将以下路线添加到 routes.go 文件中:

```
Route{
    "TodoCreate",
    "POST",
    "/todos",
    TodoCreate,
},

```

### 创建端点

现在我们必须将创建端点添加到处理程序文件中。

```
func TodoCreate(w  http.ResponseWriter,  r  *http.Request)  {
    var todo Todo
    body,  err  :=  ioutil.ReadAll(io.LimitReader(r.Body,  1048576))
    if err  !=  nil  {
        panic(err)
    }
    if err  :=  r.Body.Close();  err  !=  nil  {
        panic(err)
    }
    if err  :=  json.Unmarshal(body,  &amp;todo);  err  !=  nil  {
        w.Header().Set("Content-Type",  "application/json; charset=UTF-8")
        w.WriteHeader(422)  // unprocessable entity
        if err  :=  json.NewEncoder(w).Encode(err);  err  !=  nil  {
            panic(err)
        }
    }

    t  :=  RepoCreateTodo(todo)
    w.Header().Set("Content-Type",  "application/json; charset=UTF-8")
    w.WriteHeader(http.StatusCreated)
    if err  :=  json.NewEncoder(w).Encode(t);  err  !=  nil  {
        panic(err)
    }
}

```

我们做的第一件事是打开请求的主体。请注意，我们使用 io.LimitReader。这是一个很好的方法来保护您的服务器免受恶意攻击。想象一下，如果有人想给你发送 500GBs 的 json！

在我们读取了主体之后，我们将它解组到我们的 Todo 结构。如果失败，我们将做正确的事情，不仅用适当的状态代码 422 来响应，而且我们还将在 json 字符串中发回错误。这将允许客户不仅了解出了问题，而且我们有能力交流具体出了什么问题。

最后，如果一切顺利，我们发送回状态代码 201，这意味着实体被成功创建。我们还发送回我们创建的实体的 json 表示，因为它包含一个 id，客户端可能需要它来进行下一步。

### 贴一些 JSON

既然我们已经有了假回购和“创建”端点，现在是时候发布一些数据了。我使用 curl 通过下面的命令做到这一点:

```
curl  -H  "Content-Type: application/json"  -d  '{"name":"New Todo"}'  http://localhost:8080/todos
Now,  if you go to http://localhost/todos we should see the following response:
[
    {
        "id":  1,
        "name":  "Write presentation",
        "completed":  false,
        "due":  "0001-01-01T00:00:00Z"
    },
    {
        "id":  2,
        "name":  "Host meetup",
        "completed":  false,
        "due":  "0001-01-01T00:00:00Z"
    },
    {
        "id":  3,
        "name":  "New Todo",
        "completed":  false,
        "due":  "0001-01-01T00:00:00Z"
    }
]

```

## 我们没有做的事情

虽然我们有了一个良好的开端，但仍有许多工作要做。我们尚未解决的问题有:

*   版本控制——如果我们需要修改 API 并导致重大变更，该怎么办？我们可以在所有路由中添加/v1/前缀吗？
*   认证——除非这是一个免费/公共 API，否则我们可能需要一些认证。我建议学习一下 [JSON web 令牌](http://jwt.io/)

eTags——如果你正在构建需要扩展的东西，你可能需要实现 [eTags](https://en.wikipedia.org/wiki/HTTP_ETag)

## 还剩下什么？

与所有项目一样，事情开始时都很小，但很快就会失控。如果我要将此提升到下一个级别，并使其为生产做好准备，这些只是要做的一些额外的事情:

*   大量的重构！
*   为其中的几个文件创建包，比如一些 JSON 助手、装饰器、处理程序等等。
*   测试…哦，是的，你不能忘记这一点。我们在这里没有做任何测试。对于一个生产系统来说，这是必须的。

## 我能拿到密码吗？

是啊！以下是这篇文章中使用的所有代码示例的报告:

[https://github.com/corylanou/tns-restful-json-api](https://github.com/corylanou/tns-restful-json-api)

## 摘要

对我来说最重要的事情是记住构建一个负责任的 API。发回正确的状态代码、内容头等对于 API 被广泛采用至关重要。我希望这篇文章能让你尽快开始使用自己的 API！

[C](https://twitter.com/corylanou) 他目前是 gSchool 的首席教练，在那里他教授围棋，并领导当地的丹佛围棋聚会，被恰当地称为丹佛地鼠。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>