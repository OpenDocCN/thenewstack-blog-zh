# 集装箱营地:来自现场集装箱黑客会议的四个安全教训

> 原文：<https://thenewstack.io/four-security-lessons-live-container-hacking/>

在今年的伦敦集装箱营中，演示神是仁慈的。在舞台上做直播黑客战的时候，死机的几率极高。但是在 40 分钟的时间里，当[安德鲁·马丁](https://twitter.com/sublimino)玩着捕捉比特币并直接黑进[本·霍尔](https://twitter.com/ben_hall)的集装箱时，演示神照耀着他。

这一切都始于在线学习服务的创始人霍尔发出的号召:“安德鲁，你能提供我的系统的安全概况吗？如果你设法闯入，你可以获得一个比特币。”

遗憾的是，我们不能为你破解容器提供一枚比特币——在印刷时价值近 4000 美元——但我们可以向你展示霍尔故意犯下的非常常见的容器配置错误，以及马丁如何利用这些错误，他正在创办一家[安全工程公司](https://control-plane.io)，目前是英国内政部的 DevOps 主管。

在我们开始之前，有一件事要提一下，比特币被分成五份，以诱使马丁在短暂、毫无压力的舞台和现场体验中，在霍尔系统的不同部分找到它们。因此，有五种方法可以避免被黑客攻击。尽情享受吧！

## 黑客如何看待你的容器

谈到这次经历，霍尔解释说，“我真的不知道安迪会如何进攻，但我知道他会寻找什么和他的目标。”

Martin 告诉大家，他从查看 Linux 盒子开始，每个盒子可能在任何地方，并从那里尝试通过任何必要的手段来利用该系统。他可以尝试的三种主要方法是:

1.  枚举外部接口——在本例中为互联网——并通过远程代码执行(RCE)突破安全边界——应用程序运行代码并做一些它不应该做的事情。
2.  确定在该服务器上运行我们的代码的特权——如果是受限的，则交换给特权用户。
3.  在容器的情况下，爆发。

“系统应该给攻击者提供尽可能少的信息，”马丁说，但情况并非总是如此。这是他正在寻找的玉米粒…

### 容器黑客#1:特权容器就是不包含

马丁开始利用一个名为 [SambaCry](https://securelist.com/sambacry-is-coming/78674/) 的漏洞，这个漏洞是黑客组织影子经纪人从美国国家安全局渗透出来的。第一个漏洞类似于发生在 [WannaCry](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack) 攻击中的漏洞，该攻击导致 NHS(英国国家医疗服务)和电信巨头 Telefonica。他运行的不是同样的代码，而是类似的协议攻击。

“表面上，我们让它在 Linux 容器中运行，这样 Linux 机器就可以与 Windows 机器对话。因为这很容易受到攻击，我能够探查桑巴的股票，”马丁说。

他扫描 Samba 共享，找到一个，运行 RCE 漏洞，然后进入容器。

“我仍然必须找到一种方法成为根用户，因为这是谁拥有比特币钱包的文件系统权限，”他说。

马丁从使用[一个包含](https://github.com/jessfraz/amicontained)容器的自省工具开始。

“你可以在任何机器上运行它，看看你有多安全，”霍尔解释说，称之为“一个非常好的快速胜利，真的很方便安迪看到他有多少访问权限。”

原来是特权容器。**–privileged**标志赋予容器所有的能力，它也解除了[设备组控制器](https://www.kernel.org/doc/Documentation/cgroup-v1/devices.txt)施加的所有限制。本质上，容器可以做主机可以做的大多数事情。

[根据 StackOverflow](https://stackoverflow.com/questions/36425230/privileged-containers-and-capabilities) ，“这个标志的存在是为了允许特殊的用例，比如在 Docker 中运行 Docker”，但这不是这里的用例。

Martin 通过 amiccontained 发现“这是一个特权容器，运行这个工具可以显示所有的内核功能，然后建议检查/dev 中有哪些设备可用。”

从这里，他发现了一个非常重要的内核 **cap_sys_admin** 调用“这是一个几乎可以做任何事情的全权委托，”马丁说。

霍尔说:“强调这一点真的很重要，当人们不能让东西在集装箱内工作时，他们就只是坚持集装箱上的特权并离开它。”

这是开发人员经常犯的错误，他们通过让容器具有特权来降低安全性，因为这是让容器像你希望的那样运行的最快方法。这是早期的旧容器所做的事情，但是你永远不会想要运行特权容器，尤其是在一个公开于互联网的服务上。

“最好的特权模式是证明事物工作的概念，但它是如此危险，而且有如此多的警告，”霍尔警告说。

“我认为最好的情况是证明在一个容器内可以做一些事情，因为你可以单独禁用所有的安全措施。其实最好是把所有权限都放下，然后把你想要的东西还回去。”

在 Martin 访问它的时候，容器已经用**–privilege**标志启动，这意味着大量的安全性被禁用，大多数名称空间被共享。

应用**–无新权限**，确保用户不能在容器内获得新权限，避免**–权限**。

### 容器黑客#2:不要把应用程序放在你的容器周围

接下来，Martin 尝试将主机的文件系统装入容器。

“秘密存在于容器之外，所以因为我们在容器中，所以我们想把它提供给宿主。为了做到这一点，我们可以挂载一个分区，但标准的 Linux 安全模型仍然适用于容器——只有当我是容器内的 root 用户时，我才能这样做，但我是“无名之辈”，这意味着 Martin 无法挂载。

此时，作为黑客的 Martin 必须成为容器中的 root 用户，以便在容器中挂载主机文件系统。

他解释说，“在这次攻击中，我们并没有试图逃离容器，而是试图将主机上的信息拉入容器中进行读取或编辑，基本上可以获得完全的访问权限。”

在正常的无容器情况下，通过成为根用户，他可以获取包括密码在内的客户数据并访问服务器。

“在这一点上，我们正在寻找一种方法来成为特权容器内的 root 用户，然后我们在主机上拥有等同的 root 权限。

最重要的是，一旦您有权访问文件系统，您就可以向任何用户添加凭据并直接访问主机马丁说，“然后游戏就结束了。”

因此，Martin 使用了一个特权检查脚本来检查整个系统的配置是否正确，以及正确的文件权限是否到位。

“因为一台计算机上有多个管理员，如果一个人进去修复某个东西，然后另一个人做其他事情，就没有连贯的状态，除非他们交流每一次击键。这意味着错误配置变得更有可能，并且是部署不可变基础设施的好理由，”Martin 说。

他发现 Hall 有一个调试应用程序仍在容器中运行，该程序已经成熟，可以利用了。

霍尔解释了他故意犯的错误:“人们总是把东西放在容器里，因为这让生活更容易。在这个例子中，我在容器中有额外的工具，它不是为应用程序准备的，而是为我准备的，所以它可以被重新利用。如果你以容器安全的方式思考，你会移除任何多余的东西。”

然后使用调试应用程序获得容器内部的 root 访问权限。

“一旦我们在容器中获得了 root 权限，就可以在其中安装主机文件系统，并读取包含比特币的文件内容。”

又获得了一块比特币。

接下来，马丁进行了一次更简单的利用，他使用 [nmap](https://nmap.org/nsedoc/scripts/http-shellshock.html) 扫描是否存在[shell shock](https://en.wikipedia.org/wiki/Shellshock_(software_bug))——有时也被称为 bash door——漏洞，这是一个几年前开始流行的安全漏洞家族。Nmap 通过执行打印随机字符串的命令来检测此漏洞，然后尝试在响应正文中找到它。

Martin 能够远程利用此漏洞在容器中运行代码。

他说，“用容器来防御网络或协议攻击是不可能的，因为漏洞是在应用程序级别上——这就像把你的头伸出护栏，人们仍然可以攻击他们看到的东西，并越过容器/城堡的墙壁进入。集装箱防御是为了阻止他们进一步进入城堡。Shellshock 是一种远程代码执行——我们用它来进入容器并开始运行命令。”

Hall 补充道，“基本上，当我们向服务器发送请求时，你可以在 HTTP 头中发送额外的数据——比如你正在运行的浏览器。对于 Shellshock，这允许任何命令在系统上运行。Andy 用它来查找属于 Docker 的特定套接字文件，并访问 Docker 引擎守护进程。一旦你可以访问 Docker 守护进程，你就可以访问所有的系统。”

然后，一旦攻击者可以编写自己的命令，他就可以运行自己的容器，从主机装载卷并访问任何内容。

获得了第二枚比特币。

### 容器黑客#3:在你的应用中构建层来建立你的防御

毫无疑问，PHP 是最流行的编程语言之一。部分原因是它是一种更简单的语言，学习起来会有更多的人知道，这意味着用 PHP 构建任何东西通常会减少你的人员成本。但它也更容易受到攻击。

举一个常见的例子，Hall 托管了一个运行带有特定漏洞的表单的示例应用程序，该应用程序可以在后台执行任意代码。

他解释说“在高层次上，它使用了一个已知问题的 **PHPMailer** 功能，你可以向它发送一个允许你访问系统的特定请求。”

所以马丁可以利用这一点“通过漏洞创建一个后门”。我们从前门开始 web 应用程序——一些东西通过易受攻击的 **PHPMailer** 在服务器上运行，并在磁盘上放置另一个文件。通过对新文件发出 HTTP 请求，我们可以运行代码。”

霍尔说，反击固有安全问题的最好方法是在你的容器周围建立更复杂的安全层。

“对于防守来说，一切都是为了增加层数，而从进攻的角度来说，一切都是为了减少层数，”霍尔说。

在一次类似的攻击中，他说“黑客发现了 **PHPMailer** 的样子，这给了他们访问系统一部分的权限，这给了他们访问 rest 的起点。就在那时:游戏结束了。所有这些奇怪的字符串让你接触到重要的部分。”

马丁急切地补充道:“黑客最有趣的部分是运行一个看起来绝对荒谬的命令，事实上，这是一个神奇的咒语，可以打开目标系统的秘密之门。”

在这个实时黑客案例中，PHP bug 运行在一个迁移的 [Kubernetes](/category/kubernetes/) 上，默认的 RBAC 之前的安全设置，“没有关闭任何东西，没有真正锁定任何东西。”

Hall 解释说，“正因为如此，在 Kubernetes 1.5 中，您获得了一个特殊的令牌，允许您访问 Kubernetes 集群，这又让您可以访问任何内容。”

这显然是 Kubernetes 做的事情，看起来和感觉上更像是谷歌的祖父辈。

正如 Martin 所说，“不同之处在于，在谷歌内部，这些服务账户是被锁定的，但 Kubernetes 是一个开源项目，安全性往往被置于功能之后。对于产品开发和用户获取来说，这是正确的做法，每个人都这样做，但实际上，这使安全性变得更加困难。”

“每个项目都有把安全放在第二位危险，”霍尔附和道。

虽然特性交付的速度通常比安全性更重要，但是您通常可以用付费服务来补充您的开源工作。霍尔提供 Aqua 作为安全工具，仅仅因为每天都有容器被黑客攻击，就筹集了数百万美元。

“如果你不能依靠开源项目，你必须依靠供应商来添加额外的模型，”霍尔说。

然而，在这种情况下没有使用 Aqua， **PHPMailer** 被渗透，并且找到了第三块比特币。

### 容器黑客#4:保持更新并使用入侵检测系统

接下来，马丁使用 Kubernetes 容器编排引擎运行另一个攻击: [Dirty COW](https://dirtycow.ninja/) ，Linux 内核中的一个权限提升漏洞。

Hall 称之为“一个特殊的问题，因为它攻击了 Linux 内核中的一个底层部分，而大多数黑客进出容器，这一个则深入内核，允许它执行任意代码。你可以做所有正确的设置，优化一切，但是如果你运行的是这个版本的内核，你仍然暴露在外，突出了不打补丁的危险。

“即使你认为你处于高度安全的配置中，如果你不给主机打补丁，你仍然容易受到攻击，”他说。

你必须时刻记住更新所用系统的安全强度。

但是在这种情况下——为了节省时间，也为了不损失很多钱——Hall 通过更新他的内核安全设置阻止了 Martin。当然，他知道自己被袭击了，就在那时。

有入侵检测系统或 IDS 可以帮助检测这些安全漏洞并向您发出警报，这是两位专家推荐的。对于容器，您需要一个容器原生 id，比如:

*   Aqua 和 [Twistlock](https://www.twistlock.com/) 是专有的闭源软件，可以检测和关闭正在进行的攻击
*   Sysdig 更具可观察性和监控性，是一款开源入侵检测工具——激光精确定位每个违规的容器

“你可以让它们变得更加敏感，这样你就可以非常迅速地发现各种异常行为。Martin 解释说:“通常，IDS 依赖于蜜罐和强力登录检测，而使用容器和名称空间，您可以看到是否有人试图在容器内运行外壳或正在运行未列入白名单的程序。

## 如果你是好人，为什么还要做黑客呢？

霍尔和马丁都是热情的集装箱用户和集装箱安全爱好者。正如马丁总结的那样:“防守比进攻困难得多，因为这是一个不对称的战场，你必须有一个无懈可击的防守。我们演示的东西通常是 Linux 配置的问题。”

集装箱带来了它们自己的一系列问题。

“在使用容器之前，您必须为运行在主机上的任何东西配置整个主机。现在，您可以使用不同的安全配置自定义每个容器的周界。”Martin 补充说“Kubernetes 的安全性随着每个版本的发布都在提高，但是它仍然是一个移动的目标。”

“这是 Katacoda 的动机之一，”Hall 说，指的是他的在线学习服务，其中有专门针对码头工人和集装箱安全的内容。“一切都在以如此快的速度发展，开发人员有一个地方可以学习和试验这些新技术，尤其是在安全环境中的安全功能，这一点至关重要。如果一切都出错了，他们可以点击“刷新”,获得一个全新的环境。”

照片:*T3【保罗布沃 *

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>