# Hummingboard 上的 Node.js 入门，这是一个 Raspberry Pi 克隆

> 原文：<https://thenewstack.io/getting-started-node-js-raspberry-pi/>

Javascript 的事件驱动执行模型非常适合服务器端的物联网应用，特别是在 nanoLinux 设备上，比如 Raspberry Pi 或 Hummingboard 克隆。我有几个滑板，它们是结实的小装置。因为我刚刚开始尝试 Javascript，所以首先要做的是安装和快速检查，看看是否能在网页上放些东西。在后续文章中，我可能会将探索扩展到更复杂的 Web 示例，并尝试在主板的 GPIO 引脚上进行一些输入/输出。

## 装置

使用命令行安装相当简单。我使用的是 Hummingboard-i2eX，配有 i.MX6 双核处理器、1 GB 的 64 位 1066 Mbps 内存和 Debian Linux 版本 3.0.35。该设置还具有供电的 4 端口集线器、Logitech 无线键盘/鼠标垫和 EdiMax 802.11n USB 无线加密狗。视频通过标准 HDMI 电缆传输到三洋大屏幕。Raspberry Pis 和它们的克隆产品似乎都对电力需求非常敏感，所以一个电力集线器是非常必要的。为 Pi 和 Hummingboard 使用一个 5 伏 2 安培的壁式电源插座，并配有一根良好的 USB 电缆，以防止出现问题。

我按照 justplugin 网站上的指示在我的 Hummingboard 设备上加载 node.js。下面是一些带有注释的步骤:

1.创建一个新目录来保存下载的 nodejs 文件。

```
cd  ~

mkdir nodejs_download

cd nodejs_download

```

2。从网上取 node.js。

```
wget http://nodejs.org/dist/v0.11.7/node-v0.11.7.tar.gz

tar  -xzf node-v0.11.7.tar.gz

```

3。编译并构建 node.js 程序。

```
cd node-v0.11.7

./configure

make

```

即使有双核 Hummingboard、相当快的互联网连接和 1 GB 的内存，编译和构建程序也要花大约 40 分钟。

4.在蜂鸣板系统上安装程序。

5。重启蜂鸣板。

6。确定 node.js 的版本和模块安装程序。这些命令还验证一切都在工作。

## 一个极其简单的例子

Web 上有大量的例子说明如何在基于 Raspberry Pi 的机器上开始使用 node.js。我发现了一个小程序，它使用 node.js 服务器将“hello world”简单地发布到浏览器屏幕上。查看 [howtonode 网站](http://howtonode.org/hello-node)了解完整的细节和一些额外的脚本示例。

1.这是来自 howtonode 站点的 hello-node 脚本。

```
// ******************************************

// Load the http module to create an http server.
var http  =  require('http');

// Configure our HTTP server to respond with Hello World to all requests.
var server  =  http.createServer(function  (request,  response)  {
response.writeHead(200,  {"Content-Type":  "text/plain"});
response.end("Hello World\n");
});

// Listen on port 8000, IP defaults to 127.0.0.1
server.listen(8000);

// Put a friendly message on the terminal
console.log("Server running at http://127.0.0.1:8000/");

// ******************************************

```

2。使用您喜欢的命令行编辑器，将文本放在一个文件中，并将其命名为 hello-node.js。

3.启动服务器，用下面的命令行运行脚本:

您将收到一条消息，说明服务器正在本地主机(127.0.0.1:8000)上运行。

4.把这个 IP 地址输入到你 Pi 的浏览器中,“hello world”消息应该会出现在屏幕的顶部。你也可以通过使用 Hummingboard 的 IP 从同一个网络上的其他机器上看到这个页面。用 ifconfig 查找。

就我而言，当我在 Chrome 浏览器中指向 192 . 168 . 1 . 111:8000(Hummingboard 的地址，在我的局域网上)时，我可以看到来自我的 XFCE Linux 华硕笔记本的消息。

## 结论

我很高兴地发现，让 node.js 在基于 Raspberry Pi 的 nanoLinux 机器上运行只需要付出适度的努力。网上有很多关于 Javascript 的信息，它是一种流行的语言。我将在以后的文章中介绍如何访问 GPIO 引脚。

通过 Flickr 知识共享的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>