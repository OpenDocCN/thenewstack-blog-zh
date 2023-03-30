# 护链:这都是关于基地形象

> 原文：<https://thenewstack.io/chainguard-its-all-about-that-base-image/>

在我们的容器驱动的技术世界中，容器的基本映像，我们用来创建工作容器映像的基础，必须尽可能没有错误，这一点至关重要。[chain guard](https://chainguard.dev/),[零信任安全](https://thenewstack.io/zero-trust-security-and-the-software-development-lifecycle/)公司，在其新白皮书“[关于基础图像](https://chainguard.dev/blog-static/chainguard-all-about-that-base-image.pdf)”中深入探讨了集装箱图像安全的主题唉，他们发现一些“流行的基础图像可能有数百个已知的安全漏洞。”这不是建造容器的方法！

开发人员明智地选择基本容器映像只是常识。否则，他们将面临安全问题。借用技术债务的概念，Chainguard 将这些基础映像漏洞描述为“安全债务”

不幸的是，根据他们的研究，太多流行的基础图片，已经被下载了数十亿次，带有数十或数百个已知的安全漏洞。甚至在您开始构建应用程序之前，您的映像中就有大量的安全债务需要克服！

## 该过程

Chainguard 使用 [GitHub](https://github.com/) code search 从公开可用的容器映像“Dockerfile”规范中收集数据，以确定哪些是最流行的基础映像。最上面的图片基于 [Alpine](https://alpinelinux.org/) 、 [Ubuntu](https://ubuntu.com/) 和 [Debian](https://www.debian.org/) Linux。其他流行的基础映像是特定于编程语言的应用程序，如 Node/Javascript (node.js)和 Java (OpenJDK)。

然后，他们使用广受好评的容器图像静态分析工具检查这些图像。有[trivy](https://github.com/aquasecurity/trivy)(0 . 23 . 0)[grype](https://github.com/anchore/grype)(0 . 32 . 0)[Snyk](https://snyk.io/)(0 . 16 . 0)。最差的图像是 Debian Node 17 的基本图像。

该报告的作者，[约翰·斯皮德·迈耶斯](https://www.linkedin.com/in/john-speed-meyers-66b6a740/)和[扎克·纽曼](https://github.com/znewman01)报道说，“根据扫描仪的不同，这张基础图像中可能有数百个或近千个已知漏洞。这一债务水平甚至会让美国医学院的学生汗颜。”

然而，Alpine(节点:17-alpine)在设计时将安全性放在首位，根据分析测试，它有 0 到 4 个漏洞。这表明节点基础映像的漏洞存在于基础操作系统映像本身，而不是节点 JavaScript 代码。

二十五到一百个中低级别的漏洞，Debian，Red Hat Universal Base Image，Ubuntu images 大致相同。不到十个软件包的 Alpine base 映像没有已知的安全漏洞。也就是说，安全漏洞每天都会出现，基础映像也在不断变化。换句话说，一般来说，Alpine 图像是安全的，但你不能假设即使 Alpine 也是永远安全的。

其他基础映像开发人员也可以提高其映像的安全质量。正如 Alpine 的程序员所展示的，这是可以做到的。

## 安静的基本图像

Chainguard 称，许多安全“污垢”来自图像的杂乱。这是那些无关的和不必要的包，在基础映像中运行。如果你的容器不需要函数，就不要包含它的包。例如，简单地从基础映像中删除一个外壳就关闭了攻击者潜在的不必要的访问点，将一扇敞开的门变成了一堵砖墙。

当然，这些最小基础映像应该很少或没有报告的漏洞。这给大家减轻了负担。开发人员避免对漏洞进行分类。安全团队避免制作冗长的漏洞和补救措施 Excel 列表。软件用户更快更便宜地获得安全软件。

因此，Chainguard 建议容器基础映像开发人员应该致力于创建“安静”的基础映像。这种安静的基础映像是具有很少或零报告漏洞的最小映像，并且包括[软件材料清单(SBOM)](https://thenewstack.io/create-a-software-bill-of-materials-for-your-operating-system/) 和内置数字签名。这将比我们目前的现状好得多。

除了简单地制作更安全的图像，从而减少安全债务，这些也将减少开发人员的工作量，提高开发速度。谁不想这样呢？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>