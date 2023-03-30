# 分布式跟踪、Istio 及其应用

> 原文：<https://thenewstack.io/distributed-tracing-istio-and-your-applications/>

[](https://aspenmesh.io/)

 [尼拉杰·波德达尔，阿斯彭网格平台主管

尼拉杰·波德达尔是阿斯彭网格平台主管。在他的职业生涯中，他研究过操作系统、网络和分布式系统的各个方面。他热衷于开发高效和高性能的分布式应用程序。他喜欢打壁球，并通过尝试新餐馆来收回打球消耗的卡路里。](https://aspenmesh.io/) [](https://aspenmesh.io/)

在微服务领域，分布式跟踪正慢慢成为调试和理解应用程序依赖性的最重要工具。

在我最近在聚会和会议上的交谈中，我发现人们对分布式跟踪如何工作很感兴趣，但同时对跟踪如何与 Istio 和 [Aspen Mesh](https://aspenmesh.io/) 之类的服务网格交互也很困惑。特别是，我经常被问到以下问题:

*   如何使用 Istio 进行跟踪？在跨度中收集和报告哪些信息？
*   我必须改变我的应用程序才能从 Istio 的分布式跟踪中获益吗？
*   如果我当前在应用程序中报告跨度，它将如何与从 Istio 报告的跨度交互？

在这篇博文中，我将尝试回答这些问题。

在我们深入这些问题之前，先快速了解一下我为什么或如何结束写追踪相关博客的背景。如果你关注 [Aspen Mesh](https://aspenmesh.io/blog/) 博客，你会注意到我写了两篇与跟踪相关的博客，[一篇是关于使用 Istio 时跟踪对 AWS 服务的请求](https://aspenmesh.io/distributed-tracing-with-istio-in-aws/)，第二篇是关于使用 Istio 跟踪 gRPC 应用程序的[。](https://aspenmesh.io/tracing-grpc-with-istio/)

我们在 Aspen Mesh 有一个非常小的工程团队，正如大多数初创公司一样，如果你经常从事子系统或组件的工作，你很快就会成为(或被贴上标签或被指派)常驻专家。我在我们的微服务中添加了跟踪功能，并将其与 AWS 环境中的 Istio 集成在一起，在这个过程中，我发现了各种有趣的交互，我认为这些交互可能值得分享。在过去的几个月里，我们一直在大量使用跟踪来了解我们的微服务，现在它已经成为我们在出现问题时首先关注的地方。现在让我们继续回答我上面提到的问题。

## 如何使用 Istio 进行跟踪？

Istio 在运行应用程序容器的 pod 中注入一个 sidecar 代理(Envoy)。这个 sidecar 代理透明地拦截(iptables magic)所有进出应用程序的网络流量。由于这种拦截，sidecar 代理处于一个独特的位置，可以自动跟踪所有网络请求(HTTP/1.1、HTTP/2.0 & gRPC)。

让我们看看 sidecar 代理对来自客户端(外部或其他微服务)的 pod 传入请求进行了哪些更改。从这一点开始，为了简单起见，我将假设跟踪头采用的是 [Zipkin 格式](https://github.com/openzipkin/b3-propagation)。

*   如果传入的请求没有任何跟踪头，sidecar 代理将在将请求传递到同一个 pod 中的应用程序容器之前创建一个根 span(其中跟踪、父和 span IDs 都相同的 span)。
*   如果传入的请求具有跟踪信息(如果您使用 Istio ingress 或者您的微服务被另一个注入了 sidecar 代理的微服务调用，就应该是这种情况)，sidecar 代理将从这些头中提取 span 上下文，创建一个新的兄弟 span(与传入的头具有相同的跟踪、span 和父 ID)，然后将请求传递到同一 pod 中的应用程序容器。

相反，当应用程序容器发出出站请求(外部服务或集群中的服务)时，pod 中的 sidecar 代理会在向上游服务发出请求之前执行以下操作:

*   如果没有跟踪头，sidecar 代理创建根 span，并将 span 上下文作为跟踪头注入新请求。
*   如果跟踪报头存在，sidecar 代理从报头中提取 span 上下文，从该上下文中创建**子 span** 。新的上下文作为请求中的跟踪头传播到上游服务。

根据上述解释，您应该注意到，对于您的微服务链中的每一跳，您将从 Istio 获得两个跨度报告，一个来自客户端侧柜(span.kind 设置为 client ),一个来自服务器侧柜(span.kind 设置为 server)。sidecars 创建的所有跨度都由 sidecars 自动报告给配置的跟踪后端系统，如 Jaeger 或 Zipkin。

接下来，让我们看看跨度中报告的信息。跨度包含以下信息:

*   **x-request-id** :报告为 guid:x-request-id，这在将访问日志与范围相关联时非常有用。
*   **上游集群**:请求所针对的上游服务。如果 span 正在跟踪对 pod 的传入请求，这通常设置为`in.<name>`。如果 span 正在跟踪出站请求，则设置为`out.<name>`。
*   **HTTP 头**:以下 HTTP 头可用时报告:
    *   +网址
    *   +方法
    *   +用户代理
    *   +协议
    *   +请求大小
    *   +响应大小
    *   +响应标志
*   **每个跨度的开始和结束时间**。
*   **跟踪元数据**:包括跟踪 ID、span ID 和 span 种类(客户端或服务器)。除此之外,*操作名称*也被报告给每个跨度。操作名被设置为影响路由的已配置虚拟服务(或 v1alpha1 中的路由规则),如果选择了默认路由，则为“默认路由”。这对于了解哪种 Istio 路由配置对 span 有效非常有用。

说到这里，让我们进入第二个问题。

### 我是否必须更改我的应用程序才能从 Istio 中的跟踪中获益？

是的，您需要在您的应用程序中添加逻辑，将跟踪头从传入请求传播到传出请求，以充分利用 Istio 的分布式跟踪。

如果应用程序容器在传入请求的上下文中发出新的出站请求，并且不传播传入请求的跟踪头，那么 sidecar 代理将为出站请求创建一个根 span。这意味着您将始终看到只有两个微服务的痕迹。另一方面，如果应用程序容器确实将跟踪头从传入请求传播到传出请求，那么 sidecar 代理将如上所述创建子跨度。子跨度的创建使您能够了解跨多个微服务的依赖性。

在应用程序中传播跟踪头有几个选项。

2.  寻找 [Istio 文档](https://istio.io/docs/tasks/telemetry/distributed-tracing/#understanding-what-happened)中提到的跟踪头，并将头从传入请求传输到传出请求。这种方法很简单，几乎在所有情况下都有效。然而，它有一个主要的缺点，那就是您不能像用户信息那样向 spans 添加定制标签。您不能创建与应用程序中您可能要报告的事件相关的子范围。由于您只是简单地传输标题，而不了解 span 格式或上下文，因此添加特定于应用程序的信息的能力有限。
3.  第二种方法是在应用程序中设置一个跟踪客户端，并使用 Opentracing APIs 将跟踪头从传入请求传播到传出请求。我已经创建了一个[样例 tracing-go](https://github.com/aspenmesh/tracing-go) 包，它提供了一个简单的方法[在你的应用程序中设置 jaeger-client-go](https://github.com/jaegertracing/jaeger-client-go) ，它与 Istio 兼容。下面的代码片段应该包含在应用程序的 main 函数中:

```
import  (
"log"
"github.com/spf13/cobra"
"github.com/spf13/viper"
"github.com/aspenmesh/tracing-go"
)

func setupTracing()  {
// Configure Tracing
tOpts  :=  &amp;tracing.Options{
ZipkinURL:      viper.GetString("trace_zipkin_url"),
JaegerURL:      viper.GetString("trace_jaeger_url"),
LogTraceSpans:  viper.GetBool("trace_log_spans"),
}

if err  :=  tOpts.Validate();  err  !=  nil  {
log.Fatal("Invalid options for tracing: ",  err)
}

var tracer io.Closer
if tOpts.TracingEnabled()  {
tracer,  err  =  tracing.Configure("myapp",  tOpts)
if err  !=  nil  {
tracer.Close()
log.Fatal("Failed to configure tracing: ",  err)
}  else  {
defer tracer.Close()
}
}
}

```

需要注意的关键点是，在 [tracing-go](https://github.com/aspenmesh/tracing-go/blob/master/config.go#L124) 包中，我已经将 Opentracing 全局跟踪器设置为 Jaeger 跟踪器。这使我能够使用 Opentracing APIs 将消息头从传入请求传播到传出请求，如下所示:

```
import  (
"net/http"
"golang.org/x/net/context"
"golang.org/x/net/context/ctxhttp"
"ot "github.com/opentracing/opentracing-go"
)

func injectTracingHeaders(incomingReq *http.Request, addr string) {
if span := ot.SpanFromContext(incomingReq.Context()); span != nil {
outgoingReq, _ := http.NewRequest("GET",  addr,  nil)
ot.GlobalTracer().Inject(
span.Context(),
ot.HTTPHeaders,
ot.HTTPHeadersCarrier(outgoingReq.Header))
resp,  err  :=  ctxhttp.Do(ctx,  nil,  outgoingReq)
// Do something with resp
}
}

```

您还可以使用 Opentracing APIs 来设置 span 标签，或者从 Istio 添加的跟踪上下文中创建子 span，如下所示:

```
func SetSpanTag(incomingReq *http.Request,  key string,  value  interface{})  {
if span  :=  ot.SpanFromContext(incomingReq.Context());  span  !=  nil  {
span.SetTag(key,  value)
}
}

```

除了这些好处，你不必直接处理跟踪头，而是由跟踪器(在这里是 Jaeger)来处理。我强烈建议使用这种方法，因为它为在应用程序中添加增强的跟踪功能奠定了基础，而不会产生太多开销。

现在进入第三个问题。

### Istio 报告的跨度如何与应用程序创建的跨度交互？

如果您希望应用程序报告的跨度是 Istio 添加的跟踪上下文的子跨度，那么您应该使用 OpenTracing API

[StartSpanFromContext](https://godoc.org/github.com/opentracing/opentracing-go#StartSpanFromContext) 而不是使用 [StartSpan](https://godoc.org/github.com/opentracing/opentracing%20go#StartSpan) 。如果存在，则`StartSpanFromContext`从父上下文创建一个子跨度，否则创建一个根跨度。

请注意，在上面的所有示例中，我都使用了 OpenTracing Go APIs，但是您应该能够使用任何用与您的应用程序相同的语言编写的跟踪客户端库，只要它与 OpenTracing API 兼容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>