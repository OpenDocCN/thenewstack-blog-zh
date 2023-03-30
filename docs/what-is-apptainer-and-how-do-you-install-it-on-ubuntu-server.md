# 什么是 Apptainer，如何在 Ubuntu 服务器上安装？

> 原文：<https://thenewstack.io/what-is-apptainer-and-how-do-you-install-it-on-ubuntu-server/>

[Apptainer/Singularity](https://apptainer.org/) 包已经成为[高性能计算](https://thenewstack.io/hpc-needs-to-be-built-for-the-cloud-not-just-run-on-the-cloud/) (HPC)最广泛使用的容器部署系统之一。该容器系统旨在执行具有裸机性能的应用程序，同时保持高级别的安全性、可移植性和可再现性。

Apptainer 是一个开源项目，拥有不断增长的社区和不断扩大的用户基础。功能集如下所示:

*   支持信任的公钥/私钥签名。
*   与 Docker 和开放容器倡议的兼容性。
*   加密。
*   便携性。
*   容器无根运行以禁止特权升级。
*   利用 GPU、FPGAs、高速网络和文件系统。
*   好用。
*   提供商业支持。

虽然 Apptainer 不像 Docker 那样容易安装，但是如果您正在寻找容器中更高的安全性，这可能就是您正在寻找的部署系统。

但是它是如何安装的呢？这就是我现在想给你看的。

## 要求

Apptainer 可以安装在基于 RHEL 和 Ubuntu 的 Linux 发行版上。我将使用我的首选服务器 Ubuntu Server 22.04 进行演示，因此您需要一个运行该操作系统的实例和一个拥有 sudo 权限的用户。就这样…让我们开始派对吧。

## 安装必要的依赖项

首先要做的是安装必要的依赖项。登录你的 Ubuntu 实例，发出命令:

```
sudo apt-get install  -y  \
    build-essential  \
    libseccomp-dev  \
    pkg-config  \
    uidmap  \
    squashfs-tools  \
    squashfuse  \
    fuse2fs  \
    fuse-overlayfs  \
    fakeroot  \
    cryptsetup  \
    curl wget git

```

对于那些可能不熟悉 Linux 的人来说，上面是一个用\字符分成几个步骤的命令。该命令的单行版本如下所示:

```
sudo apt-get install build-essential libseccomp-dev pkg-config uidmap squashfs-tools  \n
squashfuse fuse2fs fuse-overlayfs fakeroot cryptsetup curl wget git  -y

```

请注意，如果您使用的是基于 RHEL 的发行版，依赖项的安装会稍微复杂一些。首先，您必须安装带有
的开发工具

```
sudo yum groupinstall  -y  'Development Tools'

```

接下来，添加 EPEL 存储库:

```
sudo yum install  -y  epel-release

```

最后，您可以使用
安装依赖项

```
sudo yum install  -y  \
    libseccomp-devel  \
    squashfs-tools  \
    squashfuse  \
    fuse-overlayfs  \
    fakeroot  \
    /usr/*bin/fuse2fs  \
    cryptsetup  \
    wget git

```

接下来，我们必须安装 Go。首先，用
设置版本和架构

```
export GOVERSION=1.19.1  OS=linux ARCH=amd64

```

使用
下载必要的文件

```
wget  -O  /tmp/go${GOVERSION}.${OS}-${ARCH}.tar.gz   \n  
https://dl.google.com/go/go${GOVERSION}.${OS}-${ARCH}.tar.gz

```

用
解压并移动下载的文件

```
sudo  tar  -C  /usr/local  -xzf  /tmp/go${GOVERSION}.${OS}-${ARCH}.tar.gz

```

使用以下两个命令将 Go 可执行文件添加到您的用户路径中:

```
echo  'export PATH=$PATH:/usr/local/go/bin'  &gt;&gt;  ~/.bashrc
source  ~/.bashrc

```

我们现在需要用
安装 golangcli-lint 工具

```
curl  -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh \n 
|  sh  -s  --  -b  $(go env GOPATH)/bin v1.43.0

```

使用
将此添加到您的路径中

```
echo  'export PATH=$PATH:$(go env GOPATH)/bin'  &gt;&gt;  ~/.bashrc
source  ~/.bashrc

```

## 克隆 Apptainer Repo 并安装

解决了依赖关系之后，我们现在可以克隆 Apptainer 存储库并安装软件了。

使用
克隆存储库

```
git clone https://github.com/apptainer/apptainer.git

```

用
切换到新创建的目录

使用
查看最新版本

确保查看[发布页面](https://github.com/apptainer/apptainer/tags)，以确保您使用的是最新版本。

使用命令运行配置脚本:

进入构建目录:

使用以下命令编译 Apptainer:

完成上述命令需要相当长的时间(10 分钟以上)。在某些时候，你可能认为它已经停止了。不要慌！让手指远离[Ctrl]+[C]键盘快捷键，让安装完成。

make 命令完成后，用:
安装 Apptainer

当安装过程完成时，您可以通过使用命令查看 Apptainer 版本来验证一切按计划进行

您应该会在输出中看到如下内容:

```
apptainer version  1.1.0-rc.3

```

杰出。Apptainer 已安装并准备好操作。

## 如何使用 Apptainer 部署容器

现在让我们用 Apptainer 部署总是很有趣的 Hello World 容器。为此，我们将使用命令从 Singularity hub 下拉 hello-world 应用程序:

```
singularity pull shub://singularityhub/hello-world

```

您应该会在该目录中看到一个名为
的新文件

要运行应用程序，发出命令:

应用程序将打印出:

您也可以使用
来运行容器

```
apptainer run hello-world_latest.sif

```

假设你想使用 Ubuntu 20.04 作为一个容器。你可以用
来拉它

```
apptainer pull docker://ubuntu:latest

```

一旦它被拉出来，你就可以在容器中运行一个类似这样的命令:

```
apptainer exec ubuntu_latest.sif cat  /etc/os-release

```

您应该会在输出中看到以下内容:

```
NAME="Ubuntu"
VERSION="20.04.5 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.5 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal

```

这就是你开始使用 Apptainer 容器部署系统的全部过程。对于任何希望从部署中获得更多安全性的容器管理员来说，这都是一个很好的选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>