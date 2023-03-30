# SREs 如何避免配置漂移

> 原文：<https://thenewstack.io/how-enforced-configuration-and-ad-hoc-task-automation-boost-agility/>

[傀儡](https://puppet.com/)赞助本帖。

 [米克·希门尼斯-彼得森

Mikker 是 Puppet 的首席现场可靠性工程师，自 2000 年以来一直在运营领域工作，2005 年花了几年时间学习咨询。在从传统运营到开发/运营以及后来的 SRE 的演变过程中，他对自动化的关注不断增加，并与软件开发组织密切合作，这使得他对该领域的兴趣一直保持着。](https://www.linkedin.com/in/mikker-gimenez-peterson-1851441/) 

基础设施自动化可以帮助工程师将机械任务转化为可重复、一致且协调的行动，从而节省大量时间。通常，工程师关注他们已知基础架构中的内容，使用自动化来大规模实施他们的基础架构配置。

强制状态模型为您的基础架构管理带来了一致性和安全性。在专门运行强制状态模型的情况下，对未管理系统的任何更改都需要一种特别的方法(一次性任务等)。)对于简单的不经常发生的变化，这可能是没问题的。但是，在大规模自动化配置管理之外进行临时更改和运行手动任务所需的时间会迅速增加。

另一方面，如果您只运行临时更改，那么您会因为缺乏强制状态的方法而浪费时间，从而降低开销。

可持续的、敏捷的答案是:融合两个世界的精华:通过采用强制状态方法和采用简单的方法来“在堆栈之外”自动化特定的事情，sre 可以在我们的日子里获得更多的时间来处理其他事情。

换句话说:让我们结合两种普遍接受的方法来自动化配置管理，以使我们的团队更加高效。

### 在我们深入讨论基础架构管理之前，请说…

在我们深入研究之前，让我们先排除一些我将在本文中用到的术语。

典型的代理-服务器配置管理侧重于已知的基础设施，无论是本地、混合云、原生云等..此堆栈之外的东西可能是远程主机、网络设备及其各自的节点和端点、短暂的云资源、开发环境和其他被视为“您的基础架构”之外的资产

### **加强基础设施的状态**

基础设施管理工具，如 Puppet check 在您的各种节点(服务器、设备等)上。)并确保它们符合软件定义的配置。如果某个节点上存在任何与配置不相符的偏差(变化)，您的基础设施管理工具将会纠正这种情况。此外，将自动配置连接到服务器的任何新主机。它一次又一次地强制实施由您的 DevOps 团队定义的基础架构状态，因此您不必这样做。

### **临时任务**

基础架构之外的资源，如远程设备，需要通过手动的一次性任务进行控制。有时您可能需要重置一台服务器，并且只重置该服务器。发送一个远程命令来重启它要容易得多。您也可以将多个临时任务编排成更大的计划。

### 如果我们不使用混合方法自动化基础架构管理，会有什么风险？

对于只运行强制状态方法的人来说，远程节点上的任何补救都需要手动操作。当您是一个大规模处理数千个节点的团队或组织时，这种手动工作会严重增加。

团队可以通过一系列特别的任务来管理基础设施。然而，当试图用大量的手动任务来模拟强制状态配置管理的好处时，这种方法也是一种浪费。

当我们自动执行状态和编排特定任务时，我们释放了最大的灵活性。强制状态模式不符合您的日常业务现实，需要修补系统、收集报告或运行维护任务。

相反，仅依靠临时方法可能会导致手动、重复的更改，以模拟通常在整个基础架构中强制执行的配置。你不是自动化以减少工作吗？

### 工作中的解决方案:SRE 木偶的日常生活

让我们用一个真实的工作例子——作为一名主要的站点可靠性工程师，我在 Puppet 的一天。通过混合 Puppet Enterprise 指导的强制配置代理服务器方法和 Bolt 等特别方法，我们节省了大量时间并减少了需要运行的手动任务数量。这种组合为 SREs 提供了更大的灵活性来应对配置漂移，并减少与远程主机争论的工作量。

我在木偶公司经营木偶企业(PE)的团队工作。PE 执行我们基础设施的配置，并维护我们作为一个团队决定的标准。然而，配置不存在于我们的生产持续集成(CI)基础架构范围内的服务器需要临时操作。这就是我们转向开源解决方案 Bolt 的时候，以确保这些服务器以可重复的方式配置。

让我们仔细看看这个使用 Bolt、Apply 和 Plans 来补充我们现有配置管理的可扩展工作流。

### 我们如何将临时任务和计划结合到基础架构管理中

PE 管理运行 OpenStack 的物理服务器，但是虚拟机(VM)本身不是集中管理的，因为这是一个沙盒环境。我想解决该环境中的一个用户问题:我们的用户会报告他们在 OpenStack 环境中的虚拟机出现的问题，但我无法通过 ssh(一种通过互联网和设备网络访问远程设备的方法)访问我的内部客户正在设置的虚拟机。即使可以通过 ssh 访问用户的虚拟机，我也没有关于在环境中的虚拟机上的体验的历史数据。

解决方案:我在环境中构建了两台服务器，它们相互通信，使用 telegraf 将性能数据发送到 InfluxDB 来获取这些指标。这两台服务器之间有共享代码，我不想手动配置它们，尤其是在没有生产 SLA 的环境中。

为了进一步发展这个解决方案，我使用 Bolt，一个无代理的开源任务运行器，来创建计划(Bolt 中的编排任务)来帮助我快速管理这些服务器。

### 如何使用螺栓应用

为了涵盖本例中的临时任务和计划编排，我们将重点关注 Bolt，它使用与 PE 管理基础架构相同的代码和模块来管理无代理基础架构。值得注意的一点是，Bolt 对如何设置环境有自己的看法。这意味着您可以利用自己编写的代码，以及 [Puppet Forge](https://forge.puppet.com/) 上的模块来最大限度地利用您的临时任务编排。

下面是一些代码示例，为这种方法提供了更多的上下文。这些示例基于使用基于 unix 的系统的用户。【安装螺栓】后，换成你的 **~/。puppetlabs/bolt** 目录，并创建一个 Puppetfile。

```
forge  "http://forge.puppetlabs.com"

mod  'profiles',  local:  true
mod  'puppetlabs-concat',  '5.2.0'
mod  'puppetlabs-stdlib',  '5.1.0'
mod  'puppet-telegraf',  '2.1.0'

```

需要注意的几件事:

*   **添加您将使用的任何模块，**在这种情况下，我知道我想要使用 telegraf 模块，并且 telegraf 模块依赖于 *concat* 和 *stdlib* 模块；
*   **确保您在这里添加了将要创建的模块，并且标记为 local: true。从现在开始，bolt 将管理你的模块，如果你不把它列为 local_true，Bolt 将删除你写的代码，试图用 forge 的模块覆盖它。**

使用命令 **bolt puppetfile install** 安装您在 puppetfile 中列出的所有模块，然后创建一个模块目录(如果不存在)，并在该目录中为您的模块创建目录。Bolt 支持更简单的任务，它可以运行在您想要的任何语言中，以及更具可扩展性的计划，并使用 puppet 语言，在这种情况下，我想使用需要 Puppet 计划的 bolt apply 特性。我在目录 **~/中创建了木偶计划 telegraf.pp。puppet labs/bolt/modules/profiles/plans/tele graf . PP**。

```
plan profiles::telegraf(
  TargetSpec  $nodes,
  String[1]  $influxdb_hostname,
  String[1]  $influxdb_password,
)  {

  # Install the puppet-agent package if Puppet is not detected.
  # Copy over custom facts from the Bolt modulepath.
  # Run the `facter` command line tool to gather node information.
  $nodes.apply_prep

  # Compile the manifest block into a catalog
  apply($nodes)  {

    class  {  'telegraf':
      hostname  =&gt;  $facts['networking']['fqdn'],
      logfile  =&gt;  '/var/log/telegraf/telegraf.log',
      outputs  =&gt;  {
          'influxdb'  =&gt;  {
              'urls' =&gt;  [  "http://${influxdb_hostname}:8086"  ],
              'database'  =&gt;  'telegraf',
              'username'  =&gt;  'telegraf',
              'password'  =&gt;  $influxdb_password,
              },
          },
      inputs =&gt;  {
        'cpu' =&gt;  {
          'percpu' =&gt;  true,
          'totalcpu'  =&gt;  true,
        },
        'disk'      =&gt;  {},
        'diskio'    =&gt;  {},
        'mem' =&gt;  {},
        'net' =&gt;  {},
        'processes'  =&gt;  {},
        'syslog'    =&gt;  {
          'server'  =&gt;  'tcp://:6514',
        },
        'system'    =&gt;  {},
      },
    }
  }
}

```

这是用于在节点上安装 telegraf 的计划。在这个计划中，我传入了三个变量:

```
$nodes
$influxdb_hostname,
$influxdb_password,

```

节点变量使用螺栓标志-节点填充。下面是一个如何应用这个 bolt 计划的例子:

```
bolt plan run profiles::telegraf  --nodes centos@10.234.0.115  --run-as root  --tty  influxdb_hostname=hostname.puppet.com influxdb_password=ReallySecureP@ssword

```

*$nodes.apply_prep* 让节点准备好在其上运行 puppet，尽管这是一种无代理的体验，但我们需要将运行 puppet apply 的代码复制到运行该代码的主机上。

*apply($nodes) {* 这一行告诉 bolt 您将向 bolt 传递 Puppet 语言代码，以应用到服务器上。您正在传递给$nodes 的节点上运行它。这意味着，如果您希望以编程方式开发节点列表，可以用其他方式生成该变量。

### 大局

Bolt 是一个很好的例子，说明了如何在您的组织中自动化脱离主环境的基础架构。这为运营工程师和 sre 提供了在管理基础设施的团队之间重用代码的好处，同时也使我们的代码库更小，更有针对性。这种特别的能力允许团队即时响应基础设施的变化。

强制配置管理为您当前的堆栈提供了许多效率。但是，随着您的业务需求发生变化，需要更多的远程主机，SREs 需要一种专门的方法来自动化这些任务。将强制的和临时的自动化方法结合起来，可以释放一些真正的灵活性，让您有时间专注于其他优先事项。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>