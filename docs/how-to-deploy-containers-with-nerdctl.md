# 如何用 nerdctl 部署容器

> 原文：<https://thenewstack.io/containers/how-to-deploy-containers-with-nerdctl/>

有多少种方法可以部署容器？我们要数数吗？

说真的，我们没有一整天的时间。

实际上，部署容器的方式比我能想到的要多得多。对某些人来说，这可能有点矫枉过正。然而，对于那些喜欢选项的人来说，有这么多部署方法的想法是一个很大的优势。

对于那些属于这一类的人，让我为你不断增长的可能性增加另一种方法。所述方法是通过 nerdctl 的方式。

你怎么能抗拒这个名字？你不能，就是这样。

[nerdctl 命令](https://github.com/containerd/nerdctl)位于 [containerd](https://containerd.io/) 之上，使得通过该运行时部署容器成为可能。为什么？因为就其本身而言，containerd 帮不上什么忙。事实上，您不能用 containerd 部署容器，因为它是一个运行时，与用于此目的的其他工具一起使用。

因此，nerdctl。

让我们首先在一个 [Ubuntu 服务器系统](https://ubuntu.com/download/server)上安装 containerd，然后在其上添加 nerdctl。然后我们将部署我们的第一个容器。

## 为什么使用 nerdctl？

除了酷炫的名字，nerdctl 还提供了以下特性:

*   功能类似于 docker
*   支持 Docker 编写
*   支持无根模式(没有 slirp 开销)
*   支持图像的延迟拉取
*   支持加密图像
*   支持 P2P 图像分发
*   支持容器图像签名和验证

## 要求

要成功安装这些工具，你需要一个 Ubuntu Server 22.04 的运行实例和一个拥有 *sudo* 权限的用户。一旦你有了这些东西，就该开始忙碌了。

## 安装集装箱 d

首先要做的是安装 containerd。在您做任何事情之前，请确保检查 Containerd 下载页面，以确保您下载的是该软件的最新版本。在撰写本文时，这个版本应该是 1.6.8。

登录你的 Ubuntu 实例，打开一个终端窗口。从终端发出命令:

```
wget https://github.com/containerd/containerd/releases/download/v1.6.8/containerd-1.6.8-linux-amd64.tar.gz

```

下载完成后，使用命令:
将 containerd 解压到 */usr/local*

```
sudo tar Cxzvf  /usr/local containerd-1.6.8-linux-amd64.tar.gz

```

牛逼！

接下来，我们必须下载带有命令的 runc 命令行工具:

```
wget https://github.com/opencontainers/runc/releases/download/v1.1.3/runc.amd64

```

用:
安装 runc

```
sudo install  -m  755  runc.amd64  /usr/local/sbin/runc

```

接下来，我们需要容器网络接口(CNI)，可以通过
下载

```
wget https://github.com/containernetworking/plugins/releases/download/v1.1.1/cni-plugins-linux-amd64-v1.1.1.tgz

```

创建一个新的目录来存放 CNI:

```
sudo mkdir  -p  /opt/cni/bin

```

用:
将 CNI 解压到新目录中

```
sudo tar Cxzvf  /opt/cni/bin cni-plugins-linux-amd64-v1.1.1.tgz

```

我们现在必须配置 containerd。创建一个目录来存放配置:

```
sudo mkdir  /etc/containerd

```

用
生成配置文件

```
containerd config default  |  sudo tee  /etc/containerd/config.toml

```

接下来，我们必须使用
启用 SystemdCgroup

```
sudo sed  -i  's/SystemdCgroup \= false/SystemdCgroup \= true/g'  /etc/containerd/config.toml

```

为了能够管理 containerd 服务，我们必须使用命令下载一个预配置的 systemd 文件:

```
sudo curl  -L  https://raw.githubusercontent.com/containerd/containerd/main/containerd.service -o /etc/systemd/system/containerd.service

```

使用:
重新加载 systemd 守护程序

```
sudo systemctl daemon-reload

```

使用
启动并启用容器

```
sudo systemctl enable  --now containerd

```

万岁！您现在已经为 nerdctl 做好了准备

## 安装 nerdctl

在安装 nerdctl 之前，我们必须首先用命令添加几个必要的依赖项:

```
sudo apt-get install uidmap rootlesskit  -y

```

解决了依赖关系之后，用:
下载 nerdctl 文件

```
wget https://github.com/containerd/nerdctl/releases/download/v0.22.2/nerdctl-0.22.2-linux-amd64.tar.gz

```

使用命令:
将文件解压到/usr/local/bin 中

```
sudo tar Cxzvf  /usr/local/bin nerdctl-0.22.2-linux-amd64.tar.gz

```

您应该能够使用命令:
来验证 nerdctl 是否准备好使用

你应该看到:

现在，我们需要配置系统，以便能够部署无根容器。使用
创建一个 systemd 文件

```
sudo nano  /etc/sysctl.d/99-rootless.conf

```

在新文件中，粘贴以下内容:

```
kernel.unprivileged_userns_clone=1

```

保存并关闭文件。要为无根设置 containerd，请发出以下命令:

containerd-root less-setup tool . sh 安装

为了在不使用 sudo 的情况下运行 nerdctl，发出以下两个命令:

```
sudo sh  -c  "echo 1 &gt; /proc/sys/kernel/unprivileged_userns_clone"
sudo sysctl  --system

```

我们现在准备摇动我们的第一个容器。

## 使用 nerdctl 部署容器

幸运的是，用 nerdctl 部署容器与 Docker 非常相似。例如，要用 Docker 部署 NGINX 容器，命令应该是:

```
docker run  --name docker-nginx  -p  8080:80  -d  nginx:alpine

```

要用 nerdctl 做同样的事情，命令应该是:

```
nerdctl run  --name nerdctl-nginx  -p  8080:80  -d  nginx:alpine

```

恭喜你，你的容器部署变得有点乏味了(谁不喜欢呢？).如果您发现自己处于 containerd 是首选引擎的情况，并且您想要类似 Docker 的部署，那么使用 nerdctl 是不会错的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>