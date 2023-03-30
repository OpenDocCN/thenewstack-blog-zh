# Linux 内核 5.10 引入了静态调用来防止推测性执行攻击

> 原文：<https://thenewstack.io/linux-kernel-5-10-introduces-static-calls-to-prevent-speculative-execution-attacks/>

您可能熟悉 [Spectre](https://thenewstack.io/impact-spectre-meltdown-cloud/) ，这是 x86 处理器中的一个推测性执行漏洞，它打破了各种应用程序之间的隔离，允许攻击者欺骗程序向黑客泄露机密。更糟糕的是，为防范此类攻击而创建的安全检查实际上使这些应用程序更容易受到 Spectre 的攻击。

像 Spectre 和 Spectre version 2(也被称为分支目标注入— [CVE-2017-5715](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715) )都是操作系统不可知的，所以市场上的每个平台都必须采取措施来保护用户和数据免受这种攻击。

[Linux 5.10 内核](https://www.omgubuntu.co.uk/2020/12/new-linux-5-10-kernel-features)的发布带来了一个新特性——防止投机性执行攻击。这个特性被称为静态调用，是 Linux 内核中全局函数指针的替代品。

新的静态调用函数是`static_call()`，它使用代码修补来允许直接调用(与间接调用相反)并提供函数指针的灵活性和改进的性能，特别是在使用 retpolines 的情况下。

等等，什么？

## 什么是 Retpoline？

retpoline 是一个返回蹦床，它利用一个永不执行的无限循环来防止 CPU 推测间接跳转的目标。该系统还使用返回堆栈缓冲器(RSB)作为预测结构，类似于返回指令的分支预测器。为了确保 RSB 不会被恶意训练出无限循环，retpolines 总是从直接调用开始，以确保 RSB 预测到无限循环。

Retpolines 不是针对 Spectre 的原始缓解措施，而是 Google 在发现原始 Spectre 缓解措施会导致某些 CPU 架构(AMD 和 Intel)和特定工作负载下的相对速度变慢后创建的。

您可以通过发出以下命令来检查您正在运行的内核是否包含完整的 retpoline 支持:

`cat /sys/devices/system/cpu/vulnerabilities/spectre_v2`

您应该会看到类似如下的内容:

`Full generic retpoline, IBPB: conditional, IBRS_FW, STIBP: conditional, RSB filling`

在微软意识到其最初的解决方案无法与谷歌的竞争后，它在 Windows 10 中实现了 retpoline。2018 年，retpolines 找到了进入 Linux 内核的方法，从而保护开源平台免受此类攻击。

然而，retpolines 从来都不是理想的解决方案。开发人员不得不尽力避免间接调用，因为他们现在不得不用 retpolines 来实现。

什么是间接呼叫？这些调用发生在编译时不知道要调用的函数的地址时。相反，地址存储在指针变量中，以便在运行时使用。正如许多人(不幸地)发现的那样，这些间接调用很容易被推测性执行攻击所利用。

Retpolines 避免在指针变量中存储地址。然而，返回极化会引入以下问题:

1.  正确预测时速度会减慢。
2.  当预测错误时，速度会大幅降低。
3.  干扰英特尔的 CET 和其他保护。
4.  太复杂了。

因此，令开发者沮丧的是，retpolines 并不比最初的 Spectre 缓解方案好多少。

## 静态呼叫救援

自从 retpolines 出现以来，内核开发人员一直在努力寻找一个更好的解决方案，一个不从可写内存中可以找到间接跳转的位置开始工作的解决方案。

这就是静态调用发挥作用的地方。静态调用使用可执行内存(而不是可写内存)中的一个位置，该位置包含指向目标函数的跳转指令。执行静态调用需要调用特殊位置，然后跳转到实际目标。这就是所谓的经典代码蹦床，完全避免使用 retpolines。

## 如何声明静态调用

在使用静态调用之前，必须先用两个宏之一声明它们:

```
DEFINE_STATIC_CALL(name,  target);

```

或

```
DECLARE_STATIC_CALL(name,  target);

```

`DEFINE_STATIC_CALL`用一个给定的名字创建一个指向函数目标()的新的静态调用。DECLARE_STATIC_CALL 声明在别处定义的静态调用的存在。

静态调用的实际调用由:
处理

```
static_call(name)(args...);

```

您用 name 定义调用，这将导致通过 trampoline 直接跳转到目标函数。如果函数返回 X 值，那么`static_call()`将返回 X 值。

## 欢迎对 Linux 内核的静态调用

从内核 5.10 开始，静态调用已经成为现实。这意味着 Linux 操作系统的基础受到保护，不会受到类似 Spectre V1/2 的攻击，也不会遭受 retpolines 带来的问题。

阅读更多关于 Linux 内核静态调用的内容(由 Josh Poimboeuf 编写)[在这里](https://lore.kernel.org/patchwork/patch/1136425/)，你可以看到他为使用这个新特性而创建的内核补丁。

尽管 Linux 内核 5.10 还没有进入大多数发行版(到目前为止，大多数基于 Ubuntu 的发行版都在运行内核 5.8)，你应该期待这个内核在 2021 年 4 月达到 Ubuntu 的 21.04 版本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>