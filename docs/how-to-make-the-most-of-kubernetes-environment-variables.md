# 如何充分利用 Kubernetes 环境变量

> 原文：<https://thenewstack.io/how-to-make-the-most-of-kubernetes-environment-variables/>

在传统系统中，环境变量起着重要的作用，但并不总是至关重要的。有些应用程序比其他应用程序更多地使用环境变量。有些人更喜欢配置文件而不是环境变量。然而，当涉及到 [Kubernetes](https://thenewstack.io/category/kubernetes/) 时，环境变量比你想象的更重要。这部分是由于容器的一般工作方式，部分是由于 Kubernetes 的特性。在这篇文章中，你将了解到 Kubernetes 中所有的环境变量。

> 传统上，环境变量是动态的键值变量，系统上运行的任何进程都可以访问它们。

## **基础知识**

让我们从基础开始。什么是环境变量，它们为什么存在？传统上，环境变量是动态的键值变量，系统上运行的任何进程都可以访问它们。操作系统本身会设置许多环境变量，帮助正在运行的进程理解系统的细节。由于这一点，软件开发人员可以在他们的软件中包含逻辑，使程序适应特定的操作系统。

环境变量还包含许多关于用户的重要信息，如用户名、首选语言、用户主目录路径和许多其他有用的信息。

## **用户定义的环境变量**

 [达维德·齐奥尔科夫斯基

Dawid 有 10 年的经验，最初是网络/系统工程师，中间是 DevOps，最近是云原生工程师。他曾在一家 IT 外包公司、一家研究机构、电信公司、一家托管公司和一家咨询公司工作过，因此他从不同的角度收集了很多知识。如今，他正在帮助公司迁移到云和/或重新设计他们的基础设施，以实现更加云本地化的方法。](https://twitter.com/DavidZisky) 

作为用户，您可以轻松地创建和访问自己的环境变量。在基于 Unix 的系统上，可以通过执行`export`命令，后跟变量名和值来实现。

因此，例如，要创建一个名为`myvar`的值为 10 的环境变量，您需要执行以下命令:

`export myvar=10`

然后，您可以使用美元符号后跟变量名来访问变量值。

在我们的例子中，要打印(使用 Linux 命令`[echo](https://en.wikipedia.org/wiki/Echo_(command))`)变量的值，我们可以执行以下命令:

`echo $myvar`

如果你想打印所有的环境变量，你可以执行`printenv`或者`env`命令。

所有这些也适用于在您的 pod 中运行的应用程序。

## **Kubernetes 中的环境变量**

Kubernetes 中环境变量的基本原理是相同的。然而，Kubernetes 非常广泛地使用环境变量，用于一些不同的事情。因此，理解环境变量在 Kubernetes 中扮演的角色是有好处的。如果您想迁移一个不经常使用环境变量的现有应用程序，这一点尤其正确。您仍然可以创建没有任何环境变量的 pod。但是如果您完全忽略 Kubernetes 中的环境变量，您可能会失去一些更强大的 Kubernetes 特性的价值。

在我们继续下一步之前，您还需要知道，在开发微服务时，尽可能将配置作为环境变量提供给 Docker 容器通常是一种良好的做法。这样你可以使你的 Docker 图像更加通用，并且可以重复使用相同的图像用于不同的目的。也就是说，让我们看看如何将一些环境变量注入到 Kubernetes pods 中。

> Kubernetes 中环境变量的主要用例类似于传统软件开发中的用例。

## **你的吊舱配置**

Kubernetes 中环境变量的主要用例类似于传统软件开发中的用例。也就是为你的软件提供环境信息。这些信息通常用于改变或调整软件的工作方式以适应特定的环境。定义可能看起来比较模糊，我举个例子吧。您可以使用同一个映像，但在基于环境变量的开发或生产模式下运行您的应用程序，而不是为您的开发和生产环境使用单独的 Docker 映像。

在 Kubernetes 中，环境变量的作用域是一个容器，添加它们有三种主要方式。让我们把它们分解开来。

### **直接**

第一种选择是最直接的。您可以简单地在部署定义中用关键字`env`:
直接指定环境变量

```
---

apiVersion:  apps/v1

kind:  Deployment

metadata:

name:  example-app

spec:

replicas:  1

selector:

matchLabels:

app:  example-app

template:

metadata:

labels:

app:  example-app

spec:

containers:

-  name:  example-app-dev

image:  [yourimage]

<strong>env:</strong>

-  <strong>name:  ENVIRONMENT</strong>

<strong>  value:  "development"</strong>

```

一旦您的应用程序被指示读取一个名为`ENVIRONMENT`的环境变量的值，您就可以直接使用它在所需的模式下运行您的应用程序。

要在生产模式下运行相同的应用程序，您可以简单地重用相同的部署定义。您只需要更改环境变量的值，并且可选地更改 pod 的名称:

```
---

apiVersion:  apps/v1

kind:  Deployment

(...)

containers:

-  name:  example-app-prod

image:  [yourimage]

<strong>env:</strong>

-  <strong>name:  ENVIRONMENT</strong>

<strong>  value:  "production"</strong>

```

下面是另一个例子:假设您有一个 web 应用程序，需要下载一个产品目录提供给用户。该目录可能在几个方面有所不同，例如，因国家、月份或供应商而异。这是一个环境变量的完美用例。您的应用程序可以保持通用，而不是创建许多不同版本的应用程序来适应不同的下载选项。它必须下载哪个目录将由某个特定环境变量的值决定。

### **秘密**

向应用程序提供环境变量的另一种方式是从 Kubernetes [secrets](https://kubernetes.io/docs/concepts/configuration/secret/) 传递它们。您可能会猜测，当您需要传递一些敏感信息(如密码或令牌)时，这是一个不错的选择。这样，您就不必像之前那样在部署中直接指定环境变量的值。相反，您指示 Kubernetes 获取指定的 secret 对象的值，并将其用作 pod 的环境变量的值。

例如，如果你有一个 Kubernetes 的秘密是这样的:

```
apiVersion:  v1

kind:  Secret

metadata:

name:  secret_data

type:  Opaque

stringData:

username:  "example"

password:  "supersecretpassword"

and you want to pass the password as an environment variable to your pod,  you can reference it in the deployment definition as follows:

---

apiVersion:  apps/v1

kind:  Deployment

(...)

containers:

-  name:  example-app-prod

image:  [yourimage]

env:

# Inject variables from a Kuberentes secret

-  name:  secret_variables

valueFrom:

secretKeyRef:

name:  secret_data

key:  password

In your pod,  you will then be able to access the actual password  (supersecretpassword)  by accessing an environment variable called secret_variable.  For example,  in Python you could do it like this:

import os

PASSWORD  =  os.environ.get['secret_variable']

```

如你所见，在我们的例子中，我们在 Kubernetes secret 中定义了`username`和`password`，但是我们只将`password`值传递给 pod。如果您想传递 Kubernetes secret 中的所有秘密而不指定每个密钥，您可以使用`secretRef`而不是`secretKeyRef`。这样，您只需要指定 Kubernetes secret 对象名，其中的所有值将作为环境变量自动加载:

```
---

apiVersion:  apps/v1

kind:  Deployment

(...)

containers:

-  name:  example-app-prod

image:  [yourimage]

env:

# Inject variables from a Kuberentes secret

-  name:  secret_variables

valueFrom:

secretRef:

name:  secret_data

```

### **配置图**

将环境变量注入 pod 的另一种方法是使用来自 [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/) 的值。例如，如果您有这样的配置图:

```
apiVersion:  v1

kind:  ConfigMap

metadata:

name:  config-data

data:

environment:  "dev"

timezone:  "UTC"

```

并且您希望将`environment`和`timezone`作为环境变量加载到您的 pod 中，那么您可以将下面的`valueFrom`定义添加到您的部署中:

```
---

apiVersion:  apps/v1

kind:  Deployment

(...)

containers:

-  name:  example-app-prod

image:  [yourimage]

env:

# Inject variables from a Kuberentes ConfigMap

-  name:  config_variables

valueFrom:

configMapRef:

name:  config-data

```

在您的 pod 中，您将能够看到配置图中定义的两个环境变量:

```
# env

HOSTNAME=5ad4e9e78e57

environment=dev

timezone=UTC

```

与 secrets 一样，如果您不想从 ConfigMap 加载所有值，您可以通过将`configMapRef`更改为`configMapKeyRef`来定义特定的键。

从 ConfigMaps 传递环境变量和在第一个示例中直接指定环境变量之间的主要区别在于，这里的环境变量生命周期与 pod 生命周期是分开的。这意味着您可以独立于正在运行的 pod 更新变量的值。或者换句话说，您需要自己重新启动 pod，以便将环境变量的新值加载到 pod 中。另一方面，当您在部署中直接指定环境变量时，对变量的每次更改都会自动触发 pod 重新启动。

## **总结**

环境变量在 Kubernetes 中起着重要的作用。您不仅可以使用它们向您的应用程序提供有关操作系统的基本信息，还可以将它们作为您的 pod 的主要配置机制或用于传递敏感信息。在 Kubernetes 中，提取尽可能多的配置信息、配置图和环境变量以保持 Docker 图像尽可能通用的情况并不少见。如您所见，即使是像环境变量这样简单的东西在 Kubernetes 中也有一些选项。如果你想了解更多，Release 创始人工程师 [Regis Wilson 写了为什么 Kubernetes 很难以及你能做些什么。](https://releasehub.com/blog/why-kubernetes-is-so-hard)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>