# DigitalOcean 和 Northwestern Mutual 如何使用 GitLab 帮助运行 CI/CD

> 原文：<https://thenewstack.io/how-digitalocean-and-northwestern-mutual-use-gitlab-to-help-run-ci-cd/>

GitLab 赞助了这个播客。

持续集成/持续交付，GitLab 在新环境中的体验，甚至大型机都是最新的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中的讨论主题，该播客是在 GitLab Commit 与[digital ocean 的开发者关系经理 Eddie Zaneski](https://www.linkedin.com/in/eddiezane) 的采访中进行的；[凯尔·珀森，](https://www.linkedin.com/in/kyle-persohn)西北互助银行高级工程师；还有[肖恩·考克姆](https://www.linkedin.com/in/seancorkum/) [，](https://www.linkedin.com/in/kyle-persohn)西北互助银行的高级软件工程师。TNS 创始人兼主编亚历克斯·威廉姆斯主持了这次播客。

发起讨论的主题是组织如何让他们的团队参与并构建 CI/CD。

“它必须植根于团队文化中，才能真正充分利用你从中可以获得的一切。确保你建设得快，失败得快，每个人都理解并完全同意，就像'是的，这是我们应该走的正确的路'，”科尔库姆说。

[CI/CD in Kubernetes](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes)

Persohn 随后解释了西北互惠银行内部核心 CI/CD 团队结构，该结构领导并维护其最佳实践，并补充说，“CI/CD 不仅仅停留在那里，开发团队中还有大使，他们正在成为 CI/CD 实践者或领导者，试图培养同样的心态，并在整个企业中传播这种文化。”

在 Digital Ocean，Zaneski 指出，他们的工程部门也有一个完整的 CI/CD 管道团队。

然后讨论转移到西北互助银行向 GitLab 的转移，以及是什么促使了这种转移。“一旦 GitLab CI 出现，我们向它过渡就更有意义了。它将一切都推近了开发人员，他们知道如何测试他们的代码，他们知道如何构建他们的代码，所以我们可以设置，“嘿，如果你只是想去，这里有一个模板，给你，”但如果你需要离开常规的东西，他们可以自己处理，他们不必担心联系另一个团队，比如，“嘿，我需要改变一下，”他们可以这样做，开始工作，“科尔库姆说。

在随后的对话中，扎内斯基深入探讨了数字海洋是如何利用工作流构建工具 GitLab Runners 的。“GitLab 跑步者给我留下了非常深刻的印象。为了我的演讲，我做了很多准备，反复练习了很多次。所以，我用的是共享跑鞋，构建时间有时会从一分钟到六分钟不等，这是非常不稳定的。如果你不熟悉的话，GitLab Runner 只是一个二进制文件，你可以在服务器上部署它，你可以把它部署到 Kubernetes 集群，有很多不同的方式来运行 Runner。runner 所做的只是从 GitLab 中拉一个 jobs 来运行，这也是它的独特之处，它不是一个推的东西，而是一个拉的东西。因此，跑步者会向 GitLab 伸出手，像这样说，“嘿，你有什么要我跑的吗？”然后，GitLab 中的所有 CI/CD 管道都可以启动到运行程序中，实际运行并完成。因此，通过在我自己的虚拟机上替换我自己的运行程序，而不是使用共享的运行程序，我将构建时间减少到了一致的 30-45 秒。当需要构建时间时，这就是你想要依靠这些跑步者的时候，他们可以为你做很多事情。"

[https://www.youtube.com/embed/6cIjVDJIzFQ?feature=oembed](https://www.youtube.com/embed/6cIjVDJIzFQ?feature=oembed)

视频

### 在这个版本中:

[1:17:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=1:17) 打造 CI/CD。
[3:05:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=3:05) 在 GitLab 之前。
[9:29:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=9:29)gitop 和连续交货。
[11:04:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=11:04) 西北互助与工作流。
[12:44:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=12:44)digital ocean 如何使用 GitLab Runners。
[17:39:](https://thenewstack.simplecast.com/episodes/ci-cd-in-kubernetes?t=17:39) 可观测性和 GitLab Runners。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>