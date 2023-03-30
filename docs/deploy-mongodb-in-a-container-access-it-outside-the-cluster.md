# 在容器中部署 MongoDB，在集群外部访问它

> 原文：<https://thenewstack.io/deploy-mongodb-in-a-container-access-it-outside-the-cluster/>

在某种程度上，在容器开发的过程中，您将不得不部署一个数据库作为应用程序的数据存储工具。或者，您可能计划使用一个 [NoSQL 数据库](https://thenewstack.io/why-choose-a-nosql-database-there-are-many-great-reasons/)进行分析，为了方便起见，您宁愿将该数据库部署为一个容器。

这就是 [Docker 容器](https://www.docker.com/?utm_content=inline-mention)的魅力所在……它们部署和使用都很简单。考虑一下 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 。我遇到过许多例子(尤其是在部署一个新版本到我的首选服务器发行版、 [Ubuntu](https://ubuntu.com/) 时)，mongod 服务就是无法启动。

然而，如果我将数据库作为容器部署，我很少(如果有的话)会遇到问题。我可以在几秒钟内部署 MongoDB 容器，并从集群外部连接到它。

等一下。如果你足够精明，你就知道事情没那么简单。无论您如何部署 MongoDB，默认配置都不允许来自本地主机之外的任何地方的连接。那么，如何部署 MongoDB 的容器化版本，并从主机服务器之外的机器或服务连接到它呢？

有一个窍门。

现在，我并不是说这是使用 MongoDB 作为容器的理想方法。然而，它确实提供了一个很好的视角来了解 Docker 容器是如何使用的，我将向您展示如何使用。

你准备好了吗？

## 要求

为了成功实现这一点，你需要一个支持 Docker 的操作系统。我将在 Ubuntu Server 22.04 上演示，但您可以使用自己选择的平台。您唯一需要更改的是 Docker 的安装过程(因为我也将向您展示如何处理这个问题)。

让我们开始吧。

## 安装 Docker

为了不让您阅读另一篇文章，让我向您展示如何在 Ubuntu Server 上安装 Docker。这其实很简单…只需将以下命令剪切并粘贴到 Linux 终端窗口中。

首先，您必须使用下面的命令添加官方的 Docker GPG 键:

```
curl  -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

```

下一步是添加 Docker 存储库，这可以通过
来实现

```
echo  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] &amp;
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"  |  sudo tee  /etc/apt/sources.list.d/docker.list  &gt;  /dev/null

```

安装必要的依赖项:

```
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release  -y

```

用:
更新 apt

用
安装 Docker 社区版

```
sudo apt-get install docker-ce docker-ce-cli containerd.io  -y

```

使用命令将您的用户添加到 Docker 组:

```
sudo usermod  -aG docker  $USER

```

注销并重新登录，使更改生效。

迄今为止工作出色。

## 部署 MongoDB 容器

是时候部署 MongoDB 容器了。只是为了好玩，让我们部署带有[持久存储的容器。](https://thenewstack.io/kubernetes-and-the-challenge-of-adding-persistent-storage/)首先，我们将使用命令
在主机上创建一个目录来存放数据

准备好存放持久数据的目录后，使用
部署容器

```
docker run  -d  --name example-mongo  -v  ~/mongo/data:/data/db  -p  27017:27017  mongo:latest

```

要验证数据库容器是否正在运行，发出命令:

您应该在输出中看到类似这样的内容:

```
a30ddb85c456     mongo:latest     "docker-entrypoint.s…"     5  days ago     Up  5  days     27017/tcp,  0.0.0.0:27017-&gt;27017/tcp,  :::2701y-&gt;2701y/tcp     example-mongo

```

恭喜，您的数据库容器已经部署完毕，可以进行配置了。

## 为外部连接配置数据库

此时，容器已经启动并运行，但是只能从 localhost 内部访问。换句话说，你不能从容器外面够到它。幸运的是，这个修复相当简单。首先，您必须知道如何访问正在运行的容器的 Bash 提示符。记住，当我们在上面部署容器时，我们用选项`--name example-mongo`将其命名为`example-mongo`。我们将使用这个名称通过命令来访问容器:

```
docker exec  -it example-mongo bash

```

现在，您应该会发现自己在容器的 Bash 提示符下，它会被表示成这样:

在我们做任何事情之前，让我们安装 nano 文本编辑器(因为它比附带的 vi 更容易使用。】。为此，用:
更新 apt

apt 更新后，用
安装 nano

使用命令打开 MongoDB 配置文件:

```
nano  /etc/mongod.conf.orig

```

找到以下部分:

```
net:
port:  27017
bindIp:  127.0.0.1

```

您必须将该部分更改为:

```
net:
port:  27017
bindIp:  0.0.0.0

```

上面的配置向任何连接开放了 MongoDB。如果你想限制你的网络上的一个特定的 IP，你可以这样配置它:

```
net:
port:  27017
bindIp:  192.168.1.62

```

或者，如果您想限制网络上的所有机器，您可以使用类似下面的代码:

```
net:
port:  27017
bindIp:  192.168.1.0/24

```

使用键盘组合[Ctrl]+[X]保存并关闭文件。使用 Exit 命令退出容器。由于我们已经对数据库配置进行了更改，重启 MongoDB 最简单的方法就是重启容器本身。为此，我们首先必须定位容器 ID，这是通过命令:
完成的

您只需要集装箱 ID 的前四个字符。有了这些，用
重新启动容器

其中 ID 是示例 mongo 容器的 ID。如果您再次访问容器的 Bash 提示符，您可以查看 MongoDB 配置文件，并看到您的更改仍然完好无损。

我发现对 MongoDB 有很大帮助的一件事是安装 [MongoDB Compass](https://www.mongodb.com/products/compass) 应用程序，这是一个用于管理数据库的 GUI 工具。安装好之后，您可以使用如下连接字符串连接到容器化的 MongoDB:

```
mongodb://192.168.1.7:27017

```

在 Compass 中，您可以创建/编辑数据库/收藏。

现在，您可以从宿主文件之外访问 MongoDB 容器，这意味着您可以将该数据库用于许多目的。但是，最重要的是，您已经学会了如何安装 Docker、部署具有持久存储的容器、访问容器、配置服务以及重启容器。

如果我没有提到这并不是使用 MongoDB 最安全的方法，那也是我的失职。毕竟，您希望创建一个能够访问特定数据库的数据库用户，但这超出了本文的范围。但是，如果您知道如何使用 MongoDB，您就已经知道如何创建经过身份验证的用户。

即便如此，这也是了解部署 Docker 容器的细节的好方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>