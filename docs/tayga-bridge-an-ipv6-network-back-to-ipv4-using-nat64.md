# TAYGA:使用 NAT64 将 IPv6 网络桥接回 IPv4

> 原文：<https://thenewstack.io/tayga-bridge-an-ipv6-network-back-to-ipv4-using-nat64/>

地球上的每个网络管理员都知道这个肮脏的小秘密:我们的 IPv4 地址快用完了。鉴于网络和网络设备已经变得如此广泛，这是不可避免的。即使在您的局域网上，您有时也必须使用子网划分，原因很简单，因为您发现大型企业网络上的设备已经吞噬了所有 192.68.1.x 地址。

这是个问题。

这就是开发 IPv6 的原因。IPv6 提供了更大的地址池供使用。问题是 IPv6 不像 IPv4 那么容易使用。毕竟 192.168.1.1 比 0:0:0:0:0:ffff:c0a8:101 好记多了。

但是网络管理员应该怎么做呢？将所有这些服务器和各种硬件设备从 IPv4 迁移到 IPv6？理论上，是的，这正是应该发生的。然而，这并不像人们想象的那么容易。毕竟，您可能有成百上千的设备和众多的位置。最重要的是，总是有讨厌的 DNS 必须更新(这可能等同于停机)。

哦，别忘了 IPv6 并不向后兼容 IPv4。为什么做出这个决定？谁知道呢，但这已经导致许多管理员避免部署 IPv6。为什么？他们已经够忙的了。在这种特别的伤害上再加上侮辱，会对他们的生产力和心智造成严重的伤害。

网络管理员应该做什么？

这可能是解决这些问题的办法。

## 什么是 NAT64？

简单来说，NAT64 被认为是 IPv4 和 IPv6 网络寻址的过渡工具。就像网络地址转换(NAT)可以将 WAN 转换为 LAN 地址一样，NAT64 可以将 IPv6 转换为 IPv4 地址。或者更确切地说，NAT64 通过 NAT 的方式，通过 IPv4 网络促进 IPv6 和 IPv6 主机之间的通信。

为此，使用 IPv6 的设备使用 IPv6 网段的主机部分将 IPv4 地址嵌入数据包。最后，它创建一个嵌入 IPv4 的 IPv6 地址。这种嵌入发生在 IPv6 地址的 32 位地址空间内。

有了这个，你就有了一个广域网和局域网都可以访问的服务器。假设您公司的台式机都使用 IPv6，但您的服务器使用 IPv4。在这些台式机和服务器之间，您将有一个运行 NAT64 转换器的网关，该转换器可以将这些 IPv6 地址转换为 IPv4 地址，然后服务器可以看到这些地址。

这样做的一个问题是，翻译是不对称的。为什么？因为 IPv6 拥有的地址比 IPv4 多得多。因此，一对一的地址映射是不可能的。为了避免这种情况(或为此进行调整)，NAT64 网关使用一种特殊的算法进行无状态映射，或者可以对有状态映射进行手动转换。

还应该注意的是，NAT64 被设计为从 IPv6 转换到 IPv4，而不是相反。

现在您已经对 NAT64 有了基本的了解，让我们来看看让它工作的一种方法。

我将在 Ubuntu Server 18.04 上演示，使用的是 NAT64 的开源解决方案 [TAYGA](http://www.litech.org/tayga/) 。

## 安装 TAYGA

我们需要做的第一件事是安装几个依赖项。登录到您的 Ubuntu 服务器并发出命令:

sudo apt-get 安装构建-基本绑定 9 -y

安装完成后，我们需要修改 sysctl.conf 配置文件。使用以下命令打开该文件:

sudo nano /etc/sysctl.conf

在该文件的底部，添加以下两行:

```
net.ipv4.ip_forward=1
net.ipv6.conf.all.forwarding=1

```

保存并关闭文件。使用以下命令重新加载文件:

`sudo sysctl -p`

解决了依赖关系之后，让我们下载并安装 TAYGA。使用以下命令下载源代码:

`wget http://www.litech.org/tayga/tayga-0.9.2.tar.bz2`

使用以下命令解压缩文件:

`bzip2 -dk tayga-0.9.2.tar.bz2`

使用以下命令解压文件:

`tar xvf tayga-0.9.2.tar`

使用命令切换到新创建的目录:

`cd tayga-0.9.2`

使用以下命令运行配置命令:

`./configure`

使用以下命令编译源代码:

`make`

最后，使用以下命令安装 TAYGA:

`sudo make install`

## 最终配置

现在已经安装了 TAYGA，还需要进行一些配置。请注意，您必须修改下面看到的配置，以匹配您的网络拓扑。不要使用下面显示的精确配置(因为它们可能无法在您的网络上工作)。因此，这些只是建议。

注意:您可能还需要对路由器进行调整，这样才能工作。您做什么调整(以及如何调整)将取决于您使用的路由器。

首先，使用以下命令复制示例 TAYGA 配置文件:

`sudo cp /usr/local/etc/tayga.conf.example /usr/local/etc/tayga.conf`

现在用命令打开新的配置文件:

`sudo nano /usr/local/etc/tayga.conf`

在该文件中，找到行:

将该行更改为您将用于 TAYGA 服务器的隧道 IPv4 地址。这不是路由器的地址。

接下来，查找行:

```
prefix  2001:db8:1:ffff::/96

```

将上述 IPv6 前缀地址替换为网络中未使用的地址。请确保此地址是全局可路由的。

找线:

```
dynamic-pool  172.28.64.0/24

```

更改上面的行以匹配您网络上的 IPv4 地址范围。

保存并关闭文件。

## 开始 TAYGA

配置出来了，是时候开始 TAYGA 了。在终端窗口中，发出以下命令:

`sudo tayga --mktun`

`sudo ip link set nat64 up`

`sudo ip route add 2002:c0a8:01fe::c0a8:01fe dev nat64 (REPLACE IPV6 ADDRESS WITH YOUR ROUTER'S ADDRESS)`

`sudo ip route add 192.168.1.254 dev nat64 (REPLACE IPv4 ADDRESS WITH YOUR ROUTER'S ADDRESS)`

`sudo route add 2002:c0a8:01a7::/96 dev nat64 (THIS THE PREFIX LINE FROM THE TAYGA CONFIGURATION FILE)`

`sudo ip route add 192.168.1.0/24 (THIS IS THE DYNAMIC POOL OPTION FROM YOUR TAYGA CONFIGURATION FILE)`

您可能还想用防火墙阻止外部访问您的 NAT64 前缀。使用命令执行此操作(修改地址以匹配您的网络方案):

```
sudo ip6tables  -A  FORWARD  -s  2001:db8:1::/48  -d  2001:db8:1:ffff::/96  -j  ACCEPT
sudo ip6tables  -A  FORWARD  -d  2001:db8:1:ffff::/96  -j  DROP

```

最后，使用以下命令启动 TAYGA:

`sudo tayga`

所有消息都将记录到/var/log/syslog 中。如果你发现事情不正常，一定要检查日志。如果 syslog 对您没有帮助，您可以在前台模式下运行 TAYGA(因此所有输出都实时发送到终端窗口),命令如下:

`sudo tayga -d`

这就是在 NAT64 中使用 TAYGA 的要点。这当然不是最简单的解决方案，但是如果你需要一点帮助从 IPv4 过渡到 IPv6，这可能正是你需要的工具。

来自 Pixabay 的 Manfred Antranias Zimmer 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>