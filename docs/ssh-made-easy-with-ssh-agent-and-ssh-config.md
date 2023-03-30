# SSH 代理和 SSH 配置使 SSH 变得简单

> 原文：<https://thenewstack.io/ssh-made-easy-with-ssh-agent-and-ssh-config/>

您很有可能使用安全 Shell 登录远程服务器。SSH 是众所周知的安全协议，它不仅简化了远程管理/开发，也是与云托管的虚拟机交互的最佳工具之一。事实上，如果没有 SSH，在 Linux 机器上远程工作，无论是在云中还是在本地数据中心，都将是一个巨大的挑战，如果不是完全不可能的话。

所以好消息是 SSH 是高度可配置的，并且易于使用。对吗？

您可能想知道主要从命令行使用的任何工具是如何变得易于使用的。幸运的是，SSH 包含了几个特性和附加组件来帮助简化和保护它的使用。

今天，我想向您介绍两个非常具体的 ssh 工具:ssh-agent 和 SSH 配置文件。

## 什么是 SSH 代理？

[ssh-agent](https://linux.die.net/man/1/ssh-agent) 工具与 ssh 密钥认证相结合，使您可以启动一个会话，并且只要您在该会话中，您就可以登录和注销远程服务器，而无需键入 SSH 密码或认证密码。一旦你完成了远程工作，结束会话，一切都好了。

但是如何使用这个特性呢？让我展示给你看。

在此之前，我们需要设置 SSH 密钥认证。要做到这一点，请到您将用来登录远程服务器的机器前，打开一个终端窗口。在那里，使用以下命令创建一个新的 SSH 密钥:

`ssh-keygen`

一旦创建了 SSH 密钥，就需要将它复制到将要登录的服务器上。使用以下命令执行此操作:

`ssh-copy-id SERVER`

其中 SERVER 是远程服务器的 IP 地址或域。

现在，当您尝试 SSH 到远程服务器时，它会要求您输入 SSH 密钥短语，而不是您的用户密码。

第一步搞定了。

现在，我们如何利用 ssh-agent 呢？简单。从终端发出命令:

`eval `ssh-agent``

您将返回一个代理 PID，然后返回到您的终端。你可能会想，“什么都没变！”但是已经发生了。您现在处于 SSH 代理会话中。

接下来，使用命令添加您的 SSH 密钥:

`ssh-add`

系统将提示您输入 SSH 密钥密码。

再次尝试 SSH 到远程服务器。这一次，系统不会提示您输入密码或口令，您将被允许进入。退出远程会话，并尝试再次登录。同样的结果。这种行为将持续下去，直到您使用 *exit* 命令关闭 SSH 代理会话。

## 最大的警告

您可能已经理解了使用 SSH 代理的注意事项。您可能已经退出了该 SSH 会话，但未能退出 SSH 代理会话。在这种情况下，任何拥有您的桌面密码和远程服务器的 IP 地址/域的人都可以启动一个新的远程会话。因此，您必须总是锁定您的桌面环境，或者在完成后记得退出 SSH 代理会话。如果做不到其中任何一点，你就会给自己带来麻烦。

## SSH 配置

现在，我们已经通过 SSH 密钥认证和 SSH 代理帮助您的 SSH 远程会话变得更加安全，现在我们可以让它变得更加方便。SSH 配置文件中包含了一个非常方便的特性。该文件位于您的~/中。ssh 目录，简称为 config。

使用 SSH 配置文件，您可以为各种 SSH 连接创建单独的配置。这是一种真正简化所有 SSH 连接的方法。例如:假设您有几个经常远程访问的服务器，每个连接使用不同的用户名。让我们给这些服务器打电话:

*   自动警报系统
*   谷歌云
*   蔚蓝的
*   网
*   分贝

对于每个连接，您使用不同的用户名登录，因此:

*   AWS–奥利维亚
*   谷歌云–贝瑟尼
*   蔚蓝色–三一
*   web–Janet
*   DB–chenica

如果不必像在 ssh olivia@SERVER 中那样键入整个 SSH 命令，而只需键入:

`ssh AWS`

你可以这样做。让我告诉你怎么做。我将在 macOS 上演示，但是如果您使用 Linux 作为客户端，过程是相同的。

通过打开终端应用程序并发出以下命令来创建新的配置文件:

`nano ~/.ssh/config`

每个配置条目看起来都像这样:

```
Host AWS
   HostName ADDRESS
    User olivia
   IdentityFile  ~/.ssh/id_rsa.pub

```

上述配置分解如下:

*   主机—您将用于主机的昵称。
*   主机名—远程服务器的 IP 地址或域。
*   用户—与远程帐户关联的用户名。
*   IdentityFile —帐户的 SSH 密钥身份验证文件的位置。

显然，如果您对每个帐户使用 SSH 密钥身份验证，并且用户名不同，那么您必须为每个用户创建 SSH 身份验证密钥，并且从将要启动 SSH 会话的用户帐户读取这些文件。

为每个远程服务器创建条目。因此，该文件可能看起来像这样:

```
Host AWS
   HostName ADDRESS
   User olivia
   IdentityFile  ~/.ssh/id_rsa_olivia.pub

Host GoogleCloud
   HostName ADDRESS
   User bethany
   IdentityFile  ~/.ssh/id_rsa_bethany.pub

Host AZURE
   HostName ADDRESS
   User trinity
   IdentityFile  ~/.ssh/id_rsa_trinity.pub

Host WEB
     HostName ADDRESS
   User janet
   IdentityFile  ~/.ssh/id_rsa_janet.pub

Host DB
   HostName ADDRESS
   User chenica
   IdentityFile  ~/.ssh/id_rsa_chenica.pub

```

其中 ADDRESS 是您的远程服务器的 IP 地址或域。

保存并关闭该文件。

下次您需要登录到其中一个连接时，您只需使用以下任何一个命令:

`ssh AWS`

`ssh GoogleCloud`

`ssh AZURE`

`ssh WEB`

`ssh DB`

就是这样。如果你把这个和 ssh-agent 结合使用，你的生活会变得更加容易。

## 结论

必须不断地进出机器，这种重复会变得很乏味。如果您远程访问大量服务器，您可能甚至不记得远程 IP/域地址或与这些远程帐户相关的用户名。使用 *ssh-agent* 和 ssh 配置文件可以大大提高您的工作效率。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>