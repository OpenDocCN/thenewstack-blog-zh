# Cloud Foundry 和 Apache Brooklyn 通过服务代理实现 PaaS 自动化

> 原文：<https://thenewstack.io/cloud-foundry-and-apache-brooklyn-for-automating-paas-with-a-service-broker/>

这篇文章最初出现在

[CloudSoft blog](https://www.cloudsoftcorp.com/blog/2015/02/integrating-cloud-foundry-apache-brooklyn-part-1-service-broker/)

展示 Cloud Foundry 如何与 Apache Brooklyn 集成，Apache Brooklyn 是一个跨多个数据中心集成服务的平台。这是一系列博客文章中的第一篇，涵盖了 CF 如何在企业和云服务环境中与各种各样的布鲁克林蓝图(如 Cassandra、Couchbase、ActiveMQ 和 Kafka)一起使用。本系列的第二部分介绍了如何使用

[Brooklyn plugin](https://www.cloudsoftcorp.com/blog/2015/02/integrating-cloud-foundry-apache-brooklyn-part-2-brooklyn-plugin/)

将 Cloud Foundry 与 Apache Brooklyn 整合。

[Cloud Foundry](https://www.cloudfoundry.org/) 是一个平台即服务(PaaS ),使得在一系列运行时框架之上部署、运行和扩展应用变得容易。

[Apache Brooklyn](https://brooklyn.incubator.apache.org/) 是一个应用蓝图和管理系统，支持云中的各种软件和服务。

在本帖中，我们将了解 Cloud Foundry 生态系统中的服务代理。我们将探讨这个模块化组件如何在服务提供商和 CF 工具之间架起桥梁。下一篇文章将介绍一个 CF 插件，它使得在应用程序清单中指定服务变得很简单，因此您可以用一个命令创建服务并将它们绑定到您的应用程序。之后，我们将给出一些例子，包括一个真正可伸缩的应用程序和一个 Riak 集群的 manifest 中的一个分片 MongoDB 实例。

## 服务代理

CF 中的 Service Broker 组件允许开发人员将他们的应用与他们消费的服务分离。`cf create-service`命令调用代理来创建服务的新实例。然后，您可以在您的应用程序清单中包含对这个服务实例的引用，或者手动发出一个`bind-service`，将它与一个或多个应用程序相关联。然后，CF 会自动将服务实例的细节——比如使用它的 URL 和凭证——注入到应用程序的运行时中。

到目前为止，大多数服务代理都处理单一类型的服务，需要大量的前期投资才能在 CF 中提供新的服务，并且限制了这些服务在应用程序需要时的定制程度。

然而，通过将 Apache Brooklyn 作为服务代理提供，您只需要一个代理就可以公开现有 Brooklyn 蓝图的广泛目录。添加新服务就像在布鲁克林目录上张贴蓝图一样简单。

让我们从安装 Brooklyn 服务代理开始。你需要安装 Java 8、git 和 Gradle，然后:

```
<tt>$  git clone https://github.com/cloudfoundry-community/brooklyn-service-broker.git
$  cd brooklyn-service-broker
$  gradle clean build
</tt>

```

这会生成一个包含服务代理的文件`brooklyn-service-broker.war`。

接下来，我们需要一个 Apache Brooklyn 服务器。如果你没有，很容易按照这里的说明[安装](https://brooklyn.incubator.apache.org/v/latest/start/running.html)。

运行之后，记下`brooklyn-host`和`brooklyn-password`，并将 Brooklyn service broker WAR 文件安装到`/path/to/broker-war/`中。选择一个`broker-user`和`broker-password`，在下面的 YAML 中用真实值替换这五个代币。将生成的蓝图粘贴到 Brooklyn 服务器的“Add Application”对话框中，一分钟之内您的 Service Broker 就应该运行了(通常在端口 8080 上，但是如果该端口已经被使用，请查看 Tomcat 的传感器)。

```
<tt>name:  Brooklyn Service Broker
location:  localhost
services:
-  type:  brooklyn.entity.webapp.tomcat.TomcatServer
  name:  Tomcat Server
  war:  /path/to/broker-war/brooklyn-service-broker.war
  brooklyn.config:
    java.sysprops:
      brooklyn.uri:  https://brooklyn-host:8081
      brooklyn.username:  admin
      brooklyn.password:  brooklyn-password
      security.user.name:  broker-user
      security.user.password:  broker-password
      spring.data.mongodb.host:  $brooklyn:component("mongodb").attributeWhenReady("host.address")
      spring.data.mongodb.port:  $brooklyn:component("mongodb").attributeWhenReady("mongodb.server.port")

-  type:  brooklyn.entity.nosql.mongodb.MongoDBServer
  id:  mongodb
  name:  Service Broker Mongo DB
</tt>

```

## 将布鲁克林服务添加到 Cloud Foundry

接下来，我们将向 Cloud Foundry 注册这个代理。如果您还没有 CF 的运行实例，请参见[https://docs.cloudfoundry.org/deploying/](https://docs.cloudfoundry.org/deploying/)，登录它，然后继续。

首先，让我们向 Brooklyn 目录添加一个服务，这样我们就可以从 Cloud Foundry 访问一些内容。在 Brooklyn GUI 中，选择“Catalog”选项卡，然后单击“+”和“entity”按钮，并添加以下服务蓝图:

```
<tt>brooklyn.catalog:
  id:  mysql
  version:  1.0
  iconUrl:  classpath://mysql.png
  description:  MySql is an open source relational database management system  (RDBMS)
name:  MySQL Database
services:
-  type:  brooklyn.entity.basic.BasicApplication
  brooklyn.children:
  -  type:  brooklyn.entity.database.mysql.MySqlNode
    id:  mysql
    name:  MySQL Node
</tt>

```

现在向 Cloud Foundry 注册代理:

```
<tt>$  cf create-service-broker brooklyn broker-user broker-password https://broker-host:8080/
Creating service broker brooklyn as admin...
OK
</tt>

```

```
<tt>$  cf service-access
Getting service access as admin...
broker:  brooklyn
 service          plan access orgs
 MySQL Database localhost  none

</tt>

```

我们添加到布鲁克林的蓝图现在在 Cloud Foundry 中可见。它的访问是没有，但所有剩下的是让它在市场上可用。

```
<tt>$  cf enable-service-access  "MySQL Database"
Enabling access to all plans of service MySQL Database for all orgs as admin...
OK

$  cf marketplace
Getting services from marketplace in org cloudsoft  /  space development as admin...
OK

    service          plans description 
    MySQL Database localhost MySql is an open source relational database management system  (RDBMS)
</tt>

```

要创建该服务的实例，只需:

```
<tt>$  cf create-service  "MySQL Database"  localhost mysql
Creating service mysql in org cloudsoft  /  space development as admin...
OK
$  cf services
Getting services in org cloudsoft  /  space development as admin...
OK

    name    service plan bound apps 
    mysql MySQL Database localhost      
</tt>

```

要部署到新机器，您只需更改蓝图的位置部分。例如，如果我们希望在 Softlayer 中有一个 5 节点 8GB 的 Riak 集群，而不是在 localhost 上有一个 MySQL，我们可以将它添加到 Brooklyn 目录中(用您的 SL 用户名和访问密钥替换 XXX):

```
<tt>brooklyn.catalog:
  id:  riak
  version:  1.0
  iconUrl:  classpath://riak.png
  description:  Riak
name:  riak-cluster
location:
  jclouds:softlayer:
    identity:  XXX
    credential:  XXX
services:
-  type:  brooklyn.entity.basic.BasicApplication
  brooklyn.children:
  -  type:  brooklyn.entity.nosql.riak.RiakCluster
    initialSize:  5
    provisioning.properties:
      minRam:  8GB
</tt>

```

刷新目录，Riak 现在为您服务。

## 绑定到应用程序

现在，您可以将这些服务实例绑定到您的应用程序。如果您的应用程序已经部署，请使用:

```
<tt>$  cf bind-service my-app mysql
</tt>

```

这将使您的应用程序运行时可以使用以下环境变量:

```
<tt>"VCAP_SERVICES":  {
  "MySQL Database":  [
 {
    "credentials":  {
 "MySqlNode:tE5W":  {
      "host.address":  "127.0.0.1",
      "host.name":  "127.0.0.1",
      "mysql.password":  null,
      "mysql.port":  3306,

…

 }
    },
    "label":  "MySQL Database",
    "name":  "mysql",
    "plan":  "localhost",
    "tags":  []
 }
  ]
  }
</tt>

```

或者，您可以将它添加到您的清单中:

```
<tt>applications:
-  name:  my-app
  path:  path/to/app.war
  memory:  512M
  services:
  -  mysql
</tt>

```

然后像平常一样做一个`cf push`。

很酷，是吧？但是，如果我们想要指定新的服务添加到市场中呢？嗯，我们有一个专为你准备的插件！敬请期待！

通过 Cloud Foundry 的服务代理映像[。](https://github.com/openservicebrokerapi/servicebroker/blob/v2.12/spec.md)

通过 Flickr 知识共享[发布的专题图片。](https://www.flickr.com/photos/dilworthdesigns/321103988/in/photolist-unK2E-47Nw5f-5y2Zgd-5BtSXZ-4ZdeN6-77TvL2-5E8vrU-edkS4R-9kzqY-7B5eFd-6Hun1K-rj4Vqu-5M4Qag-biTAbp-nZEFdN-r72yfP-qhtnFn-qMSGBW-qheF23-73BLZm-81dnit-dry4BR-a6KWE-75ymP3-75y7TJ-73GFfa-qEKCeH-qCQaKH-8cNAgd-phwdfa-8Uwq5U-pHY3oi-9bTnPd-8UtkEe-jJqbw1-jJqU5o-jJqb1w-jJqbjN-5eHoe2-83SeLb-cwyqrJ-7z9K7M-9f4k7K-9Rm9tQ-95T2Ax-2NU1FA-m1YBxB-5UAAjg-dpC7zp-58bGLv)

云软是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>