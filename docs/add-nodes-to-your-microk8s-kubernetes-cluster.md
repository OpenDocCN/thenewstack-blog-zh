# 向您的 MicroK8s Kubernetes 集群添加节点

> 原文：<https://thenewstack.io/add-nodes-to-your-microk8s-kubernetes-cluster/>

Kubernetes 是[硬](https://thenewstack.io/nsa-on-how-to-harden-kubernetes/)。这是无可避免的。有如此多的移动部件，所有这些部件都必须相互连接，并且[有复杂的清单](https://thenewstack.io/aws-cdk8s-a-dev-friendly-alternative-to-yaml-for-managing-kubernetes-clusters/)，这项技术可能会令人望而生畏。如果你投入得太快，你可能会不知所措，甚至不知道该走哪条路

这就是为什么慢慢地、一步一步地接近 Kubernetes 很重要。在这个 Kubernetes 101 系列中，我们之前已经介绍过将 [MicroK8s](https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-with-microk8s/) 部署到一台由 [Rocky Linux](https://thenewstack.io/centos-creator-gregory-kurtzer-discusses-his-new-distro-rocky-linux/) 驱动的服务器上。

这一次，我们将向我们的第一台 Kubernetes 机器添加节点来创建一个集群。这些节点都是由原机器管理的，我称之为控制器。您将希望确保遵循“ [Kubernetes 101:在 Rocky Linux](https://thenewstack.io/wp-admin/post.php?post=22693941&action=edit) 上安装 Kubernetes 的最简单的方法”教程，并确保在集群所需的所有节点上这样做。一旦在每台机器上完成了这些步骤，就可以开始向群集中添加节点了。

对于我的集群，我将有三个节点和一个控制器。IP 地址方案如下所示:

*   kubecontroller
*   192.168.1.101 库贝诺德 1
*   kubenode2
*   192.168.1.103 库贝诺德 3

更改每个节点的主机名也很重要。记住，在 Linux 上更改主机名的命令是:

```
sudo hostnamectl set-hostname NAME

```

其中 NAME 是您要为机器指定的主机名。在我们的例子中，这些主机名将是:

*   kubecontroller
*   kubenode1
*   kubenode2
*   kubenode3

## 编辑节点上的主机文件

我们要做的第一件事是编辑每台机器上的 hosts 文件。用
打开文件

在文件的底部，我们将添加:

```
192.168.1.100  kubecontroller
192.168.1.101  kubenode1
192.168.1.102  kubenode2
192.168.1.103  kubenode3

```

使用[Ctrl]+[X]快捷键保存并关闭文件。

## 打开必要的防火墙端口

为了使节点能够与控制器通信，您必须打开必要的防火墙端口。这在控制器上用命令完成:

```
sudo firewall-cmd  --add-port={25000/tcp,16443/tcp,12379/tcp,10250/tcp,10255/tcp,10257/tcp,10259/tcp}  --permanent
sudo firewall-cmd  --reload

```

在每个节点上，您还需要使用以下命令打开特定的防火墙端口:

```
sudo firewall-cmd  --add-port={25000/tcp,10250/tcp,10255/tcp}  --permanent
sudo firewall-cmd  --reload

```

您可能还需要使用命令
再添加一个端口(在所有机器上)

```
sudo firewall-cmd  --add-port=19001/tcp  --permanent
sudo firewall-cmd  --reload

```

## 生成添加节点命令

不过，在控制器上，您必须运行一个命令，然后生成所需的 add 命令。那个命令是:

输出将包括要在每个要加入的节点上运行的完整命令。这个命令看起来会像这样:

```
microk8s join  192.168.1.100:25000/87636eo7d6r80787576t37o08ft2f2ac/979uj65e74b6

```

在所有节点上运行 join 命令后，给它几分钟时间来确保一切正常运行。然后，您可以使用命令:
从控制器检查节点

```
microk8s kubectl get nodes

```

您应该看到所有三个节点现在都是集群的一部分。

## 让这变得简单一点

如您所见，使用 MicroK8s，您可以通过 microk8s 命令使用 kubectl 命令。这比您可能想要处理的输入要多一点。幸运的是，您可以设置 MicroK8s 使用 kubectl 命令的系统版本。为此，我们首先在 Rocky Linux 上安装 kubectl 命令，如下所示:

```
curl  -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
sudo chmod  +x  kubectl
sudo mv kubectl  /usr/local/bin/

```

接下来，我们生成一个配置文件，并将其保存在~/中。kube/用命令:

```
microk8s config  &gt;  ~/.kube/config

```

您现在应该能够使用 kubectl 命令，而不需要键入`microk8s`。例如，要查看新添加的节点，命令应该是:

你可以不走这条路线。如果你不介意额外的输入，`microk8s kubectl`是一个完美的选择。

## 从集群中删除节点

万一您需要从集群中删除一个节点，您只需登录到该节点，并发出命令:

## 稍后添加更多节点

你不仅仅局限于你这一轮添加的节点。很久以前，我只是将 join 命令保存到一个文件中，并在需要时随时复制/粘贴它。这不再有效，因为 join 令牌是时间敏感的。尽管如此，您可以根据需要添加和删除节点，以增加或减少集群的大小。任何时候你需要加入一个新的节点，你所要做的就是运行 join 命令，就像这样:

您将收到在初始节点上运行的相同的 join 命令，只是使用了不同的 join 令牌。如果您尝试像前面一样重新运行相同的 join 命令，您将得到一个无效的令牌命令。所以一定要记住 add-node 命令，以便以后可以加入更多的节点。

这就是通过 MicroK8s 将节点连接到控制器来创建第一个 Kubernetes 集群的全部内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>