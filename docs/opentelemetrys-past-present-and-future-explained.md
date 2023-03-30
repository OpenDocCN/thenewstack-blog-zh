# OpenTelemetry 的过去、现在和未来

> 原文：<https://thenewstack.io/opentelemetrys-past-present-and-future-explained/>

[Epsagon](https://epsagon.com/) 赞助本帖。

 [冉·里本扎夫特

不断追逐新技术(比如无服务器)作为 AWS 无服务器英雄，冉热爱分享开源工具，让大家的生活更轻松。在目前的职位上，他是 Epsagon 的联合创始人兼首席技术官，该公司为无服务器应用程序提供监控。](https://epsagon.com/) 

直到几个月前，在过去的两年里，分布式追踪库的世界里有两个主要的玩家: [OpenTracing](https://opentracing.io/) 和 [OpenCensus](https://opencensus.io/) 。而在两者之间做出选择往往并不容易。毕竟，两者都旨在解决同一个基本问题，即拥有一个用于分布式跟踪的供应商中立的 API(尽管方式略有不同)，这导致了两个相互竞争的标准。

今年早些时候，两个项目团队决定联手，合并为 [OpenTelemetry](https://opentelemetry.io/) :云本地计算基金会(CNCF) 旗下的一个全新项目。

虽然 OpenTelemetry 仍在开发中，但在这篇文章中，您将通过它所起源的两个项目了解 OpenTelemetry 的过去、现在和未来，包括一些比较这三者的代码示例。

## 过去

### OpenTracing

OpenTracing 是这两个项目中最老的，在 2016 年 12 月发布 1.0 之后。像 OpenTelemetry 一样，它也是 CNCF 的一个项目。顾名思义，主要的焦点是分布式跟踪，这就是它要做的一切。库有九种语言版本，但是 OpenTracing 真正的亮点在于它的简单性。

这些库本身有一个小的 API 表面，并定义了一个接口，跟踪器必须实现这个接口。如果想要支持 OpenTracing，像 Jaeger 这样的追踪器必须实现他们的客户机库。许多追踪器是官方支持的，还有一些是社区支持的。只需要三种方法来满足 OpenTracing 的 Tracer 接口，这使得添加新方法变得非常容易。

### 公开普查

OpenCensus 最初始于谷歌，于 2018 年 1 月首次发布。它诞生于 Google 的内部人口普查库，因此，OpenCensus 也支持追踪信息和指标的捕获。如今，它拥有一个充满活力的合作伙伴生态系统，其中包括其他云提供商，如微软和分布式跟踪和度量领域的许多供应商。像 OpenTracing 一样，OpenCensus 也支持九种语言，两者共有八种语言。

OpenCensus 旨在保持供应商中立，因此供应商可以为他们的跟踪和度量后端实现导出器。然而，OpenCensus 也总是向一些出口商提供它的一些库。在一些语言中，这些已经被转移到它们自己的单独的库中，这样它们就可以与核心项目分开维护。然而，在其他地方，它们仍然是图书馆的一部分。实际上，对于希望使用 OpenCensus 的应用程序开发人员来说，差别不大:软件通常必须导入并初始化它希望使用的导出程序。对于您控制下的软件(即内部开发的软件)，这不太可能是一个问题，因为您将选择您的组织正在使用的软件。

然而，在云环境中，您可能正在运行一个或多个开源微服务，您希望在这些微服务之间传播跟踪信息。例如，当你使用 [Zipkin](https://zipkin.io/) 时，它们可能会将 g 输出到 Jaeger。OpenTracing 也有同样的问题，具体的 tracers 必须导入并初始化。但是，与 OpenTracing 不同，OpenCensus 提出了一个解决方案。

### 公开普查服务

OpenCensus 服务是一个独立进程的集合，这些进程接收数据，要么是自己的 OpenCensus 格式，要么是 Zipkin、Jaeger 或 [Prometheus](https://prometheus.io/) 格式。至于输出，该服务支持许多格式/供应商，包括 OpenCensus 已经支持的格式/供应商。可以将 OpenCensus 服务部署为在应用程序附近运行的收集器，并将数据发送到一个或多个监控后端。

另一种选择是在同一个主机(或 sidecar 容器)上作为代理运行它，它导出到 OpenCensus 收集器，甚至直接导出到监控服务。这种方法有几个优点:

*   导出器的配置不在应用程序本身中。例如，您可以通过更改 OpenCensus 服务流程的配置来更改导出器后端或添加一个额外的后端，而无需重新部署您的代码。
*   你可以在不同格式之间转换，例如，从 Zipkin 到 Jaeger，或者从 Prometheus 到 Stackdriver，所有这些都不需要修改任何代码。这对于处理外部构建软件的操作员特别有用。
*   没有必要在您的代码中包含导出器并使它们保持最新。
*   OpenCensus 的维护者和贡献者不需要用所有的库语言实现导出器，只需要用 Go(选择用来实现 OpenCensus 服务的语言)就可以了。

这两个项目都很好地满足了追踪需求，但 OpenCensus 有一个稍微更雄心勃勃的目标和一个“包含电池”的方法。

## 开放式遥测:两全其美

OpenTelemetry 真正从两个项目中吸取了最好的想法。在发布时，它将支持分布式追踪和度量，就像 OpenCensus 一样。对日志的支持将在初始版本发布后推出。

OpenCensus 服务——可以说是最好的功能——已经被合并到这个新项目中，成为 OpenTelemetry Collector。虽然它仍然支持同时作为代理和收集器运行，但对于这两种用例，它现在是完全相同的二进制文件(和 Docker 映像)。

但是如果你已经在使用 OpenTracing 或者 OpenCensus 了呢？没什么可担心的——当 OpenTelemetry 发布时，它将向后兼容这两个项目，所以随着项目的发展和成熟，您将有足够的时间来采用新的 API。

对于整个 CNCF 生态系统来说，OpenTelemetry 也是一个好消息，因为它现在支持度量。这意味着普罗米修斯——另一个 CNCF 项目——将从一开始就作为度量标准的输出者得到支持。说到 Jaeger，不仅支持可用，而且 Jaeger 目前还开发、维护和分发自己的代理和收集器实现。Jaeger 还计划与 OpenTelemetry 合作，看看是否有可能逐步淘汰 Jaeger 的代理和收集器，正如关于 [Jaeger 和 OpenTelemetry](https://medium.com/jaegertracing/jaeger-and-opentelemetry-1846f701d9f2) 的帖子中所详述的那样。

## 现状和路线图

所有 OpenTelemetry 子项目(规范、库和收集器)仍在 alpha 阶段开发中。许多库暂时还没有版本。

2019 年语言 SDK 的高质量预览版可以期待，包括对 OpenTelemetry Collector 的支持。在 2020 年第二季度，该计划将终止 OpenTracing 和 OpenCensus 项目。

需要注意的是，没有一个 OpenTelemetry 项目可以投入生产使用。OpenTelemetry 协议仍在变化，SDK 的 API 也是如此。OpenTelemetry Collector 文档目前规定，在稳定版本发布之前，应该使用 OpenCensus 服务。

## 代码比较

为了更好地理解每个项目在实现时的实际差异，让我们深入一个真实的例子。让我们使用 OpenTracing、OpenCensus 和 andOpenTelemetry 的 JavaScript SDKs 创建一个带有注释的 span。所有的例子都使用 Jaeger 作为后端。

### OpenTracing

```
const jaeger  =  require('jaeger-client');

const tracer  =  jaeger.initTracer({  /* Jaeger options */  });

const span  =  tracer.startSpan('my_span');
span.setTag({  'key':  'value'  });
// Code to instrument goes here...
span.finish();

```

使用 OpenTracing 要注意的第一件事是，你甚至不需要导入任何特定于 OpenTracing 的库，因为客户端库直接实现了公共的 OpenTracing API。然而，OpenTracing 库提供了附加功能，比如模拟跟踪器和众所周知的标记键的常量。

### 公开普查

```
const tracing  =  require('@opencensus/nodejs');
const  {  JaegerTraceExporter  }  =  require('@opencensus/exporter-jaeger');

const tracer  =  tracing.start({  samplingRate:  1  }).tracer;

tracer.registerSpanEventListener(new  JaegerTraceExporter({
    /* Jaeger options */
}));

tracer.startRootSpan({  name:  'my_span'  },  rootSpan  =&gt;  {
    rootSpan.addAttribute('key',  'value')
    // Code to instrument goes here...
    rootSpan.end();
});

```

与 OpenCensus 的主要区别在于，它的图书馆是主要焦点，而 Jaeger 只是一个需要注册的出口商。抛开 API 差异不谈，OpenCensus 和 OpenTracing 在设置、span 创建和 span 属性/标签方面都是相似的。

### 开放式遥测

```
const opentelemetry  =  require('@opentelemetry/core');
const  {  BasicTracer,  SimpleSpanProcessor  }  =  require('@opentelemetry/tracing');
const  {  JaegerExporter  }  =  require('@opentelemetry/exporter-jaeger');

const tracer  =  new BasicTracer();

tracer.addSpanProcessor(new  SimpleSpanProcessor(new  JaegerExporter({
    /* Jaeger options */
})));

opentelemetry.initGlobalTracer(tracer);

const span  =  opentelemetry.getTracer().startSpan('my_span');
span.setAttribute('key',  'value');
// Code to instrument goes here...
span.end();

```

OpenTelemetry 在设置方面可能有点冗长，但这是由于它的模块化设计。类似于 OpenCensus，它的库是核心。然而，除了可以选择导出器之外，还有不同的量程处理器，如批量量程处理器和控制台处理器，它可以将量程打印到控制台，用于诊断目的。这种更加模块化的设计为进一步定制提供了可能性。

请注意，此示例使用的是 OpenTelemetry 的 alpha 版本，该版本可能会更改。

## 摘要

OpenTracing 和 OpenCensus 都有庞大、健康的社区支持它们——因此看到它们联手令人印象深刻。这次合并，大家都赢了:

*   开发人员不再需要在两个相互竞争的标准之间做出选择，可以专注于编写真正便携的遥测代码。
*   得益于 OpenTelemetry Collector，操作人员有了一种标准化的方法来配置、收集、解释和导出跟踪数据。
*   应用程序性能监控解决方案的供应商只需要支持和测试单一标准，而不需要自己实现代理或收集器。

如果你今天开始一个新项目，你可能应该坚持使用 OpenTracing 或 OpenCensus，尤其是在稳定性至关重要的情况下。由于兼容性垫片，当 OpenTelemetry 的稳定版本最终发布时，您将无需担心立即升级到新的 API，并将能够利用 OpenTelemetry 中的新功能和改进。

*[AWS 高级技术合作伙伴爱普生](https://epsagon.com/)，为云微服务——容器和无服务器——提供自动化监控和跟踪。[立即开始免费试用](https://epsagon.com/)，了解 Epsagon 如何帮助您节省高达 95%的故障排除时间，并减少 75%的错误。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>