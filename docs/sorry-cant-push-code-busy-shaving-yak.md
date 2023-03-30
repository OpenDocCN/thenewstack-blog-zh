# 牦牛不再剃毛，或者容器如何简化应用程序部署

> 原文：<https://thenewstack.io/sorry-cant-push-code-busy-shaving-yak/>

毫无疑问，容器可以让开发人员的工作变得更容易。让跨平台的机器能够运行相同的代码并得到相同的结果，这在几乎任何环境中都是一件好事。然而，当玫瑰色眼镜开始褪色时，开发团队通常会考虑如何编排他们的容器并可靠地伸缩它们。像 [Docker Swarm](https://www.mirantis.com/software/docker/kubernetes/) 和 [Red Hat OpenShift](https://www.openshift.com/) 这样的平台只是开发者可以选择的几个选项，他们希望超越在他们的堆栈中运行几个容器。

在这一集的[The New Stack Makers](https://thenewstack.io/podcasts/)embedded below 中，New Stack 创始人 Alex Williams 在 [Red Hat](https://www.openshift.com/) 与开发者倡导者 [Steven Pousty](https://twitter.com/thesteve0) (自称为“PaaS 灰尘散布者”)进行了交谈，以了解更多关于在生产中使用容器的信息，为什么开发者应该放弃过时的“宠物与牛”的类比，以及容器如何从整体上改变了应用程序开发。

[应用开发和容器:史蒂夫·普斯蒂带着红帽在奥斯丁的 OSCON](https://thenewstack.simplecast.com/episodes/app-development-and-containers-steve-pousty-with-red-hat-at-oscon-in-austin)

对话[也可以在 YouTube 上听到](https://youtu.be/NRdZc-cbtEU)。

Pousty 继续解释说，开发人员关心他们的代码是否工作，而不一定关心容器本身。“最后，我认为大多数开发人员一点也不关心容器。开发人员关心的是，我写了我的代码，它能工作，我没有把所有的时间都花在刮胡子上。”

你没听错。牦牛毛是由卡林·维耶里于 90 年代在麻省理工学院创造的一个术语。

简而言之，在达到主要目标之前，不得不做许多其他任务，这使得本应简单的过程变得不必要的复杂。花一整天的时间在你的笔记本电脑上安装一个 Tomcat 服务器，仅仅是为了构建一个简单的 Web 应用程序，就是一个例子。

“容器平台和容器正在帮助开发人员摆脱很多麻烦。这就像，'这是一个容器，它让 Tomcat 按照我们想要的方式设置它:当你开发它时，你就是在开发我们将在生产中使用的完全相同的容器。'它给了你一种担心你的代码的方式，而不是你不想做的所有其他事情来让你的代码工作，”Pousty 说。

Pousty 毫不掩饰对激情的憎恨的一件事是开发人员用来比较虚拟机和容器的过时的类比:“宠物和牛。”Pousty 明确指出，这种类比不仅因为宗教原因冒犯了世界上 10 亿人，而且从根本上说是不准确的。

“在我以前的生活中，我是一名保护生物学家。我和牧场主谈过。他们非常关心他们的奶牛。每头牛都是几千块钱，所以他们跟踪他们所有的牛。我更喜欢的一个比喻是“大象和蚂蚁”，大象关心群体中的每一个成员。整个鹿群都会保护后代。那是你的虚拟机。蚂蚁不太关心彼此，没有哀悼期，它们在工作中非常容易互换，而且基因完全相同。这是一个比牛和宠物更好的类比。”

使用这种类比还可以让开发人员习惯于这样一个事实，即他们的数据库和服务器偶尔会停机或遇到问题。不要认为一个系统是不可战胜的，把一个人的架构的一部分想象成可以轻易来去的工蚁是有帮助的。

Pousty 后来回忆了一次交流，总结了容器给发展生态圈带来了什么:“在第一次 DockerCon 上，我与 Dan Walsh 进行了交谈。他对 Docker 最感兴趣的一点是，它摆脱了 [RPM](http://www.rpm.org/) s。他说，“现在我们可以交付位以及它应该如何配置。这是从 RPM-install 向前迈出的一大步，然后去阅读这本 30 页的手册，了解如何配置它。它改变了每个人的整个谈话。"

[码头工人](https://www.mirantis.com/software/docker/kubernetes/)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>