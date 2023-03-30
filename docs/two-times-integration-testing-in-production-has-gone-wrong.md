# 生产中的两次集成测试都出错了

> 原文：<https://thenewstack.io/two-times-integration-testing-in-production-has-gone-wrong/>

[](https://pt.linkedin.com/in/bruno-lopes-a73b48103)

[](https://pt.linkedin.com/in/bruno-lopes-a73b48103)[](https://pt.linkedin.com/in/bruno-lopes-a73b48103)

很久以前，有一个开发人员只是简单地运行一个测试，但是在这个过程中的一个小失误无意中把他们变成了一个互联网迷因。

当葡萄牙连锁超市 Continente 不小心发送了一个测试通知，大致翻译为“测试马里亚纳-收到？”对于 Continente 应用程序的所有用户来说，它引发了一场互联网狂潮，各大品牌纷纷开起了玩笑。

老实说，当你意识到你精心策划的测试出了可怕的错误时，我们可以同情你内心深处那种可怕的下沉感。我们去过那里！

![](img/b76fa6ce71f2c823918aecefa483f782.png)

通知上写着:“测试玛丽安娜——收到？”

![](img/705ad5f4827567378145e7a6bb06984b.png)

翻译:“这不是一个测试，玛丽安娜”和“史泰博卡，高达 50%的折扣。”—图片[通过](https://www.reddit.com/r/portugal/comments/ngdegw/a_mariana_do_continente_tamb%C3%A9m_vos_anda_a_enviar/) Reddit

![](img/d9f94ee795434e70a7ad3f9d5e9dbaca.png)

翻译:“试试吧，玛丽安娜”和“嗨，玛丽安娜。”—照片[通过](https://www.instagram.com/p/CPGdNC4tUsi/?utm_source=ig_web_copy_link) Instagram

![](img/991ecd8e1ae03bdf2121fde5d78c3b64.png)

翻译:“寻找玛丽安娜。这不是测试。”—照片[通过](https://www.instagram.com/p/CPGJGnGK1h7/?utm_source=ig_web_copy_link) Instagram

不仅仅是我们和 Continente 的开发者。有许多非常公开的测试失败了。我想分享一些我最喜欢的:

## HBO Max 集成测试

去年夏天，HBO Max 向其邮件列表上的许多 HBO Max 订户发送了一封集成测试电子邮件，并迅速收回了这条病毒式的推文。关于这次测试失败，我最喜欢的是大量的高级工程师回答说，每个人都会中断生产，并分享他们自己的一些令人愉快的错误，这让这位身份不明的实习生感到放心！

## 你是说你不想公开犯错？

如果你渴望不意外地看到你的测试像病毒一样传播，这是我们都应该努力达到的目标，你能做些什么来使集成测试变得简单一点呢？

在产品中运行 Kubernetes 时，经历了我们自己惊人的测试失败之后，我们创建了一个框架，明确地为开发人员和测试人员提供了一个不太容易出错的测试工作流程。Testkube 是一个 Kubernetes 本地测试框架，允许测试人员和工程师管理他们集群中发生的所有测试活动。

为什么不从 [GitHub](https://github.com/kubeshop/testkube) 下载最新版本，亲自体验一下呢？如果你有兴趣了解更多，或者只是需要一些人在你的测试出现滑稽错误时给予同情，请加入我们的 [Discord 服务器](https://discord.gg/hfq44wtR6Q)，在 Twitter @Testkube_io 上关注我们，或者直接给我发电子邮件。我们期待着你的消息！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>