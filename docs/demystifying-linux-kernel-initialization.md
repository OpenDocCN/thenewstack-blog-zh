# 揭秘 Linux 内核初始化

> 原文：<https://thenewstack.io/demystifying-linux-kernel-initialization/>

*你是否想过，当你打开笔记本电脑，拿着一杯热气腾腾的你最喜欢的饮料回来时，会发生什么？本文将揭开盖子，揭开 Linux 内核引导过程的神秘面纱。*

让我们首先讨论一下用户对他们系统上发生的事情和内核本身的状态有多少了解。Linux 内核不断地将诊断消息打印到内核环形缓冲区。顾名思义，这个环形缓冲区是一个循环缓冲区，旧消息会被新消息覆盖。它在初始化和引导期间打印关于初始化过程的重要消息。支持多个优先级，如紧急、关键、错误、警告和信息，并记录到环形缓冲区中。

如果您想知道如何查看这些消息，命令行工具 [dmesg](https://man7.org/linux/man-pages/man1/dmesg.1.html) 就是为此而存在的。用户可以运行`dmesg`命令行工具来检查或控制内核环形缓冲区。`dmesg`控制选项允许用户清除、首先读取、然后清除、启用和禁用向控制台打印消息。我们将主要关注检查选项。

`dmesg`命令是一个多用途的工具，有几个选项可以针对支持的日志工具和优先级来锁定特定的消息。

**支持的日志工具:**

*   kern–内核消息
*   用户-随机用户级消息
*   邮件-邮件系统
*   守护程序–系统守护程序
*   auth–安全/授权消息
*   syslog–syslogd 内部生成的消息
*   lpr–行式打印机子系统
*   新闻-网络新闻子系统

**支持的日志级别(优先级):**

*   紧急—系统不可用
*   警报—必须立即采取行动
*   crit —临界条件
*   err —错误条件
*   警告—警告条件
*   注意——正常但重要的情况
*   信息—信息
*   调试—调试级别的消息

例如，以下命令可用于查看特定的优先级消息:

*   `dmesg -l emerg#`显示紧急信息
*   `dmesg -l alert#`显示警报
*   `dmesg -l crit#`显示关键信息
*   `dmesg -l err#`显示低于紧急和严重级别的错误信息
*   `dmesg -l err+#`显示所有错误级别紧急、严重和错误

例如，以下命令可用于查看日志工具消息:

*   `dmesg -f kern`
*   `dmesg -f daemon`

这些信息可能很难解析和理解，除非你日复一日地查看它们。让我们看几个有用的选项来提高可读性。

*   -t(–notime)选项显示不带时间戳的消息；
*   -x(–decode)选项将日志工具和优先级数字解码为用户友好的可读信息。

将这两个选项结合起来会产生易于阅读和理解的消息。此外，这种没有时间戳的格式非常适合比较和分析来自不同内核引导的消息，以发现错误。

`dmesg -t -x` 

`Here is an excerpt from `dmesg`包括信息、调试、警告级别的消息:` 

 ````
kern  :warn  :  [drm]  Fence fallback timer expired on ring gfx
kern  :info  :  fbcon:  amdgpudrmfb  (fb0)  is primary device
kern  :info  :  [drm]  DSC precompute is not needed.
kern  :debug  :  calling  nf_defrag_init+0x0/0xff0  [nf_defrag_ipv4]  @  1037
kern  :debug  :  initcall nf_defrag_init+0x0/0xff0  [nf_defrag_ipv4]  returned  0  aft
er  1  usecs
kern  :debug  :  calling  nf_defrag_init+0x0/0xff0  [nf_defrag_ipv6]  @  1037

```

概述了内核环形缓冲区以及如何查看内核消息后，我们可以深入内核初始化序列。

内核初始化序列很复杂，使用 initcalls 分几个阶段执行。initcalls 为 Linux 引导过程贡献了大量时间。initcall 按功能分组，早期 init call[early _ init call(fn)]在初始化 SMP(对称多处理)之前运行，针对内置(静态链接)代码，不针对动态可加载模块。在撰写本文时，内核中定义了超过 110 个`early_initcall()`。纯 initcall 的限制要多得多，它不依赖于任何其他东西，并且只初始化无法静态初始化的变量。和`early_initcall()`一样，`pure_initcall()`也是为内置代码而存在，而不是为模块而存在。根据这种类型的 initcall 的限制性使用，内核中只有大约 10 个`pure_initcall()`定义。在 pci 子系统中可以找到一个这样的使用纯 initcall 的例子，当早期的参数在`pci_realloc_setup_params()`中被解析时初始化参数。

在[include/Linux/init . h](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/include/linux/init.h):
中定义了八个 initcall 调用级别

```
#define pure_initcall(fn)               __define_initcall(fn, 0)

#define core_initcall(fn)               __define_initcall(fn, 1)
#define core_initcall_sync(fn)          __define_initcall(fn, 1s)
#define postcore_initcall(fn)           __define_initcall(fn, 2)
#define postcore_initcall_sync(fn)      __define_initcall(fn, 2s)
#define arch_initcall(fn)               __define_initcall(fn, 3)
#define arch_initcall_sync(fn)          __define_initcall(fn, 3s)
#define subsys_initcall(fn)             __define_initcall(fn, 4)
#define subsys_initcall_sync(fn)        __define_initcall(fn, 4s)
#define fs_initcall(fn)                 __define_initcall(fn, 5)
#define fs_initcall_sync(fn)            __define_initcall(fn, 5s)
#define rootfs_initcall(fn)             __define_initcall(fn, rootfs)
#define device_initcall(fn)             __define_initcall(fn, 6)
#define device_initcall_sync(fn)        __define_initcall(fn, 6s)
#define late_initcall(fn)               __define_initcall(fn, 7)
#define late_initcall_sync(fn)          __define_initcall(fn, 7s)

```

并与 [init/main.c](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/init/main.c) :
中的 initcall_level_names[]保持同步

```
static const char *initcall_level_names[]  __initdata  =  {
        "pure",
        "core",
        "postcore",
        "arch",
        "subsys",
        "fs",
        "device",
        "late",
};

```

启用 KNL(内核启动参数) [initcall_debug](https://docs.kernel.org/admin-guide/kernel-parameters.html) 允许我们在执行 initcall 时跟踪它们。这对于理解内核启动顺序、调试早期内核崩溃和测量每个 initcall 初始化所花费的时间非常有用。这是跟踪内核启动时间从一个版本到另一个版本的回归的好方法。如果一个或多个 initcalls 开始花费更长时间运行，这可能表明可能有问题。

另一个有用的 KNL [initcall_blacklist](https://docs.kernel.org/admin-guide/kernel-parameters.html) 参数可用于指定要跳过的 initcall 函数列表。这对于调试内置模块和 initcalls 很有用。请参考[内核的命令行参数](https://docs.kernel.org/admin-guide/kernel-parameters.html)。

现在让我们看看如何为 initcalls 启用`initcall_debug`并解析`dmesg`。

第一步是确保在您的内核中启用`CONFIG_PRINTK_TIME`和`CONFIG_KALLSYMS`内核配置选项。如果没有，您将不得不构建、安装并引导一个启用了这些选项的新内核。请参考“[Linux 内核开发初学者指南”(LFD103)](https://training.linuxfoundation.org/training/a-beginners-guide-to-linux-kernel-development-lfd103/) 或其他关于如何构建和引导定制内核的资源。一旦您启用了正确的选项，您就可以编辑`/etc/default/grub`来将`printk.time=1 initcall_debug`追加到`GRUB_CMDLINE_LINUX`变量，如下所示:

`GRUB_CMDLINE_LINUX="earlyprintk=vga printk.time=1 initcall_debug"`

现在，让我们在系统准备就绪后重启并运行`dmesg -t -x`命令。我通常将`dmesg`保存到一个文件中进行解析和分析。

```
kern  :debug  :  initcall con_init+0x0/0x378  returned  0  after  0  usecs
kern  :debug  :  initcall hvc_console_init+0x0/0x1f  returned  0  after  0  usecs
kern  :debug  :  initcall xen_cons_init+0x0/0x80  returned  0  after  0  usecs
kern  :debug  :  initcall univ8250_console_init+0x0/0x39  returned  0  after  0  usecs
kern  :debug  :  initcall kgdboc_earlycon_late_init+0x0/0x31  returned  0  after  0  usecs
kern  :debug  :  initcall init_hw_perf_events+0x0/0x6d8  returned  0  after  0  usecs
kern  :debug  :  initcall do_init_real_mode+0x0/0x1a  returned  0  after  0  usecs
kern  :debug  :  initcall trace_init_perf_perm_irq_work_exit+0x0/0x1c  returned  0  after  0  usecs

```

下面(来自 https://elinux.org/Initcall_Debug)的简短脚本向您展示了需要更长时间才能完成的 initcalls:

`cat dmesg.out | grep "initcall" | sed "s/\(.*\)after\(.*\)/\2 \1/g" | sort -n`

来自我的系统的例子:

```
64564  usecs kern  :debug  :  initcall serial8250_init+0x0/0x245  returned  0  
87029  usecs kern  :debug  :  initcall btusb_driver_init+0x0/0xff0  [btusb]  returned  0  
110960  usecs kern  :debug  :  initcall ahci_pci_driver_init+0x0/0xff0  [ahci]  returned  0  
120384  usecs kern  :debug  :  initcall init_kprobe_trace+0x0/0x21c  returned  0  
227677  usecs kern  :debug  :  initcall br_init+0x0/0x12a  [bridge]  returned  0  
281999  usecs kern  :debug  :  initcall init_module+0x0/0xff0  [raid6_pq]  returned  0  
1104000  usecs kern  :debug  :  initcall acpi_init+0x0/0x647  returned  0  
2218805  usecs kern  :debug  :  initcall inet6_init+0x0/0x413  returned  0

```

启用`[initcall_debug](https://docs.kernel.org/admin-guide/kernel-parameters.html)`增加消息数量。请确保`CONFIG_LOG_BUF_SHIFT`内核配置选项为 18，以将日志缓冲区大小设置为 256K。通过启用 [driver_async_probe](https://docs.kernel.org/admin-guide/kernel-parameters.html) KNL 以异步模式运行驱动程序探测，可以加速内核启动过程。使用此选项，可以指定异步探测的驱动程序名称列表。请注意，并非所有驱动程序都支持异步探测。如果你想了解更多关于 initcalls 的知识，请参考“[Linux 内核 initcalls 简介](https://www.collabora.com/news-and-blog/blog/2020/07/14/introduction-to-linux-kernel-initcalls/)”

`[bootgraph.pl](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/scripts/bootgraph.pl)`脚本将一个`dmesg`输出转换成 SVG 图形，显示哪些函数需要多少时间。你可以用各种程序查看 SVG 图形，包括 Inkscape、Gimp 和 Firefox。随着您对 initcalls 的了解越来越多，我将把它作为一个资源留给您去探索。

下面是我用来跟踪 initcall 时间和错误的 shell 脚本。

```
====================================================================
#!/bin/bash
#
# SPDX-License-Identifier: GPL-2.0
#
# Copyright(c) Shuah Khan <skhan@linuxfoundation.org>
# License: GPLv2
#
# Generates wiki format table of initcall times list from
# dmesg | grep initcall output
# Boot kernel with printk.time=1 initcall_debug command line options 
# Usage: boot_initcall_tbl.sh <dmesg.out>
# See async_run_entry_fn() and Documentation/core-api/printk-formats.rst

# Print Table header
echo  "Init Call times"
uname  -a
cat  /proc/cmdline
grep  "Command line"  $1  |  awk  -F  ']'  '{print $2}'
echo  "===================================================================="
echo  "Init calls that took longer to complete > 0 usecs"
echo  "===================================================================="
echo  "| **Init Call** | **Module** | **Retun Value** | **Time (uses)** |"
echo  "===================================================================="
grep initcall  $1  |  awk  -F  ' '  '{ if (NF == 9 && $8 > 0) print "| " $4 " | --- | " $6 " | " $8 " | "}'
grep initcall  $1  |  awk  -F  ' '  '{ if (NF == 10 && $9 > 0) print "| " $4 " | " $5 " | " $7 " | " $9 " | "}'
echo  "===================================================================="
echo  "Failed Init calls (return value < 0)"
echo  "===================================================================="
echo  "| **Init Call** | **Module** | **Retun Value** | **Time (uses)** |"
echo  "===================================================================="
grep initcall  $1  |  awk  -F  ' '  '{ if (NF == 9 && $6 < 0) print "| " $4 " | --- | " $6 " | " $8 " | "}'
grep initcall  $1  |  awk  -F  ' '  '{ if (NF == 10 && $7 < 0) print "| " $4 " | " $5 " | " $7 " | " $9 " | "}'
echo  "===================================================================="
====================================================================

```

正如您所看到的，一旦您有了 initcall 信息，这些数据就可以用来理解引导顺序、调试问题以及跟踪从一个内核版本到另一个内核版本的内核引导时间。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>`