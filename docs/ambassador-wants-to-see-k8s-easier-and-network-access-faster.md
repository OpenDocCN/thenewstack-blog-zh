# 大使希望看到 K8s 更容易，网络访问更快

> 原文：<https://thenewstack.io/ambassador-wants-to-see-k8s-easier-and-network-access-faster/>

大使实验室的最新版本代表了一项雄心勃勃的努力，旨在帮助开发人员和运营团队进行 Kubernetes 的部署和管理。对于拥有大使云版本 [Teams Edition 的开发人员来说， 已经进行了改进，现在，作为 CI/CD 管道的一部分，整个团队在开发和部署软件时可以同时协作，而不是单个开发人员使用大使堆栈上传和更新 Kubernetes 环境的代码和应用。运营团队受益于管理和上传应用程序的网络性能的提升，以及对 HTTP/3 协议的支持和对 3.0 版 Edge Stack 的其他改进，完全支持 Envoy v3 APIs。](https://blog.getambassador.io/https-blog-getambassador-io-build-faster-and-ship-safer-on-kubernetes-as-a-team-1ff4e3fc105)

“我们有两个角色:开发者和平台工程师，”大使实验室开发者关系主管丹尼尔·布莱恩特告诉新堆栈。“工程师经常建立基础设施，开发人员的专业知识从 Kubernetes 上的超级专家到那些希望从 Kubernetes 中抽象出来交付应用的人都有。我们专注于帮助开发人员完成后者，并使任何摩擦点变得更容易。”

## 或多或少的 Kubernetes

Bryant 说，有了 Ambassador，平台工程师通常会设置和安装基础设施，并完成“繁重的工作”。这为开发者创造了条件，他们可以根据自己的意愿获得或多或少的 Kubernetes。[正如之前报道的](https://thenewstack.io/how-a-flexible-control-plane-helps-deploy-apps-on-kubernetes/)，Ambassador 可以生成 YAML 文件，对于使用 Kubernetes 环境的开发人员来说，这是一项比较麻烦和乏味的任务。“许多开发者不想写 YAML，”布莱恩特说。“我们这样做是为了让他们可以专注于应用程序代码，而不用担心 YAML。”

平台工程师配置好入口后，开发人员从菜单中选择图像和容器，并在发出拉请求后监控代码的部署。

## 提高网络性能

对开发者来说，这个版本的主要推动力是帮助团队利用 Ambassador 扩展 Kubernetes 的部署。“我们现在让从一个开发者到整个团队变得更容易了，”科比说。“开发人员更喜欢预配置的解决方案，我们希望为整个团队安全可靠地进行代码发布和运行”，而不是将它的使用局限于单个开发人员。

Ambassador Labs 通过在[Ambassador Edge Stack 3.0](https://www.getambassador.io/docs/edge-stack/latest/topics/install/upgrade/helm/edge-stack-2.3/edge-stack-3.0/)中添加 HTTP/3 支持等方式，提高了 Kubernetes 应用部署和管理的网络性能。它还增加了对使者入口的支持，这是该公司最初捐赠的 CNCF 项目。这有助于管理和观察从互联网到他们的 Kubernetes 服务的流量。

该公司表示，73%的浏览器和超过 25%的网站使用 HTTP/3 协议在网上交换数据，HTTP/3 对有损耗网络的用户尤其有利，例如那些连接到手机、物联网设备或服务于新兴市场的应用的用户。新协议通过快速重新连接和减少延迟而增加的弹性有利于许多不同类型的互联网应用，包括典型的网络浏览、电子商务或基于网络的交互式应用的使用。

在一篇 [的博客文章](https://blog.getambassador.io/benchmarking-http3-performance-envoy-proxy-and-edge-stack-96c37faac832) 中，Bryant 写道:“ 值得一提的是，互联网上的平均数据包丢失率为 2%，投资于您的应用程序的 HTTP/3 支持可以提供前瞻性的能力，以处理网络中任何因地理位置而增加的性能下降。”

Bryant 告诉新的堆栈，由于支持 HTTP/3，网络质量因此“取决于您的使用情况，可以得到相当大的改善”，并补充说 Ambassador 是第一个支持该协议的边缘网关。“重点是延迟和有损耗的网络，”布莱恩特说。

Bryant 告诉新的堆栈，由于支持 HTTP/3，网络质量因此“取决于您的使用情况，可以得到相当大的改善”，并补充说 Ambassador 是第一个支持该协议的边缘网关。“重点是延迟和有损耗的网络，”布莱恩特说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>