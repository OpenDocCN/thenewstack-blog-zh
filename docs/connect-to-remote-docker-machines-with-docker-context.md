# 使用 Docker 上下文连接到远程 Docker 机器

> 原文：<https://thenewstack.io/connect-to-remote-docker-machines-with-docker-context/>

Docker 是开发和部署容器化应用程序和服务的一个很好的工具。该工具有大量的选项，使其非常强大和灵活，足以用于几乎所有类型的工作流和流程。

对于大多数开发人员和管理员来说， [Docker](https://www.docker.com/?utm_content=inline-mention) 最好从 CLI(命令行界面)使用。使用命令行，您几乎可以做开发和部署所需的一切事情。虽然有些人宁愿选择使用设计良好的 GUI(比如我最喜欢的， [Portainer](https://thenewstack.io/an-introduction-to-portainer-a-gui-for-docker-management/) )来完成这个过程，但是 Docker 的锦囊妙计仅限于 CLI。

一个这样的工具是 [Docker Context](https://docs.docker.com/engine/context/working-with-contexts/) 。这使得从安装了 Docker 的不同机器上导出和导入上下文成为可能。Context 的最佳特性是连接到远程 Docker 实例的能力。这意味着，如果您有多个 Docker 节点，您可以很容易地从一台机器上管理它们。

需要记住的一点是，上下文是在 Docker v19.03 之前引入的。因此，如果你使用的是之前的版本，你需要升级。要了解您运行的是哪个版本的 Docker，请登录到您的主机并发出以下命令:

docker -v

如果你看到任何 19.03 之前的版本，是时候升级了。在我的测试机器上，我运行 Docker 20.10.14，build a224086。

Docker 上下文提供了四个不同的命令选项:

*   创建–创建一个上下文
*   导出–将上下文导出到 tar 或 kubeconfig 文件
*   导入–从 tar 或 zip 文件导入上下文
*   检查–显示一个或多个上下文的详细信息
*   ls–列出上下文
*   RM–删除一个或多个上下文
*   更新–更新上下文
*   使用–设置当前 docker 上下文

我想做的是向您展示如何使用 Docker 上下文连接到远程 Docker 实例。

## 你需要什么

为了跟进，您需要两个 Docker 节点。我将用 IP 地址为 192.168.1.5 和 192.168.1.60 的节点进行演示，但是您可以使用您需要的任何 IP 地址方案。只需记住在运行命令时更改 IP 地址以适应您的方案。

您还需要 SSH 密钥认证设置。

## 设置 SSH 密钥认证

在 192.168.1.15 上，发出命令:

接下来，我们使用命令将密钥复制到 IP 地址 192 . 168 . 1 . 60:

## 连接到第二个节点

我们要做的第一件事是登录 IP 地址为 192.168.1.15 的机器，并检查默认上下文。为此，发出命令:

您应该在输出中看到类似这样的内容:

```
default *     Current DOCKER_HOST based configuration     unix:///var/run/docker.sock                         swarm

```

让我们使用 Linux export 命令在第一台机器上设置目标主机，如下所示:

```
export TARGET_HOST=192.168.1.60

```

我们必须做的下一件事是配置 SSH 以信任新主机。为此，我们将像这样使用 *ssh-keyscan* 命令:

```
ssh-keyscan  -H  $TARGET_HOST  ~/.ssh/known_hosts

```

在我们实际连接到远程主机之前，我们必须首先使用以下命令启动 ssh-agent:

```
eval  `ssh-agent  -s`
ssh-add

```

第二个命令将提示您输入 SSH 密钥认证密码。成功认证后，您就可以继续前进了。

```
Let's  view the running containers on the second node with the command:

DOCKER_HOST=ssh://$TARGET_HOST docker container ls

```

您应该会看到第二个节点上的运行目标列表。

现在，我们可以成功地使用 Docker 上下文。

## 如何使用 Docker 上下文

我们必须做的第一件事是用
取消变量的设置

我们现在可以像这样创建一个新的上下文:

```
docker context create node2  --description  "Docker Node 2"  --docker  "host=ssh://$TARGET_HOST"

```

您应该在输出中看到类似这样的内容:

```
node2
Successfully created context  "node2"

```

牛逼。

现在，如果发出 ls 命令，应该会在输出中看到 node2。所以发出命令:

输出应包括:

```
node2           Docker Node  2                                            ssh://192.168.1.60

```

接下来，我们将使用
切换到节点 2

使用
查看节点 2 中的所有远程容器

你可以根据需要添加任意多个上下文，并使用 docker 上下文使用命令在它们之间切换。

在使用上下文时，您甚至可以像平常一样将容器部署到远程主机。所以当使用 node2 上下文时，我可以像这样部署一个 NGINX 容器:

```
docker container run  -d  -p  80:80  nginx

```

用
列出正在运行的容器

您应该看到 NGINX 容器在 node2 上运行。

如果你想删除一个上下文，可以这样做:

如果您发现上下文正在使用中，请切换到默认设置:

```
docker context use default

```

然后，您应该能够删除节点 2。

这就是用 docker 上下文命令连接到远程 Docker 节点的全部内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>