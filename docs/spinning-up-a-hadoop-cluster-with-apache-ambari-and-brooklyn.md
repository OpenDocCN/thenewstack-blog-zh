# 使用 Apache Ambari 和 Brooklyn 构建 Hadoop 集群

> 原文：<https://thenewstack.io/spinning-up-a-hadoop-cluster-with-apache-ambari-and-brooklyn/>

部署和管理 Hadoop 堆栈可能是一项艰巨的任务。Hadoop 生态系统中存在大量的服务，部署它们以使它们正确地相互连接可能是困难和耗时的。Apache Ambari 的目标是让这变得更容易，在云软，我们已经开始向 Apache Brooklyn 添加功能，以增强 Ambari 提供的功能。

[Apache Ambari](https://ambari.apache.org/) 旨在简化 Apache Hadoop 集群的供应、管理和监控。

[Apache Brooklyn](https://brooklyn.incubator.apache.org/) 是一个应用蓝图和管理系统，支持云中的各种软件和服务。

通过将两者结合起来，我们可以立即进一步简化部署过程，尤其是当我们想要部署到云时。这篇文章将快速简单地介绍启动 Hadoop 集群的过程。

## 布鲁克林装置

*   首先，您需要一个 Apache Brooklyn 安装。如果你还没有，这里有说明。
*   如果 Brooklyn 当前正在运行，停止它(ctrl-c)。
*   下载并复制[brooklyn-ambari-0.1-snapshot . jar](https://github.com/brooklyncentral/brooklyn-ambari/releases/download/v0.1.0-20150331/brooklyn-ambari-0.1-SNAPSHOT.jar)到<Brooklyn _ home>/libs/drop ins/，这将使它在 Brooklyn 类路径中可用。
*   [启动布鲁克林](https://brooklyn.incubator.apache.org/v/latest/start/running.html#launch-brooklyn) ( <布鲁克林 _ home>/bin/布鲁克林启动)。
*   通过 Ambari 部署 Hadoop。

Brooklyn 使用基于 YAML 的蓝图来部署蓝图。下面将把 Ambari 部署到一个包含四台机器(一台 Ambari 服务器和三个代理)的集群中，部署到 AWS EC2。然后，它会将列出的服务部署到这些机器上。

```
<tt>name:  Ambari driven cloud installation
location:  
  jclouds:aws-ec2:
    region:  eu-west-1
    identity:  &lt;your aws identity&gt;
    credential:  &lt;your aws credential&gt;
    osFamily:  ubuntu
    osVersionRegex:  12.*
    minRam:  8192
services:
-  type:  io.brooklyn.ambari.AmbariCluster
  securityGroup:  &lt;the name of  a  security group exposing  8080&gt;
  initialSize:  3
  services:
  -  GANGLIA
  -  HDFS
  -  MAPREDUCE2
  -  NAGIOS
  -  YARN
  -  ZOOKEEPER
</tt>

```

将它保存到一个名为 simple-ambari-hdp.yaml 的文件中，编辑身份、凭证和安全组。将所有的虚拟机放在同一个安全组中可以让所有的服务进行内部通信，但是您至少需要为端口 8080 设置一个入站规则。如果您更愿意部署到 AWS 以外的云提供商，请参见此处的位置文档。

**先不说**:虽然您不能使用本地主机部署来测试 Ambari，但是您可以使用虚拟机网络。最简单的方法是在这里使用 Ambari-vagger 项目。然后，您可以将这些虚拟机视为 Brooklyn 内的 BYON。

假设 Brooklyn 本地部署在端口 8081 上，您可以使用以下命令部署应用程序:

```
<tt>curl https://127.0.0.1:8081/v1/applications --data-binary @/path/to/simple-ambari-hdp.yaml</tt>

```

一旦安装并启动了 Ambari，您应该会看到类似下面的截图:

绿色交通灯表示 Ambari 服务器和代理安装没有任何问题。

单击“Ambari Server ”,然后打开页面顶部附近的“sensors”选项卡。

在这里，您将看到关于 VM 实例和 Ambari 服务器进程的信息。找到“main.uri”并将鼠标悬停在其所在的行上。将出现一个小箭头。将鼠标悬停在箭头上方将显示选项“open”，这将在一个新的选项卡中打开 Ambari 服务器 web 界面。

使用用户名/密码 admin/admin 登录 Ambari 服务器 web 界面。您应该能够看到已经创建了一个名为 Cluster1 的集群，并且有一个操作正在进行中。如果您调查当前的操作，您会看到“安装并启动所有服务”正在进行中。这将需要几分钟时间，但最终您应该会从仪表盘上看到您的 Hadoop 集群已经启动并正在运行。

您可以通过导航到主应用程序的“效应器”选项卡并单击“停止”效应器来停止您的应用程序，并终止其所有虚拟机。这将确保从 AWS 中删除所有资源。

## 路标

显然，到目前为止，我们只实现了最简单的功能，虽然我们希望这对人们有用，但我们仍有一长串功能需要添加。

首先，我们需要扩展 YAML 描述中可用的参数。例如，添加一个参数以允许指定 Ambari 蓝图。我们还需要更多的参数来连接非 Ambari 服务，比如 MySQL。

同样，我们需要添加一系列传感器，以便我们可以获得有用的数据来实施策略。例如，HDFS 容量传感器将允许我们制定一个策略，在净空降至特定阈值以下时，自动创建额外的虚拟机或添加额外的存储。

允许我们改变集群大小的效应器也是有用的(并且对于支持上述策略是至关重要的)。这将使得通过添加额外的节点和指示 Ambari 重新平衡服务来扩展集群变得容易。

## 最后

希望这篇文章是一个有用的演示，展示了如何在一个机器集群上快速建立一个完整的 Hadoop 堆栈。要亲自尝试一下，最新的代码可以在 [GitHub](https://github.com/brooklyncentral/brooklyn-ambari) 上找到。如果您有任何想法或问题，请访问#brooklyncentral 上的 IRC 或通过我们的邮件列表联系我们[。](https://brooklyn.incubator.apache.org/community/mailing-lists.html)

云软是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/goincase/8369055858/in/photolist-orPfct-dXufBA-bP6NWV-r6mZx2-dKxAJw-ipL2a8-oKmmg2-dVq6QU-nfDeJK-dFm5Yg-fnfzxs-dXXP6L-9J7s7h-5qXwW5-axn2Nw-m1GuLw-rfz1R7-eDX8VN-pqkMxb-pqkMZo-pzCUe8-pz8E8w-cyaDq5-gdFFBR-cHenny-9hof8c-ky7wuB-4NvmJS-p17dtx-awNz2o-318K46-d4EFP3-cCVGXy-c63qYw-92ydgy-ayMyiw-dYmHJb-7jMmvm-7xXTc8-drNEJZ-9J4gd2-5Dfb5i-o1SADb-dENA73-8vYMyE-6tYZwp-awKQ9H-4nBvHg-9RGXMW-9Zei9J)