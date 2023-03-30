# Linux 内存访问工作负载模拟器(masim)简介

> 原文：<https://thenewstack.io/an-intro-to-the-linux-memory-access-workload-simulator-masim/>

内存子系统是 Linux 内核最关键的部分之一，因此，它必须是高性能、稳定和可靠的。多年来，已经开发了许多工具和机制来帮助改进内存子系统。其中包括超级页面、NUMA 节点/NUMA 仿真、内存压缩、OOM 杀手等。

为内存子系统开发的另一个有用的工具是 [masim](https://github.com/sjp38/masim) ，这是一个用户空间工具，用于模拟密集型内存访问工作负载，以测试内存系统的行为和性能。它是 2018 年由 SeongJae Park 推出的。

截至 2023 年初，它被积极用于生成测试 [damo、](https://github.com/awslabs/damo)DAMON[的用户空间工具](https://sjp38.github.io/post/damon)等用例的人工工作负载。masim 的一个重要特性是能够定制正在生成的工作负载。因此，我们可以使用 masim 来测试存储器的多个方面。

## 使用预定义的配置安装和使用 Masim

现在，让我们看看如何使用 [masim](https://github.com/sjp38/masim) 。为此，我们必须首先下载并安装它，可以这样做:

```
$  git clone https://github.com/sjp38/masim
$  cd masim
$  make

```

这将生成 masim 可执行文件。现在，我们可以通过使用 configs 文件夹中的预定义配置或自己定义一个配置来开始生成工作负载。让我们使用一个预定义的配置`–100mb.cfg`。

```
$  ./masim configs/100mb.cfg
huge phase  1  :  74868  accesses/msec,  5000  msecs run

```

我们来看看`100mb.cfg`包含了什么:

```
$  cat configs/100mb.cfg
#regions
# name, length
a,  100000000

# phase 1
# name of phase
huge phase  1
# time in ms
5000
# access patterns
# name of region, randomness, stride, probability
a,  1,  64,  80

```

配置文件包含多个部分——区域、阶段和访问模式。让我们逐一剖析:

### 地区

区域定义了我们希望用于工作负载的所有内存区域。每个区域都有名称和字节大小。上面的例子定义了一个名为“a”的内存区域，大小为 100 MB。

### 阶段

在阶段部分，我们可以定义 masim 要进行的存储器访问的性质。每个阶段的子部分解释如下:

*   阶段名称:
    *   用户提供的每个阶段的名称。在上面的例子中，名字是`huge phase 1`。
*   时间:
    *   masim 应该运行该阶段的持续时间(以毫秒为单位)。
*   访问模式:
    *   这里，我们指定应该如何访问特定的内存区域。在上面的例子中，提到 masim 应该访问随机性设置为 1 的区域“a ”( 0 表示顺序访问)，跨距 64 表示当读或写存储器时应该有 64 字节的间隙(与顺序读/写相关),概率表示该特定模式应该得到的总访问的份额。如果以 40 的概率为这个阶段定义另一个访问模式，它将获得比上面定义的模式更少的内存访问份额。

### 定义自定义配置

让我们看看如何定义我们自己的配置。对于这个例子，我们将使用 masim 的另一个特性——huge pages。Masim 能够使用大型页面，以及普通页面。让我们首先定义一个访问 4MB 内存的自定义配置，如下所示:

```
#regions
# name, length
a,  4194304

# phase 1
# name of phase
huge phase  1
# time in ms
5000
# access patterns
# name of region, randomness, stride, probability
a,  1,  64,  90

```

现在让我们用巨大的页面来运行这个工作负载:

```
$  ./masim  -p  -h  configs/custom_config.cfg
memory regions
        a:  4194304  bytes

Phase  (huge phase  1)  for  5000  ms
        Pattern  0
                randomly access region  a  with stride  64
huge phase  1:                  86428  accesses/msec,  5000  msecs run

```

在上面的例子中，`-h`标志指示 masim 使用 HugePages，`-p`标志仅用于给出详细的输出。

### 其他重要标志

我们可以看到所有可以传递给 masim 的标志如下:

```
$  ./masim  --help
Usage:  masim  [OPTION...]  [config file]
Simulate given memory access pattern

  -d,  --dry_run              flag for dry run;  If this flag is set,  the program
 ends without real access
  -h,  --use_hugetlb          use hugepages
  -p,  --pr_config            flag for configuration content print
  -q,  --quiet,  --silent      suppress all normal output
  -r,  --default_rw_mode=<ro|wo|rw>
 set default read/write mode as this
  -t,  --hint=<hint method> gives access pattern hint to system with given
 method
  -?,  --help Give this help list
      --usage                Give  a  short usage message

```

我们已经看到了`-h`和`-p`，旗`-d`、`-q`和`-?`不言自明。让我们看看其他的旗子。

*   `-r`:指定默认模式来调整 masim 的存储器访问行为。我们可以指定只读、只写或读写。
*   `-t`:这里可以指定`mlock`或者`madvise`。`mlock`防止内存被交换到交换区，而`madvise`指导内核如何访问内存以优化系统性能。

### 测试运行示例

让我们看一些`--hint`和`--default_rw_mode`标志的测试运行示例。

1.  在读/写模式下使用`mlock`

在本例中，我们生成一个工作负载来读写内存，并使用`mlock`来确保进程使用的内存不会被换出。

```
  $  ./masim  -r  rw  -t  mlock configs/stairs.cfg
initial phase: 42961  accesses/msec,  10001  msecs run
phase  0: 43262  accesses/msec,  5002  msecs run
phase  1: 44188  accesses/msec,  5001  msecs run
phase  2: 41742  accesses/msec,  5002  msecs run
phase  3: 43122  accesses/msec,  5000  msecs run
phase  4: 43594  accesses/msec,  5000  msecs run
phase  5: 49676  accesses/msec,  5000  msecs run
phase  6: 46549  accesses/msec,  5012  msecs run
phase  7: 43498  accesses/msec,  5002  msecs run
phase  8: 42170  accesses/msec,  5001  msecs run
phase  9: 41418  accesses/msec,  5000  msecs run

```

1.  在只写模式下使用`madvise`

在本例中，我们正在生成一个只写入内存的工作负载，并使用`madvise`来指导内核了解内存访问模式并优化性能。Masim 确保配置文件中指定的内存区域按照页面大小对齐。

```
$  ./masim  -r  wo  -t  madvise  configs/stairs.cfg
initial phase: 67672  accesses/msec,  10000  msecs run
phase  0: 69480  accesses/msec,  5001  msecs run
phase  1: 43018  accesses/msec,  5003  msecs run
phase  2: 32479  accesses/msec,  5004  msecs run
phase  3: 32198  accesses/msec,  5003  msecs run
phase  4: 32184  accesses/msec,  5001  msecs run
phase  5: 32735  accesses/msec,  5001  msecs run
phase  6: 37524  accesses/msec,  5002  msecs run
phase  7: 43079  accesses/msec,  5002  msecs run
phase  8: 49813  accesses/msec,  5002  msecs run
phase  9: 55050  accesses/msec,  5000  msecs run

```

### 摘要

总而言之，我们了解了什么是 masim，如何使用它，以及如何定制它来生成定制的工作负载。我们还了解了它与各种标志和配置文件的内部工作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>