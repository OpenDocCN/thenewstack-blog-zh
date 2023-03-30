# 是时候说再见了:Python 3.6 已经寿终正寝了

> 原文：<https://thenewstack.io/time-to-say-goodbye-python-3-6-is-end-of-life/>

到这个月为止，Python 3.6 对我来说已经死了。

你也应该死了。

为什么？因为它将不再接收错误或安全修补程序。那是什么意思？这意味着如果你在这个月之前使用 Python 3.6，你要自担风险。

相信我，当我说你不想那样的时候。尤其是最近发现的 [Log4j 漏洞](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)。不，这并不直接涉及 Python，但它为始终保持最新提供了一个非常响亮而痛苦的例子。

这是个问题。考虑一下:截至 2021 年 12 月 16 日，从 PyPI 下载的包中至少有 [17.39%](https://pypistats.org/packages/__all__) 是基于 Python 3.6 的。那就是知道这个版本的 [Python](https://www.python.org/) 即将走到生命的尽头。

那是自找麻烦。

想知道你用的是哪个版本的 Python？发出命令:

`python3 --version`

如果你看到 3.6 或更早的版本，到 2021 年 12 月底，你将不再收到更新或错误修复。要解决这个问题，你必须升级到 Python 的[最新版本](https://www.python.org/downloads/)。因为 3.6 将达到寿命终止(EOL)，它将不再接受错误修复，即使它们是关键的。您可能会发现自己在使用 Python 处理一个已知的 CVSS 得分为 10.0 的 CVE，并且不会得到修补。

但是等等，对于那些仍然拒绝意识到从 Python 3.6 开始有多重要的人来说，这里有一些伪漏洞。

比方说，你正在使用 Ubuntu Server 20.04，这是一个长期版本。这种 LTS 分布支持到 2025 年。所以，理论上，你还有三年的支持时间。这是否意味着你可以免于更新 Python？理论上，是的。使用 LTS 版本时，您将收到安全更新。有一个警告。即使您收到了安全更新，您也无法获得错误修复，当然也不会包含新功能。

你想要新功能，对吗？
你应该也想修复 bug 吧？

更糟糕的是，你的第三方框架和库都不会被更新。您将被那些仍然支持 Python 3.6 的版本所困扰。

## 有好消息

大多数更新的版本(比如 Ubuntu 20.04.3 和 RHEL 8.5)都附带了 Python 3.9。我目前有一个 Ubuntu Server 20.04，它是 Python 3.8 附带的。运行`sudo do-release-upgrade`(要升级到 20.04.3)后，Python 包升级到了 3.9。但是即使是最初的 20.04 版本也包含了 Python 3.8。

是的，你很可能仍然在使用 Ubuntu 18.04，直到 2023 年它仍然被支持。但是 Ubuntu 18.04 附带了 Python 3.6…即将被送下悬崖的版本。因此，尽管离 18.04 还有一年的时间，你的 Python 版本已经过时了。

如果你想在 Ubuntu 18.04 上升级 Python，可以借助 Anaconda。为此，使用以下命令下载 Anaconda 安装程序:

`wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh`

使用以下命令运行安装程序:

`bash Anaconda3-2021.11-Linux-x86_64.sh`

脚本需要一些时间。完成后，注销并重新登录，然后使用以下命令升级 Python:

`conda update python`

更新完成后，您可以使用以下命令检查新安装的版本:

`python3 --version`

您现在应该已经安装了 Python 3.9。

危机避免了。

算是吧。

事情是这样的…你可能正在使用各种各样的库、框架和其他与 Python 3.6 相关的零碎东西。如果你升级到 Python 3.9，不能保证那些外部位不会被破坏。这对你来说意味着什么？这意味着你必须非常小心地对待这个转变。你需要找出你在 Python 3.6 中使用的所有东西，看看 A)每一部分是否也能在 Python 3.9 中运行，或者 B)是否有可用的升级，以便那些外部库和框架能在最新版本中运行。

请理解，这不是一件容易的事，而且很耗时。然而，最终的结果将是值得你努力的。您不想让您的服务器、应用程序和服务在未来几个月里受到 Python 3.6 带来的任何数字灾难的影响。

花费必要的时间和精力将 Python 升级到 3.9，并确保您结合它使用的所有东西都可以按预期升级和运行。

已经警告过你了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>