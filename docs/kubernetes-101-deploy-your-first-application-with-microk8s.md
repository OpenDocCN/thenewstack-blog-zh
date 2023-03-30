# Kubernetes 101:用 MicroK8s 部署您的第一个应用程序

> 原文：<https://thenewstack.io/kubernetes-101-deploy-your-first-application-with-microk8s/>

Kubernetes 很有挑战性。这一点毋庸置疑。在将容器部署到 Kubernetes 集群时，不仅有许多移动部件，而且在部署过程中可能会出现很多问题。让事情变得更加复杂的是，部署 Kubernetes 集群可能是一件非常棘手的事情。

这就是为什么像 Canonical 的 [MicroK8s](https://microk8s.io/) 这样的工具被开发出来。有了这样的软件，[部署 Kubernetes 集群](https://thenewstack.io/deploy-a-kubernetes-cluster-on-ubuntu-server-with-microk8s/)的过程挑战性大大降低，因此您可以将更多精力放在加快向集群部署应用和服务上。

促使[将应用和服务](https://thenewstack.io/deploy-a-single-node-kubernetes-instance-in-seconds-with-microk8s/)部署到 Kubernetes 集群的众多因素之一就是访问它们。与 Docker 不同，当您将一个应用程序或服务部署到 Kubernetes 集群时，它不会自动供您的网络使用。如果你所在的机器是集群的一部分，你当然可以访问该应用或服务，因为该机器将可以访问集群使用的子网。如果没有一点额外的技巧，该应用程序和服务在集群之外是不可用的。这意味着您必须手动使其可用。

再次…许多移动部件。

我已经完成了在 Rocky Linux 上安装 [Microk8s，然后](https://thenewstack.io/kubernetes-101-install-kubernetes-on-rocky-linux/)[将节点连接到控制器](https://thenewstack.io/deploy-a-single-node-kubernetes-instance-in-seconds-with-microk8s/)的步骤。通过添加节点，您可以创建一个可以部署应用程序和服务的集群。

我现在要做的是向您展示如何将您的第一个应用程序部署到群集，然后使该应用程序可以在群集外部访问。需要注意的一点是，将应用程序/服务部署到 MicroK8s 集群类似于任何其他 Kubernetes 发行版。对用户来说，最大的区别是部署需要 MicroK8s 命令，而其他 Kubernetes 发行版没有这个要求。

## 你需要什么

为此，您唯一需要的是一个至少包含一个控制器和两个节点的正在运行的 MicroK8s 集群。这些可以部署到您的数据中心、测试网络或第三方云主机。只要节点连接到控制器，就可以开始了。

如果您不确定节点是否已连接，请登录到您的控制器并发出命令:

```
microk8s kubectl get nodes

```

您应该看到列出了控制器和所有连接的节点。如果没有，请确保按照步骤重新连接节点。

## 如何用 MicroK8s 部署您的第一个应用程序

登录 MicroK8s 控制器。在这个演示中，我们将部署一个 [NGINX web 服务器应用程序](https://www.nginx.com?utm_content=inline-mention)。我们将这个部署命名为 nginx-webserver，并使用官方的 nginx 容器映像进行部署。这个命令是:

```
microk8s kubectl create deployment nginx-webserver  --image=nginx

```

该命令的输出应该如下所示:

```
deployment.apps/nginx-webserver created

```

使用命令
验证部署是否成功

```
microk8s kubectl get pods

```

您应该在输出中看到类似这样的内容:

```
nginx-webserver-67f557b648-4mfc6              1/1        Running                    0               9m59s

```

恭喜，您的第一个 pod 已部署到集群。什么是 pod？Kubernetes pod 是一个或多个容器的集合，是应用程序的最小单元。pod 通常由多个集成容器组成，但也可以由单个容器组成。在我们上面的实例中，我们部署了一个带有单个容器(NGINX)的 pod。

此时，NGINX 应用程序正在运行，但不可访问。为了使其可访问，我们还必须部署一个服务。这里我们要做的是公开我们的 nginx-webserver 部署，在端口 80 上使用“NodePort”类型。什么是节点端口？简单地说，节点端口是连接到集群的每个节点上的开放端口。Kubernetes 将节点端口上的传入流量路由到您部署的服务或应用程序。

要部署服务，命令应该是这样的:

```
microk8s kubectl expose deployment nginx-webserver  --type="NodePort"  --port  80

```

该命令的输出应该如下所示:

```
service/webserver exposed

```

如果你试图访问端口 80 上正在运行的容器，比如 http://192.168.1.45，你会发现无法访问。怎么回事？Kubernetes 将内部端口 80 映射到一个随机的内部端口。在我们访问正在运行的 web 服务器之前，我们必须找出它被映射到了哪个端口。为此，发出命令:

```
microk8s kubectl get svc nginx-webserver

```

输出应该是这样的:

```
nginx-webserver     NodePort     10.152.183.105     &lt;none&gt;            80:31508/TCP     3m11s

```

如您所见，Kubernetes 已经将内部端口 80(NGINX 使用的端口)映射到外部端口 31508(Kubernetes 集群使用的端口)。因此，如果您将 web 浏览器指向 192.168.1.45:31508，您应该会在浏览器中看到 NGINX 欢迎屏幕。

当然，您可以使用任何一个节点的 IP 地址。但是，如果您使用控制器的 IP 地址，NGINX 站点将不会出现。为什么？因为控制器将容器部署到节点，而不是自身。

这就是使用 MicroK8s 将您的第一个应用程序部署到 Kubernetes 集群的全部内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>