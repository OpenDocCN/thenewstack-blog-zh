# 在 Ubuntu Linux 上安装 Minikube 以方便 Kubernetes 开发

> 原文：<https://thenewstack.io/install-minikube-on-ubuntu-linux-for-easy-kubernetes-development/>

我早就说过 Kubernetes 远非用户友好。不仅将 pod 和服务部署到集群是一项挑战，而且简单地启动和运行集群也是一场真正的噩梦。

幸运的是，有一些应用程序可以使 Kubernetes 友好环境的部署相对简单。我已经谈过[通过 MicroK8s](https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-with-microk8s/) 部署 Kubernetes 集群，这一次我们将用一个叫做 [Minikube](https://minikube.sigs.k8s.io/docs/start/) 的工具做类似的事情。Minikube 的目的是创建一个用于开发目的的本地 Kubernetes 集群。这意味着您不会在这个平台上大规模部署应用和服务。相反，Minikube 是开始学习如何使用 Kubernetes 的好方法。

您可以在 Linux、macOS 和 Windows 上部署 Minikube。鉴于 Linux 是我选择的操作系统，我将在 Ubuntu Linux 上演示。通过本教程，您应该能够在不到五分钟的时间内启动并运行 Kubernetes 环境。

准备好了吗？让我们忙起来。

## 要求

要做到这一点，你需要一个基于 Ubuntu 的 Linux 发行版的运行实例和一个拥有 *sudo* 特权的用户。Minikube 的最低要求是:

*   两个或更多 CPU
*   2GB 的可用内存
*   20GB 的可用磁盘空间

满足这些要求后，就该安装了。

## 安装 Docker CE

与普通的 Kubernetes 不同，Minikube 依赖于 Docker。因此，在 Minikube 运行之前，您必须首先安装 Docker 运行时。以下是方法。

第一件要做的事情(在你登录到你的 Ubuntu 实例之后)是用命令添加官方的 Docker GPG 键:

```
curl  -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

```

接下来，添加 Docker 存储库:

```
echo  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"  |  sudo tee  /etc/apt/sources.list.d/docker.list  &gt;  /dev/null

```

使用以下命令安装必要的依赖项:

```
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release  -y

```

用这两条命令安装最新版本的 Docker 引擎:

```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io  -y

```

最后，使用命令将您的用户添加到 docker 组:

```
sudo usermod  -aG docker  $USER

```

注销并重新登录，以使更改生效。

Docker 现已安装。

## 安装 Minikube

使用命令下载最新的 Minikube 二进制文件:

```
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

```

使用命令将文件复制到/usr/local/bin 目录:

```
sudo cp minikube-linux-amd64  /usr/local/bin/minikube

```

使用
赋予 Minikube 可执行文件适当的权限

```
sudo chmod  +x  /usr/local/bin/minikube

```

接下来，我们需要安装 kubectl 命令行实用程序。使用
下载二进制可执行文件

```
curl  -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

```

用
赋予新文件可执行权限

用
命令将文件移动到 */usr/local/bin*

```
sudo mv kubectl  /usr/local/bin/

```

您现在可以使用命令启动 Minikube:

```
minikube start  --driver=docker

```

命令完成后，您可以使用命令来验证它是否正常运行:

输出如下所示:

```
minikube
type:  Control Plane
host:  Running
kubelet:  Running
apiserver:  Running
kubeconfig:  Configured

```

## 通过 Minikube 使用 kubectl

准备好 Minikube 后，您现在可以开始玩 Kubernetes 了。例如，您可以使用命令检查集群的状态:

该命令的输出如下所示:

```
Kubernetes control plane is running at https://192.168.49.2:8443
CoreDNS is running at https://192.168.49.2:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

```

要进一步调试和诊断集群问题，请使用' *kubectl cluster-info dump*

使用命令
检查节点的状态

```
NAME           STATUS     ROLES                 AGE     VERSION
minikube     Ready      control-plane     16m     v1.25.3

```

## 安装附加组件

Minkube 还包括许多扩展特性集的附加组件，如 ingress、metrics server 和 dashboard。要找出可用的附加组件，发出命令:

假设您想要添加 Dashboard 附加组件，这可以通过命令来实现:

```
minikube addons enable dashboard

```

该命令的输出将包括用于访问新仪表板的地址。当然，需要注意的是，这将是一个本地地址，比如 127.0.0.1，并且您不能从托管 Minikube 的机器外部访问它。因此，您最好在有桌面的 Linux 发行版上安装和使用 Minikube，否则，仪表板将无法访问。

除此之外，你可以在 Minikube 的帮助下开始开发或学习 Kubernetes 的诀窍。您肯定不会在生产环境中使用 Minikube，但是作为开发环境，使用 Kubernetes 平台很难这么简单。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>