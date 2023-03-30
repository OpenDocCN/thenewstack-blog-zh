# 为什么您的组织不能仅靠 Git 生存

> 原文：<https://thenewstack.io/why-your-organization-cannot-live-on-git-alone/>

Twistlock 赞助了这个播客。

[为什么你的组织不能仅靠 Git 生存](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone)

Linux 内核背后的主要开发者 [Linus Torvalds](https://github.com/torvalds) 创建了 [Git](https://github.com/gitster/git) 开源代码库，这无疑是天才之举。但是，虽然 Junio Hamano 继续在维护开源 Git 方面做得非常出色，但是那些希望跳跃到所谓的敏捷开发和部署周期的组织必须超越依赖 Git 的核心版本控制和软件库功能。

如果你愿意，可以称之为成长的烦恼——但是 DevOps 敏捷性的下一阶段需要更多更多的东西。这尤其适用于开发运维团队，他们希望在周期开始时增加嵌入安全性的部署节奏(是的，虽然说起来容易做起来难，但这是可能的)。

要实现这一点，需要重新思考传统的软件开发周期。这需要做一些必要的工作，以便代码一存储到 Git 上，就可以立即集成到主生产管道中。

在五月底于巴塞罗纳举行的 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 会议期间录制的本期[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中，如何跨越主要使用 Git 作为版本控制的软件存储库是与[产品营销总监](https://www.linkedin.com/in/ashishkuthiala)[Ashish Kuthiala](https://gitlab.com/gitlab-com)的主要话题。

However, Git has and should continue to play its part in the software development and delivery in the indefinite future. Git, indeed, has its place in DevOps. Kuthiala noted how open source Git offers well-known advantages over other repositories, including its distributed mechanism, its speed and the ease and elegance with which it enables code-sharing. But as mentioned above, that is not enough.

“If you look at the complete software development lifecycle when storing code somewhere, then taking it and making it usable for the end user — you still very often have traditional software process that in place that needs to go through traditional software development lifecycles — and that hasn’t changed for a very long time,” Kuthiala said.

This traditional build and deploy model continues to still often involve different specialized teams, each separately adding code to the repository and testing performance and security before the code is processed by operations. “So, there’s still a lot of manual handoff from one team to the other. But this is changing and isn’t really that acceptable anymore in a world that wants to go faster,” Kuthiala said. “The customers want to use software as a differentiating mechanism for their competitors and you need to respond really fast. And this manual hand-off process is error-prone, takes time and ultimately, is costly.”

It was this problem that prompted GitLab to see the importance of how a repository by itself was insufficient to accommodate where software development was headed. The end result was enabling DevOps to merge all the processes into a single application. “As soon as you’ve committed your coding into Git, it will start building and integrating into the main track. And the users found this experience to be immensely valuable, which led to the realization that since there are so many stages in the software development cycle, it is necessary to really not have to stitch together many different tools,” Kuthiala said. “And so, [GitLab] has built a single tool for the entire application development process, especially focused on DevOps.”

The numbers say a lot. Kuthiala said GitLab’s software-as-a-service sees about 165 to 170 deploys a day. For the self-hosted version, Based on the open source forum model,  a realize takes place on the 22nd of each month, which has occurred during the past “90 plus months without fail,” Kuthiala said.

GitLab’s external contributors number more than 2,200\. “Our customers are all actually contributing code to make this better,” Kuthiala said. “Our customers, they’re all working to better each other.”

[https://www.youtube.com/embed/rA7reJ0y1mY?feature=oembed](https://www.youtube.com/embed/rA7reJ0y1mY?feature=oembed)

VIDEO

### In this Edition:

[1:22:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=1:22) 采用 Git 和 GitLab。
[凌晨 4 点 48 分:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=4:48)流程和发射井。
[7:32:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=7:32) 度量。
[13:20:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=13:20) 现实检查现在是发展的时候。
[15:25:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=15:25)DevSecOps 的想法。
[21:24:](https://thenewstack.simplecast.com/episodes/why-your-organization-cannot-live-on-git-alone?t=21:24) 云原生开发。

KubeCon + CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>