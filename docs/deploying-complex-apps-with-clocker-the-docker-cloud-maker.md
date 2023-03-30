# 利用 Docker 云制造商 Clocker 部署复杂的应用程序

> 原文：<https://thenewstack.io/deploying-complex-apps-with-clocker-the-docker-cloud-maker/>

在 DockerCon Europe 上，Cloudsoft 的 Andrew Kennedy 做了一个 Docker cloud maker 的演示。他展示了如何通过 [SoftLayer 的](http://www.softlayer.com/)分布式基础设施，使用孵化器项目 [Apache Brooklyn](https://brooklyn.incubator.apache.org/) 来简化向 Docker 部署复杂应用的过程。

[https://www.youtube.com/embed/7umGdpDHhzI?feature=oembed](https://www.youtube.com/embed/7umGdpDHhzI?feature=oembed)

视频

Clocker 利用了布鲁克林的蓝图，因此不必从头开始创建 Dockerfiles 和 images。有了使用 YAML 文件的蓝图，Clocker 会自动创建 Clocker 文件。在这个例子中，Kennedy 使用了一个 [Riak](http://basho.com/riak/) 、 [Basho 的](http://basho.com/) NoSQL 数据库的蓝图来展示它是如何被部署的。

在演示中，Kennedy 展示了一个 YAML 文件如何描述一组服务:一个 Riak 集群和一个由 [Nginx](http://nginx.com/) 提供的 web 应用集群。它有三个节点是 JBOSS 服务器。YAML 文件被复制并发送到 Docker cloud，Docker cloud 是 Clocker 在 SoftLayer 中管理的一组虚拟机，每个虚拟机都运行 Docker Engine 的副本。

Clocker 运行 Docker 基础设施。每个 Docker 主机都由 Clocker 管理。它显示 CPU 利用率，内存使用和其他信息。还有一个自动扩展策略，以确保用户有扩展和创建更多容器的空间。如果开发人员开始用完，Clocker 将创建一个虚拟机，部署 Docker 引擎并设置它。在设置中， [Weave](http://weave.works/) 被用作覆盖网络来连接多个运行 Docker 的主机。它允许开发人员运行更复杂的应用程序，而不必担心端口转发等问题。

在最终部署中，网址显示了由不同组件构建的应用程序。管理功能之一是扩展能力。例如，Riak 管理页面显示了正在进行的变更和正在添加的节点。Clocker 正在使用新的 Docker 容器扩展 Riak 集群，这些容器可以通过 web 应用程序访问。

云软和 Basho 都是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/alancleaver/2661425133/in/photolist-54buYe-4pcoL6-ajVTPV-67X3cp-6UTokr-4iC8YP-dff6Z4-dffa8m-dff987-fLkCim-fLkACo-fLkxHb-dffcuJ-dffbC1-bXcg7w-6nUTfw-nvZdFV-5QRfPt-oF3cuE-syhqo-9GCRGh-dFXzSm-tw5Xp-tFZXM-a5qRqq-5EBQdg-8fjWy3-tv4wq-5EDEL6-5EFd93-68ZzFg-5EBJxV-Gtmcy-53X9jk-8RWmDx-4kz2wS-tv4x5-5W4ukX-5EBTsP-gRxJ73-gRxKic-5EFmpy-5EHLWS-5EBQNB-9G73jH-5VenAs-9fn2xc-4ChFw1-5EG7h7-5EBLVx)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>