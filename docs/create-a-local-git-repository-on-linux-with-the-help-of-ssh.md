# 借助 SSH 在 Linux 上创建一个本地 Git 存储库

> 原文：<https://thenewstack.io/create-a-local-git-repository-on-linux-with-the-help-of-ssh/>

您是否曾经发现自己需要在局域网内的一台机器上部署一个 [quick Git 存储库](https://thenewstack.io/git-at-15-how-git-changed-the-way-we-code/)？如果你是一名开发人员，这个任务很有可能已经多次落到你的肩上。

幸运的是，你真的不需要依赖一堆过于复杂的软件包或第三方工具来实现这一点。当然，如果你想要一个可爱的图形用户界面，让所有为你的开发项目做出贡献的人的生活变得更加容易，你可能会转向像 [Gitea](https://gitea.io/en-us/) 这样的平台。但是，如果您喜欢命令行带来的部署的简单性和方便性，那么您会想要尝试这种方法。它可能不具备基于网络的选项的所有功能，但它能可靠、快速地完成工作。

那么，你如何部署这个神奇的仓库呢？在 [git](https://thenewstack.io/tutorial-git-for-absolutely-everyone/) 和宋承宪的帮助下。所有 Linux 发行版都可以免费获得这两个工具，所以您不必担心寻找工具或为工具付费。

听起来像个赢家吗？我想是的。让我们实现它。

## 你需要的所有东西

为此，您需要一个 Linux 发行版来托管存储库，另一台机器来使用存储库，以及一个拥有 sudo 特权的用户。我将在 Ubuntu Server 22.04 上演示，但我也将展示如何在基于 RHEL/Fedora 的 Linux 发行版上安装该软件。

准备好了吗？我想是的。

## 安装必要的软件

我们要做的第一件事是安装必要的软件。您只需要 SSH 和 Git 这两个包。很可能已经安装了 SSH(因为几乎世界上所有的 Linux 发行版都安装了 SSH)。另一方面，Git 可能在您的机器上找不到。因此，要在基于 Ubuntu 的发行版上安装 Git，可以发出命令:

```
sudo apt-get install git  -y

```

如果您使用的是基于 Red Hat Enterprise Linux/Fedora 的发行版，那么这个命令应该是:

需要记住的一点是，您必须在托管存储库的机器和使用存储库的机器上安装 git。

## 创建特殊用户

我们现在将创建一个特殊帐户，用于该存储库。为此，无论您使用什么发行版，命令都是相同的，并且是在托管存储库的机器上完成的。要创建用户，发出命令:

adduser 命令应该要求您为用户设置密码。如果没有，使用
进行操作

使用:
更改为该新用户

使用
切换到 git 用户的主目录

现在，我们需要创建一个。ssh 目录，命令:

使用
赋予该目录适当的权限

下一步是使用命令:
创建 authorized_keys 文件

```
touch  .ssh/authorized_keys

```

使用
赋予该文件所需的权限

```
chmod  600  .ssh/authorized_keys

```

## 在本地机器上创建一个 SSH 密钥，并将其复制到存储库机器上

接下来，我们需要在您用来访问存储库的机器上创建一个 SSH 密钥。为此，登录客户机并发出命令:

生成密钥后，您需要复制密钥的内容。先用
查看密钥

```
cat  /home/USER/.ssh/id_rsa.pub

```

其中用户是您的用户名。

回到托管存储库的机器上，用
打开 *authorized_keys* 文件

```
nano  /home/git/.ssh/authorized_keys

```

将 SSH 密钥的内容粘贴到该文件并保存/关闭。

## 创建新的存储库

在托管存储库的机器上，使用命令创建一个新目录:

使用命令:
切换到新目录

使用如下命令创建一个新的项目文件夹:

当然，你可以随意命名文件夹。

使用
切换到该文件夹

使用
初始化存储库

## 克隆新存储库

回到客户机，用命令
克隆新的存储库

```
git clone git@SERVER:/home/git/git_repo/PROJECT

```

其中 SERVER 是托管存储库的服务器的 IP 地址，PROJECT 是项目文件夹的名称。

您将被提示输入 SSH 密钥密码。身份验证成功后，项目文件夹的内容将被提取到您的本地计算机上。

您现在可以添加您的第一个提交(让我们添加一个 README)并将更改推回到存储库中，使用:

```
touch README
git add  --all
git commit  -m  "Added README file"
git push origin master

```

给你。您刚刚创建了一个快速 Git 存储库。如果您需要让其他用户访问存储库，您应该只需要让他们在自己的机器上创建 SSH 密钥，并以与上面相同的方式将它们复制到服务器上。

祝贺您在短短几分钟内建立并运行了一个 Git 存储库。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>