# Ubuntu Pro 是什么，怎么用？

> 原文：<https://thenewstack.io/what-is-ubuntu-pro-and-how-can-you-use-it/>

Canonical 一直在寻找新的方法来使其 Ubuntu 操作系统更加安全可靠。考虑到市场上有多少发行版是基于 Ubuntu 的，这个平台的可靠性令人印象深刻。我很少遇到 Ubuntu 操作系统的单一问题(无论是在桌面上还是在服务器上)。尽管 Ubuntu 已经相当安全，Canonical 还在继续挑战极限。

为了进一步突破这些界限，Canonical 推出了 Ubuntu Pro 。什么是 Ubuntu Pro？简而言之，这是一个安全和维护订阅，提供了长达 10 年的安全覆盖，不仅涵盖了操作系统，还涵盖了 23，000 多个应用程序，如 Ansible、Apache Tomcat、Apache Zookeeper、Docker、Drupal、Nagios、Node.js、phpMyAdmin、Puppet、PowerDNS、Python 2、Redis、Rust、WordPress 等。所以，如果你依赖于你使用的软件的安全性和合规性，Ubuntu Pro 就是你所需要的。

最近，Canonical 决定将 Ubuntu Pro 扩展到商业用途之外，并进入个人和小规模部署。这意味着即使是消费者桌面用户也可以在最多五台机器上免费享受 Ubuntu Pro 的好处。因此，无论你是一个使用 Ubuntu 作为日常工作操作系统的桌面用户，一个使用 Ubuntu 作为开发平台的开发人员，一个依赖 Ubuntu 服务器做各种事情的小企业，甚至是一个大型企业公司，你都可以从 Ubuntu Prol 中受益。

当然，只有那些个人和小规模商业用例可以利用免费价格层。

十年的安全感……谁不想要呢？

但是如何利用 Ubuntu Pro 呢？我要给你看。我将在 Ubuntu 22.04 桌面上演示这一点，但同样的过程也适用于其他版本(以及服务器版本)。

## 要求

要使用 Ubuntu Pro，您需要具备以下条件:

*   运行 LTS 版 Ubuntu 的机器(LTS 16.04，LTS 18.04，LTS 20.04，LTS 22.04)
*   拥有`sudo`权限的用户
*   电子邮件地址(或现有的 Ubuntu One 帐户)。

## 安装 Ubuntu Pro

根据您使用的 Ubuntu 版本，您可能安装了 Ubuntu Pro，也可能没有安装。要检查它是否存在，请发出命令:

您应该在输出中看到类似这样的内容:

要实现这一点，您必须至少拥有版本 27.11.2。如果您拥有的版本比这个版本旧，您需要使用以下命令运行升级:

```
sudo apt-get update  &amp;&amp;  sudo apt-get upgrade  -y

```

升级完成后，重启、重新登录并检查版本。

如果你发现没有安装 Ubuntu Pro，你可以用命令安装它:

```
sudo apt-get install ubuntu-advantage-tools=27.11.2~$(lsb_release  -rs).1

```

安装后重启。

现在，从技术上讲，你应该在软件和更新应用中看到一个新的 Ubuntu Pro 标签。我还没有看到该选项卡出现，相反，只看到 Livepatch。因此，我们将通过命令行工作。

发出命令:

您可能会在输出的底部看到以下警告:

这台机器没有连接到 Ubuntu Pro 订阅。

要安装这台机器，你必须打开一个网页浏览器，访问 ubuntu.com/pro 网站，注册一个免费账户(或者登录你的 Ubuntu One 账户)。登录或创建帐户后，您应该会在您的订阅页面上看到一个免费的个人令牌。将该令牌复制到剪贴板。

接下来，您需要将机器与您的帐户相关联，这是通过以下命令实现的:

其中 TOKEN 是您从 Ubuntu Pro 订阅页面复制的免费个人令牌。

一旦你的机器连接上了，你需要使用命令
来启用 sem-apps 服务(目前处于测试阶段)

```
sudo pro enable esm-apps  --beta

```

当您的系统完全连接到 Ubuntu Pro 时，您可以通过发出以下命令来查看您的系统是否有可用的安全补丁:

```
apt list  --upgradable  |  grep apps-security

```

如果输出表明 esm-apps 没有安全更新，您就可以开始了。

需要记住的一点是，在安装属于 esm-apps(扩展安全维护)更新过程的应用程序之前，您可能必须禁用 esm-apps。为此，您可以使用:
禁用该服务

```
sudo pro disable esm-apps

```

禁用服务后，像往常一样安装应用程序。安装应用程序后，使用
重新启用服务

```
sudo pro enable esm-apps  --beta

```

现在，当您运行命令:

```
apt list  --upgradable  |  grep apps-security

```

您可能会看到指示有可用补丁的输出。

## 警告

需要记住的一点是(在撰写本文时)，即使在安装并启用 Pro 之后，我还没有看到 Ubuntu Pro 标签出现在软件和更新 GUI 中。这可能是因为这项服务太新了。正因为如此，每一个与 Ubuntu Pro 相关的任务都必须通过命令行来完成。

我遇到的另一个问题是一个错误，即公钥不可用于 esm 更新。apt-get 更新运行时显示该错误，如下所示:

```
GPG error:  https://esm.ubuntu.com/apps/ubuntu jammy-apps-security InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY AB01A101DB53907B

```

你可以这样解决这个问题:

```
sudo apt-key adv  --keyserver keyserver.ubuntu.com  --recv-keys AB01A101DB53907B

```

你会看到一个 apt-key 被否决的警告，所以我们必须修复它。为此，使用命令找到密钥 ID:

您应该会看到 esm 条目列出了一个随机字符串，第二行如下:

```
E8A4  43CE  3581  13D1  87BE   E0E6 AB01 A101 DB53  907B

```

复制最后 8 个字符并删除空格。现在，运行命令:

```
sudo apt-key export DB53907B  |  sudo gpg  --dearmor  -o  /etc/apt/trusted.gpg.d/esm.gpg

```

这将解决 GPG 问题，从那时起，一切都会顺利得多。

现在，你已经在你的台式机或服务器上启用了 Ubuntu Pro，并且可以享受 10 年安全更新和补丁带来的额外好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>