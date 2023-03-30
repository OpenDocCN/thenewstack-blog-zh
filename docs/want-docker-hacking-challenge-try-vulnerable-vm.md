# 想要 Docker 黑客挑战吗？试试这个易受攻击的虚拟机

> 原文：<https://thenewstack.io/want-docker-hacking-challenge-try-vulnerable-vm/>

如果您与 Docker 合作，并想看看您是否有足够的技能来发现错误配置和不安全的部署，渗透测试公司为您带来了一个挑战:[一个易受攻击的 Docker 虚拟机](https://www.notsosecure.com/vulnerable-docker-vm/)。

虚拟机是作为一个捕捉旗帜的游戏而构建的，玩家需要更深入地访问系统并收集“旗帜”这些可以是作为检查点的文件或内容片段，确认玩家是否在正确的轨道上。

该游戏有两个难度级别—简单和困难—但最终目标是相同的:突破 Docker 容器并获得主机系统的 root 权限。

解决这个简单的挑战只需要知道 Docker 是如何工作的， [Anant Shrivastava](https://www.linkedin.com/in/anantshri?ppe=1) 说，他是 [NotSoSecure 全球服务](https://www.notsosecure.com)的 APAC 地区总监，也是 VM 的作者之一。

然而，硬难度级别需要 Docker 和渗透测试(pentesting)的知识。玩家必须通过易受攻击的 web 应用程序访问 Docker 容器，然后逃入主机系统。

需要发现和利用的安全问题包括错误配置和传统漏洞。一路上有三面“旗帜”需要收集。一些缺陷与 Docker 有关，而另一些则与容器内部运行的 Web 应用程序有关。

NotSoSecure 为安全专业人员提供测试服务和培训，Shrivastava 是该公司高级基础设施黑客课程的首席培训师之一。

Shrivastava 说，Docker VM 中包含的安全问题实际上是在渗透测试活动的真实部署中发现的。他说，公开发布虚拟机的想法是在今年早些时候该公司在黑帽美国安全会议上举办的培训课程中受到好评后产生的。

解决游戏没有奖励，所以玩家不必向公司汇报解决方案。然而，Reddit 上有一个帖子，作者在那里回答问题，VM 内部提供了一个电子邮件地址，可以用来联系团队。

该公司发布了一个免费的网络研讨会，涵盖了 Docker 安全评估期间使用的一些技术，虽然该演示不会提供虚拟机挑战的确切解决方案，但它可以给玩家一些他们可以尝试的想法。

该公司计划在两周内发布一份详细的书面报告，介绍 Docker VM 中包含的安全问题，以及这些问题如何被利用来达到危害主机的最终目标。回到这里，我们将详细讨论结果。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>