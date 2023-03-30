# Kubernetes 101:在 Rocky Linux 上安装 Kubernetes

> 原文：<https://thenewstack.io/kubernetes-101-install-kubernetes-on-rocky-linux/>

Kubernetes 是一个非常强大的容器编排器，它可以大规模地部署和管理容器化的应用程序，比市场上任何其他工具都更加强大和灵活。

事情是这样的，Kubernetes 很难做。真的很难。有了这么多可移动的部分，开发一个部署到 Kubernetes 集群的应用程序或服务可能是一个巨大的挑战。做好这件事需要很多技巧和耐心。

考虑到 Kubernetes 容器开发本身就是一个如此大的挑战，您可能不想为了让事情正常运行而处理更多的障碍。猜猜看，在 Linux 服务器上安装 Kubernetes 也不是一件容易的事情。

曾几何时，这要简单得多，感谢 Ubuntu 和 Docker 容器运行时这样的发行版。然而， [Kubernetes](https://kubernetes.io/) 团队决定[从 Kubernetes](https://thenewstack.io/docker-versus-kubernetes-start-here/) 剥离 Docker 支持，这使得在一些操作系统上使用它变得更具挑战性。Kubernetes 是[云原生计算基金会的一个开源项目。](https://cncf.io/?utm_content=inline-mention)

当然，考虑到这些都是开源的，其他公司也挺身而出，开发了一些应用程序，使得 Kubernetes 的部署和运行变得不那么困难。

一个这样的工具叫做 MicroK8s，它和 Kubernetes 上的其他工具一样强大和灵活(如 OpenShift、Azure Kubernetes 服务、Rancher 和官方的 Google Kubernetes 引擎)。

[Microk8s 更易于部署，](https://thenewstack.io/deploy-microk8s-and-the-kubernetes-dashboard-for-k8s-development/)更安全，占用空间小，并为入口、DNS、仪表板等提供了全面的清单集合。最后，Microk8s 是上游 Kubernetes 的可靠替代品，因此它将无缝地用于您的容器编排。

我想带你看一下在 Rocky Linux 9 上安装 MicroK8s 的过程。为什么是洛基 Linux 9？简单地说，这是一个高性能的以服务器为中心的 Linux 发行版。是的，你可以在像 Ubuntu 这样的操作系统上安装 Microk8s(过程非常相似)，但是我想向你展示如何在一个不包括 Snap out of the box 的发行版上安装。因为…好玩！

我们开始工作吧。

## 你需要什么

为了实现这一点，你需要至少三个 Rocky Linux 9 的实例。这些可以安装在裸机上，作为虚拟机，或者安装在云主机上(比如[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，谷歌云，或者 Azure)。您还需要为每台服务器分配一个静态 IP 地址，并让一个用户拥有 sudo 特权。

是时候让这一切发生了。

## 在 Rocky Linux 上安装 Snap

我们必须做的第一件事是在 Rocky Linux 上安装 Snap。为此，您必须首先使用命令添加 EPEL 存储库:

```
sudo dnf install epel-release  -y

```

完成后，使用
安装 Snap

```
sudo dnf install snapd  -y

```

这应该是您进行备份和运行所需的全部内容。但是，如果您发现无法使用 Snap 成功安装 Microk8s，您可能需要注意以下问题。

创建将启用 Snap classic 支持的符号链接。这是通过命令完成的:

```
sudo ln  -s  /var/lib/snapd/snap  /snap

```

使用命令:
导出快照$路径

```
echo  'export PATH=$PATH:/var/lib/snapd/snap/bin'  |  sudo tee  -a  /etc/profile.d/snap.sh

```

使用
确保系统意识到变化

```
source  /etc/profile.d/snap.sh

```

使用命令启用快照服务:

```
sudo systemctl enable  --now snapd.socket

```

## 更改 SELinux 模式

为了让 Microk8s 正常工作，我们需要将 SELinux 切换到许可模式，这可以通过以下两个命令来完成:

```
sudo setenforce  0
sudo sed  -i  's/^SELINUX=.*/SELINUX=permissive/g'  /etc/selinux/config

```

第一个命令将 SELinux 临时设置为许可模式，第二个命令将其设置为即使在系统重启后也将保持许可模式。

## 安装 Microk8s

我们现在可以用命令安装 micrk 8s:

```
sudo snap install microk8s  --classic

```

然后，我们必须使用命令将我们的用户添加到 microk8s 组；

```
sudo usermod  -aG microk8s  $USER

```

用`*mkdir ~/.kube*`新建一个目录。使用命令
更改`~/.kube`目录的所有权

```
sudo chown  -f  -R  $USER  ~/.kube

```

注销并重新登录，使更改生效。登录后，使用命令
验证安装

输出中唯一重要的一行是:

安装了 MicroK8s 之后，您还可以访问 kubectl 命令。例如，您可以使用
来检查节点的状态

```
microk8s kubectl get nodes

```

## 更改主机名并编辑主机文件

我们现在需要更改控制器的主机名并编辑 hosts 文件，这样我们就可以将集群上所有节点的 IP 地址映射到主机名。首先，我们将使用命令
更改控制器的主机名

```
sudo hostnamectl set-hostname kubecontroller

```

接下来，将主机名映射到`*/etc/hosts*`文件中控制器的 IP 地址。使用命令打开该文件进行编辑:

在文件的底部，您将添加这样一行:

```
192.168.1.184  kubecontroller

```

保存并关闭文件。

至此，您已经有了一个 Microk8s 控制器，可以开始处理节点了。下周，我们将学习如何创建节点并将其添加到控制器中，以获得更好的性能和高可用性。是的，您可以使用单节点 Microk8s 部署，但是它不能很好地扩展。

在此之前，请尽情享受单节点 Kubernetes 集群。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>