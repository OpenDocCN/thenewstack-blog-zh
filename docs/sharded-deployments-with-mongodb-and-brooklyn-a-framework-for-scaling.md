# MongoDB 和 Brooklyn 的分片部署，一个扩展框架

> 原文：<https://thenewstack.io/sharded-deployments-with-mongodb-and-brooklyn-a-framework-for-scaling/>

这篇文章最初出现在

[Cloudsoft blog](https://www.cloudsoftcorp.com/blog/2015/02/integrating-cloud-foundry-apache-brooklyn-part-1-service-broker/)

演示如何使用 Cloud Foundry 的 Apache Brooklyn 插件创建服务。Apache Brooklyn 是一个跨多个数据中心集成服务的平台。这是一系列文章中的第四篇，介绍了布鲁克林如何与各种服务合作。第一部分探讨了

[Cloud Foundry service broker](https://thenewstack.io/cloud-foundry-and-apache-brooklyn-for-automating-paas-with-a-service-broker/)

和布鲁克林一起工作。本系列的第 2 部分介绍了用户如何部署

[Brooklyn plugin](https://www.cloudsoftcorp.com/blog/2015/02/integrating-cloud-foundry-apache-brooklyn-part-2-brooklyn-plugin/)

整合 Cloud Foundry。第三部分演示了如何

[Apache Ambari’s deployment integration technology](https://thenewstack.io/spinning-up-a-hadoop-cluster-with-apache-ambari-and-brooklyn/)

符合阿帕奇布鲁克林。

分布式架构的本质要求用户考虑应用和服务如何跨多个云服务和数据中心运行。应用程序是一回事，但是在这些类型的环境中运行数据库会带来不同程度的复杂性。

在这个例子中，我们将创建一个涉及 MongoDB 和分片的更复杂的服务。然后，我们将向您展示如何使用效应器来扩展或缩小这个服务。

MongoDB 为水平和垂直伸缩提供了一些非常高级的选项。因此，我们将看看如何使用 Brooklyn 插件创建一个分片部署(如上图所示)。

## 创建分片部署服务

首先，利用我们在应用程序清单中指定蓝图的新能力，在 Brooklyn 部分下，创建一个`MongoDBShardedDeployment`服务:

```
<tt>applications:
-  name:  my-app
  memory:  512M
  brooklyn:
  -  name:  Sharded MongoDB
    location:  localhost
    services:
    -  type:  brooklyn.entity.nosql.mongodb.sharding.MongoDBShardedDeployment
      id:  mongo
      name:  Mongo DB Backend
      provisioning.properties:
        minRam:  16gb
      brooklyn.config:
        initialRouterClusterSize:  1
        initialShardClusterSize:  5
        shardReplicaSetSize:  3</tt>

```

注意，使用蓝图，您还可以指定供应属性并配置分片部署。在这个蓝图中，我们指定了一个路由器、五个分片和每个分片三个节点的最小 16GB RAM。简单推一下这个蓝图……

```
<tt>$  cf brooklyn push
Running the brooklyn command
Enter broker:  brooklyn
Enter username:  user
Enter password:  simple-password

...
OK
</tt>

```

你有一个 MongoDB 的分片部署。

## 检查传感器

正如我们在第二部分中看到的，您可以使用 sensors 命令查看与正在运行的服务相关联的传感器，所以让我们对这个服务也这样做:

```
<tt>$  cf brooklyn sensors brooklyn user simple-password  "Sharded MongoDB"
Sharded MongoDB
---------------
Entity:Mongo DB Backend
  service.state  :  RUNNING
  ...
    Cluster  of  MongoDBConfigServer  (LocalhostMachineProvisioningLocation{id=Bg7x8Kpi,  name=localhost})
      service.state  :  RUNNING
      mongodb.config.server.addresses  :  [127.0.0.1:27019  127.0.0.1:27020  127.0.0.1:27021]
      ...
        MongoDBConfigServer:buuD
          service.state  :  RUNNING
          host.address  :  127.0.0.1
          mongodb.server.port  :  27019
          ...
        MongoDBConfigServer:v3Uq
          service.state  :  RUNNING
          host.address  :  127.0.0.1
          mongodb.server.port  :  27020
          ...
        MongoDBConfigServer:rHuG
          host.address  :  127.0.0.1
          service.state  :  RUNNING
          mongodb.server.port  :  27021
          ...
        quarantine
          group.members  :  []
          group.members.count  :  0
          ...
    Cluster  of  MongoDBRouter  (LocalhostMachineProvisioningLocation{id=Bg7x8Kpi,  name=localhost})
      service.state  :  RUNNING
      ...
        MongoDBRouter:JScw
          service.state  :  RUNNING
          mongodb.router.config.shard.count  :  5
          host.address  :  127.0.0.1
          mongodb.server.port  :  27018
          ...
        quarantine
          group.members  :  []
          group.members.count  :  0
          ...
    Cluster  of  MongoDBReplicaSet  (LocalhostMachineProvisioningLocation{id=Bg7x8Kpi,  name=localhost})
      group.members.count  :  5
      service.state  :  RUNNING
      ...
        Cluster  of  MongoDBServer  (LocalhostMachineProvisioningLocation{id=Bg7x8Kpi,  name=localhost})
          service.state  :  RUNNING
          mongodb.server.network.bytesIn  :  318844
          group.members.count  :  3
          ...
            MongoDBServer:GApX
              mongodb.server.network.bytesIn  :  145177
              host.address  :  127.0.0.1
              mongodb.server.network.bytesOut  :  883410
              mongodb.server.port  :  27027
              service.state  :  RUNNING
              ...
            MongoDBServer:Ep4N
              mongodb.server.network.bytesOut  :  761446
              mongodb.server.network.bytesIn  :  87014
              mongodb.server.port  :  27026
              host.address  :  127.0.0.1
              service.state  :  RUNNING
              ...
            MongoDBServer:EqDn
              mongodb.server.port  :  27035
              service.state  :  RUNNING
              mongodb.server.network.bytesIn  :  86653
              mongodb.server.network.bytesOut  :  763923
              host.address  :  127.0.0.1
              ...
            quarantine
              group.members  :  []
              group.members.count  :  0
              ...
          ...
          quarantine
            group.members  :  []
            group.members.count  :  0
            ...

OK
</tt>

```

在这个例子中，有很多实体和更多的传感器，但有几个值得指出:`service.state`显示实体是否在运行；`host.address`和`mongodb.server.port`展示了如何连接到单个 MongoDB 服务器，如果你需要的话；`mongodb.server.network.bytesIn`和`mongodb.server.network.bytesOut`显示进出的流量。

## 使用效应器将其缩小

所以，看看传感器，假设我们决定把碎片的数量减少到一个。为了找出使用哪个效应器，我们使用效应器命令:

```
<tt>$  cf brooklyn effectors brooklyn user simple-password  "Sharded MongoDB"
Sharded MongoDB
---------------
Application:m6obgkNz
  m6obgkNz:start Start the process/service represented by an entity
    parameters:
    locations The location or locations to start in,  as  a  string,  a  location object,  a  list of strings,  or  a  list of location objects
  m6obgkNz:restart Restart the process/service represented by an entity
  m6obgkNz:stop Stop the process/service represented by an entity
  Mongo DB Backend
    htgPyEms:restart Restart the process/service represented by an entity
    htgPyEms:start Start the process/service represented by an entity
    parameters:
    locations The location or locations to start in,  as  a  string,  a  location object,  a  list of strings,  or  a  list of location objects
    htgPyEms:stop  Stop  the  process/service  represented  by  an  entity
    Cluster  of  MongoDBReplicaSet  (LocalhostMachineProvisioningLocation{id=Bg7x8Kpi,  name=localhost})
      cfgFazAk:restart Restart the process/service represented by an entity
      cfgFazAk:start Start the process/service represented by an entity
        parameters:
        locations The location or locations to start in,  as  a  string,  a  location object,  a  list of strings,  or  a  list of location objects
      cfgFazAk:stop Stop the process/service represented by an entity
      cfgFazAk:resizeByDelta Changes the size of the cluster.
        parameters:
        delta The change in number of nodes
      cfgFazAk:resize Changes the size of the entity  (e.g.  the number of nodes in  a  cluster)
        parameters:
        desiredSize The new size of the cluster
      cfgFazAk:replaceMember Replaces the entity with the given ID,  if it is  a  member;  first adds  a  new member,  then removes this one.  Returns id of the new entity;  or throws exception if couldn't  be replaced.
        parameters:
        memberId The entity id of  a  member to be replaced
...
OK
</tt>

```

我们需要的是`cfgFazAk:resize`，所以让我们调用它:

```
<tt>$  cf brooklyn invoke brooklyn user simple-password  "Sharded MongoDB"  cfgFazAk:resize  --desiredSize  1
Invoking effector cfgFazAk:resize
1
OK
</tt>

```

## 向外扩展

如果我们需要再次向外扩展，我们只需再次运行相同的命令，但是改变了参数:

```
<tt>$  cf brooklyn invoke brooklyn user simple-password  "Sharded MongoDB"  cfgFazAk:resize  --desiredSize  3
Invoking effector cfgFazAk:resize
3
OK
</tt>

```

复制增加怎么办？只需查看效应器来找到您想要增加的集群，并运行相同的命令:

```
<tt>$  cf brooklyn invoke brooklyn user simple-password  "Sharded MongoDB"  RaArKduP:resize  --desiredSize  5
Invoking effector RaArKduP:resize
5
OK
</tt>

```

## 录像

作为这篇文章的总结，再一次，这里是我们插件运行的视频:

[https://www.youtube.com/embed/7Suvgz1yY9A?feature=oembed](https://www.youtube.com/embed/7Suvgz1yY9A?feature=oembed)

视频

## 下次

在之前的帖子中，我们看到了使用 Cloud Foundry Service Broker 和插件管理 Brooklyn 服务的基础知识，从在目录中创建服务到向目录中添加新项目；从在清单中指定目录项到在目录中指定新的服务类型。现在我们已经看到了一个更大的服务，我们可以使用传感器和效应器进行控制。

但是 Brooklyn 还有更多，在下一部分中，我们将向您展示如何使用 Apache Brooklyn 提供的多云、多语言持久性将应用程序部署到 Cloud Foundry。到时候见。

云软是新堆栈的赞助商。

特色图片[通过](https://www.flickr.com/photos/99824102@N08/16459404082/in/photolist-r5sKp1-qNo3md-pSweU8-bNvPUc-8suRqs-rAcNLm-qj5YU6-bgT3dX-rPmUHy-mdDdde-cc45fh-rfe14A-9huHQR-qX6ZM9-9aYisN-pZAQMh-6BpsKt-izpNCW-pZxiif-nerTPS-6hbQTQ-pYBYaw-eVGah1-rRwpCu-riHYr1-ishV3U-pcAuMf-rhMK8P-q9pDLX-pP2Veg-qhPUSJ-gvixTe-iK6B1U-q3pwpV-bgSWN8-qNNbVy-pH5AmA-pY77FF-qcRnSm-r6g6iQ-iK4iBX-dcygb8-pZsYH6-pZxfRG-iK6Nqh-p9HwW8-q3y3mt-q7i3ys-q54PMC-qBgvMz) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>