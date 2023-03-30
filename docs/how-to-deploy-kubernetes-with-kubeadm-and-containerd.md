# 如何用 Kubeadm 和 containerd 部署 Kubernetes

> 原文：<https://thenewstack.io/how-to-deploy-kubernetes-with-kubeadm-and-containerd/>

很难说出口，但是 Kubernetes 很有挑战性。尽管在裸机上部署一个 [Kubernetes](https://thenewstack.io/category/kubernetes/) 集群曾经相当简单(部分归功于 Docker)，但现在已经不像以前那么简单了。让事情变得更复杂的是，有几乎无穷无尽的方法可以让平台运行起来。

你选择哪一个？这个问题的答案取决于你用 Kubernetes 做什么，你计划部署它的平台，以及你选择的操作系统。

部署 Kubernetes 集群的一种方法是使用 *[kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/)* (一种帮助快速跟踪部署的工具)和 *[containerd](https://containerd.io/)* (一种容器运行时引擎)。这就是我在这里要说明的方法。完成这个过程，您将得到一个工作的 Kubernetes 集群。我将把它限制为只有一个主节点和一个节点(为了简单起见)，但是您可以根据需要部署任意多的节点。

为此，您至少需要两台机器(一台用于主节点，一台用于节点)。我将在我选择的服务器 Ubuntu 20.04 上进行演示。每台机器应该至少有 2GB 的内存，主机器应该至少有两个 CPU。

## 设置主机名和主机文件

我们要做的第一件事是为每台机器设置主机名。首先，登录到您的主机并发出命令:

`sudo hostnamectl set-hostname kubemaster`

接下来，使用以下命令编辑主机文件:

`sudo nano /etc/hosts`

在该文件中，在底部添加以下内容:

```
kubemaster IP_ADDRESS
kubenode1 IP_ADDRESS

```

其中 IP 地址是每台机器的 IP 地址。保存并关闭文件。

登录到节点计算机，并使用以下命令设置主机名:

`sudo hostnamectl set-hostname kubenode1`

以与主服务器相同的方式编辑/etc/hosts 文件(使用相同的设置)。

## 安装必要的软件

在两台机器上，您都需要安装一些软件。首先，登录到主服务器，使用以下命令运行更新/升级:

`sudo apt update`

`sudo apt upgrade -y`

如果内核升级，请确保重新启动机器。

升级完成后，安装第一个依赖项，包括:

`sudo apt install curl apt-transport-https -y`

接下来，使用命令添加必要的 GPG 键:

`curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -`

使用以下内容添加 Kubernetes 库:

`echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list`

更新 apt:

`sudo apt update`

使用命令安装所需的软件:

`sudo apt -y install vim git curl wget kubelet kubeadm kubectl`

最后，将 *kubelet* 、 *kubeadm* 和 *kubectl* 置于待命状态，其中:

`sudo apt-mark hold kubelet kubeadm kubectl`

使用以下命令启动并启用 *kubelet* 服务:

`sudo systemctl enable --now kubelet`

在 *kubenode1* 上重复该过程。

## 禁用交换

接下来，我们需要在 kubemaster 和 *kubenode1* 上禁用 swap。用以下命令打开 *fstab* 文件进行编辑:

`sudo nano /etc/fstab`

在该文件中，注释掉该行:

```
/swap.img        none     swap     sw        0          0

```

这一行现在应该类似于:

```
#/swap.img      none    swap    sw      0       0

```

保存并关闭文件。您可以重新启动以禁用交换，或者只需发出以下命令来完成作业:

`sudo swapoff -a`

## 启用内核模块并更改 sysctl 中的设置

接下来，我们需要启用两个内核模块，并给 *sysctl* 添加一些设置。首先，使用以下命令启用覆盖和 *br_netflilter* 模块:

`sudo modprobe overlay`

`sudo modprobe br_netfilter`

使用以下命令打开必要的文件，更改 *sysctl* 设置:

`sudo nano /etc/sysctl.d/kubernetes.conf`

寻找下面的行，并确保它们的设置如下所示:

```
net.bridge.bridge-nf-call-ip6tables  =  1
net.bridge.bridge-nf-call-iptables  =  1
net.ipv4.ip_forward  =  1

```

保存并关闭文件。用以下内容重新加载 sysctl:

`sudo sysctl --system`

确保在 kubemaster 和 *kubenode1* 上注意上述事项。

## 安装容器 d

我们现在将安装*容器和*运行时引擎。这在两台机器上都完成了。首先要做的是配置必要的*容器和*模块的持久加载。这是通过下面的命令完成的(您应该照原样复制并粘贴):

```
sudo tee  /etc/modules-load.d/containerd.conf  &lt;&lt;EOF
overlay
br_netfilter
EOF

```

我们再次重新加载配置:

`sudo sysctl --system`

安装必要的依赖项:

`sudo apt install curl gnupg2 software-properties-common apt-transport-https ca-certificates -y`

使用以下内容添加 GPG 键:

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

使用以下内容添加所需的存储库:

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

使用命令:+-安装*容器 id*

`sudo apt update`

`sudo apt install containerd.io -y`

通过以下方式更改为 root 用户:

`sudo su -`

使用以下内容为*容器 id*创建一个新目录:

`mkdir -p /etc/containerd`

使用以下内容生成配置文件:

`containerd config default>/etc/containerd/config.toml`

使用以下命令退出 root 用户:

`exit`

使用命令重启*容器*:

`sudo systemctl restart containerd`

启用 *containerd* 在启动时运行:

`sudo systemctl enable containerd`

最后，您需要创建一个新目录来存放配置文件，并赋予它适当的权限，这是通过以下命令完成的:

`mkdir -p $HOME/.kube`

`sudo cp -f /etc/kubernetes/admin.conf $HOME/.kube/config`

`sudo chown $(id -u):$(id -g) $HOME/.kube/config`

## 初始化主节点

转到 *kubemaster* 并下拉必要的容器图像:

`sudo kubeadm config images pull`

现在，使用 *kubemaster* IP 地址初始化主节点:

`sudo kubeadm init --pod-network-cidr=IP/16`

其中 IP 是 *kubemaster* 的 IP 地址。当初始化命令时，你会看到这样的内容:

`sudo kubeadm join 192.168.1.100:6443 --token 0dt0kt.h4i71m34tbfqup83 --discovery-token-ca-cert-hash sha256:c74be4fd295c172ba0fd6bdae870a834b051327c45fa46cc9d738e74f5de82a0`

上面的命令是您随后在 *kubenode1* 上运行以将其加入集群的命令。加入应该很快发生。一旦完成，返回 kubemaster 并发出命令:

`kubectl get nodes`

您应该会看到主节点和节点都列出来了。恭喜，您刚刚部署了一个 Kubernetes 集群，并且可以将它用于开发目的。

我不建议将它用于生产，因为它太小而无法扩展，并且我们没有考虑安全性(比如使用 SSL 证书)。但是这是练习部署集群的好方法，也是 Kubernetes 开发的可行入门。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>