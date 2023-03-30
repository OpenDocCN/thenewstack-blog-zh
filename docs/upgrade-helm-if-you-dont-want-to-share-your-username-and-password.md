# 升级头盔，如果你不想分享你的用户名和密码

> 原文：<https://thenewstack.io/upgrade-helm-if-you-dont-want-to-share-your-username-and-password/>

如此多的安全漏洞，当你开始着手处理时，是非常糟糕的。最新的一款是[赫尔姆的 CVE-2021-32690](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-32690) 。所有 [Kubernetes](https://kubernetes.io/) 用户都知道，Helm 是 Kubernetes 的软件包经理。在开发头盔源代码时，一名头盔核心维护人员发现——哎呀！—您很容易设置这样一种情况，即与一个 Helm 存储库相关联的用户名和密码凭据可能会被传递到另一个域。嗷。

回顾一下，你可以把 Helm 看作是 Kubernetes 对 Linux 的 [yum](https://access.redhat.com/solutions/9934) 或 [apt](https://wiki.debian.org/Apt) 程序的接管。的确，Helm's charts 有点像 Linux 的 RPM 和 DEB 包，它将所有版本化的、预配置的程序资源收集到一个可部署的 YAML 包中。而且，就像那些 Linux 包一样，你需要小心你放在里面的东西，以免事情变得很糟糕。

因此，当一个 Helm 核心维护人员在处理 Helm 源代码时发现，存在这样的情况:与一个 Helm 存储库相关联的用户名和密码凭证可能会被传递到该 Helm 存储库引用的另一个域。跟我一起说，“呜呜！”

具体来说，一个 Helm 图表存储库包括一个 index.yaml，它可以包含一个参考，用于获取每个图表版本的图表存档。该引用可以相对于 index.yaml 文件，也可以是指向位置的 URL。URL 可以指向任何域，这是 Helm 用户利用的一个功能。如果我见过这种技术被使用一次，那我就已经见过它被使用一百次了。

因此，例如，您的 index.yaml 文件可以托管在 GitHub 页面上，而图表归档作为 GitHub 版本托管。它们位于不同的域名上，index.yaml 文件指向另一个域。到目前为止，一切正常。

但是，这是一个很大的但是，当用户名和密码与 Helm 存储库相关联时，用户名和密码也会传递给 index.yaml 文件中引用的其他域。当 Helm 去检索另一个域上的特定图表档案时，就会出现这种情况。

雪上加霜的是，默认情况下，您的用户名和密码被传递到了 Helm 存储库的 URL 位置。用户名和密码的范围是 Helm 存储库的方案、主机和端口。简而言之，你的信息到处传播。

这个 bug 存在于从第一天到头盔 3.6 的所有头盔版本中。现在已经在头盔 3.61 中[修复了。二进制文件可用于 macOS、Linux 和 Windows 平台。](https://github.com/helm/helm/releases/tag/v3.6.1)

当然，您可能需要您的用户名和密码来访问舵图。您仍然可以通过使用 new–pass-credentials 标志将用户名和密码传递给其他域。此标志将单个存储库的旧行为恢复为选择加入行为。

作为一种解决方法，如果您使用了 Helm 存储库的用户名和密码，您可以审计 Helm 存储库，以查看另一个域是否已经收到了凭据。为此，在存储库的 index.yaml 文件中查找 URL 列表中的其他域。如果找到了另一个域，并且下载或安装了该图表版本，那么恭喜您，该域的所有者可以访问您的凭据。让我们希望他们没有，并尽快升级到头盔 3.61，以确保你再也不用担心这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>