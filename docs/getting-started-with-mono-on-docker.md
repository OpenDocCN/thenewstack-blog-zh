# Docker 上的单声道入门

> 原文：<https://thenewstack.io/getting-started-with-mono-on-docker/>

Docker 发布才两年，现在有超过 13，000 张图片可以从 Docker 中心下载。如果您是 Docker 的新手，那么最好将它描述为一种将应用程序及其依赖项打包到可以在任何 Linux 服务器上运行的虚拟容器中的方式。这比在虚拟机和操作系统中打包一个应用程序要求低得多。

## 编程单声道应用

继 Java 和 C/C++之后，下一个最流行的编程语言是 C#，它是。Windows 上的网络世界。C#发布后不久，Mono 项目启动，以开发。NET，但是运行在 Linux 和 Mac 上。尽管最初怀疑这是微软通过专利攻击 Linux 的一种方式，但它已经发展壮大，现在支撑着跨平台移动开发系统 Xamarin。

之间有一些关键的区别。NET 和 Mono，例如 WinForms 和 WPF 是唯一的 Windows，但总的来说，你可以采取大多数。NET 编译的 C#可执行文件，把它们复制到安装了 Mono 的 Linux 系统上，这个命令:

…将运行应用程序。

这篇文章的目的是提供一个如何使用 Docker 和 Mono 技术的例子。

## 为什么是 Docker？

Docker 为什么这么好？假设您想在 Nginx、Centos 或 PostgreSQL 上尝试一些东西。如果没有 Docker，您可能会花费数小时来安装、配置等。有了 Docker，你可以在几秒钟内完成。

Docker 是开源的，将出现在下一个 Windows 2016 Server 版本中，但目前它的使用仅限于 Linux 和 Mac OS X。像我一样使用开源的 [Oracle VirtualBox](https://www.virtualbox.org/ "Link to ") 可以让你在 Windows 上安装 Docker，运行在 VirtualBox 内的虚拟机中。例如，你可以在 VirtualBox 中安装一个完整的 Linux，比如 Ubuntu Server，或者使用一个叫做 [Boot2Docker](https://docs.docker.com/installation/windows/#running-docker "Link to Boot2Docker") 的特殊助手应用程序。

## 我们靠岸吧

如果你是 Docker 的新手，请阅读[用户指南](http://docs.docker.com/userguide/ "Link to Docker User guide")。你需要理解运行应用，在容器中工作和应用的后台化。这并不十分困难；用户指南页面写得很好，易于阅读。

当创建一个在 Docker 中运行的应用程序时，情况变得有点复杂。我创建的应用程序是一个简单的“计算前 1000 个素数”的 C#使用厄拉多塞的[筛子。它输出 2 到 1000 之间的所有素数。这可以在 Windows 上编译和运行，也可以在任何安装了 Mono 的 Linux 系统上运行。](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes) 

```
using System;

namespace  sieve
{
    class  Program
    {
        const int HiPrime=1000;
        static readonly bool[]  Primes  =  new bool[HiPrime];//by default they're all false

        private static void Main(string[]  args)
        {

            for  (var  i  =  2;  i  &lt;  HiPrime;  i++)
            {
                Primes[i]  =  true;//set all potential primes true
            }

            for  (var  j  =  2;  j  &lt;  HiPrime;  j++)
            {
                if  (!Primes[j])  continue;
                for  (long  p  =  2;  (p  *  j)  &lt;  HiPrime;  p++)
                {
                    Primes[p  *  j]  =  false;
                }
            }

            for  (var index  =  2;  index  &lt;  Primes.Length;  index++)
            {
                if  (Primes[index])  Console.WriteLine(index);
            }

        }
    }
}

```

我们想在一个容器中运行这个应用程序。让我们先看一个更简单的应用程序——Hello World——然后再回到这里。

为了完整起见，我们将在 Ubuntu 14.04 下运行 Hello World。如果你已经安装了 Docker，你可以用这个命令运行一行 Hello World。

```
sudo docker run ubuntu:14.04  /bin/echo  'Hello world'

<a  href="http://thenewstack.io/wp-content/uploads/2015/05/runningecho.gif"><img class="alignnone size-full wp-image-369892"  src="http://thenewstack.io/wp-content/uploads/2015/05/runningecho.gif"  alt="Running Hello World in Docker"  width="650"  height="261"  /></a>

```

在这里，Ubuntu 14.04 就是容器。第一次运行时，它将下载并安装容器，这大约需要一分钟，或者对于 68 MB 的映像来说会稍微长一点。然后，它运行命令/bin/echo 'Hello World ',并在终端上输出 Hello World。在第二次和后续运行时，它会立即运行。

因此，要运行 sieve 应用程序，我们需要确保安装了 Mono，因为我们既需要编译 sieve，也需要运行它。Docker registry 列出了一堆 Mono 库，第一个似乎很受欢迎。第一个单声道链接会将您带到[这一页](https://registry.hub.docker.com/_/mono/ "Link to Mono page on Docker")。

现在要定义发生了什么，我们需要创建一个文件，特别是一个名为 Dockerfile 的文件。

## 什么是 Dockerfile？

Dockerfile 文件是一个文本文件，它包含了获取和构建软件的所有指令。

参考页面包括一个关于 [Dockerfiles](http://docs.docker.com/reference/builder/ "Link to Docker reference page for Dockerfiles") 的页面。对于示例 sieve 程序，它是一个非常短的文件。下面是我拼凑的 Dockerfile 文件:

```
FROM mono:latest
ADD  .  /home/david/sieve
RUN mcs  /home/david/sieve/sieve.cs
CMD  [  "mono",  "/home/david/sieve/sieve.exe"  ]

```

命令是大写的。FROM 指定要使用的单色图像。在这种情况下，它是单声道:最新的。您可以在这里指定您希望使用哪个版本的 Mono。ADD 将文件复制到指定的文件夹中，RUN 使用 Mono 编译器 mcs 编译它，CMD 使用 Mono 命令运行 exe。

第一次运行构建时，它将获取本地没有的任何内容。这个命令构建它:

```
sudo docker build  -t  sieve  .

<a  href="http://thenewstack.io/wp-content/uploads/2015/05/build.gif"><img class="alignnone size-full wp-image-369893"  src="http://thenewstack.io/wp-content/uploads/2015/05/build.gif"  alt="Docker Build"  width="640"  height="405"  /></a>

```

然后这个命令运行它:

```
sudo docker run sieve

<a  href="http://thenewstack.io/wp-content/uploads/2015/05/runsieve.gif"><img class="alignnone size-full wp-image-369894"  src="http://thenewstack.io/wp-content/uploads/2015/05/runsieve.gif"  alt="Running Mono Sieve App on Docker"  width="640"  height="255"  /></a>

```

瞧，一个显示最后一个质数的单声道应用程序。现在 Docker 有了更多的东西，例如，应用程序的后台化尤其重要，因为这使得 web 和其他服务器成为可能。

## 结论

Docker 是在不同平台上试用软件的一种非常方便和省时的方式。它使得软件从开发到生产的一致性变得容易。它允许将应用程序放在一个具有操作环境的容器中，类似于在虚拟机上运行，但占用的空间更少。每个虚拟机都有一份操作系统的副本，大小可以达到数千兆字节。Docker 实际上只有一个共享的操作系统。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>