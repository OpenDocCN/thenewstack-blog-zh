# 用 ftrace 实现 Linux 动态函数插装

> 原文：<https://thenewstack.io/linux-dynamic-function-instrumentation-with-ftrace/>

[](https://www.linkedin.com/in/yonatan-goldschmidt-a4aa83198/?originalSubdomain=il)

[yona tan gold Schmidt](https://www.linkedin.com/in/yonatan-goldschmidt-a4aa83198/?originalSubdomain=il)

[yona tan gold Schmidt 是 grate 的高级软件工程师，作为低级编程专家，负责监督他们实时持续优化解决方案的开发和部署。在加入 grate 之前，Yonatan 在以色列国防军担任了近六年的团队领导和研发专家。](https://www.linkedin.com/in/yonatan-goldschmidt-a4aa83198/?originalSubdomain=il)

[](https://www.linkedin.com/in/yonatan-goldschmidt-a4aa83198/?originalSubdomain=il)[](https://www.linkedin.com/in/yonatan-goldschmidt-a4aa83198/?originalSubdomain=il)

如果你曾经检查过一个正在运行的 Linux 内核，你可能听说过 [ftrace](https://www.kernel.org/doc/Documentation/trace/) 。这是一个跟踪内核中的流和事件的令人惊奇的工具，并且它非常通用——但是如果它不完全支持您的用例呢？

最近，在进行研究时，我想遵循一个特定的内核代码流:我要修改一个现有内核机制的行为，我需要理解不同函数之间的数据流。

与您试图分析的任何开源项目一样，您的助手就是源代码。Linux 除了是开源的，还提供了大量用于调试的动态工具，它们是静态阅读代码的很好补充。在本文中，我将重点介绍其中的一个工具 ftrace，并展示我为使其过滤功能更加通用而做的修改。

## ftrace

在其基础上，ftrace (Function Tracer)是一个动态函数检测基础设施。它可以用来在几乎所有的内核函数上设置动态跟踪，还支持大量的静态跟踪点，用来记录核心内核事件。它在大多数现代 Linux 发行版中都可用。

它是跟踪内核中的流和事件的强大工具。通过`tracefs`提供内核 API 和用户模式控制接口，它可以说是 Linux 中最全面的跟踪工具之一。

ftrace 有许多操作模式，在这篇文章中我将重点介绍`function_graph`模式:它允许你递归地记录来自给定函数的调用图。

如果您从未使用过它(或者只是作为一个小小的提醒)，下面是它在跟踪`/proc/version`上的`vfs_read`调用的内核路径时的样子:

除了阅读代码之外，这个调用图还可以为理解流程提供很大的帮助。

这不是 ftrace 的入门指南，所以我假设您从现在开始已经了解了它的基础知识。如果你想要更长的关于 ftrace 及其附加模式的介绍，我推荐阅读这些文章:[使用 Ftrace 调试内核](https://lwn.net/Articles/365835/)、 [Ftrace:隐藏的灯开关](https://lwn.net/Articles/608497/)和 [ftrace:跟踪你的内核函数](https://jvns.ca/blog/2017/03/19/getting-started-with-ftrace/)。

回到这里，我试图理解一个特定 TCP 包的接收流(它通过哪些函数)。

TCP 接收入口点函数是[TCP _ v4 _ rcv](https://elixir.bootlin.com/linux/v5.0/source/net/ipv4/tcp_ipv4.c#L1781)(https://elixir . boot Lin . com/Linux/v 5.0/source/net/IP v4/TCP _ IP v4 . c # l 1781)。我们可以`function_graph`它，但是我们很快就会遇到一个问题——有大量的数据是由图形跟踪这个函数生成的:在我的桌面上，在不太重的网络负载下，我得到了一个 5MB/s 的跟踪文件！这是大量的数据。

这里指出了两个局限性:

1.  这些呼叫没有经过任何过滤，所有呼叫都被写入跟踪文件。我希望看到特定数据包上的`tcp_v4_rcv`图，而不是系统处理的所有 TCP 数据包。
2.  调用没有附加任何信息(例如，函数参数)。看一下上面的示例图——只有函数名和持续时间。我们如何区分“有趣”的电话？

## 现有过滤器？

让我们从现有的 ftrace 特性中寻求帮助。为此，我们可以从[很长的文档](https://www.kernel.org/doc/Documentation/trace/ftrace.txt)开始。

ftrace 可以记录当前的 PID/TGID 和命令(`/proc/pid/comm`，并在跟踪文件中报告。据我所知，没有更具体的细节可以记录在每个条目上。

ftrace 还支持 PID 过滤:使用`set_ftrace_pid`文件，我们可以将跟踪的调用限制在特定的进程中。例如，这将限制对 init 进程的跟踪:

```
# cd /sys/kernel/tracing

# echo 1 > set_ftrace_pid

```

听起来不错，是吧？对于许多过滤用例来说，这就足够了:一个简单的程序将它的 PID 写到`set_ftrace_pid`，然后调用一些你希望跟踪的内核代码。

在网络 RX 的情况下，这是不可能的(虽然严格来说，这可以通过将 RX 流固定到特定的 CPU[及其 ksoftirqd/cpu 线程]来实现)。但是我想要一个更通用的解决方案。):在系统的几乎任何线程的环境中，网络分组在可能运行在任何 CPU 上的软件中断中被处理。用 PID 进行过滤。(在 Linux 中，软件中断是为响应某些内核/硬件事件而定期执行的一组常见的高优先级作业。有时，它们完成硬件中断延迟的工作，但不一定。你可以在这里阅读更多关于他们的信息。

我不知道 ftrace 允许任何其他复杂的过滤器。我们可以尝试从外部过滤掉事件(例如，在网络接收的情况下——用 iptables 过滤掉不需要的数据包，这样它们就不会出现在`tcp_v4_rcv` )…

…或者，我们可以调整 ftrace 来提供我们需要的过滤！

## 调整 ftrace 的过滤

以下所有 Linux 参考资料都基于内核 5.0+。

我的想法是:ftrace 有基于 PID 的过滤功能。我可以提供外部过滤，在一个调用之后，我希望跟踪通过我的过滤器，当前运行的进程的 PID 可以被“添加”到`set_ftrace_filter`，有效地使进程被跟踪(我将得到我想要的调用图)

当你写信给`set_ftrace_pid`时会发生什么？快速搜索该字符串会得到注册 tracefs 文件的[`ftrace_init_tracefs`](https://elixir.bootlin.com/linux/v5.0/source/kernel/trace/ftrace.c#L6593)(https://elixir . boot Lin . com/Linux/v 5.0/source/kernel/trace/ftrace . c # l 6593)；而[`ftrace_pid_write`](https://elixir.bootlin.com/linux/v5.0/source/kernel/trace/ftrace.c#L6526)(https://elixir . bootlin . com/Linux/v 5.0/source/kernel/trace/ftrace . c # l 6526)实际上实现了 write。

`ftrace_pid_write`就其看似简单的目的而言相当长。总而言之，这个函数做三件事:

1.  从输入 PID 创建一个`trace_pid_list`结构(可以编写多个 PID 进行跟踪)，并存储起来以备后用。
2.  注册一个名为[ftrace _ filter _ PID _ sched _ switch _ probe](https://elixir.bootlin.com/linux/v5.0/source/kernel/trace/ftrace.c#L6336)的`sched_switch`事件处理程序。
3.  更新使用 PID 过滤的跟踪程序，将[ftrace _ PID _ func](https://elixir.bootlin.com/linux/v5.0/source/kernel/trace/ftrace.c#L146)(https://elixir . boot Lin . com/Linux/v 5.0/source/kernel/trace/ftrace . c # L146)作为其跟踪处理程序。

实际上，第三步启用了过滤。`ftrace_pid_func`非常简单:由`reading tr->trace_buffer.data->ftrace_ignore_pid`调用它来代替原来的跟踪处理程序，并检查当前任务是否应该被跟踪。如果(且仅当)应该执行跟踪，它调用原始处理程序。

让我们看看这个字段在哪里被更新。`ftrace_pid_write`之前已经注册了`sched_switch`赛事的`ftrace_filter_pid_sched_switch_probe`。系统中的每个任务切换都会调用这个处理程序。它知道下一个要运行的任务是什么。

```
static void

ftrace_filter_pid_sched_switch_probe(void *data,  bool preempt,

struct task_struct *prev,  struct task_struct *next)

{

struct trace_array *tr  =  data;

struct trace_pid_list *pid_list;

pid_list  =  rcu_dereference_sched(tr->function_pids);

this_cpu_write(tr->trace_buffer.data->ftrace_ignore_pid,

trace_ignore_this_task(pid_list,  next));

}

```

它调用[trace _ ignore _ this _ task](https://elixir.bootlin.com/linux/v5.0/source/kernel/trace/trace.c#L354)(https://elixir . bootlin . com/Linux/v 5.0/source/kernel/trace/trace . c # L354)来查看新任务的 PID 是否被标记为跟踪:

```
bool

trace_ignore_this_task(struct trace_pid_list *filtered_pids,  struct task_struct *task)

{
/*
* Return false, because if filtered_pids does not exist,
* all pids are good to trace.
*/

if  (!filtered_pids)

return false;

return  !trace_find_filtered_pid(filtered_pids,  task->pid);
}

```

结果被写入`ftrace_ignore_pid`字段，该字段本身是一个 percpu。每 CPU 变量是有多个副本的变量，系统的每个 CPU 有一个副本。内核代码可以轻松地访问当前正在执行的 cpu 的 percpu 实例。如果一个对象可以在逻辑上绑定到一个 cpu，那么将它定义为 percpu 变量将消除所有锁定需求，因为每个 CPU 都有自己的副本(这有许多其他用途，您可以[在这里](https://0xax.gitbooks.io/linux-insides/content/Concepts/linux-cpu-1.html)阅读它的内核实现)。这是一个缓存优化:不是每当任务遇到被跟踪的函数时就通过列表过滤 PID，而是在任务切换时检查一次 PID，稍后跟踪决策只是缓存读取这个单个布尔值。整洁，并且非常好的使用了 percpu！该结果将在下一次调用`ftrace_filter_pid_sched_switch_probe`时自动失效，它将为下一个任务写入一个新值。

我想我们知道的够多了。如果我们可以更新 percpu `ftrace_ignore_pid`，我们就可以控制是否为当前 cpu 启用跟踪。如果我们可以在想要开始跟踪时设置它，在想要停止跟踪时取消设置它，我们就可以随意使用它来限制过滤。

因此，我开始编写一个内核模块来在我的测试机上解决这个问题。很快，我回忆起我为 Linux 内核开发了一个 [MicroPython 端口，就是为了这种场合](https://github.com/micropython/micropython/pull/5482)！使用它，我们可以快速定义几个钩子来完成这项工作。

我们的目标:给定一个匹配前提条件的输入 TCP 包(假设目的端口是 9000)，我们希望得到它的 ftrace 调用图`tcp_v4_rcv`。

我们将从一个钩子开始，它将对数据包进行实际的过滤。必须在`ftrace-graph`之前调用，否则我们无法控制过滤！如果我用 ftrace 钩住`tcp_v4_rcv`本身，它会在 ftrace-graph 过滤决策之后运行，这对我们来说已经太晚了。我确信有一种方法可以绕过它，但是我没有检查——相反，我钩住了用于调用`tcp_v4_rcv`的`tcp_protocol->handler`指针。这样，我们肯定会在它之前被召唤。

此时，我们有了`sk_buff`,我们可以做出跟踪决定。如果我们希望跟踪，我们可以写入`tr->trace_buffer.data->ftrace_ignore_pid` …遗憾的是，它不在导出的头中。

我希望这与标准内核头文件完全兼容，所以访问未导出的结构不是个好主意。一个变通办法是用一个简单的处理程序来挂钩`trace_ignore_this_task`,该处理程序只为我们跟踪的任务返回一个。然后我们可以调用`ftrace_filter_pid_sched_switch_probe`,就像调度程序切换已经发生一样。它将更新当前任务的跟踪状态——因为我们强制`trace_ignore_this_task`返回 0，所以当前任务将被标记为跟踪。

趣闻:ftrace 不允许在 ftrace 自己的代码上放置挂钩(比如`trace_ignore_this_task`)。但是你可以放置`kprobe`钩子，有时会被 ftrace 支持，但是在这种情况下，它们不被支持是很有用的:)

使用这两个钩子，我可以基于输入`sk_buff`启用过滤。最后的片段可以从[这里](https://gist.github.com/Jongy/af9cbb734ed7da2d8887c3640f71d2cb)获得。

可以将其粘贴到 Python shell 中(在粘贴模式下)以启用挂钩。最后，为了开始追踪，我们将做以下事情:

```
# cd /sys/kernel/tracing

# echo 2 > set_ftrace_pid

# echo tcp_v4_rcv > set_graph_function

# echo function_graph > current_tracer

```

二是`kthreadd`的 PID 我们需要往`set_ftrace_pid`里写东西，所以`PID-based`过滤被使能。这个内核线程大部分时间处于休眠状态(它是新内核线程分叉的线程。因为它不经常被调度，所以它处理任何软件中断的机会很少。

就是这样！启用 ftrace 并发送待过滤的数据包后，我在跟踪缓冲区中正好收到一个跟踪！这花费了一些时间，但是这个跟踪确实有助于我理解相关的流程。

除了动态过滤的新功能之外，我们可以从这里得到的是:只要您确切地知道您在寻找什么，您就可以在 Linux 中实现它，即使代码中不支持它。所有需要做的就是在代码中挖掘一点，也许在这里或那里添加一个小补丁。

注意:这里提出的想法——以及内核 Python 本身——都是实验性的。不要在生产系统上尝试它们。它们是作为研究和调试工具提供的，仅供测试机器使用！

Linux 基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>