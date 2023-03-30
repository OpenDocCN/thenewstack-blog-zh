# 嵌入式 Linux 系统的编译器工具

> 原文：<https://thenewstack.io/compiler-tools-for-embedded-linux-systems/>

这是将 Linux 用于嵌入式系统系列文章的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/an-introduction-to-using-linux-in-embedded-systems/)

.

Linux 基金会赞助了这篇文章。

 [约翰·博尼西奥

John 是 Linux 基金会的 Linux 讲师。](https://www.linkedin.com/in/johnbonesio/) 

当使用嵌入式 Linux 系统时，首先需要的是交叉编译器工具链。

对于外行来说，交叉编译器工具是一套工具(编译器、链接器、汇编器等)。)在编译后的程序中为不同于主机 CPU 的 CPU 指令集生成代码。例如，如果您有一个针对 ARM 的交叉工具链，您将在 x86 笔记本电脑或台式机上编译您的程序，这些程序将在您的嵌入式 ARM 系统上运行，而不是在您的笔记本电脑/台式机上运行。

这篇文章将引用很多术语，比如内核、引导加载程序、根文件系统等等。如果你对这些术语不熟悉，可以回顾一下本系列之前的文章:[第一部分](https://thenewstack.io/an-introduction-to-using-linux-in-embedded-systems/)，[第二部分](https://thenewstack.io/the-major-components-of-an-embedded-linux-system/)。

## 使用现有工具

对于 ARM、PowerPC、MIPS 等等，已经存在预构建的交叉嵌入式工具。如果你使用的是基于 Debian 的 Linux 发行版，比如 Ubuntu，你可以使用 Debian 的软件包系统来安装它们。例如:

`sudo apt-get install gcc-arm-linux-gnueabi g++-arm-linux-gnueabi`

其他 Linux 发行版也可能提供预构建的编译器工具。这些预构建的工具通常支持 C、C++、Objective C、Fortran 等等。还有一些工具支持嵌入式平台中的各种硬件特性，比如浮点单元。

使用这些预构建的工具可能是开始构建嵌入式 Linux 系统的各种软件组件的最简单的方法。

## 构建您自己的工具

如果您需要更多的控制，比如针对大小进行优化，或者对您的处理器特性进行更多的控制，您可以自己构建编译器工具链。

构建交叉编译器工具链相当棘手。为了正确地构建它，需要构建三次来引导整个过程——构建一个简单的编译器来构建库，然后重新构建它来使用库，等等。大多数人不会手工构建交叉编译器工具；相反，他们使用其他工具来构建它们。有一些工具可以用来构建您自己的交叉编译器工具链。这里只是几个比较常用的。

### 十字工具-NG

Crosstool-NG 是一个构建交叉工具链的工具。它还将为您的程序链接构建标准库。你可以在这里找到更多关于 crosstool-NG [的信息。](http://crosstool-ng.github.io/docs/introduction/)

### Buildroot

Buildroot 的目标是构建一个完整的根文件系统——进入/bin、/sbin 等的所有程序。作为这个过程的一部分，Buildroot 还将构建交叉工具链。Buildroot 将为根文件系统构建交叉工具链、共享库和所有二进制程序，并将创建根文件系统的目录层次结构。Buildroot 还可以让您构建内核和引导装载程序。

与 crosstool-NG 相比，Buildroot 的一个优点是它将包含根文件系统中的所有共享库——如果使用动态链接，就需要这些库。使用 crosstool-NG，需要通过其他进程将它们添加到根文件系统中。你可以在这里找到更多关于 Buildroot [的信息。](https://buildroot.org)

### 约克托

Yocto 项目使用了一个名为 bitbake 的工具。Bitbake 是一个为嵌入式系统构建软件包而设计的工具。这些包可以是 RPM 包、Debian 包、ipkg 包或其他包。为了创建这些包，Yocto 项目将构建交叉工具链，并构建一组包及其依赖项。

Yocto 还将创建一个完整的根文件系统，您可以直接使用它，也可以用来调试软件包的安装方式。所以像 Buildroot 一样，Yocto 项目将构建交叉工具链、共享和静态库、根文件系统、Linux 内核和引导装载程序。Yocto 还将创建可以单独安装的软件包。你可以在这里找到关于 Yocto 项目[的更多信息。](https://www.yoctoproject.org)

一旦安装了交叉编译器工具链，就可以构建嵌入式 Linux 系统的各种组件了。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>