# 如何使用 Terraform 的' for_each '，并附有示例

> 原文：<https://thenewstack.io/how-to-use-terraforms-for_each-with-examples/>

[](https://twitter.com/DavidZisky)

[Dawid Ziolkowski](https://twitter.com/DavidZisky)

[Dawid 一开始有 10 年的网络/系统工程师经验，中间是 DevOps，最近是云原生工程师。他曾在一家 IT 外包公司、一家研究机构、电信公司、一家托管公司和一家咨询公司工作过，因此他从不同的角度收集了很多知识。如今，他正在帮助公司迁移到云计算和/或重新设计他们的基础设施，以实现更加云本地化的方法。](https://twitter.com/DavidZisky)

[](https://twitter.com/DavidZisky)[](https://twitter.com/DavidZisky)

Terraform 是最受欢迎的[基础设施之一，作为 code](https://en.wikipedia.org/wiki/Infrastructure_as_code) (IaC)工具。使用 Terraform，您可以编写代码来定义所需的基础设施组件以及它们的配置。然后执行代码，Terraform 将确保您的基础设施按照您定义的方式进行设置。这意味着要么创建新的组件，要么用“所有这些都已经创建好了”来响应

听起来很简单，对吧？

实际上，Terraform 代码可能相当复杂。当你想做一些高级的事情，比如迭代一定数量的资源时，这尤其可能。

例如，假设您想要创建多个具有相同配置的虚拟机。对于这种情况，在地形中你可以使用`for_each`。在这篇文章中，你将了解到它是什么，以及如何和何时使用它。

## **带有地形的基础设施代码**

如果你是第一次接触 [Terraform](https://www.terraform.io/) ，在我们继续之前，你需要了解它到底是什么。

现代环境非常复杂，当您想要添加、更改或销毁基础架构的某些组件时，您有几种选择。如果你在云上，你可以访问你的云提供商的 web 用户界面，并在那里执行任何必要的操作。你也可以使用 CLI，甚至自己写一些脚本，调用你的云提供商 API。

然而，所有这些选择都有一些限制。在 web 用户界面中单击不会缩放。而且，您不希望每次需要新环境时都创建许多不同的服务。

使用 CLI 或编写自己的脚本是一个进步。但是为什么不向前迈两步，使用专用的基础设施即代码工具呢？

> 使用 Terraform 的最大优势之一是它将保存您的基础设施的状态。

Terraform 就是这样一种工具。您编写特定于 Terraform 的代码，定义您希望基础设施是什么样子。然后你执行 Terraform，一切都为你照顾。这是一种高效且可扩展的创建基础设施的方式。

此外，使用 Terraform 的最大优势之一是它将保存您的基础设施的状态。因此，它会一直尝试让您的基础架构保持同步。所以一旦你执行了 Terraform，它只会创建、更改或销毁与保存状态不同步的资源。

## **地形元参数**

在我们深入解释`for_each` 是如何工作的之前，让我们简单地谈谈它到底是什么。

在 Terraform 中，我们主要讲资源块和模块块。例如，当您想要创建一个虚拟机时，您需要用该虚拟机的配置细节来定义一个资源块。在资源和模块块中，您还可以使用五个所谓的元参数之一。这些是特殊指令，本质上不是资源配置的一部分，但是它们指示 Terraform 做一些与该资源相关的动作。而这些指令中有一个是`for_each`。

正如我已经提到的，`for_each`元参数的主要目的是创建一个资源的多个实例。所以，可以想象，知道了还是挺有用的。

另外值得一提的是，0.12 版本的 Terraform 中加入了`for_each`。不过我希望你反正已经升级到 Terraform 1.x 了。

## **多种资源**

为了更好地理解`for_each`的作用，让我们看看你如何在不使用`for_each`的情况下在 Terraform 中达到同样的效果。

我们讨论的结果是部署同一资源的多个副本。让我们以虚拟机为例。

通常，要部署多个虚拟机，您必须指定多个资源块，如下所示:

```
resource  "google_compute_instance"  "vm1"  {
  name =  "vm1"
  machine_type  =  "e2-small"
  zone =  "us-central1-a"
  (...)
}

resource  "google_compute_instance"  "vm2"  {
  name =  "vm2"
  machine_type  =  "e2-medium"
  zone =  "us-central1-a"
  (...)
}

resource  "google_compute_instance"  "vm3"  {
  name =  "vm3"
  machine_type  =  "f1-micro"
  zone =  "us-central1-a"
  (...)
}

```

看起来有很多重复的代码，不是吗？这正是`for_each`可以帮忙的地方。

不用为每个虚拟机复制所有代码，您可以一次定义您的资源，并提供一个映射或一组字符串来迭代。

看一下这个例子。这就是用`for_each` :
实现上述相同结果的方式

```
resource  "google_compute_instance"  "vm"  {

for_each  =  {

"vm1"  =  "e2-small"

"vm2"  =  "e2-medium"

"vm3"  =  "f1-micro"

}

name  =  each.key

machine_type  =  each.value

zone  =  "us-central1-a"

(...)

}

```

如您所见，我们在`for_each`块中将每个虚拟机不同的配置参数定义为键值对，并将每个虚拟机相同的参数留在资源块中。然后，我们通过特殊的关键字`each.key`**和`each.value`**访问键值对。****

 ****如果您想传递两个以上的参数(键和值)该怎么办？例如，如果您还想参数化上面示例中的区域，该怎么办呢？您可以简单地将值更改为映射，如下所示:

```
resource  "google_compute_instance"  "vm"  {

for_each  =  {

"vm1"  =  {  vm_size  =  "e2-small",  zone  =  "us-central1-a"  }

"vm2"  =  {  vm_size  =  "e2-medium",  zone  =  "us-central1-b"  }

"vm3"  =  {  vm_size  =  "f1-micro",  zone  =  "us-central1-c"  }

}

name  =  each.key

machine_type  =  each.value.vm_size

zone  =  each.value.zone

(...)

}

```

您可以在值中传递任意数量的参数。那么在实际的资源配置中，可以用`each.value.<parameter_key>`**来引用它们。**

 **为了保持代码的整洁，并且能够重用不同资源的值，您甚至可以将实际参数提取到一个变量中:

```
locals  {
  virtual_machines  =  {
 "vm1"  =  {  vm_size  =  "e2-small",  zone  =  "us-central1-a"  },
 "vm2"  =  {  vm_size  =  "e2-medium",  zone  =  "us-central1-b"  },
 "vm3"  =  {  vm_size  =  "f1-micro",  zone  =  "us-central1-c"  }
  }
}

resource  "google_compute_instance"  "vm"  {
  for_each  =  local.virtual_machines
  name  =  each.key
  machine_type  =  each.value.vm_size
  zone  =  each.value.zone
  (...)
}

```

## **‘for _ each’对‘count’**

如果您不熟悉 Terraform，您可能已经使用了另一个类似的元参数:`count`**。虽然`count`**也允许您创建同一个资源的多个实例，但是`count`**和`for_each`是有区别的。后者对资源顺序的变化不敏感。******

 ******`count`**的一个常见问题是，一旦你删除了除最后一个资源以外的任何资源，Terraform 就会试图强制替换所有与索引不匹配的资源。**

 **使用`for_each`不会有这个问题，因为它使用映射的键作为索引。你不能在同一个资源上同时使用`count`**和`for_each`，但是你为什么要这样做呢？**

 **`for_each`有什么弊端吗？是的。

## **‘for _ each’的局限性**

虽然`for_each`使用起来非常简单，但是有一些限制你应该知道。首先，您的`for_each`映射块中的键必须有一个已知的值。因此，例如，它们不能由函数动态生成(如`bcrypt`**或`timestamp`**)。它们也不能引用云提供商提供的特定于资源的属性，比如云资源 ID。另一个限制是不能使用敏感值作为`for_each`的参数。基本上在使用`for_each`的时候，需要直接指定数值。****

 ****> 使用‘for _ each’相对容易，但是你需要对它的工作原理有一个坚实的理解，才能从中获得最大的好处。

## **总结，多学习**

`for_each`大概是最常用的 Terraform 元论之一。出于高可用性和可伸缩性的原因，现代环境通常由多个资源实例组成。使用`for_each`相对容易，但是你需要对它的工作原理有一个坚实的理解，以便从中获得最大的好处。它也有自己的局限性。

在本文中，您了解了`for_each`是如何工作的，并获得了一些如何有效使用它的技巧。现在，你可以试着自己摆弄它或者研究其他元论点。

## **按比例地形**

[ReleaseHub](https://hubs.li/Q011Rfby0) 的环境即服务(environment as a service)是一种易于使用、高度可扩展的服务，它利用 Terraform 来创建甚至是最复杂的环境的快照，并在您的开发生命周期中自动管理它们的创建和拆除。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>********************