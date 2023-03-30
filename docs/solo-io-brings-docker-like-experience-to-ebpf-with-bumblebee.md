# Solo.io 通过大黄蜂为 eBPF 带来“码头工人般的体验”

> 原文：<https://thenewstack.io/solo-io-brings-docker-like-experience-to-ebpf-with-bumblebee/>

服务网格集成软件提供商 [Solo.io](https://solo.io/?utm_content=inline-mention) 发布了[大黄蜂](https://bumblebee.io/)，这是一个新的开源项目[称](https://www.solo.io/blog/get-started-with-ebpf-using-bumblebee/)“为 eBPF 带来 Docker 般的体验。”

Solo.io 首席执行官兼创始人 [Idit Levine](https://www.linkedin.com/in/iditlevine) 表示，为了提高度量等特定领域的性能，Solo.io 转向了[扩展的伯克利数据包过滤器(eBPF)](http://ebpf.io/) 以便“简化 HTTP 堆栈”。eBPF 为 Linux 用户提供了一种在内核空间中运行沙盒程序的方法，而无需更改内核源代码或加载模块。然而，编写 eBPF 应用程序需要多个任务，Solo.io 团队发现他们不得不花费时间为每个运行环境重新编译程序。

## **便携性问题**

Levine 解释说，编写 eBPF 程序涉及多个任务，从编写程序本身，到编写与之交互的用户模式程序，再到将 C 源代码编译成特定内核的 eBPF 字节码，这导致了可移植性问题。

由于 Linux 内核不是向后兼容的，为一个内核编译的 eBPF 字节码不能在不同版本的内核中使用。例如，如果一个 eBPF 程序在一个版本的内核中读取一个结构中的字段，而在一个较新的内核中，该结构的字段顺序发生了变化，程序现在将读取错误的字段，”Levine 在一封电子邮件中解释道。

有一段时间，解决方案是以源代码的形式发布 eBPF 程序，以便在运行它的机器上编译。这也意味着程序的依赖项需要随之而来。然而，最近的一个变化使得修复这个可移植性问题成为可能，就像 Docker 帮助开发人员解决应用程序可移植性一样。

Levine 解释说，添加了 [BPF 类型格式(BTF)](https://www.kernel.org/doc/html/latest/bpf/btf.html) “(以及 clang 中添加的一些智能)使得 BPF 程序加载器能够修复 BPF 字节码，以便在不同版本的内核上正确工作。例如，如果一个 BPF 程序访问一个结构，clang 现在将所有这些结构访问存储在 BPF 程序二进制文件中的一个特殊位置。libbpf 可以访问这些结构中的每一个，并使用来自当前内核的 BTF 信息(在运行时获得)来将这些访问固定到正确的偏移量。”

## **大黄蜂前来救援**

随着 BTF 的加入，Solo.io 创建了 BumbleBee，它不仅使用 BTF 来解析 eBPF 程序的地图并将其带到用户空间，还为 eBPF 应用程序使用了[开放容器倡议(OCI)图像规范](https://github.com/opencontainers/image-spec)，这意味着它们可以更容易地存储和分发，并集成到现有的工作流中。

“现在你基本上可以在任何地方构建它，并在任何地方运行它，这使你能够像 Docker 容器一样分发它，”Levine 说。“它让您能够在一个命令行中获取云中注册表上的内容，并在您的内核上运行它，这非常疯狂。”

除了简化 eBPF 程序的分发，BumbleBee 还自动化了样板文件，包括用户空间代码，让用户自己编写 eBPF 代码。

总之，莱文说她在索洛使用这个项目时立即看到了大黄蜂的效果。

“我认为我们在公司内部看到的是巨大的速度提升。我觉得这不仅仅是我的员工，而是整个社区。这正是 Docker 潜在的效果，它能够让社区编写 eBPF 并让其他人运行它。我认为这很重要，”莱文说。

BumbleBee 本身是一个命令行工具，需要 Linux 内核版本 5.4 或更新版本，以及一些命令的知识——bee init、build、run、list 和 push——才能[入门](https://www.solo.io/blog/get-started-with-ebpf-using-bumblebee/)。

[https://www.youtube.com/embed/4js-blTUV1Q](https://www.youtube.com/embed/4js-blTUV1Q)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>