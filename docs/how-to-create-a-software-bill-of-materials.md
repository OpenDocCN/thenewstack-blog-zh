# 如何创建软件物料清单

> 原文：<https://thenewstack.io/how-to-create-a-software-bill-of-materials/>

虽然有时候你可能会想把“s”放在左边或右边，但在科技领域，我们不是在谈论以“s”开头的四个字母单词的另一个术语。

SBOM 代表软件材料清单，已经成为企业业务和开发人员安全的一个重要方面。从本质上来说，SBOM 是一个嵌套的软件清单，集合在一起服务于一个更大的整体。SBOMs 对于维护成功开展业务所需的高安全标准已经变得绝对必要，尤其是在供应链风险管理方面。

你看，曾经创建的每一个软件都可能包含漏洞，也可能不包含。这只是处理技术的一部分。随着一个软件需要越来越多的依赖，这变得越来越困难。

让我解释一下。

假设您需要安装软件 X 来为您的系统或供应链提供特定的功能。当你去安装软件 X 时，你可能会发现它依赖于软件 1、软件 2、软件 3 和软件 4。因此，为了安装软件 X，您还必须安装所有其他的位。

这在安装开源软件时总是非常明显。例如，当您安装 Node.js 这样的程序时，您会发现它还需要 libc-ares2、libjs-highlight.js、libnode72 和 nodejs-doc。你没想到会这样。尽管您可能已经检查了 Node.js 中发现的当前漏洞，但您可能不知道检查其他所有内容。

在处理集装箱时尤其如此。为什么？因为您依赖的图像不是您创建的，也无法控制。如何知道最新的 [NGINX 镜像](https://www.nginx.com?utm_content=inline-mention)是否没有漏洞？当您构建全栈容器部署时，突然之间您必须考虑多个映像，每个映像都可能包含漏洞。

为此，您使用一个工具来收集您使用的每个映像的软件材料清单。Syft 就是这样一个工具，它可以让你很容易地用 T4 为你使用的 T5 图片生成 SBOM。但是你如何阅读这些信息呢？如果你能找到一个像 Syft 这样的工具，它能产生比你想看到的更多的数据，你会怎么看待它？

让我们看看我们是否能深入挖掘，增加一些清晰度。

## SBOM 标准

幸运的是，已经为 SBOMs 设置了标准，提供了描述已安装软件(或容器映像)组成的通用格式，这使得使用报告数据变得相当容易。

SBOMs 有两个常用标准:

*   软件产品数据交换(SPDX) —是一种国际开放标准，用于列出与软件相关的组件、许可证和版权。使用的格式有 RDF、XLS、SPDX、YAML 和 JSON。
*   [CycloneDX](https://github.com/CycloneDX/specification) —用于应用安全环境以及供应链组件分析。使用的格式是 XML 和 JSON。

安全和开发团队都使用 SBOMs，因此它们遵循标准的事实使得它们通常更容易使用。

## SBOMs 包括哪些内容？

SBOMs 显示有问题的应用程序的完整清单，包括所有开源组件、许可证、版本信息和漏洞。对此需要注意的是，像 [syft](https://github.com/anchore/syft) 、[这样的工具，它们只生成 SBOM](https://thenewstack.io/give-jenkins-a-software-bill-of-materials-with-syft/) ，不包括漏洞。要想在组合中添加漏洞，你必须添加一个像 grype 这样的工具。

也就是说，让我们用 syft 生成一个 SBOM，然后用 grype 生成一个漏洞列表，看看有什么可看的。

## 使用 syft 生成 SBOM

要安装 syft，请打开一个终端窗口并发出以下命令(具有管理员权限):

```
​​curl  -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b /usr/local/bin

```

一旦安装了 syft，拉出一个你想要扫描的容器映像，比如:

现在，使用
运行扫描

Syft 将加载图像，然后，一旦扫描完成，将所有内容输出到终端。显示的信息将类似于这样:

```
nginx                                                   1.23.1-1~bullseye                       deb
nginx-module-geoip                 1.23.1-1~bullseye                       deb
nginx-module-image-filter   1.23.1-1~bullseye                       deb
nginx-module-njs                       1.23.1+0.7.6-1~bullseye        deb
nginx-module-xslt                     1.23.1-1~bullseye                       deb
openssl                                             1.1.1n-0+deb11u3                     deb
passwd                                             1:4.8.1-1                                            deb
perl-base                                         5.32.1-4+deb11u2                       deb
readline-common                     8.1-1                                                     deb

```

这只是您将看到的输出的一小部分，应该很容易理解。左边一列是软件的名称，中间一列是版本号，右边一列是用于安装容器映像应用程序的包管理器。

有了这些信息，您可以查找安装的每个软件包版本，看看是否有任何已知的漏洞。或者，你可以走捷径，使用 [grype](https://github.com/anchore/grype) ，来自 [Anchore](https://anchore.com/?utm_content=inline-mention) 。

## 使用 grype 生成漏洞报告

SBOM 的信息会给你很多细节，但缺少一个非常重要的元素——漏洞。为此，我们将使用命令安装 grype:

```
curl  -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b /usr/local/bin

```

现在，让我们使用
对同一个容器图像运行 grype 扫描

该命令的输出将包括如下详细信息:

```
passwd                  1:4.8.1-1                                                         deb     CVE-2007-5686        Negligible
passwd                  1:4.8.1-1                                                         deb     CVE-2013-4235        Negligible
perl-base              5.32.1-4+deb11u2     (won't  fix)        deb     CVE-2020-16156     High
perl-base              5.32.1-4+deb11u2                                    deb     CVE-2011-4116        Negligible
tar                             1.34+dfsg-1                                                   deb     CVE-2005-2541        Negligible
util-linux               2.36.1-8+deb11u1                                      deb     CVE-2022-0563      Negligible
zlib1g                     1:1.2.11.dfsg-2+deb11u1                     deb     CVE-2022-37434   Critical

```

现在，我们来谈谈。下面是如何阅读上面的输出:

*   第 1 列(最左侧)—已安装软件包的名称。
*   第 2 列—已安装软件包的版本号。
*   第 3 列—用于安装软件的软件包管理器。
*   第 4 列— CVE 漏洞列表。
*   第 5 栏——CVE 脆弱性评级。

此时，您不仅知道安装在容器映像中的每一个软件，还知道它是否包含任何已知的漏洞。这些信息对于您的安全和开发团队来说绝对是无价的。例如，正如您在上面看到的，NGINX 容器中包含的 zlib1g 包有一个严重的漏洞。随着 CVE 上市，你可以研究一下，看看它是否会影响你的业务。如果是这样的话，你的开发团队要么修复这个漏洞，要么等待官方的 NGINX 映像被修补。

尽管您可能会倾向于忽略 syft 而支持 grype，但这两种工具都有其用途。但是不管你用什么工具来生成你的 SBOMs，确保你理解输出，这样你就可以更有效地利用它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>