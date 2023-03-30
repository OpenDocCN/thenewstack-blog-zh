# 将微软的新 Linux 发行版部署为虚拟机并不容易

> 原文：<https://thenewstack.io/deploying-microsofts-new-linux-distribution-as-a-vm-is-not-easy/>

地狱已经冰封，猪正从地壳下面裂开的、充满熔岩的裂缝中飞出来。

没错，微软有自己的 Linux 发行版。

在你失去理智之前，雷德蒙巨人并没有用一个更好的桌面来取代 Windows(尽管《永不言弃》和《七宝奇谋》不会死)。相反，微软专门为微软的内部云基础设施和边缘产品和服务构建了一个轻量级 Linux 发行版。有了这个版本的 Linux，微软将能够增强其在以 Linux 为中心的云环境中保持最新的能力。

鉴于企业业务对 Linux 的绝对依赖，这是微软的明智之举。我甚至可以说这应该在几年前就发生了。但是，你瞧，时机已经到来，任何人现在都可以部署微软的 CBL 水手 Linux。对于那些好奇的人来说，CBL 代表通用基础 Linux，源代码是在开源许可证的混合下许可的，包括 GNU 通用公共许可证和 MIT 许可证。你可以从[CBL-水手 GitHub 页面](https://github.com/microsoft/CBL-Mariner)下载源代码，但是你找不到一个方便的 ISO 镜像来安装 CLB-水手。

是的，微软并没有让那些想要尝试这种新的云原生的、有容器味道的、有价值的 Linux 发行版的人变得容易。事实上，目前让 CBL 水手号启动并运行是一件非常复杂的事情。

这并不意味着这是不可能的。这只是运行一堆命令的问题。这正是我要给你们展示的。但是要知道:最终，你会得到一个 vhd 文件，然后你可以用它来启动一个虚拟机(VM)。因此，您不仅需要完成创建虚拟设备文件的步骤，还需要创建虚拟机。但是你是一个云原生开发者，所以你习惯于经历重重困难。要做到这一点，您需要一个 Linux 发行版。我会在 Ubuntu 桌面 21.04 上演示。

让我们实现它。

## 安装必要的依赖项

首先要做的是必须安装几个依赖项，所以登录到您的 Linux 机器并打开一个终端窗口。在执行任何操作之前，您必须添加 backports 存储库，这是通过以下命令完成的:

`sudo add-apt-repository ppa:longsleep/golang-backports`

出现提示时，按 Enter 键。

接下来，我们需要用以下命令更新 apt:

`sudo apt-get update`

apt 更新完成后，使用以下命令安装所有必需的依赖项:

`sudo apt-get install make tar wget curl rpm qemu-utils golang-1.15-go genisoimage python2-minimal bison gawk -y`

注意:如果你在一个旧版本的 Ubuntu 上安装(比如 18.04)，上面的命令应该是:

`sudo apt-get install make tar wget curl rpm qemu-utils golang-1.15-go genisoimage python-minimal bison gawk -y`

为了获得更快的压缩，您可以选择使用以下命令安装 pigz:

`sudo apt-get install pigz -y`

您需要为 go 创建一个链接，链接内容为:

`sudo ln -vsf /usr/lib/go-1.15/bin/go /usr/bin/go`

最后一个依赖是 Docker。我们不安装标准存储库中的可用版本，而是使用最新版本，命令如下:

`curl -fsSL https://get.docker.com -o get-docker.shsudo sh get-docker.sh`

您还需要将您的用户添加到 docker 组中(否则您必须使用 sudo 运行 *docker* 命令，这可能是一个安全问题)。使用命令添加您的用户:

`sudo usermod -aG docker $USER`

注销并重新登录，以便更改生效。

## 克隆并构建必要的工具包

使用以下命令克隆 CBL 水手工具包源代码:

`git clone https://github.com/microsoft/CBL-Mariner.git`

将当前目录保存到堆栈中，并使用以下命令切换到新创建的 CBL-水手目录:

`pushd CBL-Mariner/toolkit`

使用以下命令签出稳定版本:

`git checkout 1.0-stable`

使用以下工具构建工具包:

`sudo make package-toolkit REBUILD_TOOLS=y`

使用以下命令变回存储的目录:

`popd`

## 克隆 CBL-水手号并提取工具包

在 git 的帮助下克隆实际的 CBL 水手源代码:

`git clone https://github.com/microsoft/CBL-MarinerDemo.git`

保存当前目录，并使用以下命令切换到新目录:

`pushd CBL-MarinerDemo`

复制源:

`cp ../CBL-Mariner/out/toolkit-*.tar.gz ./`

打开工具箱:

`tar -xzvf toolkit-*.tar.gz`

## 建造 VHD

下一步需要一些时间。我们现在要做的是构建将用于虚拟机的 vhd 文件。首先，使用命令切换到正确的目录:

`cd toolkit`

现在，您可以使用以下命令构建 vhd 文件:

`sudo make image CONFIG_FILE=../imageconfigs/demo_vhd.json`

要么坐下来看输出，要么去做别的事情，直到构建完成。这可能需要 10 到 30 分钟，具体取决于您的硬件。

一旦构建完成，你会在~/CBL-水手演示/out/images/demo_vhd/中找到 vhd 文件。您可以启动您选择的虚拟机工具，并使用该文件创建虚拟来宾。启动 CBL 水手号后，你将使用用户名 root 和密码 p@ssw0rd 登录。

仅此而已。你现在已经准备好测试微软自己的 Linux 版本了。尽管您可能不想将它作为默认的云原生开发平台，但您至少可以了解一下微软的发展方向。我要说的是，CBL-Linux 已经非常稳定，很快就会成为容器、物联网、edge 和云开发的优秀候选。到了吗？大概不会。但是考虑到这个平台是多么的新，微软已经取得的成就令人印象深刻。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>