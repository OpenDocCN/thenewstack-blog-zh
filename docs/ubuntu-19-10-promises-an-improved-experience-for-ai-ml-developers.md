# Ubuntu 19.10 承诺为 AI/ML 开发者提供更好的体验

> 原文：<https://thenewstack.io/ubuntu-19-10-promises-an-improved-experience-for-ai-ml-developers/>

Canonical 的 Ubuntu 19.10 Linux 发行版已经发布，它很可能是开源平台未来相当长一段时间内更令人兴奋的版本之一。尽管有一些用户界面/UX 的改进，大新闻还是在引擎盖下。来自 [Canonical](https://canonical.com/) 的最新版本不仅包含了对 ZFS 的实验性支持，还为开发者提供了相当多的支持。事实上，如果你是一名人工智能(AI)或机器学习(ML)开发者，Ubuntu 19.10 已经为你准备好了一个大大改进的体验。

## Microk8s

19.10 中一个最大的开发者特有的改进是以集成 AI 的形式出现的。从这个版本开始，不再需要手动安装 Kubeflow，它现在可以作为一个 MicroK8s 附件使用。这个插件大大提高了 Ubuntu 的 AI/ML 能力。根据 Canonical 的说法，开发人员可以在几分钟内完成设置、开发、测试和扩展，以满足他们的应用需求。由于包含了所有必要的依赖项(还包括自动更新和过渡安全修复)，开发人员可以花更少的时间来配置他们的环境，而将更多的时间用于编程和创新。Kubeflow 和 GPU 加速都是在 Ubuntu 19.10 上用 Microk8s 开箱即用的。

### 什么是库伯流

对于那些不熟悉 Kubeflow 的人来说，它是一个免费的开源平台，由谷歌创建，唯一的目的是开发机器学习应用程序(如 Tensorflow)并将其与 Kubernetes 一起部署。这个项目致力于使在 Kubernetes 上部署 ML 工作流变得简单、可移植和可扩展。

### 更多在边缘

与新的 AI/ML 功能相关的是新的边缘计算功能。MicroK8s 将包括严格的隔离，这将确保 Kubernetes 完全隔离和严密安全的生产级环境。任何使用 Microk8s 的人都会喜欢这种更高级别的安全性。因为这一切都是在一个很小的空间内完成的，所以它是边缘网关的理想选择。最重要的是，Microk8s 插件(包括 Istio、Knative、CoreDNS、Prometheus 和 Jaeger)现在可以通过一个命令安全部署。例如，安装 Knative 和 Prometheus 可以通过命令完成:

```
sudo microk8s.enable knative prometheus

```

### 提高了多云基础设施的经济性

随着 19.10 的发布，Ubuntu 现在附带了 Charmed OpenStack 的第 20 个版本(又名 Train)。Train 提供实时迁移扩展，可以帮助电信公司进行基础设施操作，并允许用户将机器从一个虚拟机管理程序移动到另一个虚拟机管理程序(无需关闭操作系统)。与此同时，鹦鹉螺公司发布了 Ceph。这个新版本引入了自动放置组调优功能，极大地改进了 Ceph 分布式存储集群的操作。Ceph 放置组是在对象存储守护进程(OSD)上复制的对象的逻辑集合，以提供更可靠的存储系统。

### 立即下载

Ubuntu 19.10 现在已经可以下载了。你可以在这里获得一个可安装的 ISO [。确保安装完操作系统后，立即运行更新和升级。这可以通过 GNOME 软件或终端命令来完成:](https://ubuntu.com/download) 

```
sudo apt-get update
sudo apt-get upgrade  -y

```

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>