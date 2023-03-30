# PyTorch 在软件供应链攻击中中毒

> 原文：<https://thenewstack.io/pytorch-poisoned-in-software-supply-chain-attack/>

如果你在 2022 年 12 月 25 日到 2022 年 12 月 30 日之间通过 pip 在 Linux 上下载了 PyTorch-nightly，那你就有麻烦了。

有人，我们仍然不知道是谁，上传了一个[中毒的 Python 包索引(PyPI)依赖关系](https://pytorch.org/blog/compromised-nightly-dependency/)，它隐藏在真实的依赖关系名称 torchtriton 下。一旦就位，[山寨](https://snyk.io/advisor/python/torchtriton) [火炬](https://snyk.io/advisor/python/torchtriton) [3.0.0](https://snyk.io/advisor/python/torchtriton) 就会运行恶意二进制。

一旦就位，这将获取以下系统信息:

*   来自 */etc/resolv.conf* 的名称服务器
*   来自*的主机名 gethostname()*
*   来自 *getlogin()* 的当前用户名
*   当前工作目录名来自 *getcwd()*
*   环境变量
*   阅读以下文件
    *   */etc/hosts*
    *   */etc/passwd*
    *   *$HOME/** 的前 1000 个文件
    *   *$HOME/。gitconfig*
    *   *$HOME/。ssh/**
*   通过加密的 DNS 查询将所有这些信息(包括文件内容)上传到域*.h4ck[。]cfd，使用 DNS 服务器呼哧呼哧。]木卫一。

## 正是你假期后需要的，对吗？

好消息是，这种供应链攻击只针对夜间构建。如果你不用这些，你就安全了。

您可能想知道这是如何发生的，因为恶意代码没有被复制到好的版本上。PyTorch 团队解释说:“由于 [PyPI 索引优先于](https://github.com/pypa/pip/issues/8606)，这个恶意的包被安装了，而不是我们官方仓库中的版本。这种设计允许某人用与第三方索引中存在的相同名称注册一个包，pip 将默认安装他们的版本。”

## 哎哟

尽管如此，好消息是这是“唯一的”夜间。坏消息是 PyTorch 非常受新锐机器学习开发者的欢迎。于是， [火炬](https://archive.is/6r1mr) [的](https://archive.is/6r1mr)[恶意软件版本最终被下载了 2386 次](https://archive.is/6r1mr)。这是一大堆混乱的开发机器。

那么，你现在做什么？

首先，用下面的命令检查您是否有案例:

```
python3  -c  "import pathlib;import importlib.util;s=importlib.util.find_spec('triton');  affected=any(x.name  ==

```

如果你尽快转储坏文件。您可以通过卸载它，并用日期为 2022 年 12 月 31 日或之后的命令替换它:

```
$  pip3 uninstall  -y  torch torchvision torchaudio torchtriton

$  pip3 cache purge

```

这次攻击比你想象的要容易。正如 [Endor Labs](https://www.endorlabs.com/) 安全研究员 Henrik Plate 所观察到的，“[依赖混淆攻击](https://www.endorlabs.com/blog/introducing-the-state-of-dependency-management-report)是 2022 年最常用的攻击载体之一，其中大部分针对私有二进制存储库上托管的公司内部软件包(而不是 PyTorch 案例中的开源软件包)。这是因为制造(和自动化)这样的攻击相对便宜，因为攻击者不需要干涉现有的合法项目的任何资源。相反，他们可以在公共包存储库中保留合法包的名称，如 PyPI 或 npm。

所以，再一次，带着感情，采用安全扫描器，而不是仅仅相信最新的代码是安全的。有很多黑客已经做好准备，等着在你的程序和机器上插入坏代码。

基于 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) ， [Pytorch](https://pytorch.org/) 是一个流行的[开源机器学习框架](https://thenewstack.io/pytorch-takes-ai-ml-back-to-its-research-open-source-roots/)，支持[多种多样的数学运算](https://www.techtarget.com/searchenterpriseai/definition/PyTorch)和深度学习运算。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>