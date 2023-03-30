# 安装 Calico 以增强 Kubernetes 的内置网络功能

> 原文：<https://thenewstack.io/install-calico-to-enhance-kubernetes-built-in-networking-capability/>

来自网络软件提供商 Tigera 的 Calico 是 Kubernetes 的第三方插件，旨在使完整的网络连接更加灵活和简单。Kubernetes 提供了现成的 NetworkPolicy API 来管理集群中的网络策略。许多 Kubernetes 管理员发现的问题(特别是那些新技术的管理员)是，网络可能很快变成一个相当复杂的 YAML 配置的混乱局面，您必须正确配置流量入口和出口，否则 Kubernetes 对象(如 pod 和容器)之间的通信可能会很困难。

这就是像[印花布](https://docs.projectcalico.org/about/about-calico)发挥作用的地方。因为不是每个 Kubernetes 网络插件都支持 NetworkPolicy API，所以选择一个能够满足您需求的插件是很重要的。例如，最流行的 Kubernetes 网络插件是[法兰绒](https://github.com/flannel-io/flannel)，它不能配置网络策略。使用 Calico，您可以显著增强 Kubernetes 网络配置。

例如，默认网络策略中的功能限制如下:

*   策略仅限于单个环境，并且仅适用于标有标签的 pod。
*   您只能将规则应用于单元、环境或子网。
*   规则只能包含协议、数字端口或命名端口。

当您添加 Calico 插件时，这些功能会扩展如下:

*   策略可以应用于 pod、容器、虚拟机或界面。
*   规则可以包含特定的操作(如限制、权限或日志记录)。
*   规则可以包含端口、端口范围、协议、HTTP/ICMP 属性、IP、子网或节点选择器(如主机或环境)。
*   可以通过 DNAT 设置和策略来控制流量。

Calico 还支持多个数据平面，这允许您选择最适合您项目需求的技术(包括纯 Linux eBPF 数据平面)。其他功能包括:

*   高性能。
*   巨大的可扩展性。
*   与当前非 K8s 工作负载的互操作性。
*   全面的 Kubernetes 网络政策支持。
*   非常活跃的开发社区。

为了让 Calico 更有吸引力，它可以在所有流行的云平台上使用，如亚马逊网络服务、微软 Azure、谷歌云平台、IBM、Red Hat OpenShift 和 SUSE 的 Rancher。

或者，如果您愿意，您可以在数据中心的裸机上部署 Calico。

让我们看一下在小型 Kubernetes 集群上安装 Calico 的过程。我们将在一个运行在 Ubuntu Server 20.04 实例上的集群上进行演示，但是这个过程应该是相同的，与您的平台无关。只要您可以访问 kubectl，就应该可以使用了。

第一种方法假设您已经启动并运行了 Kubernetes 集群，而第二种方法从裸机 Ubuntu 服务器实例开始。

## 安装印花棉布

首先，我将向您展示如何为少量节点(50 个或更少)安装 Calico。首先，使用命令下载清单:

`curl https://docs.projectcalico.org/manifests/calico-typha.yaml -o calico.yaml`

文件下载完成后，使用以下命令应用它:

`kubectl apply -f calico.yaml`

当该命令完成时，您应该看到已经创建了许多新的对象/服务，例如:

`clusterrolebinding.rbac.authorization.k8s.io/calico-kube-controllers created`

`clusterrole.rbac.authorization.k8s.io/calico-node created`

`clusterrolebinding.rbac.authorization.k8s.io/calico-node created`

`daemonset.apps/calico-node created`

`serviceaccount/calico-node created`

`deployment.apps/calico-kube-controllers created`

`serviceaccount/calico-kube-controllers created`

`poddisruptionbudget.policy/calico-kube-controllers created`

如果您需要将 Calico 部署到超过 50 个节点的集群，您需要首先编辑 YAML 文件。使用命令打开文件:

`nano calico.yaml`

在该文件中，查找行:

要配置该线路，您需要为每 200 个节点设置一个副本。因此，如果您有 600 个节点，您应该将其设置为:

需要记住的一点是，您应该设置不超过 20 个副本，并且(在生产中)您应该至少使用三个副本。

下一步是安装 calicoctl 命令。使用以下命令下载可执行文件:

`curl -o calicoctl -O -L "https://github.com/projectcalico/calicoctl/releases/download/v3.19.1/calicoctl"`

在可执行文件下载到您的系统之后，使用以下命令将其移动到您的路径中的一个目录，例如/usr/local/bin/:

`sudo mv calicoctl /usr/local/bin/`

接下来，使用以下命令授予文件可执行权限:

`sudo chmod +x /usr/local/bin/calicoctl`

通过运行以下命令来验证安装:

`calicoctl -h`

您应该会看到如何使用该命令的列表。

## 安装在裸机上

我们来看看如何在 Ubuntu Server 20.04 的裸机实例上安装 Calico。以下是步骤:

**步骤 1:** 使用以下命令更新 apt 并安装必要的依赖项:

`sudo apt-get update`

`sudo apt-get install -y apt-transport-https ca-certificates curl`

**第二步:**使用以下命令下载谷歌云 GPG 密钥:

`sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg`

**步骤 3:** 使用以下命令添加 Kubernetes 存储库:

`echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list`

**步骤 4:** 使用以下命令更新 apt 并安装 kubeadm/kubectl:

`sudo apt-get update`

`sudo apt-get install -y kubelet kubeadm kubectl`

`sudo apt-mark hold kubelet kubeadm kubectl`

**第 5 步:**使用以下命令安装 Docker:

`sudo apt-get install docker.io -y`

**步骤 6:** 使用以下命令将您的用户添加到 docker 组:

`sudo usermod -aG docker $USER`

注销并重新登录。

**步骤 6:** 通过使用以下命令打开 fstab 文件来禁用交换:

`sudo nano /etc/fstab`

查找以
开头的行

将该行改为以:
开头

保存并关闭文件。

发出命令:

`sudo swapoff -a`

**第 7 步:**使用以下命令初始化 Kubernetes:

`sudo kubeadm init --pod-network-cidr=SERVER/16`

其中 SERVER 是托管服务器的 IP 地址。

**步骤 8:** 创建必要的目录，并使用以下命令复制配置文件:

`mkdir -p $HOME/.kube`

`sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`

`sudo chown $(id -u):$(id -g) $HOME/.kube/config`

**步骤 9:** 使用以下命令安装 Tigera Calico 操作器:

`kubectl create -f https://docs.projectcalico.org/manifests/tigera-operator.yaml`

使用以下命令下载必要的自定义 Calico 资源 YAML:

`wget https://docs.projectcalico.org/manifests/custom-resources.yaml`

打开该文件，并使用以下命令检查是否需要任何必要的定制:

`nano custom-resources.yaml`

自定义 YAML 后，保存并关闭文件，然后使用以下命令应用它:

`kubectl create -f custom-resources.yaml`

等待几分钟，使用以下命令确认所有 Calico pods 都在运行:

`watch kubectl get pods -n calico-system`

当所有的 pod 都处于运行状态时，您需要使用以下命令删除主服务器上的污点:

`kubectl taint nodes --all node-role.kubernetes.io/master-`

如果您发出以下命令:

`kubectl get nodes -o wide`

您应该看到您的 Kubernetes 集群现在已经启动并运行了 Calico。此时，您应该查看官方 Calico 网络文档,了解如何充分利用您的新部署。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>