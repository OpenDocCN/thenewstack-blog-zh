# 如何在 Red Hat CentOS 8 上安装 Kubernetes 集群

> 原文：<https://thenewstack.io/how-to-install-a-kubernetes-cluster-on-red-hat-centos-8/>

如果你已经从 Red Hat 的 [CentOS 7](https://www.centos.org/download/) 迁移到 [CentOS 8](https://www.centos.org/) ，你可能已经注意到发生了很多变化。这些变化中的许多已经导致管理员以不同的方式处理他们的任务。安装 Kubernetes 就是这种情况。如果您希望在 CentOS 8 上部署 Kubernetes 集群，对操作系统所做的更改将直接影响您。

但是怎么做呢？尽管它们不会改变您部署实际集群的方式，但是为部署准备好一切是完全不同的。

不用担心，我将带您完成在 CentOS 8 上安装 Kubernetes 的过程，这样您就可以继续部署您的集群和管理您的容器。

## 你需要什么

为了成功安装 Kubernetes(并创建一个集群)，您至少需要两台机器。我将在两台 CentOS 8 服务器上进行演示，它们运行在以下 IP 地址上:

*   kube master–10 . 34 . 1 . 139
*   kube node–10 . 34 . 1 . 161

您还需要一个拥有 sudo 特权的用户帐户，并且能够访问 root 用户帐户。

有了这些，让我们开始工作吧。

除非另有说明，否则您将负责主节点和节点上的所有工作。

## 主机名

首先要做的是设置服务器的主机名，然后修改/etc/hosts 文件。首先使用命令设置主机名:

`sudo hostnamectl set-hostname HOSTNAME`

其中 HOSTNAME 是要使用的主机名(例如 kubemaster 或 kubenode)。设置主机名后，注销并重新登录。

接下来，使用命令打开 hosts 文件进行编辑:

`sudo nano /etc/hosts`

在该文件中，在底部添加如下内容(修改以匹配您的主机名和 IP 地址):

```
kubemaster  -  10.34.1.139
kubenode  -  10.34.1.161

```

保存并关闭文件。

## 安装 Docker-CE

目前，Kubernetes 不能与 Podman 一起工作(Podman 现在是 RHEL 和 CentOS 的默认容器引擎)。因此，您需要安装 docker 引擎。在这个过程中有一点诡计。

以下是方法。

首先要做的是使用以下命令安装旧版本的 docker-ce:

`sudo dnf install docker-ce-3:18.09.1-3.el7`

接下来，您需要使用以下命令打开正确的防火墙端口:

`sudo firewall-cmd --permanent --add-port=6443/tcp`

`sudo firewall-cmd --permanent --add-port=2379-2380/tcp`

`sudo firewall-cmd --permanent --add-port=10250/tcp`

`sudo firewall-cmd --permanent --add-port=10251/tcp`

`sudo firewall-cmd --permanent --add-port=10252/tcp`

`sudo firewall-cmd --permanent --add-port=10255/tcp`

`sudo firewall-cmd –reload`

`sudo modprobe br_netfilter`

`sudo echo '1' > /proc/sys/net/bridge/bridge-nf-call-iptables`

使用以下命令启动并启用 Docker 守护程序:

`sudo systemctl enable --now docker`

现在，您可以使用以下命令将您的用户添加到 docker 组:

`sudo usermod -aG docker $USER`

添加用户后，注销并重新登录，这样用户就可以使用 docker 引擎，而不必使用 **sudo** (出于安全目的)。

接下来，使用以下命令安装 containerd.io 包:

`sudo dnf install https://download.docker.com/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm`

完成后，使用以下命令安装 docker-ce 的最新版本:

`sudo dnf install docker-ce`

你可以继续下去了。

## 安装 Kubernetes

现在我们可以在 CentOS 上安装 Kubernetes 了。首先，我们必须使用以下命令创建一个新的存储库文件:

`sudo nano /etc/yum.repos.d/kubernetes.repo`

在该文件中，粘贴以下内容:

```
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg

```

保存并关闭文件。使用以下命令安装必要的 Kubernetes 包:

`sudo dnf install -y kubelet kubeadm kubectl --disableexcludes=kubernetes`

使用以下命令启动并启用服务:

`sudo systemctl enable --now kubelet`

现在，我们将不得不 *su* 到 root 用户，然后使用以下命令创建一个新文件(以帮助配置 iptables):

`nano /etc/sysctl.d/k8s.conf`

在该文件中，粘贴以下内容:

```
net.bridge.bridge-nf-call-ip6tables  =  1
net.bridge.bridge-nf-call-iptables  =  1

```

保存并关闭文件。使用以下命令加载新配置:

`sysctl --system`

用*退出*命令退出根用户。

## 禁用交换

接下来，我们必须禁用交换。使用以下命令执行此操作:

`sudo swapoff -a`

这将暂时禁用交换。要永久禁用交换(以便在重新启动时不会重新启用)，请使用以下命令打开 fstab 进行编辑:

`sudo nano /etc/fstab`

在该文件中，注释掉(在行首添加#字符)以下列内容开头的行:

`/dev/mapper/cl-swap`

保存并关闭文件。

## 创建守护程序文件

最后，我们必须创建一个守护文件。首先发出命令 *su* ，然后用命令创建新的守护程序文件:

*`nano /etc/docker/daemon.json`*

在该文件中，粘贴以下内容:

```
{
  "exec-opts":  ["native.cgroupdriver=systemd"],
  "log-driver":  "json-file",
  "log-opts":  {
     "max-size":  "100m"
  },
  "storage-driver":  "overlay2",
  "storage-opts":  [
     "overlay2.override_kernel_check=true"
  ]
}

```

保存并关闭文件。

使用以下命令创建新的 **systemd** 目录:

`mkdir -p /etc/systemd/system/docker.service.d`

使用命令重新加载并重启 Docker 守护进程:

```
systemctl daemon-reload
systemctl restart docker

```

用**退出**命令退出根用户。

## 初始化集群

这只能在 Kubernetes master 上完成。要初始化集群，请发出以下命令:

`sudo kubeadm init`

上述操作将初始化集群，并向您报告用于将节点加入主节点的必要命令。

这就是当前在 CentOS 8 上安装 Kubernetes 和初始化集群的方法。目前，还不知道一旦波德曼进化成熟，这种情况是否会改变。然而，在那之前，这是我成功使用的方法之一。尝试一下，看看它是否会成为您在 CentOS 8 上启动和运行 Kubernetes 的必经之路。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>