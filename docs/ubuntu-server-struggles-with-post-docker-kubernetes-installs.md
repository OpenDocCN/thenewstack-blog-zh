# Ubuntu 服务器在 Docker Kubernetes 安装后苦苦挣扎

> 原文：<https://thenewstack.io/ubuntu-server-struggles-with-post-docker-kubernetes-installs/>

我对某人有意见。老实说，我不知道该对谁发火，但是现在使用 Ubuntu Server 作为 Kubernetes 的基础有一个很大的问题。

在过去的几天里，我一次又一次地试图让 [Kubernetes](https://kubernetes.io/) 在 [Ubuntu Server 22.04](https://ubuntu.com/engage/ubuntu-server-22-04-LTS) 上运行，无论我尝试了多少次，都失败了。现在，我可以毫无问题地将 Kubernetes 安装到 Ubuntu 服务器上，就像我以前多次做的那样。唯一的区别是现在，我不得不使用类似于 [containerd](https://containerd.io/) 的运行时，而不是使用 [Docker](https://www.docker.com/?utm_content=inline-mention) 。然而，当尝试初始化集群时，我(每次)都遇到错误:

```
[kubelet-check]  Initial timeout of  40s  passed.

Unfortunately,  an error has occurred:
    timed out waiting for the condition
This error is likely caused by:
    -  The kubelet is not running
    -  The kubelet is unhealthy due to  a  misconfiguration of the node in some way  (required cgroups disabled)

```

不管我是全新安装还是已经完成了 *sudo kubeadm 复位*，它都会超时并且永远不会初始化。我已经尝试了三次(每次都是用 Ubuntu Server 22.04 的新实例)，但都没有成功。

这个问题给我带来了一些希望，即最新版本的 containerd 在 Ubuntu Server 上安装时有问题，但即使在尝试用旧版本的 containerd 进行新的部署后，我还是遇到了同样的问题。

简单地说，我从这个小实验中沮丧地走了出来。Ubuntu Server 22.04 上的 Kubernetes 集群应该是显而易见的。不是的。虽然我可以让单个实例运行良好，甚至用它部署一个应用程序。但是当我想走集群路线的时候，事情变得很糟糕。

## 钻取

关于这个错误有趣的是 kubelet 正在运行。但是，运行时:

`sudo systemctl status kubelet`

我看到这样的错误:

`Aug 04 13:56:19 kubecontroller kubelet[550949]: E0804 13:56:19.613305  550949 kubelet.go:2424] "Error getting node" err="node \"kubecontroller\" not found"`

`Aug 04 13:56:19 kubecontroller kubelet[550949]: E0804 13:56:19.714099  550949 kubelet.go:2424] "Error getting node" err="node \"kubecontroller\" not found"`

`Aug 04 13:56:19 kubecontroller kubelet[550949]: E0804 13:56:19.814923  550949 kubelet.go:2424] "Error getting node" err="node \"kubecontroller\" not found"`

下一个兔子洞与~。/kube/config 文件。即使在重新检查了该文件的权限后，我还是遇到了问题。已修复问题，并使用以下命令重新启动 kubelet:

`sudo systemctl restart kubelet`

你猜怎么着？现在，库伯莱不会开始。

开始拉头发吧！

快速重启系统，看看它是否能清除任何残留的垃圾。机器重启后，我运行了 *init* 命令，这样我就可以查看更多的故障排除信息，如下所示:

`sudo kubeadm init`

你猜怎么着？新错误，例如:

`error execution phase wait-control-plane`

`k8s.io/kubernetes/cmd/kubeadm/app/cmd/phases/workflow.(*Runner).Run.func1    cmd/kubeadm/app/cmd/phases/workflow/runner.go:235`

`k8s.io/kubernetes/cmd/kubeadm/app/cmd/phases/workflow.(*Runner).visitAll    cmd/kubeadm/app/cmd/phases/workflow/runner.go:421`

`k8s.io/kubernetes/cmd/kubeadm/app/cmd/phases/workflow.(*Runner).Run    cmd/kubeadm/app/cmd/phases/workflow/runner.go:207`

`k8s.io/kubernetes/cmd/kubeadm/app/cmd.newCmdInit.func1    cmd/kubeadm/app/cmd/init.go:153`

`k8s.io/kubernetes/vendor/github.com/spf13/cobra.(*Command).execute    vendor/github.com/spf13/cobra/command.go:856`

`k8s.io/kubernetes/vendor/github.com/spf13/cobra.(*Command).ExecuteC    vendor/github.com/spf13/cobra/command.go:974`

`k8s.io/kubernetes/vendor/github.com/spf13/cobra.(*Command).Execute    vendor/github.com/spf13/cobra/command.go:902`

`k8s.io/kubernetes/cmd/kubeadm/app.Run    cmd/kubeadm/app/kubeadm.go:50`

`main.main    cmd/kubeadm/kubeadm.go:25`

`runtime.main    /usr/local/go/src/runtime/proc.go:250`

`runtime.goexit    /usr/local/go/src/runtime/asm_amd64.s:1571`

很明显，那是零帮助。无论我花多少时间和我的朋友谷歌在一起，我都找不到困扰我的问题的答案。

回到绘图板。另一个安装和相同的结果。当然，官方的 Kubernetes 文档绝对没有帮助。

得出什么结论，你能做什么(当 Ubuntu 服务器是你的首选)？

## 都是关于 Docker 的

很久以前，在 Ubuntu 服务器上部署 Kubernetes 集群非常简单，而且很少失败。有什么区别吗？

一句话……Docker。

第二个 Kubernetes 去掉了 Docker 支持，在 Ubuntu 服务器上部署集群成了绝对的噩梦。考虑到这一点，你能做什么？嗯，您总是可以使用以下命令通过 snap 安装 microk8s:

`sudo snap install microk8s --classic --channel=1.24`

当然，众所周知，快照安装可能需要一些时间，而且它的响应速度远不如标准安装。然而……入乡随俗。

安装完成后，使用以下命令将您的用户添加到必要的组中:

`sudo usermod -a -G microk8s $USER`

更改的权限。kube 目录，包含:

`sudo chown -f -R $USER ~/.kube`

注销并重新登录，然后运行命令:

`microk8s status --wait-ready`

一切都在运转。我可以使用以下工具部署 NGINX 应用程序:

`microk8s kubectl create deployment nginx --image=nginx`

但这不是一个集群。啊，但是 microk8s 已经掩护你了。在控制器节点上，发出命令:

`microk8s add-node`

您将得到一个 join 命令，可以在任何其他安装了 microk8s 的机器上运行，如下所示:

`microk8s join 192.168.1.43:25000/bad12d3d8966b646442087d6a1edde436/6407f3e21772`

哦，但是我想你也会犯类似这样的错误:

`*Contacting cluster at 192.168.1.43*` 

 *`*Connection failed. Invalid token (500).*`

重新启动两台机器，使用*–skip-verify*命令再次运行 add-node 命令，但没有骰子。

确保为两台机器设置主机名，这些主机名映射到/etc/hosts 中，并仔细检查两台机器上的时间是否正确。没有交易。

但是，在两台机器第二次重新启动后，无论出于何种原因，该节点都能够加入控制器。这一过程花费的时间远远超过了预期，但我认为这与使用 snap 版本的服务有关。

在运行了*microk8s ku bectl get nodes*之后，我现在可以看到集群上的两个节点。

万岁。

## 为什么要为难呢？

对那些参与其中的人来说…这应该不会太难。说真的。Kubernetes 已经是一个具有挑战性的平台。为了让启动和运行变得同样困难，没有失败，我马上回到了 Docker Swarm 的简单性。

当然，我可以为我的 Kubernetes 部署迁移到一个基于 RHEL 的服务器上，但是 Ubuntu 服务器已经是我多年的首选了。不要误会我，我不介意 microk8s，但它不会与类似的 [Portainer](https://thenewstack.io/an-introduction-to-portainer-a-gui-for-docker-management/) (这是我对这类事情的首选)一起工作。为此，我必须添加 Portainer 插件:

`microk8s enable community`

`microk8s enable portainer`

杰出…只是不。现在的问题是什么？启用 Portainer 后，会通知您通过 nodeport 访问它，您可以使用以下命令获得地址:

`export NODE_PORT=$(kubectl get --namespace portainer -o jsonpath="{.spec.ports[1].nodePort}" services portainer)`

但是等等… *因为我用的是 microk8s 所以没有安装 kubectl* ！我必须像这样修改命令:

`export NODE_PORT=$(microk8s kubectl get --namespace portainer -o jsonpath="{.spec.ports[1].nodePort}" services portainer)`

然后，您必须运行命令(同样，修改下一个命令以包含 microk8s):

`export NODE_IP=$(microk8s kubectl get nodes --namespace portainer -o jsonpath="{.items[0].status.addresses[0].address}")  echo https://$NODE_IP:$NODE_PORT`

最后一个命令将报告用于访问 Portainer 的地址。

如果成功了，那不是很好吗？它没有。

你猜怎么着？所有这些都来自官方文档(除了添加的命令的 microk8s 部分，它被方便地省略了)。

对于那些负责这些技术的人来说，这并不困难。我意识到 Kubernetes 和 Canonical 之间可能有嫌隙，但当这种嫌隙蔓延到用户空间时，真正的挫败感就会落到管理员和开发人员的头上。

拜托，拜托，拜托，解决这些问题吧，这样那些喜欢 Ubuntu 服务器的人就可以像以前一样轻松地使用他们的 Kubernetes 了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*