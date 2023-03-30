# 5 种 Go Web 框架综述

> 原文：<https://thenewstack.io/a-survey-of-5-go-web-frameworks/>

在 Go 中构建套接字服务器几年后，我突然需要为 Javascript 和 Objective-C 客户端构建一些基于 HTTP 的 REST APIs。有了 Rails 的背景，我对通用 MVC 框架有很高的期望。然而，像 Ruby 中的 Sinatra 这样的框架为简单的 REST 端点取得了简单性的良好平衡。为此，我选择继续使用 Go，因为它的性能和静态类型，我认为它将在那些不需要在传统 web 应用程序风格开发中使用大量模板和表单的项目中赢得长期优势。

## 比格

Beego 看起来是一个全功能的 MVC 框架，可能与 Rails 处于同一水平。它没有试图变小。它有自己的日志库、ORM 和 Web 框架。

### 社区:

Beego 社区相当大。然而，似乎大多数使用它的公司都是中国人，所以这个社区肯定有语言障碍。它可能会扩展到大量的流量，因为大型的中国网站都使用这个框架。

### 最佳特性:

由于这是一个成熟的 MVC 框架，你不必在网上搜寻大量的库。许多问题马上就被抛到了九霄云外，比如使用什么日志框架以及如何构建应用程序。这些都是在新项目开始时节省大量时间的特性。

## 马提尼酒

受 Sinatra 启发的 Martini 给人一种非常轻便的框架感。它处理一些基本的事情，比如路由、异常处理和做中间件的通用方法。最初在 Go 社区中有一些反弹，因为它有许多反射技术来从路由中清理 API 结构。它可以做一些很酷的事情，比如根据类型将不同的数据集动态地注入到处理程序中(参见最佳特性的例子)。这个在 Ruby 框架中很常见的“魔术”在 Go 社区中引起了很大的关注。以至于作者正在开发一个更简单的框架，叫做尼格罗尼。然而，在我看来，它提供的价值没有马提尼多。

### 社区:

虽然是一个小社区，但它看起来仍然非常活跃，大约有 20 个左右的[活动插件](https://github.com/martini-contrib)，我还有一个用于集成到 GetSentry [source](https://github.com/hyperworks/raven-martini) 。鉴于框架的口头禅是要小，所以没有那么多需要添加的东西是有道理的。

### 最佳特性:

由于框架使用了反射，它可以根据你的需要动态地将数据插入到处理函数中。您甚至可以动态添加新的[服务](https://github.com/go-martini/martini#services)。

```
m.Get("/",  func(res http.ResponseWriter,  req *http.Request)  {  // res and req are injected by Martini
  res.WriteHeader(200)  // HTTP 200
})
m.Get("/",  func()  {
  // show something
})
m.Get("/",  func(c *Context,  r  render.Render)  {
  // show something
})

```

## 大猩猩

可能是最大和运行时间最长的 Gi web 框架， [Gorilla](http://www.gorillatoolkit.org/) 是一个模块化框架，可以为用户提供尽可能多或尽可能少的内容。例如，在一个项目中，我们只是取出 Sessions 包并将其重新用于 Auth。我认为 Gorilla 很好，因为许多组件都可以直接通过`net/http`库重用。

### 社区:

Gorilla 可能拥有所有框架中最大的英语社区。它显示了 GitHub 上可用的博客帖子和中间件的剪切量。

### 最佳特性:

我认为最近有很多关于在像 [Meteor.js](https://www.meteor.com/) 这样的框架中使用 web sockets 动态更新应用程序的宣传。Gorilla 有现成的 web sockets，因此您可以挂接与 web sockets 完全相同的代码来 REST 端点，而无需使用 Pusher 等第三方服务。

## GoCraft

我真的很想简单地谈一下这个框架。我认为 net/http 最大的问题之一是没有办法将上下文传递给你的处理程序链。所以您不能在您的中间件和处理程序之间轻松地共享数据或事务。这个框架的目标是超级最小化，并解决这个问题。让我给你看几个简单的例子

让我们举一个典型的例子，在这个例子中，某个中间件授权一个用户，然后将一个用户对象放入会话中。

```
router  :=  web.New(YourContext{})
router.Middleware((*YourContext).UserAuthRequired)
router.Put("/users/:id",  (*YourContext).UsersUpdate)

func  (c *YourContext)  UserAuthRequired(rw web.ResponseWriter,  r  *web.Request,  next web.NextMiddlewareFunc)  {
    //Auth the user and put the data into the context
    user  :=  userFromSession(r)  // Pretend like this is defined. It reads a session cookie and returns a *User or nil.
    if user  !=  nil  {
        c.User  =  user
        next(rw,  r)
    }  
}

func  (c *YourContext)  Root(rw web.ResponseWriter,  req *web.Request)  {
    if  c.User  !=  nil  {
        fmt.Fprint(rw,  "Hello,",  c.User.Name)
    }  else  {
        fmt.Fprint(rw,  "Hello, anonymous person")
    }
}

```

## Net/HTTP

如果你阅读 Go 邮件列表，你可能会被告知这是你唯一需要的框架。在某些方面，这是真的。我们只用 net/http 构建了一个完整的 XMPP 服务器，并且运行良好。然而，复杂的 web 应用程序往往需要中间件。有一些有趣的项目，比如 [interpose](https://github.com/carbocation/interpose) ，它允许你将其他 GO web 框架中的中间件与标准的 net/http 混合搭配。

### 社区

这个社区显然很大，因为用户可以重用许多其他项目的内容。然而，它有一个非常有限的接口，并且它没有真正定义任何扩展中间件的标准方式。路由在开箱即用时非常脆弱，所以通常使用框架。

## 结论

我们尝试了几个这样的框架来感受一下。我们在 REST API 中使用了 Martini。虽然我们很喜欢它，但我想在未来我会尝试使用 GoCraft，因为它更加轻量级，但解决了 Martini 面临的同样的上下文问题。也许我们会采用一些 Martini 中间件作为实验。最初我们尝试使用 Gorilla 作为我们的管理系统，我认为这是一个很大的错误。它真的缺乏 RAILS 的固执己见，以及许多用于制作真正基本的 cookie cutter web 应用程序的小功能。对于传统的基于表单的 CRUD 应用，我认为我们将来会更倾向于 Beego，因为它真的感觉像一个完整的 MVC 特性集。

Matthew 是一名黑客，他经常往返于纽约和曼谷。他为 Thomson Reuters 编写了大型 XMPP 服务器，将 Bloomberg.com 移植到 Ruby on Rails，甚至为古驰从事电子商务工作。在他的许多合同之间，他经营着一家名为 Langfight 的新公司。他经营曼谷 GO Lang Meetup，并发表了一篇关于外包有趣一面的博客，名为 DistributedAgile。博客上有一本关于外包的免费电子书。你可以在推特上关注他，地址是 [@kanwisher](https://twitter.com/kanwisher)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>