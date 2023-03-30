# Amazon Web Services 发布了为容器构建的 Linux 发行版

> 原文：<https://thenewstack.io/amazon-web-services-releases-a-linux-distribution-built-for-containers/>

亚马逊网络服务公司发布了一个预览版的 [Bottlerocket](https://aws.amazon.com/bottlerocket) ，这是一个基于 Linux 的开源操作系统，用于托管容器。

与大多数发行版不同，Bottlerocket 只包含托管容器所必需的包。它支持所有符合[开放容器倡议](https://www.opencontainers.org/) (OCI)规范的容器图像格式。

对于编排，这个版本的 Bottlerocket 专门与[亚马逊 EKS 管理的 Kubernetes 服务](https://aws.amazon.com/eks/)一起工作，该公司欢迎其他人为其他编排引擎调整代码。

Bottlerocket 不使用 Linux 的传统更新机制。而不是更新单个的包。Bottlerocket 更新作为单个新映像的一部分进行收集和发布。AWS 声称，这种方法使得快速、轻松地更新大量容器图像变得更加容易。如果用户发现映像由于某种原因不适合，可以回滚到早期的工作版本。

这种方法减轻了许多组织在保持 Linux 发行版更新时面临的安全性和性能挑战。这样的发行版是由数百个第三方库和工具构建的。随着时间的推移，这些包中会出现安全漏洞，必须由这些发行版的用户或维护者单独更新。

Bottlerocket 在许多其他方面不同于其他 Linux 发行版。它使用的文件系统大部分是只读的。每次启动时，文件系统的完整性都由 [dm-verity](https://www.kernel.org/doc/html/latest/admin-guide/device-mapper/verity.html) 进行加密检查。为了保持云安全的最佳实践，出于安全原因(尽管 AWS 提供了一个单独的管理容器，可以提供 ssh 访问以进行故障排除)，Bottlerocket 映像不能被 [ssh](https://thenewstack.io/dr-torq-go-remote-with-ssh/) 访问。

几乎所有的第一方组件都是用 [Rust](https://www.rust-lang.org/) 编写的，这是一种新兴的系统语言，旨在最小化内存安全问题和远程安全设计。

AWS 看到了简化容器主机的需求，因为它看到了自己的大量客户群和亚马逊 ECS。AWS 首席传播者[杰夫·巴尔](https://aws.amazon.com/blogs/aws/author/jbarr/)在[的博客文章](https://aws.amazon.com/blogs/aws/bottlerocket-open-source-os-for-container-hosting/)中称，超过 80%的基于云的容器运行在 AWS 上。

AWS 并不是唯一一个为管理容器而构建简化的 Linux 发行版的公司。SUSE 提供 [MicroOS](https://en.opensuse.org/Kubic:MicroOS) 。还有基于 Kubernetes 的 [Talos](https://www.talos.dev/) ，以及[红帽的 Enterprise Linux CoreOS](https://access.redhat.com/documentation/en-us/openshift_container_platform/4.1/html/architecture/architecture-rhcos) ，它将红帽 Enterprise Linux 与 CoreOS Container Linux 结合在一起，后者是红帽在 2018 年以[其购买的](/docker-acquiring-coreos-red-hat-aims-kubernetes-company/)core OS 收购的。

该项目是 AWS 为帮助用户更容易适应其云服务而采取的众多开源举措之一。该公司最近还发布了 cdk8s，这是一个使用面向对象编程的 Kubernetes 本地应用和抽象库

Bottlerocket 的 [GitHub repo](https://github.com/bottlerocket-os/bottlerocket) 列出了该项目的 14 名贡献者，他们至少从 2019 年 3 月开始就一直在从事这项工作。该发行版至少记录了 [61 个问题](https://github.com/bottlerocket-os/bottlerocket/issues)，项目团队欢迎[错误报告](https://github.com/bottlerocket-os/bottlerocket/issues)，以及[拉取请求](https://github.com/bottlerocket-os/bottlerocket/pulls)。它同时获得了阿帕奇和麻省理工的许可。

潜在用户可以参考 Bottlerocket 的快速入门指南，在 EKS 集群上设置它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>