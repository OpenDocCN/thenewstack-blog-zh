# CloudFlare 现在支持 WebSockets，但并非没有挑战

> 原文：<https://thenewstack.io/cloudflare-now-supports-websockets-but-not-without-challenges/>

基本上所有的浏览器都支持 WebSockets(甚至是黑莓浏览器),并且被开发者广泛使用。CDN cloud flare 本周宣布支持 WebSockets，由此可见其受欢迎程度。据该公司称，WebSockets 支持是其客户最常要求的功能。

CloudFlare 的 Matthew Prince 提供了一个很好的解释器，它从历史的角度介绍了 WebSockets 提供的功能，并解释了 CloudFlare 如何设法支持它。

提示:对于 CloudFlare 来说，支持 WebSockets 并不容易。CloudFlare 面临的挑战可能有助于解释为什么 WebSockets 已经并将继续需要一段时间才能变得更加普及。

“挑战在于 WebSockets 具有非常不同的连接配置文件，而 CloudFlare 最初并没有针对该配置文件进行优化，”Prince 写道。“WebSockets 带来了新的挑战，因为它们需要比传统 web 请求更长时间的连接，这需要改变我们的网络堆栈。”

Prince 详细介绍了 CloudFlare 如何适应 WebSockets。特别是，他写道，他们已经建立了一个系统，“指示操作系统不要太保守，并允许端口被重用。您可以在设置套接字时通过设置 SO_REUSEADDR 选项来实现这一点。

```
s  =  socket.socket(socket.AF_INET,  socket.SOCK_STREAM)

# Specify that it's ok to reuse the same port even if it's been used before

s.setsockopt(socket.SOL_SOCKET,  socket.SO_REUSEADDR,  1)

s.bind(("1.1.1.1",  0))

s.connect(("www.google.com",  80))

```

鉴于开发人员希望支持更多类型的信息交换，尽管面临挑战，但 WebSockets 的使用可能会增长。 [InfoWorld](http://www.infoworld.com/d/application-development/9-killer-uses-websockets-230771?page=0,1 "InfoWorld") 有一个很好的功能列表，WebSockets 可以帮助收集更多的点击流数据，在浏览器中构建高性能的游戏，自动获取社交信息，以及动态更新位置数据。

CloudFlare 正在向其企业客户推出 WebSockets 支持，并作为测试版提供给精选的企业客户。Prince 没有具体说明它是否会对 CloudFlare 免费层的用户可用，但他确实这样说:“在接下来的几个月里，随着我们更好地了解该功能对我们系统的需求和负载，我们计划将对 WebSockets 的支持扩展到更多客户，包括 CloudFlare 服务的其他层的客户。”

他还称赞 CloudFlare 工程师推动了 WebSockets 支持。Marek Majkowsky“令人信服地指出，网络套接字是现代网络的一部分，我们找到一种保护和加速它们的方法是至关重要的，”Prince 写道。

特色图片[通过](https://www.flickr.com/photos/crdot/ "Flickr") Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>