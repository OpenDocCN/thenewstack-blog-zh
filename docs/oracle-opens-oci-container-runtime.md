# Oracle 发布基于 OCI 的容器运行时

> 原文：<https://thenewstack.io/oracle-opens-oci-container-runtime/>

就在假期周末之前， [Oracle](https://github.com/oracle/) 发布了三个新的开源容器工具。其中包括一个调试工具，一个微容器构建器，最有趣的是，[开放容器倡议的](https://www.opencontainers.org/)[OCI-runtime specification](https://github.com/opencontainers/runtime-spec)的一个实现，称为[轨道车](https://github.com/oracle/railcar)。

Oracle 云开发架构师[唯帅·艾布拉姆斯](https://www.linkedin.com/in/vishvananda/)说，Railcar 的建立是为了确保 [Docker 的](http://www.docker.com) [runc](https://github.com/opencontainers/runc) 不是唯一按照 OCI 规范建立的容器运行时实现。OCI 运行时的 1.0 版本最早将于本周发布。Oracle 的实现内置于 Rust 中，以利用 runc 背后的两种语言 Go、T21 和 C 的一些安全优势。Abrams 是 NASA 最初创建 OpenStack 的团队的前成员，他于 2015 年加入甲骨文。

“在过去的几年里，我为甲骨文的裸机平台团队提供了很多帮助。特别是，我从事过负载平衡器和虚拟机平台等工作。我们希望获得使用容器的一些优势，然而两年前，我们对如何将这些容器投入生产有些担忧，”艾布拉姆斯说。

于是，建立这三个工具的努力就诞生了。另外两个工具， [Smith](https://github.com/oracle/smith) 和 [Crashcart](https://github.com/oracle/crashcart) 也旨在将容器集成到企业已经建立的现有连续部署管道中。因此，Smith 是一个根据企业构建管道设置的一组过程和规范来构建微容器的工具，而 Crashcart 在容器运行时将有用的 Linux 工具附加到容器中，当您创建的容器内部只有一个二进制文件时，可以进行更好的调试。

## 后备箱里没有垃圾

Abrams 说，Smith 帮助开发人员构建更瘦的容器，并对这些图像进行单一的二进制限制，确保不包含任何不良内容。然而，这确实使得对正在运行的容器进行故障诊断变得困难，因为删除多余的二进制文件意味着删除标准的 Linux 工具。Crashcart 按需处理这一缺点，作为分析运行时必须检查的容器的应急工具。

艾布拉姆斯说，轨道车最重要的部分是推动标准化。Docker 就在那里，人们不同意一些事情是如何完成的，所以 [CoreOS](https://coreos.com/) 创造了 [rkt](https://coreos.com/rkt) 。"然后 T4 OCI T5 就形成了，他补充道. "OCI 运行时规范非常重要。你需要一种标准的方式来建造和运行这些东西，”艾布拉姆斯说。

“问题是，OCI 只有一个实现:runc，它在 Docker 中。我所看到的是，当只有一个实现时，事情就变得一团糟，没有变化。并不是说轨道车做的事情和 runc 不一样。其工作原理的实现与 runc 的实现有 98%相同，”艾布拉姆斯说。

这三个工具都可以在 GitHub 上获得，有双重许可:Oracle 的通用公共许可和 Apache 2 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>