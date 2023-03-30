# 教程:使用 KubeSphere 管理数字海洋 Kubernetes 和亚马逊 EKS

> 原文：<https://thenewstack.io/tutorial-use-kubesphere-to-manage-digitalocean-kubernetes-and-amazon-eks/>

[](https://github.com/feynmanZhou)

 [费曼周

费曼是 QingCloud 的大使和开源社区经理，他正在发展和维护 KubeSphere 社区，该社区帮助用户广泛采用 Kubernetes，并减少使用云原生技术的学习曲线。](https://github.com/feynmanZhou) [](https://github.com/feynmanZhou)

[KubeSphere](https://kubesphere.io/) 是一款开源分布式操作系统，用于管理云原生应用。使用 Kubernetes 作为其内核，KubeSphere 为无缝集成第三方应用程序提供了一个即插即用的架构，以促进其生态系统。 [KubeSphere 可以在任何地方运行](https://kubesphere.io/docs/introduction/what-is-kubesphere/#run-kubesphere-everywhere),因为它是高度可插拔的，不需要侵入 Kubernetes。

KubeSphere 的开发旨在解决多集群和多云管理挑战，并实施后续用户场景，为用户提供统一的控制平面，以将应用程序及其副本分发到从公共云到内部环境的多个集群。

## KubeSphere 的 Kubernetes 集群联盟

基于 Kubernetes 集群联盟(简称为 [Kubefed](https://github.com/kubernetes-sigs/kubefed) )，KubeSphere 实现了多集群管理，允许集群管理员轻松管理跨云提供商的多个 Kubernetes 集群。

在本教程中，我们将在数据中心安装一个主机集群，充当成员集群的控制面板。然后我们使用两个流行的托管 Kubernetes 服务， [DigitalOcean Kubernetes](https://www.digitalocean.com/products/kubernetes/) 和 [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) ，并将它们导入主机集群。

![](img/96201850c87b401027ef54f88e8389cd.png)

## 准备主机集群

在开始之前，你需要安装一个 KubeSphere 集群，详情请见 Kubernetes 上的 quickstarts [All-in-one](https://kubesphere.io/docs/quick-start/all-in-one-on-linux/) 或[minimal KubeSphere](https://kubesphere.io/docs/quick-start/minimal-kubesphere-on-k8s/)。在本教程中，我们选择在数据中心安装 KubeSphere。

在 KubeSphere 集群准备就绪之后，您就可以通过使用 kubectl:
编辑集群配置来将 clusterRole 的值设置为 host

```
kubectl edit cc ks-installer  -n  kubesphere-system

```

向下滚动并将 clusterRole 的值设置为 host，然后单击 Update(如果使用 web 控制台)使其生效:

```
multicluster:

   clusterRole:  host

```

保存，您需要等待一段时间，以便更改生效。安装完主机集群后，将在 kubesphere-system 中创建一个名为 [tower](https://github.com/kubesphere/tower) 的代理服务，其类型为 LoadBalancer。

如果集群有可用的 LoadBalancer 插件，您可以看到 EXTERNAL-IP 的相应地址，KubeSphere 会自动获取该地址。这意味着您可以跳过设置代理的步骤。执行以下命令来检查服务。

```
kubectl  -n  kubesphere-system get svc

```

输出可能如下所示:

![](img/804ac6c8fdf97cbac92027759677dd9a.png)

## 准备两个成员集群

开始之前，您需要在亚马逊 EKS 和数字海洋 Kubernetes 上安装一个最小的 KubeSphere，详情请参见[在亚马逊 EKS 部署 kubes phere](https://kubesphere.io/docs/installing-on-kubernetes/hosted-kubernetes/install-kubesphere-on-eks/)和[在数字海洋 Kubernetes 上部署 kubes phere](https://kubesphere.io/docs/installing-on-kubernetes/hosted-kubernetes/install-kubesphere-on-do/)。

为了管理主机集群中的成员集群，您需要使它们之间的 **jwtSecret** 相同。因此，您需要首先通过以下命令从主机集群获取它。

```
kubectl  -n  kubesphere-system get cm kubesphere-config  -o  yaml  |  grep  -v  "apiVersion"  |  grep jwtSecret

```

输出可能是这样的:

```
jwtSecret:  "gfIwilcc0WjNGKJ5DLeksf2JKfcLgTZU"

```

如果您已经在亚马逊 EKS 和数字海洋 Kubernetes 上安装了 KubeSphere，您可以通过编辑集群配置将 **clusterRole** 的值设置为 member。请注意，该步骤应该在两个成员的集群中分别执行:

```
kubectl edit cc ks-installer  -n  kubesphere-system

```

输入对应的 **jwtSecret** 如上图:

```
authentication:

   jwtSecret:  gfIwilcc0WjNGKJ5DLeksf2JKfcLgTZU

```

向下滚动并将 **clusterRole** 的值设置为 member，然后单击更新(如果使用 web 控制台)使其生效:

```
multicluster:

   clusterRole:  member

```

## 将成员集群导入控制平面

确保您已经为亚马逊 EKS 和数字海洋 Kubernetes 安装了双成员集群。然后，您就可以将这两个成员集群启动到主机集群中了。在本教程中，我们仅以将亚马逊 EKS 导入主机集群为例，导入数字海洋 Kubernetes 的步骤如下。

打开主机集群仪表板，并单击**添加集群。**

![](img/885b9289ba821854b14617d968697c6e.png)

输入要导入的集群的基本信息，点击**下一步**。

![](img/08662ad19fc3ddb87139127e2458dfcb.png)

在连接方法中，选择群集连接代理，然后单击导入。它将在控制台中显示由主机集群生成的代理部署。

根据指令在成员集群中创建一个 **agent.yaml** 文件，然后将代理部署复制并粘贴到该文件中。在节点上执行**ku bectl create-f agent . YAML**，等待代理启动并运行。请确保成员群集可以访问代理地址。

![](img/cc076ce2a3d5d1542087fe6d7a0614e7.png)

当集群代理启动并运行时，您可以在主机集群中看到导入的集群。

![](img/9194e33394ffab4f7915010a219aea4d.png)

从成员集群列表进入亚马逊 EKS 集群，您将能够看到该集群的概览仪表板，包括集群监控指标和日志记录。

![](img/cc8aa3f4cf75d2978f8979093f37b1ab.png)

恭喜你！现在亚马逊 EKS 已经由 KubeSphere 导入并管理，您现在应该能够将数字海洋 Kubernetes 导入其中。在两个成员的集群准备就绪后，在一个多云环境中分发云原生应用将变得非常容易，尽情享受吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>