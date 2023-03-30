# K-Bench:衡量 Kubernetes 控制和数据平面性能的基准

> 原文：<https://thenewstack.io/k-bench-a-benchmark-to-measure-kubernetes-control-and-data-plane-performance/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

自然，任何人对一个新集群可能想做的第一件事就是看看它能跑多快。或者，在更实际的层面上，他们可能想要测试他们新奇的云原生应用程序将消耗多少资源。现在， [VMware Tanzu](https://tanzu.vmware.com/tanzu) 团队的项目 [K-Bench](https://github.com/vmware-tanzu/k-bench) 提供了一个基准测试 Kubernetes 性能的框架，以及运行在 K8s 之上的应用程序，也就是测试 Kubernetes 部署的控制平面和数据平面的响应能力。

本周，VMware R & D 的员工性能工程师 Karthik Ganesan 在 [KubeCon+CloudNativeCon](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 与脸书工程师[李勇](https://www.linkedin.com/in/yong-li-65508a28)一起介绍了这项技术。

Ganesan 说，K-Bench 通过部署和操作 Kubernetes 对象来实现这一点。对于控制平面，K-Bench 可以通过多种方式获取性能指标:它通过同时启动 1，000 个 NGINX pods 并对其计时，对 pod 启动延迟进行基准测试。对于存储，它测量建立永久卷的速度，然后测量从 pod 到该卷的读/写速度。一般来说，K-Bench 测量整个搭建过程中所有组件的细粒度关键路径延迟，直到达到所需状态，从服务器和客户端提取事件时间戳。

对于数据平面，模型工作负载被容器化并运行以收集系统信息。K-Bench 包包括 Redis Lab 的 [memtier](https://github.com/RedisLabs/memtier_benchmark) 基准测试的副本，用于测试 CPU 和内存使用情况等。 [FIO](https://fio.readthedocs.io/en/latest/fio_doc.html) 测试 I/O， [qperf](https://linux.die.net/man/1/qperf) 和 [iperf3](https://iperf.fr/) 进行网络测试。该框架是可扩展的，因此用户可以测量他们自己的特定工作负载。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>