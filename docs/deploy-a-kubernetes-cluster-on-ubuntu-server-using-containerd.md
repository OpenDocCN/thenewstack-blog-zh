# 使用 Containerd 在 Ubuntu 服务器上部署 Kubernetes 集群

> 原文：<https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-using-containerd/>

自从 Docker 支持从 Kubernetes 上移除后，在 Ubuntu 服务器上部署集群就成了一个挑战[。我有很多次都不确定我的头发是否能撑过去…这就是为什么会有这么复杂的问题。](https://thenewstack.io/ubuntu-server-struggles-with-post-docker-kubernetes-installs/)

但也不是不可能。

要在 Ubuntu 上成功部署 Kubernetes，您必须使用 containerd 运行时引擎(您曾经依赖于 [Docker](https://www.docker.com/?utm_content=inline-mention) )。这就是我今天要向你们展示的。

## 要求

要部署集群，您需要至少两个 Ubuntu Server 实例(我在 [Ubuntu Server 22.04](https://releases.ubuntu.com/22.04/) 上演示)和一个拥有 sudo 权限的用户。就是这样。让我们忙起来。

注意:除非另有说明，否则将在所有服务器上执行以下步骤。

## 配置主机名和主机文件

我们要做的第一件事是为我们的服务器配置主机名和主机文件。您会希望在每台机器上都这样做。

要更改机器的主机名，请登录并发出命令:

`sudo hostnamectl set-hostname HOSTNAME`

其中 HOSTNAME 是主机的名称(如 kubecontroller、kubenode1、kubenode2 等。).进行此更改后，注销并重新登录，您应该会看到主机名反映在终端窗口中。

接下来，我们将把主机名映射到主机文件中的 IP 地址。使用以下命令打开文件进行编辑:

`sudo nano /etc/hosts`

在文件的底部，您将添加如下内容(编辑它以反映您的主机名和 IP 地址):

```
192.168.1.13  kubecontroller
192.168.1.14  kubenode1
192.168.1.15  kubenod2

```

保存并关闭文件。

## 安装所需的软件

首先，我们将使用命令安装两个依赖项:

`sudo apt-get install curl apt-transport-https -y`

接下来，我们添加所需的 GPG 键:

`curl -fsSL  https://packages.cloud.google.com/apt/doc/apt-key.gpg|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/k8s.gpg`

我们现在可以使用以下命令添加存储库:

`curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.lis`

用以下内容更新 apt:

`sudo apt update`

安装 Kubernetes 所需的部件，包括:

`sudo apt-get install wget curl vim git kubelet kubeadm kubectl -y`

最后，标记 kublet、kubeadm 和 kubectl，以便 apt 将来不会升级它们:

`sudo apt-mark hold kubelet kubeadm kubectl`

## 禁用交换

Kubernetes 要求在所有服务器上禁用交换。为此，您将首先暂时禁用 swap with

`sudo swapoff -a`

接下来，通过注释掉(添加一个前导#字符)fstab 中的交换行来永久禁用它。打开文件进行编辑，使用:

`sudo nano /etc/fstab`

找到交换行，在它的开头添加一个#号，然后保存/关闭文件。

## 启用必要的内核模块并调整 sysctl

对于我们的下一个技巧，我们将使用以下命令启用必要的内核模块:

`sudo modprobe overlay`

`sudo modprobe br_netfilter`

接下来，我们用命令改变 sysctl:

```
sudo tee  /etc/sysctl.d/kubernetes.conf&lt;&lt;EOF
net.bridge.bridge-nf-call-ip6tables  =  1
net.bridge.bridge-nf-call-iptables  =  1
net.ipv4.ip_forward  =  1
EOF

```

最后，用以下代码重新加载 sysctl:

`sudo sysctl --system`

## 安装容器 d

现在是时候安装我们的运行时引擎了。在此之前，我们必须首先用
配置内核模块的持久加载

```
sudo tee  /etc/modules-load.d/k8s.conf  &lt;&lt;EOF
overlay
br_netfilter
EOF

```

然后，我们安装一些依赖项，包括:

`sudo apt install -y curl gnupg2 software-properties-common apt-transport-https ca-certificates`

Containerd 是从官方 Docker repo 中安装的。使用以下命令添加所需的 GPG 键:

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

使用以下内容添加 Docker 存储库:

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

现在是时候安装 containerd 了:

`sudo apt update`

`sudo apt-get install containerd.io -y`

我们现在将使用以下命令配置 containerd:

`sudo su -`

`mkdir -p /etc/containerd`

`containerd config default>/etc/containerd/config.toml`

使用以下命令重新启动并启用 containerd:

`sudo systemctl restart containerd`

`sudo systemctl enable containerd`

## 初始化控制平面和集群

要初始化控制平面，我们必须首先启用 kublet，在引导时使用:

`sudo systemctl enable kubelet`

使用命令下拉所需的容器图像:

`sudo kubeadm config images pull`

最后，我们可以使用(仅在控制器上完成)初始化集群:

`sudo kubeadm init --pod-network-cidr=10.244.0.0/16`

一旦集群被初始化，它将报告 join 命令供您在每个节点上运行。但是，在加入节点之前，您必须先进行快速配置。为此，发出以下命令:

`mkdir -p $HOME/.kube`

`sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`

`sudo chown $(id -u):$(id -g) $HOME/.kube/config`

完成这些配置后，将 join 命令复制并粘贴到您的节点上——viola！—您有一个运行在 Ubuntu 服务器上的 Kubernetes 集群。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>