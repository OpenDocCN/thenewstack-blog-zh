# StackStorm 1.0 是一个在 Cassandra 集群上工作的自动化库

> 原文：<https://thenewstack.io/stackstorm-1-0-is-an-automation-library-that-works-on-cassandra-clusters/>

互联网规模的数据中心改变了“容错”的含义和重要性。几年前，这个短语实际上被用作“不容忍”的同义词，好像完美执行的几率不会随着数据中心的扩大而下降。

周三，在圣塔克拉拉举行的[卡桑德拉峰会期间，一家名为](http://cassandrasummit-datastax.com/) [StackStorm](https://stackstorm.com/) 的公司揭开了其工作流程自动化系统 1.0 版本的面纱。但是受到脸书的启发——[在 2011 年](https://www.facebook.com/notes/facebook-engineering/making-facebook-self-healing/10150275248698920)披露其 FBAR 系统负责将一个部门的管理员人数从 200 人减少到两人——stack storm 已经将其关键产品重新定位为比工作流图表更新颖、当然也更有必要的东西:自动补救。

## “做傻事”

StackStorm 首席执行官 Evan Powell 在接受 New Stack 采访时说:“FBAR 向人们展示了自动补救不仅仅是减少你在凌晨 2 点被愚蠢的事情吵醒的可能性。”“自动补救的第一项工作是，把愚蠢的事情做完，这样你就不必为此烦恼了。

“但更重要的是，随着时间的推移，”鲍威尔继续说道，“你会拥有像脸书那样的系统，而这些系统是不存在的。如果 FBAR 倒下了，脸书也会倒下。控制平面最终成为一个完整的组件。”

这一评论透露了鲍威尔对 StackStorm 1.0 在企业数据中心中的作用的一些设想。正如他所描述的那样，它的目的是使管理员能够非常快速地对数据中心为响应日常事件(尤其是服务降级)而通常采取的平凡但补救性的任务进行建模。他的目标是让管理员在半小时内将数据中心从零恢复到基本的自动修复，最好是一个小时以内。

从那里，StackStorm 1.0 监听指示潜在问题的指示性事件，并作为响应，将工作流作为脚本运行。这些工作流可能包括为上一代所谓的 runbook 自动化工具开发的脚本。

“我们在这里看到的采用模式是，第一步，第一天，实际上是第一个小时——我们试图让它成为第一个半小时——你采用 StackStorm，你吸收你已经拥有的自动化，你已经拥有的任何脚本，你在 Chef 或 Puppet 中拥有的任何东西。StackStorm 是你的自动化库。但是，这些是乐高积木，你开始把它们拼在一起，变成更有趣的自动装置。”

## 补救卡桑德拉

周三发布的 StackStorm 博客文章提供了一个涉及 Cassandra 集群的自动修复用例。对于典型的 Cassandra 监控系统，当集群中的一个节点死亡时，一个警报系统通常会自动“唤醒”(因为，毕竟，这可能随时发生)DevOps 工程师之一。那个人可能负责承担[一个六步的过程来旋转一个新节点](http://docs.datastax.com/en/cassandra/2.0/cassandra/operations/ops_replace_node_t.html)并将其添加到集群中——这个过程可能比听起来更复杂，但可能不值得失去睡眠。

StackStorm 展示了这六个步骤如何转化为一卡车的 YAML 代码。对于一个人来说，阅读和破译这些信息是很容易的，但是这些信息太多了，而且并不那么直观。

然而，当表示为简单的流程图时，绿色的流向箭头表示`on_success`，红色的表示`on_error`，工作流程更有意义。人们如何将一个事件拖放到工作流中并绘制与之相关的条件，而无需先查阅字典，这一点变得更加明显。

可以通过赋予流必须实时满足的条件，将流提升为规则。

使用上一代工作流自动化工具，许多企业将其工作流视为重要的知识产权，并且只在需要知道的基础上与受信任的个人共享。它们代表了他们的业务工作方式，被认为是业务流程而不是基础设施问题。

然而，鲍威尔告诉我们，随着工作流进入基础设施的更深层次，它变得与企业的竞争优势和专有流程无关，而与保持数据中心的活力有关。无论如何，这个过程的大部分现在都是开源的。也就是说，StackStorm 确实包括基于角色的访问控制(RBAC ),以确保共享这些进程的人至少得到了管理层的授权。

“在一些 Cassandra 补救案例中，许多案例来自 Datastax 和社区编写的传统意义上的操作手册。他们说，‘当你看到这些东西的时候，去尝试那些东西来得到这些结果。’我的观点是，有很多(像这样的)免费分享。您希望人们知道如何运行它，而不是每次出现潜在的物理或虚拟故障时都找您。"

他承认，对于一家大型金融机构来说，情况可能并非如此——例如，对于一个详述银行数据中心如何应对网络钓鱼攻击的工作流来说。“有一些类型的补救措施，你想保持完全锁定，”鲍威尔说。

## 为什么分析？

这位首席执行官指出了其他主要服务提供商的例子，如思科 Spark(一个通信平台，不要与 Apache Spark 混淆)为自动修复设定了新的标准和理想，StackStorm 希望为所有人效仿。这是否意味着 StackStorm 可能会步阿尔卡特朗讯(Alcatel-Lucent)等通信提供商的后尘，后者收购了一款消费者分析工具，[将其用于服务补救](http://www.fierceenterprisecommunications.com/story/alcatel-lucent-leverages-customer-analytics-engine-operational-support-syst/2014-06-09)？

“我们喜欢被告知去做正确的事情，”StackStorm 的鲍威尔回应道。“但我们是可扩展的、易于使用的、基础设施即代码的系统，可以去做那些事情。”

这听起来像是否定的，至少现在是这样。

“我们的愿景是，随着时间的推移，你将拥有越来越多真正的自动驾驶数据中心，”他继续说道。“其中一部分是监控方面的分析。但我们也确实认为，有一个真正的机会，可以通过分析来决定您应该采取哪种补救措施。但是那只鞋没有和我们一起掉下来。”

思科是新堆栈的赞助商。

专题图片: [jwtlr freilburg](https://www.flickr.com/photos/jwltr/) 的[库](https://www.flickr.com/photos/jwltr/11050441386/in/photolist-hQupeu-2XUSwK-7JYMRm-i6Xpna-pQZGu6-qm8c8o-81t2H-82iqbY-4d3PzE-82ipB5-rq8uC9-aGsNy4-byxdLg-ci8s7s-fBiUg9-8KrU1R-itbSu3-eCJ2iZ-dDia3S-6f1zQS-7aqDQk-bwWvj2-ghnoDc-bk94WJ-rV93Kr-aUqNfk-dnwzKB-wuRhN8-sDBSH-dpMa6R-hooBf-p7XXBw-bDEK2r-968euk-5bRGno-kvTi2S-o2ucSc-k7ZENx-ruAw2-p1zb6e-nqndNS-zTFfX-mC5wvE-7Pesb4-sdDP65-KXbeu-dA9V-8tQbyw-tzQYKL-aMPX7i)在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>