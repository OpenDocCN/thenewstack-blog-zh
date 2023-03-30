# Mesos 将通过统一的容器支持多种容器格式

> 原文：<https://thenewstack.io/mesos-simplifies-support-container-formats-unified-containerizer/>

自 2014 年末以来，Apache Mesos 一直支持 [Docker](https://www.docker.com) 作为其默认[容器](http://mesos.apache.org/documentation/latest/docker-containerizer/)的替代。但是现在流行的开源集群调度器平台在一个更简化的方法上接近完成，该方法旨在取代两个现有的容器，希望简化框架的未来开发。

除了这个目标，这个新的“统一容器”将允许更新的容器格式更容易地添加到 Mesos 中。像 [rkt](https://coreos.com/rkt/) 、 [appc](https://github.com/appc) 这样的项目以及[开放容器倡议](https://www.opencontainers.org)的任何未来测试都是更广为人知的 Docker 格式的替代方案，随着时间的推移，它们可能会变得更加流行，因为每个都找到了自己的利基用例。

在解释这一变化的动机时，维护者在最近更新的文档[中说:](http://mesos.apache.org/documentation/container-image/)

维护两个集装箱很难。例如，当我们向 Mesos 添加新特性(例如，持久卷、磁盘隔离)时，更新两个容器就成了一种负担。更糟糕的是，有时某些资源的隔离(例如代理上的网络句柄)需要两个容器之间的协调，这在实践中很难实现。”

统一 Mesos 容器简化了调度器调用的 API，如 [Marathon](https://mesosphere.github.io/marathon/) 或 [Chronos](https://mesos.github.io/chronos/) ，消除了不断更新生态系统的需要，因为这些新的运行时会随着时间的推移而增加。相反，细节将从那些高级框架中抽象出来，并作为映像提供者和运行时隔离器来实现。

这一变化意味着，在您自己的集群中添加对新容器类型的支持将只需要对 **mesos-slave** 服务添加一些额外的参数，这比 Docker 容器首次在 mesos 中引入时进步了一大步。这个新的映像提供者抽象还允许更多的选项在本地部署容器映像，而不需要 Docker 注册表，这可能是小商店的一个痛点。

即使这一新功能被添加到即将到来的 0.28 版本中，经验丰富的 Docker on Mesos 用户也可能希望在切换到这一新方法之前等待一段时间。在发布时，将只支持较新的 v2 Docker 注册表 API，也不支持桥接网络。

私有注册的使用一开始也会有点笨拙。然而，这标志着在 Mesos 上成熟容器故事的另一个重要步骤，并将使该平台在整个 IT 领域的快速发展时期继续保持可行性和稳定性。

Docker 是新堆栈的赞助商。

通过 Pixbay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>