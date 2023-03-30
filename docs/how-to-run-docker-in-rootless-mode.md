# 如何在无根模式下运行 Docker

> 原文：<https://thenewstack.io/how-to-run-docker-in-rootless-mode/>

尽管可以部署没有 root 权限的 [Docker](https://www.docker.io) 容器，但这并不意味着它始终是无根的。这是因为栈中还有其他组件(比如 runc、containerd 和 dockerd)需要 root 权限才能运行。这可以等同于通过提高特权攻击的方式的安全问题。

当然，您可以将您的用户添加到 docker 组，并在没有`sudo`帮助的情况下运行 docker deploy 命令，但这并不能真正解决问题。还有其他方式运行 docker，这看起来是个好主意，但最终，它们和使用`sudo`特权运行 docker 一样危险。

你是做什么的？你可以一直无根。

## 无根是如何工作的

实际上，运行无根 Docker 利用了用户名称空间。该子系统提供跨进程的权限隔离和用户标识隔离。Linux 内核从 3.8 版开始就提供了这个特性，它可以和 docker 一起使用来映射一系列用户 id，这样最内层名称空间中的 root 用户就可以映射到父名称空间中的非特权范围。

Docker 能够利用用户名称空间特性已经有一段时间了。这是通过使用`--userns-remap`选项完成的。唯一的问题是运行时引擎仍然以 root 用户身份运行，所以它没有解决我们的问题。

这就是无根码头工人发挥作用的地方。

## 限制

不幸的是，无根模式并不完美。第一个问题是无根 docker 将无法访问特权端口，即 1024 以下的任何端口。这意味着您需要记住将您的容器暴露给 1024 以上的端口，否则，它们将无法运行。

另一个问题是，只有在使用 cgroup v2 和 systemd 运行时，才支持使用–CPU、–memory 和–pids-limit 等选项来限制资源。

您可能遇到的其他限制包括:

*   不支持 AppArmor、检查点、覆盖网络和 SCTP 端口暴露。
*   有限的存储驱动程序支持(仅支持 overlay2、fuse-overlayfs 和 vfs 存储驱动程序)。
*   不支持–net-host。

说了这么多，我们如何安装 docker，使它可以在无根模式下运行？其实挺简单的。让我告诉你怎么做。

我将在我的首选服务器 Ubuntu Server 20.04 上进行演示，但是您几乎可以在任何 Linux 发行版上进行演示。唯一的区别是要为一个依赖项运行的安装命令。

## 安装独立依赖项

我们必须做的第一件事是为这个设置安装唯一的依赖项。该依赖项是 uidmap，它处理系统的用户名称空间映射。要安装 uidmap，请登录到您的服务器并发出以下命令:

`sudo apt-get install uidmap -y`

这就是依赖关系的全部内容。

## 安装 Docker

接下来，我们安装 Docker。我们不想使用标准库中的版本，因为它不能在无根模式下成功运行。相反，我们需要下载一个特殊的安装脚本来安装无根 Docker。我们可以用一个简单的命令下载并安装 docker 的无根版本:

`curl -fsSL https://get.docker.com/rootless | sh`

安装完成后，您需要向. bashrc 添加一对环境变量。

`nano ~/.bashrc`

在该文件中，在底部添加以下行:

```
export PATH=/home/jack/bin:$PATH
export DOCKER_HOST=unix:///run/user/1000/docker.sock

```

注意:确保添加您的特定用户 ID。在上面的代码中，我的 ID 是 1000。要找到您的用户 ID，请发出以下命令:

`id`

您需要在
行中的 *uid=* 之后添加数字

```
export DOCKER_HOST=unix:///run/user/ID/docker.sock

```

其中 *ID* 是您的用户 ID 号。

保存并关闭文件。

注销并重新登录到服务器(这样修改就会生效)，你就可以测试无根 docker 了。

## 测试无根对接器

我们将部署可信赖的 NGINX 容器作为测试。请记住，我们还没有将我们的用户添加到 docker 组。如果这是一个标准的 docker 安装，如果不将我们的用户添加到 Docker 组或者使用`sudo`特权运行 deploy 命令，我们将无法成功部署 NGINX 容器。

要测试无根模式(以分离模式部署 NGINX)，发出以下命令:

`docker run --name docker-nginx -p 8080:80 -d nginx`

打开一个 web 浏览器，指向 http://SERVER:8080(其中 SERVER 是您的 Docker 服务器的 IP 地址)，您应该会看到 NGINX 欢迎页面。

这个容器是在没有使用 root 的情况下部署的，所以整个堆栈都没有那些提升的特权。您甚至可以部署一个完整的 Linux 容器，并使用如下命令访问它的 bash shell:

`docker run -it ubuntu bash`

所有这些都是在不涉及 root 权限的情况下完成的。

## 结论

这显然不是解决 Docker 容器所有安全问题的完美解决方案。你甚至可能会发现 Podman 是一个更好的解决方案，因为它可以开箱即用。但是对于那些已经投资了 Docker，但是希望获得尽可能多的安全性的人来说，在无根模式下运行 Docker 无疑是一个可行的选择。

尝试一下无根 Docker，看看它是否能减轻您的安全问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>