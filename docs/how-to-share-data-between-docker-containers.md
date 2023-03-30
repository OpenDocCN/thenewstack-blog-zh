# 如何在 Docker 容器之间共享数据

> 原文：<https://thenewstack.io/containers/how-to-share-data-between-docker-containers/>

让我们谈谈码头工人。毕竟，没有 Docker，您进入容器世界可能会有点困难。想象一下，你的第一步[集装箱化部署](https://thenewstack.io/containers/)完全以 [Kubernetes](https://thenewstack.io/kubernetes/) 为中心。这可能会很快压倒新兴市场。

我想特别谈的是在 Docker 领域的容器之间共享数据。

如果你是 Docker 的新手，你可能会想，“好吧，听起来很酷。”如果您已经对容器有了很好的理解，您可能会问，“但是容器不应该是自给自足的实体吗？”是的，他们是。但这并不意味着他们不能(或不应该)共享数据。

考虑一下:您部署需要共享数据的容器。您可能有一个网站、一个 web 应用程序和一个移动应用程序，它们都依赖于相同的数据。想象一下，让这些容器化的应用程序彼此保持同步是多么大的挑战。

如果负责同步的服务失败了，你得到了三个不同的容器和三组不同的数据，会发生什么呢？这可能会成为你本周最大的噩梦挑战。这不一定是不可能完成的任务，但肯定不是你想要处理的任务。

现在，在我们开始之前，要知道你的容器很可能是自给自足的。但是，有时您需要一个集中的数据量，供多个容器共享。比方说，您部署了一个应用程序或服务的多个实例，这些实例需要使用相同的持久数据或缓存。这些可能是简单的网站，甚至是更复杂的数据库驱动的应用程序。不管是什么用例，您都需要能够在容器之间共享数据。

让我告诉你这是怎么做的。我们将从头开始，所以准备好回到基础。

## 如何安装 Docker

我将在我的首选服务器 Ubuntu 上进行演示。如果您使用不同版本的 Linux(甚至是 Windows 或 macOS)，请确保相应地更改安装步骤。

我们要做的第一件事是安装必要的 Docker 依赖项。为此，登录到您的 Ubuntu 服务器实例并发出命令:

`sudo apt-get install ca-certificates curl gnupg lsb-release -y`

我们现在将添加官方 Docker GPG 命令:

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`

接下来，添加所需的 Docker 存储库:

`echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

我们现在可以使用以下命令更新 apt 并安装 Docker:

`sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y`

安装完成后，使用以下命令将您的用户添加到 docker 组:

`sudo usermod -aG docker $USER`

最后，注销并重新登录，以便更改生效。

## 创建卷

首先要做的是创建一个卷来存放我们的数据。让我们使用以下命令创建一个名为 persistent-data 的卷:

`docker volume create --name persistent-data`

该卷创建在/var/lib/docker/volumes 目录中。您可以向该文件夹添加数据，但只能以 root 用户的身份进行。

既然我们的卷已经创建好了，那么我们可以部署我们的第一个容器，它将使用持久卷。部署容器的命令如下所示:

`docker run -ti --name=conatiner1 -v persistent-data:/data ubuntu:latest`

上面的命令将创建一个名为 container1 的容器，将持久数据卷挂载到新容器内的/data 目录中(基于最新版本的 Ubuntu)。它还可以让您访问正在运行的容器。

一旦部署了容器，并且您可以访问 bash 提示符，就可以使用以下命令在/data 目录中创建一个新文件:

`echo "Hello, New Stack" >> /data/test.txt`

使用以下命令退出正在运行的容器:

`exit`

我们现在将使用以下命令部署第二个容器:

`docker run -ti --name=conatiner2 -v persistent-data:/data ubuntu:latest`

在容器的 bash 提示符下，键入命令:

`cat /data/test.txt`

您应该会看到以下输出:

让我们用以下命令安装 nano 编辑器:

`apt-get update
apt-get install nano -y`

使用以下命令编辑 test.txt 文件:

`nano /data/test.txt`

在文件底部添加以下内容:

```
This data is shared between container  1  and container  2.

```

保存并关闭文件。

从容器中取出:

`exit`

为了再次访问容器，我们必须重新部署它们。首先，使用命令找到容器 ID:

`docker ps -a`

用以下命令启动两个容器(因为它们通过*退出*命令退出):

`docker start ID`

其中 ID 是容器的 ID。

使用以下工具进入容器:

`docker access -it ID /bin/bash`

其中 ID 是容器 1 的容器 ID。

发出命令:

`cat /data/test.txt`

您应该看到(在 text.txt 的两个实例中):

```
Hello,  New Stack
This data is shared between container  1  and container  2.

```

使用*退出*命令退出正在运行的容器。这一次，两个容器都将保持运行。您可以使用以下命令停止并删除它们:

`docker stop ID
docker rm ID`

其中 ID 是每个容器的容器 ID。

这就是借助卷在 Docker 容器之间共享数据的全部内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>