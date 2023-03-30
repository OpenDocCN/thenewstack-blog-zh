# 教程:托管本地 Podman 映像注册表

> 原文：<https://thenewstack.io/tutorial-host-a-local-podman-image-registry/>

有些日子，人们感觉几乎不可能跟上云原生世界:Kubernetes 正在[贬低](https://thenewstack.io/this-week-in-programming-kubernetes-says-dont-panic-about-docker-deprecation/) Docker 支持，Red Hat Enterprise Linux [将](https://thenewstack.io/how-to-add-container-support-to-red-hat-cockpit/)从 Docker 迁移到 Podman，我们所知的 CentOS[正在消失](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)，取而代之的是[CentOS 流](https://thenewstack.io/wherefore-art-thou-centos-rocky-linux-cloudlinux-and-centos-stream/)。当你被即将到来的变化弄得晕头转向时，你继续发展。毕竟，您的业务不会在各部分恢复正常时暂停。

为此，你仍然需要工作。如果你的工作以容器为中心，你就要依靠图像来实现它。如果您使用 Red Hat Enterprise Linux 或 CentOS，那么您很有可能已经迁移到了 [Podman](https://podman.io/) ，这是一个用于在 Linux 系统上开发、管理和运行符合 OCI 标准的容器的无后台引擎(和 Docker 替代品)。如果您依赖 CentOS，您会看到迁移到 CentOS Stream 的可能性。您可能还想托管自己的图像存储库。为什么？这个问题很好，答案也很简单。

您可能知道，容器(和 Kubernetes)的安全性是一个热门话题。问题是这种部署的安全性贯穿整个链条，从基础到集群的核心。但是真正对您的部署造成严重破坏的是链条的最底层。如果您使用第三方图像，您可能不知道它们包含哪些漏洞。为此，你最好的选择是要么只使用官方图片(比如由 Canonical 或其他已知实体提供的图片)，要么构建自己的图片。

但是，如果你建立自己的形象，你会希望能够把它们放在本地。这些内部图像可能包含您不想公开的专有代码。

那么，如何托管自己的图像注册表呢？由于您的平台是 RHEL/CentOS Stream 和波德曼，您已经拥有了托管本地图像注册所需的一切。有一点需要注意的是，您将无法通过局域网访问这个注册表。换句话说，这个本地注册表是独立于您的开发工作站的。好处是它更加安全。

让我告诉你这是怎么做的。我将在 CentOS Stream 8 上演示。如果您仍在使用 CentOS 8，您可以继续使用该版本或将其转换为 CentOS Stream。无论哪种方式，这将工作得很好。

## 注册表与存储库和标记

在我们继续之前，让我们先了解一下注册中心、存储库和标记之间的区别。理解这一点实际上很重要，尤其是如果您刚刚进入容器开发的奇妙世界。

*   Registry 是一项负责托管和分发图像的服务(无论是本地的还是第三方的)。
*   存储库是相关图像的集合。通常，这样的存储库将包含提供相同应用程序或服务的不同版本的图像。
*   标签是附加在存储库中图像上的字母数字标识符，作为区分图像版本的一种方式。

## 创建本地注册表

第一步是创建一个存放存储库的目录。为此，请登录到 CentOS 计算机，发出以下命令:

`sudo mkdir -p /var/lib/registry`

创建了目录之后，就该部署本地注册表了。多亏了波德曼，这一步变得简单了。我们将使用–privileged 标志，它告诉引擎在没有任何进一步的安全约束的情况下启动容器，并且不要在启动容器的进程上添加任何特权。

部署注册表的命令是:

`sudo podman run --privileged -d --name registry -p 5000:5000 -v /var/lib/registry:/var/lib/registry --restart=always registry:2`

上面的命令应该毫无怨言地启动。

现在，我们可以配置 Podman registries.conf 文件，让它知道我们在本地机器上托管了一个存储库。为此，使用以下命令打开文件进行编辑:

`sudo nano /etc/containers/registries.conf`

在该文件中，查找行:

将该行改为:

```
registries  =  ['localhost:5000']

```

我们所做的是将注册地址定义为 localhost，端口定义为 5000。

保存并关闭文件。使用以下命令重新启动 Podman:

`sudo systemctl restart podman`

## 将您的第一个映像推送到新的注册表中

我们将使用久经考验的真实(和官方的)NGINX 图像对此进行测试。当然，如果你已经有了自己的图片，可以跳过 NGINX 的拉取，直接给自己的图片加标签推送。

但是对于那些还没有制作自己的图像的人，让我们用官方的 NGINX 图像来演示一下。

使用命令下拉 NGINX 映像:

`podman pull nginx`

在我们将 NGINX 映像推送到注册表之前，我们将对它进行一些更改(因此它是我们自己的映像)。首先，使用命令基于新下载的映像部署一个容器:

`sudo podman run --name nginx-template-base -p 8080:80 -e TERM=xterm -d nginx`

一旦容器部署完毕，您将看到它的 ID。使用以下命令访问正在运行的容器:

`sudo podman exec -it CONTAINER_ID bash`

其中 CONTAINER_ID 是最初部署时给您的容器的 ID。

现在，我们将使用以下命令安装 nano、build-essential 和 php:

`apt-get update`

`apt-get install nano`

`​apt-get install build-essential`

`​apt-get install php5`

完成后，使用以下命令退出容器:

`exit`

使用以下命令提交对容器的更改(从而创建一个新映像):

`sudo podman commit CONTAINER_ID nginx-template`

其中 CONTAINER_ID 是最初部署时给您的容器的 ID。

要查看您的新映像，请发出以下命令:

`sudo podman images`

您应该会看到以下内容的列表:

`localhost/nginx-template`

我们现在可以标记图像并将其推送到本地托管的注册表。

`sudo podman tag localhost/nginx-template localhost:5000/nginx-template`

现在，如果您发出以下命令:

`sudo podman images`

您将看到在 localhost:5000 注册表中列出的 **nginx-template** 映像。

恭喜，您已经部署了自己的私有 Podman 注册中心，下载了一个 NGINX 映像，修改了该映像，标记了新修改的映像，并将新映像推送到您的本地注册中心。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>