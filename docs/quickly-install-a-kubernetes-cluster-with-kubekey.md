# 使用 KubeKey 快速安装 Kubernetes 集群

> 原文：<https://thenewstack.io/quickly-install-a-kubernetes-cluster-with-kubekey/>

Kubernetes 可能是一个真正的挑战，以启动和运行正常。当您真的希望快速完成时尤其如此，这样您就可以创建一个测试或开发环境，或者只是熟悉它是如何工作的。您可能没有时间在每次需要的时候启动一个[多节点 Kubernetes 集群](https://thenewstack.io/what-does-it-take-to-manage-hundreds-of-kubernetes-clusters/)。在这种情况下，您总是可以求助于 [KubeKey](https://github.com/kubesphere/kubekey) ，这使得为开发/测试目的而加速 Kubernetes 部署变得非常容易。

但是，不要认为以这种方式使用 KubeKey 是大规模部署应用和服务的一种方式。我将向您展示的内容主要用于测试和开发目的，所以不要把它视为生产就绪型应用或服务的解决方案。

为了做到这一点，你需要一个 Ubuntu Server 20.04(或更新版本)的运行实例和一个拥有`sudo`权限的用户。您可能还想让您的 Ubuntu Server 实例拥有一个完整的桌面环境(这样您就可以部署 Kubernetes Dashboard——我也将向您展示如何做)。

说完这些，我们开始工作吧。

## 安装 Docker

我们需要做的第一件事是安装 Docker。我们将安装 Docker 的社区版，而不是安装标准存储库中的 Docker 版本。

首先，让我们安装必要的依赖项。登录到您的服务器，发出命令:

`sudo apt-get install apt-transport-https ca-certificates curl software-properties-common -y`

接下来，添加官方的 Docker GPG 键:

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

使用以下命令添加 Docker 存储库:

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu  $(lsb_release -cs)  stable"`

更新 apt 并安装 Docker:

`sudo apt-get update`

`sudo apt-get install docker-ce -y`

使用以下命令启动并启用 Docker 服务:

`sudo systemctl enable --now docker`

通过以下方式将您的用户添加到 docker 组:

`sudo usermod -aG docker $USER`

确保更改在以下情况下生效:

`newgrp docker`

## 安装 KubeKey

在我们下载 KubeKey 之前，还有另一个依赖项需要处理，可以用命令来完成:

`sudo apt-get install conntrack -y`

下载 KubeKey 二进制文件:

`curl -sfL https://get-kk.kubesphere.io | VERSION=v1.2.1 sh -`

文件下载后，使用以下命令使其可执行:

`chmod u+x kk`

让我们通过将文件复制到 */user/local/bin* 目录，使 kk 成为可执行文件，这样它可以从任何目录运行。使用以下工具完成:

`sudo cp kk /usr/local/bin`

使用以下工具验证安装:

`kk -h`

如果您看到打印出来的帮助信息，那么 kk 可执行文件就准备好了。

## 部署集群

我们现在可以部署具有以下功能的群集:

`sudo kk create cluster`

不幸的是，您必须使用 sudo 权限来运行它。这就是为什么我认为 KubeKey 的最佳用例仅用于开发/测试/教育目的的原因之一。

这个过程将需要一些时间，因为它必须下载一些二进制文件和其他位来使其工作。完成后，您将回到终端窗口，并准备好继续。

现在，您应该能够使用以下命令来验证 kubectl 已经安装:

`kubectl --help`

这一次，您应该会看到 kubectl 命令的帮助信息。

## 部署 Kubernetes 仪表板

让我们更进一步。这不是必需的，但它将有助于使事情变得更容易(要更详细地了解如何部署仪表板，请查看" [Deploy Microk8s 和 Kubernetes Dashboard for K98s Development](https://thenewstack.io/deploy-microk8s-and-the-kubernetes-dashboard-for-k8s-development/)")。使用以下命令部署 Kubernetes 仪表板:

`sudo kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml`

部署控制面板后，您需要找到集群的 IP 地址，这可以通过以下命令完成:

`sudo kubectl get svc -n kubernetes-dashboard`

您应该会看到 kubernetes-dashboard 与集群 IP 地址和端口号一起以如下形式列出:

`kubernetes-dashboard        NodePort    10.233.33.37    <none>        443:31693/TCP   57m`

您可能希望通过 NodePort 而不是 ClusterIP 来公开仪表板。为此，发出以下命令:

`sudo kubectl edit svc kubernetes-dashboard -o yaml -n kubernetes-dashboard`

这将在 vi 编辑器中打开配置文件。你必须首先键入 *i* 才能进入交互模式。然后向下滚动，直到您看到:

`type: ClusterIP`

将其更改为:

`type: NodePort`

点击 escape 退出交互模式，然后输入 *:wq* 保存并关闭文件。接下来，您必须像这样运行 kubectl 代理命令:

`sudo kubectl proxy`

在代理运行时，打开一个 web 浏览器，并将其指向从*sudo ku bectl get SVC-n kubernetes-dashboard*命令的结果中列出的 IP 地址和端口号。您将看到登录屏幕，在这里您需要一个访问令牌。要检索令牌，请发出以下命令:

`sudo kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')`

这会打印出一长串随机字符。将该字符串复制并粘贴到令牌字段中，然后就可以访问 Kubernetes 仪表板了。

这就是如何快速启动 Kubernetes 开发环境，而不必经历部署整个集群的所有麻烦。这还不能用于生产，但是这是了解 Kubernetes 甚至为该平台开发的一个很好的方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>