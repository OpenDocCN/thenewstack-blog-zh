# 如何用 SSH 密钥签署 git 提交

> 原文：<https://thenewstack.io/how-to-sign-git-commits-with-an-ssh-key/>

开发项目会变得非常繁忙。它们也可以增长到巨大的比例。当项目扩展时(尤其是那些开源项目)，他们会雇佣越来越多的开发人员。那太好了…直到它不是。

例如，如果一个流氓开发人员跳到一个项目上，添加一个将恶意软件注入代码的提交，会发生什么？没有一个项目想处理这样的问题。

为此，项目必须非常小心他们允许谁进入。但是如果有人在雷达下偷偷摸摸会怎么样呢？也许一个流氓开发人员获得了对您的项目的访问权，并在另一个开发人员的伪装下添加了一个注入恶意代码的 commit。当您看到与提交相关联的开发人员的名字时，您让它通过，假设代码是可靠的，没有必要担心。

著名的遗言。

你不知道，那个流氓开发者刚刚破坏了你的项目，除非你抓住它，否则你可能会面临一个大问题。

你能做些什么来避免这种情况？

有很多事情。您可以不断地关注每一行代码，以确保它对项目是有价值的，并且是安全的。当然，您希望信任您的开发人员，并且可能没有时间仔细检查每一行代码以发现恶意意图。

如果这描述了你的项目，你能做什么？

一件事是对提交执行安全外壳(SSH)签名，它使用公钥加密为您自己创建一个无法伪造的签名。

啊哈！你一直在到处寻找这样的解决办法。

通过在 SSH 提交中使用签名，您可以更容易地验证每个提交是由合法的开发人员而不是冒名顶替者提交的。

我在这里向你展示这是怎么做的。

## 要求

要在 git 提交中使用 SSH 密钥，您需要安装 git 版本控制软件和一个 T2 SSH 密钥。我将向您展示如何做到这两点，并将在 Ubuntu Linux 22.04 上进行演示。如果您在不同的操作系统上工作，请确保相应地改变安装步骤。

准备好了吗？我们开始吧。

## 安装 Git

我们要做的第一件事是[安装 git](https://thenewstack.io/tutorial-git-for-absolutely-everyone/) 。为此，登录到您的 Ubuntu 实例，打开一个终端窗口，发出命令:

```
sudo apt-get install git  -y

```

万岁！

## 创建您的 SSH 密钥

接下来，您必须生成一个将要使用的 SSH 密钥。为此，发出命令:

回答问题，并确保键入/验证密钥的强且唯一的密码。那把钥匙会放在你的~/里。默认情况下是 ssh 目录。这很好，因为 git 可以使用它。

## 初始化本地存储库

接下来，我们必须初始化一个本地存储库。使用命令:
为此创建一个文件夹

您可以随意命名该目录。

用
切换到新目录

用
初始化空存储库

## 配置 Git

我们现在需要配置 git 来知道我们是谁。这是通过以下两个命令完成的:

```
git config  --global user.email  "EMAIL"
git config  --global user.name  "NAME"

```

其中 EMAIL 是你的电子邮件地址，NAME 是你的全名。

我们的下一个配置告诉 git 我们想要启用 GPG 歌唱，格式将是 SSH。为此，发出以下两个命令:

```
git config  --global commit.gpgsign true
git config  --global gpg.format ssh

```

接下来，用
列出您的 SSH 密钥

您应该会看到下面列出的内容:

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCUlMZBvT363Qpg1PM9LzJHwP/ijaPD+0O7l24TchGoqVItu9N6PsnXigVT21VTNemltSfChS6A2qDPMsXKbeiK7It9tMcTDyeBJd2e9rdlzQ05cHQ65jerVIe9pyc/asbX0jtlm0+VcB0fim3gVHlVcR8a6DWrqijU5YXYt3jUzdleHv9XmRJANTRAOpPICTnkO4G9HyNgJeI9M2baFgSwiNohVFHG8KJI1rXM64ryr7Psgr/5DihYSbFfTinI731ZpA3qogIaUlyKDAP7t8Xt7ntSeIzsSfd8A8jiGeYdme+MyUBo/2ENb0UmKYI695Cf6Ua+DGR39j8kt2jGw3rgkkA3L9i2+v+6aHeMzzdgR1FFIsXHs3pfDO05+u1CUgclujamsJdreEbuEwLFHQGQ60m3it7J0T/JGRUcgvQeIukslCyFzz2Rj3j0aSsyVTeVTj7f3rZyWZJlSTVyFv5uMpfm62YzA5hPCPrMJg7XHpUbP4VkWkeTfAalTTtYz34=  jack@docker1

```

复制整个字符串。

如果在 ssh-add 命令之后出现错误，您可能需要首先运行命令:

我们现在可以用命令设置我们的签名密钥:

```
git config  --global user.signingkey  "KEY"

```

其中 KEY 是上面复制的整个字符串。

然后，您可以使用命令:
确认 SSH 签名已经正确设置

```
git commit  --allow-empty  --message="Did SSH signing work?"

```

对于我们的下一个技巧，我们需要用命令配置签名文件:

```
git config  --global gpg.ssh.allowedSignersFile  ~/.ssh/allowed_signers

```

使用:
创建允许的签名人文件

```
touch  ~/.ssh/allowed_signers

```

最后，我们必须使用命令
用我们的密钥填充这个新文件

```
echo  "EMAIL ssh-rsa KEY"  &gt;  ~/.ssh/allowed_signers

```

其中 EMAIL 是您的电子邮件地址，KEY 是您之前复制的密钥。

## 如何验证它的工作

现在一切都设置好了，让我们用命令
确保一切正常

```
git show  --show-signature

```

输出应该是这样的:

```
commit efb59f739f141f29b4c63d9c43edc7f46243ea47  (HEAD  -&gt;  master)
Good  "git"  signature for EMAIL with RSA key SHA256:YgBNmIqR3Z2ff7XoVKptRkZffw6nHC5mDKF8g6AcjVQ
Author:  Jack Wallen  &lt;EMAIL&gt;
Date:     Thu Sep  15  16:53:44  2022  +0000

Testing SSH signing

```

其中 EMAIL 是与您的 SSH 密钥相关联的电子邮件地址。

恭喜，现在您已经为 git 提交设置了 SSH 签名。每个人都会知道，这真的是你提交的项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>