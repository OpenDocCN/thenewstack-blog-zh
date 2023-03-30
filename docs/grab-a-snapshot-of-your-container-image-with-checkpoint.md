# 用检查点抓取容器映像的快照

> 原文：<https://thenewstack.io/grab-a-snapshot-of-your-container-image-with-checkpoint/>

您是否曾经遇到过这样的情况:您有一个 [Docker](https://thenewstack.io/docker-basics-how-to-use-dockerfiles/) 或 [Podman 容器](https://thenewstack.io/deploy-a-pod-on-centos-with-podman/)完全按照您需要的方式运行，并且希望您能够保存它的快照，这样您就可以确保保存了运行状态，以防容器出现问题？如果发生灾难，您只需使用快照启动一个新容器。

那很好，不是吗？

嗯，这实际上是可能的，感谢检查点功能。可以把这个特性看作是备份正在运行的容器状态的一种便捷方式，这样您就可以在任何需要的时候使用它。当从检查点启动容器时，该容器将处于创建检查点时的相同状态(包括内存和进程)。checkpoint 的另一个非常酷的特性是，当您从保存的状态启动一个新容器时，它的部署速度会比原来更快。

奖金！

现在，在我们继续之前，要知道这是一个实验性的特性，所以要谨慎使用。我建议在非生产机器上使用它，直到你 A)掌握了它的窍门，B)你信任它。在此之前，只考虑将其用于测试目的。

也就是说，让我们创建一些检查点。

## 你需要什么

要使用 docker 检查点，你需要一个运行在 Ubuntu 服务器平台上的 docker 实例和一个拥有 sudo 权限的用户。就是这样。我们开始工作吧。

## 安装必要的依赖项

首先要做的是安装唯一的依赖项， [Criu](https://criu.org/Main_Page) ，核心 Linux 检查点实用程序。登录到您的 Ubuntu 服务器实例，使用命令
为软件添加必要的存储库

```
sudo add-apt-repository ppa:criu/ppa

```

用
更新 apt

您现在可以使用命令安装 Criu:

```
sudo apt-get install criu  -y

```

## 启用实验功能

现在您已经安装了 Criu，您需要为 Docker 启用实验特性。为此，使用命令创建一个新文件:

```
sudo nano  /etc/docker/daemon.json

```

将以下三行添加到文件中:

保存并关闭文件。

使用
重启 Docker

```
sudo systemctl restart docker

```

实验功能现已启用。

## 部署测试容器

让我们部署一个示例 NGINX 容器来使用，而不是在您当前运行的容器上进行测试。使用命令部署容器:

```
docker run  --name checkpoint-test  -p  8005:80  -d  nginx

```

给容器一点时间旋转。您应该能够使用命令:
访问正在运行的容器

```
docker exec  -it checkpoint-test  /bin/bash

```

进入容器后，让我们修改 NGINX index.html 页面。使用以下两个命令在容器中安装 nano 编辑器:

```
apt update
apt install nano  -y

```

用命令打开 index.html 进行编辑:

```
nano  /usr/share/nginx/html/index.html

```

将该文件的内容更改为:

*！doctype html>* *<html lang = " en ">* *<head>* *<meta charset = " utf-8">* *<title>检查点测试</title>**</head>* 

 *保存并关闭文件。使用*退出*命令退出容器，并使用
重启容器

```
docker restart checkpoint-test

```

## 创建您的第一个检查点

我们将创建一个检查点，同时保持 NGINX 容器运行，这是通过以下命令实现的:

```
docker checkpoint create  --leave-running=true checkpoint-test checkpoint00

```

您可以随意命名该检查点。在本演示中，我选择了 checkpoint00。运行该命令后，您将看到:

检查点已成功创建。

现在，我遇到了 Docker CE 和检查点功能无法工作的情况。另一方面，我总是成功地安装了标准存储库中的 Docker 版本，可以用命令:
安装

```
sudo apt-get install docker.io  -y

```

## 使用检查点

假设您在 NGINX 容器上做了一些工作，但是失败了。因为您已经创建了一个检查点，所以您可以使用它。记住，我们的检查点被命名为 checkpoint00。让我们旋转一个新的容器，这可以用命令来完成:

```
docker start  --checkpoint checkpoint00 checkpoint-test

```

你可能比我聪明，给你的检查点起一个有意义的名字，比如表示当前状态或日期的东西。因此，您可能有检查点 022323(2023 年 2 月 23 日)，而不是检查点 00。

您可以验证为特定容器创建的检查点。例如，要列出您从 checkpoint-test 创建的所有检查点，发出命令:

```
docker checkpoint ls checkpoint-test

```

您可能会在输出中看到类似这样的内容:

```
CHECKPOINT NAME
checkpoint01
checkpoint02
checkpoint03
checkpoint04

```

## 但是波德曼呢？

波德曼有一个内置的检查点功能，但它的使用有一个问题。对容器进行检查点操作的唯一方法是使用 sudo 特权。问题是你作为标准用户部署一个容器，你不能用 sudo 检查它，因为 podman 看不到正在运行的容器(因为它是由另一个用户部署的)。

但是，如果您使用 root 用户部署 podman 容器，就像这样:

```
sudo podman run  --name checkpoint-test  -p  8006:80  -d  nginx

```

然后你可以像这样检查容器:

```
sudo podman container checkpoint checkpoint-test

```

正如你可能已经预料到的，这样做违背了无根容器的目的。然而，有传言说，最终波德曼将允许无根容器的检查点。我们会看到未来会发生什么。

这就是对 Docker 和 Podman 使用 checkpoint 命令的全部内容。尝试一下，看看它是否对您所依赖的容器始终保持运行状态有所帮助。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*