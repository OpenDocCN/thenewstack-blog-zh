# 芭蕾舞演员:API 优先的编程语言

> 原文：<https://thenewstack.io/ballerina-an-api-first-programming-language/>

开源企业应用集成软件提供商 [WSO2](https://wso2.com/) 发布了一种编程语言，该语言围绕支持应用编程接口(API)作为一级实体而构建。上个月在哥本哈根举行的 KubeCon + CloudNativeCon 欧盟会议上，该公司首次推出了这种被称为[芭蕾舞演员](https://ballerina.io/)的语言。

WSO2 首席执行官[泰勒·朱厄尔](https://www.linkedin.com/in/tylerjewell/)说:“芭蕾舞演员是我们解决市场上集成问题的方法。”他指出，网络编程语言是大规模集成工作的理想选择，在这种情况下，“你希望编写一个服务，可以灵活地与其他服务对话，”他说。

今天使用的大多数编程都是在将微服务容器化并在云中运行的想法出现之前创建的。因此，许多语言都增加了将程序连接到外部 API 的支持。在很多情况下，开发人员不得不从头开始编写驱动程序或插件。或者他们必须努力理解微妙的编程结构，比如 JavaScript/Node.js 中的回调。

Ballerina 是一种编译的、类型安全的并发编程语言。代码被编译成字节码，然后在虚拟机中运行，尽管最终，运行时将转移到能够生成本机代码的 [LLVM 编译器](https://llvm.org/)。人工制品被包装到容器中。

芭蕾舞演员是作为 WSo2 内部的一个项目诞生的，WSo2 是一家做了大量企业集成工作的公司。WSO2 工程师和云原生领域的许多其他人一样，对大多数企业服务总线(enterprise service buses，ESB)需要 XML 作为配置消息流的标准格式感到越来越沮丧，对 XML 的支持打破了开发人员的常规。开发人员寻求一种更简单的方法来构建驱动程序并封装逻辑以处理入站流量。

芭蕾舞演员的语言语义学模拟了独立当事人如何通过结构化的互动进行交流。事实上，芭蕾舞程序可以显示为序列图，这是一种常见的可视化并发程序的方式。开发人员甚至可以通过序列图，用芭蕾舞演员作曲家创作芭蕾舞演员。

![](img/aaede71ff9d17b1c0f70995aaaf0235b.png)

WSo2 首席执行官泰勒·朱厄尔(左)和 WSo2 联合创始人保罗·弗里曼特尔在 KubeCon + CloudNativeCon EU。

朱厄尔说，这种语言“融合了当今编程方法的所有最佳实践”。例如，他指出 Golang 的依赖管理模型会带来传递依赖问题，即两个应用程序可以导入相同的库，但行为不同。相比之下，Ballerina 可以为人们提供“一个非常干净的项目结构，一个非常干净的代码结构，人们永远不会有任何过渡版本问题。”与 Node.js 不同，Ballerina 提供了类型安全。

仍然围绕着“主”代码块的思想，大多数语言没有一个好的并发模型，而这对于与外界交互的软件(如 web 服务器软件)来说是绝对必要的。一些较新的语言，比如 Go，有内置的并发模型，尽管它们在理解语义方面仍然需要大量的工作。

在 Ballerina 中，HTTP 客户端是一级构造，包含在标准库中。在幕后，Ballerina 部署了一个并发异步非阻塞模型，该模型广泛用于并行编程的[管理器/工作器模型](http://etutorials.org/Linux+systems/cluster+computing+with+linux/Part+II+Parallel+Programming/Chapter+8+Parallel+Programming+with+MPI/8.2+Manager+Worker+Example/)，在该模型中，不同的工作器被分配出站工作，而其他工作器处理入站操作，消除了任何线程阻塞或性能滞后。VM 有一个定制的调度程序，它根据操作系统提供的可用线程池来管理工作线程池。

朱厄尔说，测试表明，这种方法可以在基本硬件上每秒提供 20，000-25，000 次交易，比 Spring Boot 高出约 20%，比同等的 Python 快 50 倍。

Ballerina 不是面向对象的语言，也不是函数式语言，尽管它支持对象和 lambdas。如果说网络编程的历史通过 CORBA 和 JavaBeans 教会了我们什么的话，那就是通过网络传递的大多数东西都不是对象。

Ballerina 在 Apache 许可下是开源的，商标由公司保留。

## 少说多做

下面是一个简单芭蕾舞程序的代码，**<hello-service/hello _ service . bal>**，
响应 API 调用:

```
// Packages contain functions, annotations and connectors.
// This package is referenced by ‘http’ namespace in the code
// body.
import ballerina/http;
import ballerina/io;

// A service is a network-accessible API. This service
// is accessible at '/hello', and bound to a the listener on
// port 9090\. `http:Service`is a connector in the `http`
// package.
service&lt;http:Service&gt;  hello  bind  {  port:  9090  }  {

// A resource is an invokable API method.
// Accessible at '/hello/sayHello’.
// 'caller' is the client invoking this resource.
 sayHello  (endpoint caller,  http:Request request)  {

 // Create object to carry data back to caller.
 http:Response response  =  new;

 // Objects have function calls.
 response.setTextPayload("Hello Ballerina!\n");

 // Send a response back to caller.
 // Errors are ignored with '_'.
 // ‘-&gt;’ is a synchronous network-bound call.
 _  =  caller  -&gt;  respond(response);
 }
 }

```

有关现场代码示例，请查看[芭蕾舞演员网站](https://ballerina.io/)。

[![](img/fc9bbc85b879d731afe7c4f6192c1251.png)](https://us18.wso2con.com)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>