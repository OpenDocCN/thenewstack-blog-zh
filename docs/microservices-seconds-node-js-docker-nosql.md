# 秒级微服务:Node.js + Docker + NoSQL

> 原文：<https://thenewstack.io/microservices-seconds-node-js-docker-nosql/>

Joyent 产品经理

[Tim Gross](https://github.com/tgross)

贡献了本教程，与 Linux 基金会的节点互动，在俄勒冈州波特兰举行的这个星期。

蒂姆·格罗斯

Tim 是 Triton 弹性容器服务提供商 Joyent 的产品经理。蒂姆之前在 DramaFever 负责运营，他和他斗志昂扬的团队负责 Docker 的制作，为数百万粉丝提供日常戏剧、纪录片和恐怖电影服务。在前世，Tim 是一名建筑师(建筑，不是软件)。在他发现自己可以自动处理生活中几乎所有无聊的事情后，他开始从事编程和操作。

在过去的几周里，我写了一些

[service discovery](https://www.joyent.com/blog/container-native-discovery)

对于容器本机应用程序，提供了一个

[tool](https://github.com/joyent/containerbuddy)

为了让现有的应用程序实现这一点，给出了一个动态更新的例子

[Nginx virtual host configurations](https://www.joyent.com/blog/dynamic-nginx-upstreams-with-containerbuddy)

，并展示了如何

[update external DNS](https://www.joyent.com/blog/automatic-dns-updates-with-containerbuddy)

基于集装箱的变化。

今天，我将把所有这些部分放在一个多层应用程序中，它可以作为微服务架构的蓝图。跟随 Github 上的[代码。](https://github.com/tgross/triton-touchbase/)

我们要组装的应用程序是 Touchbase，一个 Node.js 应用程序。我们需要以下零件。

*   位于堆栈中心的 Node.js 应用程序 Touchbase
*   Nginx，充当 Touchbase 节点的负载平衡器
*   Couchbase，用于数据层
*   执政官，充当发现服务
*   Containerbuddy，帮助服务发现
*   CloudFlare-watcher，用于更新 DNS
*   CloudFlare DNS，使我们的网站在互联网上可以通过域名访问
*   Triton，我们的容器原生基础设施平台

该堆栈可用于任何微服务应用，单个组件可轻松更换。更喜欢 HAProxy 而不是 Nginx？没问题——只需用您想要使用的图像更新`docker-compose.yml`文件。

![Diagram of Touchbase v2 architecture](img/6692a339306a984e166a1af709d1659c.png)

## Touchbase

[Touchbase](https://github.com/couchbaselabs/touchbase/) Node.js 应用程序由 Couchbase 实验室编写，作为 Couchbase 4.0 新 N1QL 查询特性的演示。它不是专门为容器原生世界设计的，所以我们使用 [Containerbuddy](https://github.com/joyent/containerbuddy/) 来满足我们的服务发现需求。

Touchbase 使用 Couchbase 作为其数据层。我们可以让它直接服务请求，但我们将把 Nginx 负载平衡器放在它的前面，因为我们希望 Nginx 能够执行零停机配置重新加载。(此外，在一个生产项目中，我们可能在 Nginx 后面有多个应用程序。)我们将使用 Touchbase 的[分支，它消除了配置 SendGrid 的需求，因为设置事务性电子邮件服务超出了本文的范围。](https://github.com/tgross/touchbase)

Touchbase 服务的 Containerbuddy 有一个`onChange`处理程序，它调用`consul-template `根据 Consul 中存储的模板写出一个新的`config.json`文件。不幸的是，Touchbase 不支持优雅的重新加载，所以为了给 Touchbase 一个带有 Couchbase 集群 IP 的初始配置，我们需要一个预启动脚本来完成。在派生主应用程序之前选择运行`onChange `处理程序或另一个启动脚本将是 Containerbuddy 的一个很好的特性，我会在下一篇文章中再次提到这一点。

## Nginx

Nginx 虚拟主机配置有一个`upstream`指令，为后端 Touchbase 应用程序节点运行最少连接的负载平衡器。当 Touchbase 节点上线时，它们将向 Consul 注册自己。

就像在我们最初的 Containerbuddy 示例项目中一样，Nginx 服务的 Containerbuddy 有一个`onChange`处理程序，它调用`consul-template`来写出一个基于我们存储在 Consul 中的模板的新虚拟主机配置文件。然后，它向 Nginx 发出一个`nginx -s reload`信号，使其[优雅地重新加载](http://nginx.org/en/docs/control.html#reconfiguration)其配置。

## 沙发底座

Couchbase 是一个集群化的 NoSQL 数据库。我们将使用我的 Joyent 同事 Casey Bisson 编写的[clustered couch base in containers](https://github.com/misterbisson/clustered-couchbase-in-containers)的蓝图。它使用 Couchbase 4.0 的 [`triton-couchbase`](https://github.com/misterbisson/triton-couchbase) repo 来访问新的 N1QL 特性。

当第一个 Couchbase 节点启动时，我们使用`docker exec`引导集群，并向 Consul 注册第一个节点以进行发现。然后，我们将运行适当的 REST API 调用，为我们的应用程序创建 Couchbase 存储桶和索引。此时，我们可以通过`docker-compose scale`添加新节点，这些节点将从 Consul 获得一个 Couchbase 集群 IP。在这一点上，我们移交给 Couchbase 自己的自聚类。

## 云闪观测者

就像我们本周早些时候的动态 DNS 项目一样， [`cloudflare`容器](https://github.com/tgross/triton-cloudflare/)将有一个 Containerbuddy `onChange`处理程序，它通过[它们的 API](https://api.cloudflare.com/) 更新 CloudFlare。该处理程序是一个 [bash 脚本](https://github.com/tgross/triton-cloudflare/blob/master/update-dns.sh)，它查询 CloudFlare API 以获取现有的 A 记录，然后根据 Consul 已知的 IP 地址对这些记录进行区分。如果有变化，我们首先添加新记录，然后删除任何过时的记录。

## 运行示例

您可以使用 Github repo 顶部的 [`start.sh`脚本](https://github.com/tgross/triton-touchbase/blob/master/start.sh)运行整个堆栈。您需要一个 CloudFlare 帐户和一个您已将 DNS 委托给 CloudFlare 的域，但是如果您想跳过这一部分，您可以简单地注释掉`startCloudflare`行。

一旦你准备好了:

1.  [获得 Joyent 账户](https://docs.joyent.com/public-cloud/getting-started)。
2.  在您的笔记本电脑或其他环境中安装 [Docker 工具箱](https://docs.docker.com/installation/mac/)(包括`docker`和`docker-compose`)，以及 [Joyent CloudAPI CLI 工具](https://apidocs.joyent.com/cloudapi/#getting-started)(包括`smartdc`和`json`工具)。
3.  [配置 Docker 和 Docker Compose 与 Joyent 一起使用](https://docs.joyent.com/public-cloud/api-access/docker)。
4.  准备好您的 CloudFlare API 密钥。

此时，您可以在 Triton 上运行示例:

```
<span class="pun">.</span><span class="str">/start.sh env
# here you'll be asked to fill in the .env file
./</span><span class="pln">start</span><span class="pun">.</span><span class="pln">sh</span>

```

或者在您的本地 Docker 环境中(注意，您可能需要增加 docker-machine 虚拟机的可用内存来运行完整的集群):

```
<span class="pun">.</span><span class="str">/start.sh env
./</span><span class="pln">start</span><span class="pun">.</span><span class="pln">sh  </span><span class="pun">-</span><span class="pln">f  docker</span><span class="pun">-</span><span class="pln">compose</span><span class="pun">-</span><span class="kwd">local</span><span class="pun">.</span><span class="pln">yml</span>

```

创建的`.env`文件需要填入以下值:

```
<span class="pln">CF_API_KEY</span><span class="pun">=&lt;</span><span class="pln">your  </span><span class="typ">CloudFlare</span><span class="pln">  API key</span><span class="pun">&gt;</span><span class="pln">
CF_AUTH_EMAIL</span><span class="pun">=&lt;</span><span class="pln">the email address associated  </span><span class="kwd">with</span><span class="pln">  your  </span><span class="typ">CloudFlare</span><span class="pln">  account</span><span class="pun">&gt;</span><span class="pln">
CF_ROOT_DOMAIN</span><span class="pun">=&lt;</span><span class="pln">the root domain you want to manage</span><span class="pun">.</span><span class="pln">  ex</span><span class="pun">.</span><span class="pln">  example</span><span class="pun">.</span><span class="pln">com</span><span class="pun">&gt;</span><span class="pln">
SERVICE</span><span class="pun">=</span><span class="pln">nginx  </span><span class="pun">&lt;</span><span class="pln">the name of the service you want to monitor</span><span class="pun">&gt;</span><span class="pln">
RECORD</span><span class="pun">=&lt;</span><span class="pln">the  A</span><span class="pun">-</span><span class="pln">record you want to manage</span><span class="pun">.</span><span class="pln">  ex</span><span class="pun">.</span>  <span class="kwd">my</span><span class="pun">.</span><span class="pln">example</span><span class="pun">.</span><span class="pln">com</span><span class="pun">&gt;</span><span class="pln">
TTL</span><span class="pun">=</span><span class="lit">600</span>  <span class="pun">&lt;</span><span class="pln">the DNS TTL you want</span><span class="pun">&gt;</span><span class="pln">
CB_USER</span><span class="pun">=&lt;</span><span class="pln">the administrative user you want  </span><span class="kwd">for</span><span class="pln">  your  </span><span class="typ">Couchbase</span><span class="pln">  cluster</span><span class="pun">&gt;</span><span class="pln">
CB_PASSWORD</span><span class="pun">=&lt;</span><span class="pln">the password you want  </span><span class="kwd">for</span><span class="pln">  that  </span><span class="typ">Couchbase</span><span class="pln">  user</span><span class="pun">&gt;</span>

```

随着启动脚本的运行，它将启动 Consul web UI 和 Couchbase web UI。一旦 Nginx 开始运行，它将启动 Touchbase 站点的登录页面。此时，只有一个 Couchbase 节点、一个应用服务器和一个 Nginx 服务器，您将看到消息:

```
<span class="typ">Touchbase</span><span class="pln">  cluster  </span><span class="kwd">is</span><span class="pln">  launched</span><span class="pun">!</span>
<span class="typ">Try</span><span class="pln">  scaling it up  </span><span class="kwd">by</span><span class="pln">  running</span><span class="pun">:</span>  <span class="pun">./</span><span class="pln">start scale</span>

```

如果你这样做，你将运行`docker-compose scale`操作，增加 2 个 Couchbase 和 Touchbase 节点和 1 个 Nginx 节点。您可以通过查看 Consul 和 Couchbase web UIs 来观察节点的动态变化。

## 包扎

我们在这里构建的堆栈突出了将该应用程序归档的优势。我们有一个简单、可重复的部署，我们可以在本地测试，然后将相同的堆栈推向生产。我们拥有自动发现和配置功能，使这种部署成为可能。我们可以轻松实现横向扩展，对每层的规模进行精细控制。得益于我们对 CloudFlare 的集成，我们还实现了全球发现。

我们使用 Containerbuddy 作为一个例子，它是使任意应用程序成为容器本机应用程序所需的最少垫片。现在我们已经看到在 Triton 上组装了一个生产就绪的多层应用程序，我们可以看到容器原生服务发现可以不受任何特定调度框架的限制。这使得连接非集装箱化设计的组件变得容易。

部署在 Triton 上使这一切变得更加容易。在应用程序容器拥有自己的 NIC 的环境中，就像在 Triton 上一样，我们可以依靠应用程序容器来更新发现服务，而无需重量级调度程序。这意味着您可以使用像 Docker Compose 这样的简单工具来部署和链接容器，而无需任何额外的软件。使用 Triton 的容器原生基础设施，无需供应虚拟机，Triton 按容器收费，因此很容易跟踪您的成本将如何随您的应用程序扩展。你可以部署在 Joyent 公共云中的 Triton 上，也可以部署在你自己的数据中心(它是开源的！).只需配置 Docker 并按下`start.sh`按钮。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>