# OpenTelemetry for Go 入门

> 原文：<https://thenewstack.io/opentelemetry-in-go-its-all-about-context/>

[Lightstep](https://lightstep.com/) 赞助本帖。

 [泰德·杨

Ted 是 Lightstep 的开发者教育主管，也是 OpenTelemetry 的联合创始人。他是 OpenTelemetry 治理委员会的成员。](https://www.linkedin.com/in/ted-young/) 

随着 [OpenTelemetry](https://opentelemetry.io/) 的公开测试接近尾声，感觉是时候深入了解一些使 OpenTelemetry 成为如此有用工具的基本原理了。

在过去六年左右的时间里，Go 一直是我的主要编程语言，我仍然非常喜欢它。所以我们以围棋为例。正如您将看到的，它确实是一种解释 OpenTelemetry 基本特性的优秀语言:上下文传播。

我将从解释一些理论开始，但是如果你是一个代码至上的人，请随意跳到教程中，首先检查这一部分。

## 我们在解决什么问题？

OpenTelemetry 是一组可观察性工具——我们称之为信号——通过上下文传播粘合在一起。

这有什么新的不同？大多数传统的可观察性工具——比如日志和指标——提供了记录和统计单个事件的方法。但是它们没有提供一个很好的方法来将这些事件联系起来；至少，不是没有大量的工作。

我给你举个例子。我的团队正在开发一个分布式调度程序，设计起来很有趣，但调试起来就没那么有趣了——尤其是在生产中。问题是日志。我们非常关心我们的性能和正确性保证，所以我们有详细的日志覆盖——甚至在生产中。我们甚至测试了我们的日志(！)以确保我们报告的数据不会意外地与他们记录的事件脱离。不管怎样，你明白了——很多关于可观察性的关心正在进行。

在本地运行，日志是可管理的。但是真正有趣的问题只发生在大规模重载的情况下，而且通常很少，很难重现。这就是它们“有趣”的原因

![](img/48a596ba2794aba0ef940bacadb29110.png)

### **一堆针中的一针**

当您拥有数十亿字节的日志，并且只关心其中很小的、特定的子集时，这有点像在一堆针中寻找一根针。一种常见的模式是从错误消息开始，然后从中找到一些标识符(请求 id、用户 id 等。)用作过滤器。但是在一个分布式系统中，很少有一个单独的标识符出现在错误的位置，当它从一个服务跳到另一个服务时，这个标识符也会出现在事务的每个日志上。您可能有一个请求 ID，它将为您提供来自一个服务的日志。但是到下一个服务的跳跃呢？这将是一个不同的请求 ID。因此，您最终可以收集事务中的所有日志，但这是一个临时的迭代过程，有时会非常慢，特别是如果您仍然是问题的根源，并且希望在探索不同理论时调查大量不同的事务。如果你曾经以这种方式调试过一个分布式系统，你就会知道这是多么令人沮丧。

很明显，为事务中的每个日志钉上一个统一的 ID 会使过滤日志变得容易得多。但是，携带这个 ID 并在不同的服务之间传递它却是一件很麻烦的事情。

### **进入上下文传播**

为了传递这个事务 ID，您需要两个部分。第一部分允许 ID 跟踪程序中代码的执行。如果你是一个 Go 程序员，你应该知道那是什么:它是一个上下文对象！

```
`
ctx  =  context.WithValue(cxt,  "transactionID",  "4bf92f3577b34da6a3ce929d0e0e4736")

```

毕竟如果你要传一个 ID 在身边；为什么不传递一包价值观呢？除了事务 ID，您还可以传递其他有用的东西，比如截止日期，或者日志的附加索引——项目 ID、帐户 ID 等。

第二部分是通过将事务 ID 作为元数据添加到请求中，将事务 ID 从一个服务传播到下一个服务。

```
// On the client, inject the transaction ID into the request as a header.
req,  err  :=  http.NewRequest("GET",  "http://opentelemetry.io/test",  nil)
req.Header.Add("transaction-id",  cxt.Value("transactionID"))
// on the server, extract the transaction ID and put it in the context
http.HandleFunc("/test",  func(w  http.ResponseWriter,  req *http.Request)  {
  ctx  :=  req.Context()
  ctx  =  context.WithValue(cxt,  "transactionID",  req.Header.Get("transaction-id"))
  // ...
})

```

上面的代码是劳动密集型的方式。你必须知道你想要发送的每一个值，并把它硬连接到你发出的每一个请求中。不好玩。OpenTelemetry 让这变得容易多了。

## 行李

OpenTelemetry 中最基本的工具叫做*包袱*。就其本身而言，行李甚至不是一个可观察的工具；它只是允许您将上下文从一个服务传播到另一个服务。你可以把它想成 go 上下文，只是它流经你系统中的每一个服务。当我们谈到度量时，我们将讨论为什么这是有用的。

```
`
import  (
  "http"
  otelhttp  "go.opentelemetry.io/contrib/instrumentation/net/http"
  "go.opentelemetry.io/otel/api/baggage"
  "go.opentelemetry.io/otel/label"
)
// Wrap the HTTP transport with OpenTelemetry
client  :=  http.Client{
  Transport:  otelhttp.NewTransport(http.DefaultTransport)
}
// Add any the baggage values you would like to propagate to the context
ctx  :=  baggage.NewContext(context.Background(),
  label.String("projectID",  "1234"),
  label.String("accountID",  "abcd"),
)
// add the context to the request
req,  _  :=  http.NewRequestWithContext(ctx,  "GET",  *url,  nil)
// All the baggage values will automatically be injected and propagated.
res,  err  :=  client.Do(req)

```

open telemetry 的所有可观察性工具都建立在上下文传播的基本原则之上。

## 辅导的

### **安装 OpenTelemetry**

好了，让我们开始一些实际的观察。从顶部开始，让我们设置 OpenTelemetry，并讨论它的作用。OpenTelemetry 是一个有很多选项的大型框架。为了快速开始，我们编写了一个叫做 [otel-launcher 的方便的包装器。](https://github.com/lightstep/otel-launcher-go)

```
package main
import  "github.com/lightstep/otel-launcher-go/launcher"
func main()  {
  // note: you only need the access token for connecting to Lightstep
  otel  :=  launcher.ConfigureOpentelemetry(
      launcher.WithServiceName("service-123"),
      launcher.WithAccessToken("<ACCESS TOKEN>"),
  )
  defer otel.Shutdown()
  // install
}

```

### 为关键包添加检测库

OpenTelemetry 附带了用于各种库和框架的工具。通过向您的 HTTP 服务器或框架(入口)、HTTP 和其他客户端(出口)添加工具，并使上下文流过您的应用程序，您可以获得足够的细节来开始生产中的跟踪。(在某些语言中，这些工具库是自动安装的，但在 Go 中，它们必须手动安装。)

目前，可用的仪器可以在找到[。没有看到自己喜欢的框架或者库？考虑写一个插装插件，并作出贡献！](https://github.com/open-telemetry/opentelemetry-go-contrib/tree/master/instrumentation)

### **用资源描述你的服务**

上下文的第一个关键部分是服务本身。了解跨度来自哪里很重要。在 OpenTelemetry 中，*资源*用于描述你的服务。服务中发生的每一个事件都会自动地被这些属性联系起来。

```
host,  _  :=  os.Hostname()
attributes  :=  []kv.KeyValue{
  kv.String(conventions.AttributeServiceName,  "service123"),
  kv.String(conventions.AttributeServiceVersion,  "1.2.3"),
  kv.String(conventions.AttributeHostName,  host),
}

```

### **描述您的跟踪交易**

追踪是 OpenTelemetry 的核心。这是上下文传播真正开始发光的地方。您可以把它想象成一个大的堆栈跟踪，它包括您的事务中的每个事件。

每个事件都发生在一个跨度中，这个跨度代表一个操作。跨度依次连接在一起形成轨迹。跟踪提供了一个 TraceID 来索引事务中的每个事件。跨度具有属性，这些属性提供了更多的索引。此外，跨度会自动测量完成操作所需的时间长度。

```
package robochef
// create your tracer at the package level
var tracer  =  global.Tracer("robochef")
// Create a span to index, time, and contextualize your events
func BakeCake(ctx context.Context)  {
  // When a new span is started, it automatically becomes the child of
  // the current span, if one is present in the context. The new child span
  // replaces the parent span in the new child context.
  childCtx,  childSpan  :=  tracer.Start(ctx,  "bake-cake")
  defer childSpan.End()
// sub operations
  PreheatOven(childCtx)
  MixBatter(childCtx)
  HeatCake(childCtx)
}

```

所以，那是一个跨度。让我们来看看记录一些实际事件:

```
func PreheatOven(ctx context.Context)  error  {
  // Again, the new span becomes the child of the current span.
  ctx,  childSpan  :=  tracer.Start(ctx,  "preheat-oven")
  defer childSpan.End()

// example of adding an event
  span.AddEvent(ctx,  "start oven",  label.String("target-temp",  "350"))
  err  :=  startOven(350)
  if err  !=  nil  {

    // Errors are critical events
    span.RecordError(ctx,  err)
    return err
  }
  temp  :=  0
  for temp  >=  350  {
    temp  =  checkOvenTemp()
    time.Sleep(time.Minute)
  }
}

```

## **结论**

那都是乡亲们！希望你喜欢这个介绍。如果你想更深入地了解 OTel，请查看我正在编写的新的[深入入门指南](http://opentelemetry.lightstep.com)。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>