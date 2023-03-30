# Arcadia 如何简化 Hadoop 堆栈的基于角色的访问控制

> 原文：<https://thenewstack.io/tns-tutorial-friday-arcadia-data-redefining-security-apache-hadoop/>

当将传统的商业智能软件与 Apache Hadoop 集成在一起时，开发人员经常发现自己陷入了在不同应用程序间协调访问角色的困境。Hadoop-原生安全和管理平台 [Arcadia Data](https://www.arcadiadata.com/) 利用 Cloudera 的安全特性，允许开发人员管理、分配和保护团队成员访问信息所需的角色。Arcadia Sentry 服务在 [Cloudera](https://www.cloudera.com/) 内部建立，包括角色管理和定义，允许管理员更好地控制其堆栈内的权限。

在这个简短的教程中，Arcadia Data 的解决方案工程师 Shaun Ahmadian 探讨了用户如何设置哨兵服务、定义和管理角色、定义用户权限以及维护系统安全。通过将 Arcadia 与 [Kerberos](https://web.mit.edu/kerberos/) 认证协议集成，用户能够根据访问信息的个人的配置文件和权限从 Hadoop 中访问数据。

[https://www.youtube.com/embed/2rf7VNdRpH4?feature=oembed](https://www.youtube.com/embed/2rf7VNdRpH4?feature=oembed)

视频

Arcadia Data 利用三个组件组成其权限选项卡。这些包括“系统”，其中包括查看系统日志，“连接”和“数据集”，这是其可视化所基于的对象。在创建了一个具有安全分析师角色的新用户后，Fishman 指出“对于安全分析师，我们将只授予他们访问安全日志的权限。我们不会给他们实际管理和创造新的视觉效果的能力，或者进行探索。这将纯粹是一个查看特权。”

通过利用基于角色的访问控制(RBAC), Arcadia 数据用户被分配权限，允许他们根据其角色可以访问的信息创建、查看和管理数据。管理员不再需要为不同的平台重新创建安全性。Arcadia 在安装时批量导入角色，并在底层哨兵角色改变时镜像这些角色定义。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>