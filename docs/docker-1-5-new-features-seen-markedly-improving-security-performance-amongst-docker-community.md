# Docker 在支持 IPv6、只读容器的最新版本中表现出了成熟性

> 原文：<https://thenewstack.io/docker-1-5-new-features-seen-markedly-improving-security-performance-amongst-docker-community/>

Docker 版本 1.5 于本周发布，其亮点是新功能的升级和专注于安全性、IPv6 和改进的统计日志的错误修复。在 Docker 社区通过 GitHub 和谷歌用户组定期提供意见的四轮迭代进展之后，新功能在 Docker 博客上宣布。

总之，功能升级得到了社区的普遍好评。如果没有别的，升级显示了 Docker 的普遍接受，以及为什么 Docker 将成为未来几年打包应用程序的标准变得越来越明显。

主要新功能包括:

## IPv6 支持

Orchard 的创始人、并将其出售给 Docker 的产品经理 Ben Firshman 说，企业客户要么正在向 IPv6 发展，要么已经完全使用 IPv6 了。在 Orchard，他和他的团队创造了 Fig，Docker 采用的网络技术。根据 Docker 的博客帖子，客户现在可以为每个带有新的“–IPv6”标志的容器分配一个 IPv6 地址。IPv6 地址可以从容器内部解析。它还可以用于跨多台主机进行通信。想知道更多吗？正如在[黑客新闻](https://news.ycombinator.com/item?id=9029762)上提到的，在这里阅读[文档](https://docs.docker.com/articles/networking/#ipv6)并在 [GitHub 上关注这个讨论。](https://github.com/docker/docker/pull/8947#discussion_r22534269)

## 只读容器

迄今为止，Docker 的主要安全批评之一是容器可能包含恶意代码，这些恶意代码使运行应用程序或微服务的容器能够在容器外部更改外壳或根脚本。随着 Docker 1.5 的发布，用户可以将容器设置为只读，增加了另一种防止这种风险的方法。

“Docker 社区继续专注于添加新的安全功能，我们在每个版本中都取得了进步，”Firshman 说。只读允许您准确指定运行容器的哪些部分可以修改，从而大大减少您的攻击面

《黑客新闻》上有一个关于所罗门·海克斯(Solomon Hykes)的体面对话，讨论了帖子中提出的问题。

## 改进了容器内部的统计记录

Docker 引入了新的 API 端点，允许从每个容器中更深入地记录应用程序性能和用户体验。虽然用户可以访问 API 来创建自己的仪表板，但应用程序日志服务 [Logentries](https://logentries.com/doc/docker/) 已经基于 Docker Stats API 构建了一个新的 Docker Logentries 容器产品，其中包括用于创建通用仪表板的标准模板。联合创始人兼首席科学家 Trevor Parsons 表示，Logentries 将“使生产环境中的日志记录变得更容易，并将侦听并直接与所有容器通信，并实时发送这些信息。”

## 能够指定在构建中使用的 Dockerfile 文件

Firshman 解释说，能够指定在构建中使用的 docker 文件“通过允许您使用相同的代码生成几个不同的图像，在构建图像时提供了更多的灵活性。例如，您可能希望有一个编译代码的映像，然后有一个不同的映像来运行您编译的代码。这使得这一过程变得更加容易。”

艾德里安·穆特是[集装箱解决方案](http://container-solutions.com/)的首席科学家，他同意这个观点。Mouat 说:“如果你想构建一个以上的映像，你必须使用 shell 脚本，这样就可以在一个构建环境中自动构建多个映像。”

## 使用主机 PID 命名空间

讨论较少的一个新特性是新的 run 命令功能，可以使用—pid=host 标志来使用主机 pid 名称空间。去年在 Docker 上写了关于包装桌面应用程序的文章后，Mouat 对这种开放的潜力感到兴奋。

“我认为 PID 特性可以让更多的工具/应用被包装在容器中。Docker 特别提到，这个特性旨在允许带有调试器的容器检查主机上的进程。我认为这个想法是，你可以下载并运行一个容器，这个容器是专门为调试你正在运行的程序类而设置的，解决你的问题，然后再扔掉这个容器。这可能会节省大量安装和配置专业调试工具的时间。”

詹姆斯·特恩布尔(James Turnbull)对这一更新印象深刻，他是《T4》一书的作者。

“对我来说，Docker 1.5.0 最重要的方面是在稳定性和性能方面的巨大进步。我真的很高兴看到这么多的错误得到修复，性能问题得到解决。围绕网络和图像的更加开放的开发也已经奠定了基础。”

图片 [via](http://www.flickr.com/photos/xiaming/2577691920/in/photolist-4VMm19-aPWKnt-adJTup-cSHwEu-4gLMc1-pU2nho-9qnqUZ-78prAL-4MSVg3-byibb7-oGigRS-hCUo1P-7oiwxu-cjfUe3-7pBFng-fDLxs1-jV6TNm-o2zN7k-hCUotH-fDLxxy-fDtXdx-fDLxm3-73fiEF-9M1Tpv-4cozjw-37zX8Z-hEAe3x-a7DSEP-kBxKZz-hjEf4L-fDLw1A-9XaZY7-8mSPWc-uoStV-jKY16k-hCT8yC-g2Pe48-hjFfjF-a7DSCp-aLbfhT-4Kr3qH-mGMkB-8QAfau-cSHx1b-fqg29v-jxwpFn-7wbeUe-HZ7W-avw8Zh-8YpXwV "New containers") Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>