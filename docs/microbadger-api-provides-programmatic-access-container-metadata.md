# MicroBadger API 提供了对容器元数据的编程访问

> 原文：<https://thenewstack.io/microbadger-api-provides-programmatic-access-container-metadata/>

[](http://www.microscaling.com)

 [利兹·赖斯

利兹·赖斯是 Microscaling Systems 的首席执行官，也是 MicroBadger 的开发者之一。](http://www.microscaling.com) [](http://www.microscaling.com)

如果没有元数据，容器图像就像一个黑盒:除了名称和可能出现在标记中的一些有限的版本信息之外，你几乎没有什么可知道的。容器图像元数据(以标签键值对的形式)让您有机会在图像中构建更丰富的信息。布偶公司的加雷思·拉什格罗夫把这比作海运集装箱的货单。

我们新发布的 [MicroBadger API](https://medium.com/microscaling-systems/experimental-microbadger-metadata-api-for-docker-hub-images-3114a374353b#.rdexvk539) 允许您以编程方式查询关于容器图像的元数据。我是[微缩系统](http://microscaling.com/)的首席执行官，也是 API 的创造者之一。在本文中，我将讨论为什么您可能想要开始考虑元数据——以及为什么这只是更强大的部署管理的第一步。

## 查询元数据

当您的本地机器上有图像时，您可以使用 docker inspect 查询它们的元数据(包括任何标签)(这里，为了简洁起见，我只显示标签):

```
<span style="font-weight: 400;">$  docker inspect  -f  "{{json .Config.Labels }}"  microscaling/microscaling  |  jq</span>
<span style="font-weight: 400;">{</span>
<span style="font-weight: 400;">   "com.microscaling.docker.dockerfile":  "/Dockerfile",</span>
<span style="font-weight: 400;">   "com.microscaling.license":  "Apache-2.0",</span>
<span style="font-weight: 400;">   "org.label-schema.build-date":  "2017-01-03T13:16:08Z",</span>
<span style="font-weight: 400;">   "org.label-schema.description":  "Our Microscaling Engine provides automation, resilience and efficiency for microservice architectures. Experiment with microscaling at app.microscaling.com.",</span>
<span style="font-weight: 400;">   "org.label-schema.name":  "Microscaling Engine",</span>
<span style="font-weight: 400;">   "org.label-schema.schema-version":  "1.0",</span>
<span style="font-weight: 400;">   "org.label-schema.url":  "https://microscaling.com",</span>
<span style="font-weight: 400;">   "org.label-schema.vcs-ref":  "a8bce60",</span>
<span style="font-weight: 400;">   "org.label-schema.vcs-url":  "https://github.com/microscaling/microscaling.git",</span>
<span style="font-weight: 400;">   "org.label-schema.vendor":  "Microscaling Systems",</span>
<span style="font-weight: 400;">   "org.label-schema.version":  "0.8.0"</span>
<span style="font-weight: 400;">}</span>

```

很容易想象出能够很好地利用元数据的工具，例如:

*   为了清晰起见，日志记录和可视化工具可以使用人类可读的名称
*   警报可以使用版本控制标签 *vcs-ref* 和 *vcs-url* 发送关于代码确切版本的信息
*   假设您最大的竞争对手刚刚获得了您使用的一些代码，您被要求从您的运行部署中消除他们的代码。如果标签都在适当的位置，您可以使用它们来识别该供应商提供的所有运行容器。

您会注意到许多标签使用名称空间 org.label-schema。这是第三方工具可以共享的标签名称的[约定。](https://thenewstack.io/label-schema-launches-provide-standard-approach-container-metadata/)

## 查询预部署

但是 docker inspect 命令只有在本地有图像的情况下才有效。如果您想在提取图像之前从容器注册表中查询信息，该怎么办？

您可以编写代码来使用 registry API 获取元数据，但是这需要多次调用。我们用 MicroBadger 让它变得简单多了。像这样试试吧！

```
<span style="font-weight: 400;">$  curl  -s  https://api.microbadger.com/v1/images/microscaling/microscaling | jq</span>

```

你可能想知道为什么这比 Docker inspect 对你更有帮助。

如前所述，您不必在本地获取图像。该 API 还返回关于所有图像版本的元数据信息，而不仅仅是一个特定的版本，尽管目前这仅支持 [Docker Hub](https://hub.docker.com/) ，我们的目的是添加其他注册表。

> 运行在容器中的代码可以通过这种方式访问自己的元数据，而不需要比网络访问更多的权限。

也许最大的优势是你只需要网络访问就可以获得这些信息(当然是为了公众形象。)您不需要访问 docker CLI。这意味着在容器中运行的代码可以访问它。运行在容器中的代码可以通过这种方式访问自己的元数据，而不需要比网络访问更多的权限。

## 实验性的！

MicroBadger API 仍处于试验阶段——还远未实现安全加固。也就是说，请随意踢轮胎！

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>