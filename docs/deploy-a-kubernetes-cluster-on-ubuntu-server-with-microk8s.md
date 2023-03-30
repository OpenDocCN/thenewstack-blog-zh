# 使用 Microk8s 在 Ubuntu 服务器上部署 Kubernetes 集群

> 原文：<https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-with-microk8s/>

Kubernetes 很难。这是不可避免的。从开始到结束，你会发现在你的道路上有如此多的障碍，有时，你可能会觉得很想放弃。

不要。

实际上有一种非常简单的方法来部署一个用于开发甚至生产的 Kubernetes 集群。

那个方法多亏了 [Microk8s](https://microk8s.io/) 。

Microk8s 由 Canonical 创建，作为一种将 Kubernetes 环境部署到商用硬件或第三方云主机(如 [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) 、Azure、Rackspace 和 Linode)的简化方法。毫无疑问，Microk8s 是掌握 Kubernetes 最简单的工具。

而且差远了。

因为太简单了，你可能会认为 Microk8s 仅限于单节点开发环境。按照这种想法，你就错了。Microk8s 的开发人员实际上已经使实例集群化成为可能。举个例子，只需要三个 Microk8s 节点就可以将故障转移添加到组合中。

这正是我今天要做的…向您展示如何在 Microk8s 的帮助下部署 Kubernetes 集群。

## 要求

我将在 Ubuntu Server 22.04 上演示，但这个过程可以在任何支持 Snap 包的操作系统上运行。你需要三个在同一个网络上的 Ubuntu Server 实例和一个拥有 sudo 特权的用户。就这样…让我们变点魔法吧。

## 安装 Microk8s

您要做的第一件事是在每个节点上安装 Microk8s。因此，登录到您的第一个节点并发出命令:

`sudo snap install microk8s --classic`

在每个节点上做同样的事情。同样，您需要使用以下命令将您的用户添加到 microk8s 组:

`sudo usermod -aG microk8s $USER`

注销并重新登录，以使更改生效。在每个节点上执行此操作。

使用以下命令创建一个新目录:

`mkdir ~/.kube`

使用以下命令为新目录提供适当权限:

`sudo chown -f -R $USER ~/.kube`

万岁。

## 配置主机名和主机

在继续之前，您需要在每个节点上配置主机名和主机文件。要设置主机名，可以发出如下命令:

`sudo hostnamectl set-hostname microk8scontroller`

你可以给系统起任何你喜欢的名字(比如 microk8scontroller，microk8snode1，microk8snode2 等。).

接下来，您需要在每台机器上配置 hosts 文件。使用以下命令打开该文件进行编辑:

`sudo nano /etc/hosts`

在该文件的底部，添加如下行(使用您的主机名和 IP 地址):

```
192.168.1.100  microk8scontroller
192.168.1.101  microk8snode1
192.168.1.102  microk8snode2

```

您需要将上述内容添加到每个节点的 hosts 文件中。保存并关闭文件。

此时，如果您可以通过在控制器节点上运行以下命令来验证到目前为止一切都已启动并运行:

`microk8s kubectl describe node`

您应该会看到控制器节点的详细描述。

## 如何加入节点

与标准的 Kubernetes 不同，这一过程要简单得多。从控制器节点发出命令:

`microk8s add-node`

上面的输出将包括类似如下的 join 命令:

`microk8s join 192.168.1.137:25000/d6c656de35d466889c92cebcaca0d843/30b781bb37e8`

转到第一个节点，运行 join 命令。完成后，转到下一个节点并运行相同的命令。继续这样做，直到所有节点都加入到集群中。

然后，您可以使用以下命令检查以确保所有节点都已联接:

`microk8s kubectl get nodes`

您应该会看到类似如下的输出:

`microk8scontroller   Ready    <none>   23d   v1.24.3-2+63243a96d1c393`

`microk8snode1        Ready    <none>   23d   v1.24.3-2+63243a96d1c393`

`microk8snode2        Ready    <none>   23d   v1.24.3-2+63243a96d1c393`

您也可以使用以下命令验证群集的状态:

`microk8s status`

上述命令的输出应该如下所示:

`microk8s is running`

`high-availability: yes`

`datastore master nodes: 192.168.1.100:19001`

`datastore standby nodes: none`

需要注意的是，只有当您拥有 3 个或更多节点时，您才会看到高可用性列为是。如果您的节点少于三个，高可用性将被列为否。如果您只是将它用作开发集群(并且不立即需要 HA)，那么只需要两个节点就可以了。否则，请确保添加更多以享受该功能。

## 将 Hello World 部署到您的集群

作为一个快速测试，让我们将 Hello World 应用程序部署到集群。在控制器上，运行以下命令:

`microk8s kubectl create deployment hello-world --image=tutum/hello-world:latest`

`microk8s kubectl expose deployment hello-world --type=NodePort --port=80 --name=hello-world-service`

`microk8s kubectl port-forward -n default service/hello-world-service 8080:80`

最后一个命令不会将您的终端返回给您，但会显示端口转发正在运行，输出如下:

`Forwarding from 127.0.0.1:8080 -> 80`

`Forwarding from [::1]:8080 -> 80`

`Handling connection for 8080`

从第二个终端登录到您的控制器节点，并发出命令:

`curl localhost:8080`

您将看到包含 *< h1 > Hello world 的输出！< /h1 >* 。当然，如果你在桌面上工作，你可以打开一个浏览器，指向这个页面，你会看到 Hello World 页面被打印出来。

我的新 Kube 朋友们，这就是如何在 Microk8s 的帮助下快速部署 Kubernetes 集群。这是快速启动和运行集群的好方法，因此您可以花更多的时间进行开发，减少管理时间。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>