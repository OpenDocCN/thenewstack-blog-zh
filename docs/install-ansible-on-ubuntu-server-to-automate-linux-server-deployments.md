# 在 Ubuntu Server 上安装 Ansible 来自动部署 Linux 服务器

> 原文：<https://thenewstack.io/install-ansible-on-ubuntu-server-to-automate-linux-server-deployments/>

在您的网络或云托管平台上，您管理着多少台 Linux 机器？如今，这个数字可能正在快速增长，尤其是考虑到很多企业不仅依赖 Linux 提供常规服务，还依赖于容器化和云原生部署。

所以，是的，这些 Linux 机器可能正在以指数级的速度增长。这意味着您要管理越来越多的机器，这可能相当耗时。考虑到您的日常工作已经非常繁忙，您不需要登录每一台机器并手动运行命令。

考虑到这一点，你会怎么做？一个解决方案是求助于集中式配置管理工具，比如[红帽](https://www.openshift.com/try?utm_content=inline-mention)的 Ansible。关于 [Ansible](https://www.redhat.com/en/technologies/management/ansible) 最好的事情之一是，它利用 SSH 和 YAML 文件来处理繁重的远程工作。这意味着您不必费心在需要管理的服务器上安装代理，因为这都是通过控制器处理的。

我将带您完成 Ansible 在 Ubuntu Server 上的安装和配置，然后向您展示如何使用该平台运行您的第一本 Ansible 剧本。

## 你需要什么

我将完全用 Ubuntu Server 安装来演示这一设置，具体来说就是 [Ubuntu Server 22.04](https://ubuntu.com/engage/ubuntu-server-22-04-LTS) 。你可以在其他操作系统上使用 Ansible，但是因为 Ubuntu 是我的首选，所以我选择使用它。最重要的是，Ansible 安装在 Ubuntu 上非常容易。

说完这些，你准备好进入正题了吗？我想是的。

## 安装 Ansible

登录到您的 Ubuntu Server 22.04 实例，使用以下命令安装 Ansible:

`sudo apt-get install ansible -y`

上面的命令也将获得 ansible 启动和运行所需的所有依赖项。然而，我们还要安装一个软件，那就是 sshpass。SSHpass 是一个非交互式的 ssh 密码提供程序，因此您可以使用密码来配置您的远程服务器清单，以便于使用。

要安装 sshpass，发出以下命令:

`sudo apt-get install sshpass -y`

这就是你需要安装的所有软件。

## 创建库存文件

我将演示如何使用一台服务器创建清单。您可以根据需要向该文件中添加任意数量的服务器，只需确保将它们分成不同的类别(如 web、dev、database 等)。)，因此您可以对配置有更多的控制权。

首先，使用命令创建一个新目录来存放清单文件:

`sudo mkdir /etc/ansible`

接下来，使用以下内容创建库存文件:

`sudo nano /etc/ansible/hosts`

这是事情发生转折的地方。Ansible 要求您以一种非常特殊的方式配置您的主机。我将为 IP 地址为 192.168.1.13 的机器创建一个名为 testServer 的条目，用户为 jack，ssh 密码为 Th3N3w$t@ck。该库存文件将如下所示:

```
<i>[testServer]
</i><i>192.168.1.13</i>

<i>[testServer:vars]
</i><i>ansible_user=jack
</i><i>ansible_ssh_pass=  Th3N3w$t@ck</i>

<i>[all:vars]
</i><i>ansible_python_interpreter=/usr/bin/python3
</i><i>ansible_sudo_pass:  SUDO_PASSWORD</i>

```

底部为所有服务器设置变量，并指示 Ansible 使用 Python3 而不是默认的 Python。确保在那里插入您的用户的 sudo 密码。

太棒了。

让我们测试一下我们的库存。为此，发出以下命令:

`ansible all -m ping`

上面命令的输出应该类似于这样:

```
192.168.1.13  |  SUCCESS  =&gt;  {
     "changed":  false,
     "ping":  "pong"
}

```

成功输出就是你要找的。你看，你是金色的。

## 创建并运行行动手册

现在让我们创建第一个可行的剧本。我们将创建一个简单的剧本，在我们的 Ubuntu 服务器上安装完整的 LAMP 堆栈。这是非常重要的，你缩进这个剧本完美，因为它是一个 YAML 文件，将失败，如果缩进不正确。

使用以下命令创建新的行动手册:

`nano lampstack.yaml`

在该文件中，粘贴以下内容:

```
#Install LAMP Stack On Ubuntu Server
-  hosts:  testServer
  tasks:
  -  name:  install lamp stack
     become:  yes
     apt:
       pkg:
         -  apache2
         -  mysql-server
         -  php
         -  php-mysql
       state:  present
       update_cache:  yes

  -  name:  start apache service
     become:  yes
     become_user:  jack
     service:
       name:  apache2
       state:  started
       enabled:  yes

  -  name:  start mysql service
     become:  yes
           become_user:  jack
     service:
       name:  mysql
       state:  started
       enabled:  yes

```

保存并关闭文件。不要这样做，您需要将上面的*插孔*更改为在您的服务器上拥有 sudo 权限的用户。

创建行动手册后，您现在可以使用以下命令运行它:

`ansible-playbook lampstack.yaml  --user=jack --extra-vars ansible_sudo_pass="Th3N3w$t@ck"`

同样，您会希望用一个在您的服务器上实际工作的用户和密码来更改 jack 和 *Th3N3w$t@ck* 。

随着剧本的运行，您应该会看到如下输出:

```
PLAY  [testServer]  *****************************************************************************************************************************************************

TASK  [Gathering Facts]  *****************************************************************************************************************************************************
ok:  [192.168.1.13]

TASK  [install lamp stack]  *****************************************************************************************************************************************************
ok:  [192.168.1.13]

TASK  [start apache service]  *****************************************************************************************************************************************************
ok:  [192.168.1.13]

TASK  [start mysql service]  *****************************************************************************************************************************************************
ok:  [192.168.1.13]

PLAY RECAP *****************************************************************************************************************************************************
192.168.1.13  :  ok=4  changed=0  unreachable=0  failed=0  skipped=0  rescued=0  ignored=0

```

行动手册应该会运行(可能需要一些时间来完成),完成后，您可以将 web 浏览器指向清单中服务器的 IP 地址，以查看远程服务器上的 Apache 欢迎页面。

这就是安装 Ansible 并使用它来管理远程服务器的全部内容。有关 Ansible 行动手册的更多信息，请务必查看官方文档。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>