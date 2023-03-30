# Docker 呼吁红帽对最近的 RunC 漏洞进行雄心勃勃的营销

> 原文：<https://thenewstack.io/docker-calls-out-red-hat/>

Red Hat 和 Docker 再次竞争[友敌](http://www.urbandictionary.com/define.php?term=frenemy)在一次分歧后，Docker 的首席技术官批评 Red Hat 在其营销材料上有点过于激进。

争议集中在开源 [runC](https://runc.io/) 容器运行时引擎中最近发现(并迅速纠正)的一个错误的影响上。如果没有别的，这场争端说明了开源生态系统中竞争营销的边界(以及 Docker 联合创始人所罗门·海克斯(Solomon Hykes)坚定不移地拒绝呆在公司公关防火墙后面，这对美国科技记者来说是令人耳目一新的)。

1 月 2 日，SUSE 的 [Aleksa Sarai](https://github.com/cyphar) 和 Docker 的[tnis ti igi](https://github.com/tonistiigi)发现了这个权限提升漏洞。[引用 CVE 的话](https://bugzilla.redhat.com/show_bug.cgi?id=1409531):

*RunC 允许额外的容器进程通过`runc exec`被容器的 pid 1 处理。这允许容器的主进程(如果以 root 用户身份运行)在初始化期间获得对这些新进程的文件描述符的访问，并可能导致容器溢出或在进程完全放入容器之前修改 runC 状态。*

换句话说，恶意的黑客可以利用这个漏洞从容器内部影响主机的操作。

RunC 是 Docker 容器软件的基本核心容器运行时引擎。Docker Inc .开源了 runC，并将其遗赠给了开放容器倡议组织。对于这个 bug，runC 的维护者很快发布了一个补丁，1 月 10 日，Docker 更新了自己的软件，发布了 [Docker 1.12.6](http://seclists.org/oss-sec/2017/q1/54) ，鼓励所有用户更新他们的副本(尽管其他非 Docker、[实现](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/)可能仍然需要打补丁)。

故事结束了？没那么快。几天后，红帽咨询工程师[丹·沃什](https://twitter.com/rhatdan)发表了一篇题为“[Docker 0-Day Stopped Cold by SELinux](http://rhelblog.redhat.com/2017/01/13/docker-0-day-stopped-cold-by-selinux/)”的博客文章，声称那些部署了 [SELinux](https://selinuxproject.org/page/Main_Page) (红帽企业版 Linux 中包含的一个 Linux 细粒度访问控制框架)的用户将受到保护，不会受到源于该漏洞的任何攻击。

“SELinux 是唯一能够保护主机文件系统免受来自容器内部的攻击的东西。他写道:“如果容器内部的进程能够访问一个主机文件，并试图读写其中的内容，SELinux 会检查这种访问。

在一个关于 Red Hat 帖子的黑客新闻论坛[中，有人，大概是 Docker 的人，指责 Walsh 推断用户不需要升级到 Docker 1.12.6，仅仅是因为 SELinux 可能会覆盖漏洞。](https://news.ycombinator.com/item?id=13398249)

Hykes 也加入了进来，批评红帽邮报围绕漏洞进行机会主义营销。

“一些供应商(不仅仅是红帽)错误地向他们的用户宣布，他们不需要升级到 Docker 的最新版本，因为他们的企业级商业平台将“阻止漏洞感冒”，他写道。

Hykes 还围绕博客文章的措辞提出了许多其他问题，指出 runC 不是 Docker 产品，而是 OCI 开源社区的一个产品，该漏洞不是零日漏洞。零日意味着漏洞不为供应商所知，尽管在这种情况下，维护者和 Docker 在 Walsh 的帖子发布时已经发布了补丁。Hykes 认为，所有这些细节加在一起，使得“漏洞更加可怕。”

据两家公司的发言人说，在幕后，Docker 已经联系了 Red Hat 来解决这些问题。Red Hat 将文章的标题改为更保守的“SELinux 减轻容器漏洞”

在一封关于新堆栈的电子邮件中，Red Hat 布道者 [Joe Brockmeier](https://twitter.com/jzb?) 承认使用“零日”来描述这个漏洞是不恰当的。在对 SELinux 的热情中，Walsh 的描述有点太戏剧化了(不足为奇:Walsh 是 SELinux 应该作为生产级容器安全的基本构建模块的狂热信徒)。

Brockmeier 还指出，事实上，Red Hat 正在鼓励其用户安装该补丁:“用户绝对应该更新他们的系统。SELinux 只是更全面的深度防御战略中的一个工具，应该继续下去。”

当然，激进的竞争营销在 IT 领域并不新鲜——红帽的竞争对手甲骨文和 T2 和微软在十年或二十年前就是恐惧、不确定和怀疑的大师。但是在开源社区中，竞争对手也是合作者，所以竞争的界限不是那么明显，激进的营销可能会回来困扰它的创始人。

事实上，截至去年年底，19 名 runC 贡献者自称为 Red Hat 工作，而目前只有 16 人自称为 Docker 工作。

*TNS 技术编辑 Benjamin Ball 和 TNS 研究分析师 Lawrence Hecht 对本文有贡献。*

Docker 和 Red Hat 是新堆栈的赞助商。

特征图片:Docker 的 runC 图标。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>