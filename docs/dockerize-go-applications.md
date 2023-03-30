# Dockerize Go 应用

> 原文：<https://thenewstack.io/dockerize-go-applications/>

本指南介绍了一些在 Docker 容器中运行 Go 应用程序的不同方法。我将带您完成编写 Dockerfile 文件、构建图像以及将该图像作为容器旋转的过程。

通过直接解决与从每个图像构建容器相关的权衡，我希望能够帮助您尽快将您的 Go 程序 Docker 化，并提供在 Docker 和 [Go](/tag/golang/) 社区中流行的基本解决方案。

指南中有很多有用的信息。然而，您确实需要在您的机器上安装 [Go](https://golang.org/dl/) 、 [Docker](https://docs.docker.com/engine/installation/) 和 [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 来本地构建和运行这些示例。

我推荐使用和我一样的应用程序，这样更容易跟进。它倒计时时间到 2016 年总统大选！你可以[从 GitHub:
克隆 app](https://github.com/nmccrory/go-prez)

```
$  git clone https://github.com/nmccrory/go-prez.git

```

## 使用官方形象

Docker 对于 Go 有一个官方的基础形象，简单的命名为 [**golang**](https://hub.docker.com/_/golang/) 。该图通过自动运行常用于在容器中构建和运行 Go 的命令，消除了 Go 应用程序“Dockerizing”的麻烦。

golang 图像有几种不同的变体，每种都有自己的优点和缺点。这里我只说两个镜像变体: **golang:onbuild** 和 **golang: <版本>** 。

### :onbuild 图像

使用 golang:onbuild 作为我们的基本映像，我们可以使用一行 docker 文件让我们的 hello-go 应用程序在容器内部运行。厉害！

创建一个名为 **Dockerfile** 的文件，并将其保存到您的基本应用程序目录中。

内置于 **golang:onbuild** 中的 **onbuild** 命令为我们构建并启动应用程序。然后就像用 Docker 构建镜像一样简单:

```
$  docker build  –t  yourname/go-prez  .

```

并将映像作为容器运行:

```
$  docker run yourname/go-prez

```

**优点**

*   开发人员可以在很短的时间内启动并运行。
*   开始“整理码头作业”所需的码头知识很少。
*   适合创建衍生图像。

**缺点**

*   缺乏对映像构建过程的控制。你不能控制*如何*将应用程序添加到容器中，不能控制*何时*构建 Go 二进制文件，也不能控制 **onbuild** 的执行。
*   图像开始超过 500MB！随着您制作的图像越来越多，驱动器空间可能会迅速减少。

### <version>戈朗:形象</version>

**golang: < version >**

对于这个例子，我将使用 Go 1.7 通过构建 golang:1.7 作为我的基础映像。为应用程序构建一个图像，我们称之为“hello-go ”,这意味着我们的 **dockerfile** 将不得不包含更多的行，但这是值得的，因为我们将获得构建过程的控制权。

```
FROM golang:1.7

RUN mkdir  -p  /app

WORKDIR  /app

ADD  .  /app

RUN go build  ./app.go

CMD  ["./app"]

```

为了构建映像并将其作为容器运行，我只需使用经典的 docker **build** 和 **run** 命令。

```
$  docker build  –t  yourname/hello-go  .

$  docker run  –p  8000:8000  –d  yourname/hello-go

```

**优点**

*   控制图像的构建顺序。
*   不需要手动安装 Go。

**缺点**

*   像 **golang: <版本>** 这样的图像有很多层。如果你正在寻找一个精益容器形象，这可能是一个缺点。
*   编写我们的 **dockerfile** 涉及更多的代码行。

## 使用暂存图像

golang 基本图像很大，并且包含我们不需要在我们的案例中使用的应用层。使用 golang 基础图像很方便，但是对于这个版本，我们不要担心方便性。

暂存图像是一个空图像。绝对没有任何东西与它相联系，通过传递性，它的空性也意味着它(几乎)没有大小。

创建尺寸不大的 Go 容器的诀窍是使用 scratch 作为基本映像。然后，不是复制整个应用程序并在映像中构建 Go 二进制文件，而是将 Go 二进制文件*本身*复制到映像中。

在接触 docker 文件之前，让我们在容器外编译 Go 应用程序。

```
$  GOOS=linux go build app.go

```

如果我们不把我们的 Go OS 声明为 Linux，它就不会在容器中执行——因为容器是从 Linux 派生出来的。像任何 Go 程序一样，编译后产生的二进制文件放在项目的根目录中。

从头开始构建我们的 Dockerfile 将会是这样的:

```
FROM scratch

COPY  /app  /app/

CMD  [“/app”]

```

需要注意的是，我们之前创建的二进制文件只被复制到一个容器目录中。容器内部没有构建任何东西，执行二进制文件也不需要特殊的工具。

**优点**

*   小图像文件大小。(“go-prez”出来只有~1.7MB)
*   图像没有几层。
*   利用 Go 的静态链接二进制文件。

**缺点**

*   目前，这个容器只能执行静态链接的二进制文件。
*   使用 net 包或 CGo 的程序需要额外的跑腿工作，因为这些包会创建动态链接的二进制文件。
*   大多数情况下缺少基本的应用层。例如，如果您想要安装任何语言或框架，您将在 Linux 基础上构建。

## 讨论

静态链接的二进制文件相对较大，但是它们具有难以置信的可移植性，因为你可以在任何地方执行它们。不过，你可能并不总是需要利用它们。使用 Docker 映像是快速分发和部署应用程序的好方法。

使用官方的 golang 图像是一种无痛的方式来整理 Go 程序，并会让您立即开始运行。然而，它们具有较大的尺寸折衷，并且根据图像的变化，缺乏过程控制。

暂存映像非常适合利用 Go 静态二进制文件的可移植性。因为二进制文件可以在任何环境中执行，所以您可以简单地将它注入到您的映像中并运行。从头开始也可以将你的图片的尺寸修剪得更加合理。

### **资源**

有越来越多的资源进一步阐述了图像优化和 Go 二进制文件。这些资源在使用 Docker 阐述 Go 应用程序方面做得非常好，当我有问题时，我发现它们非常有用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>