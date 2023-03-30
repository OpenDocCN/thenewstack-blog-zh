# 云铸造:为生存而生

> 原文：<https://thenewstack.io/cloud-foundry-wants-help-destroy-architecture-seriously/>

故意破坏应用程序以使其更具弹性是一个让开发人员高兴或沮丧的过程。当测试一个人的堆栈以了解潜在问题在哪里时，运营团队可能不愿意在他们精心管理的环境中引发混乱。

在这一集的[The New Stack Analysts](https://thenewstack.io/podcasts/)embedded below 中，New Stack 创始人 Alex Williams 采访了[Cloud Foundry](https://www.cloudfoundry.org/)CEO[Sam ram Ji](https://twitter.com/sramji)，以及科学出版公司 [Springer Nature](http://www.springernature.com/us/) 平台工程负责人 [Daniel Otte](https://twitter.com/MoanOps) 和 Springer Nature 平台工程师 [Simon Johansson](https://twitter.com/KarlSimonJohan) 。他们讨论了 Springer Nature 利用 Cloud Foundry 的方式，以及 Cloud Foundry 如何帮助开发人员更好地理解拆除东西可能是重建它们的最佳方式。

[论弹性:Sam Ramji、Daniel Otte 和 Simon Johansson 在 Cloud Foundry 峰会上](https://thenewstack.simplecast.com/episodes/on-resilience-sam-ramji-daniel-otte-and-simon-johansson-at-cloud-foundry-summit)

对话[也可以在 YouTube 上听到](https://youtu.be/DsDPVD3AyNA)。

最初，Springer Nature 在选择云代工厂之前已经评估了许多平台。决定性因素是信任，拉姆奇认为这是 Cloud Foundry 作为一家公司的主要关注点。简而言之，如果没有透明度，Cloud Foundry 在解决 Johansson 和 Otte 在 Springer Nature 面临的问题方面做得再好也没有用。

“你必须从建立信任开始，然后才能开始谈论技术。因为，作为技术专家，我们经常只接受技术方面的教育，这是非常重要的一课。你通过倾听、沟通和逐步满足人们的需求来建立信任，”拉姆奇指出。

面对“虚拟机自动售货机”的现实后，Springer Nature 的团队知道他们必须找到一个解决代码部署和架构困境的方案。

“一个项目的启动需要数周时间，你必须申请机器并真正建立基础设施。很多人把它称为 DevOps，老实说，我认为这是低效的。我认为我们做了一个交易，把自己从开发团队中移除。我们故意后退一步，决定创建一个平台来处理所有这些混乱，这样开发人员就可以专注于编写代码，”Otte 说。

很自然，一旦 Springer Nature 让 Cloud Foundry 顺利启动并运行其堆栈，他们就决定采取该过程中的下一个合乎逻辑的步骤:

打破它。

然而，这并不像他们想象的那么容易。“我们还没能打破云代工。我们真的很努力，”约翰松说。

Ramji 预计到了这一点，并欢迎开发者尝试以任何方式打破 Cloud Foundry。然而，它有着惊人的弹性。由 Cloud Foundry 的 [BOSH](https://bosh.io/) 生命周期管理软件提供支持，Cloud Foundry 还推出了一个名为[混沌狐猴](https://github.com/strepsirrhini-army/chaos-lemur)的自我破坏平台，专为那些像 Springer Nature 这样可能试图故意破坏他们堆栈的开发人员打造。

SwissComm 等公司更进一步，创建了他们自己的平台 Chaos Heidi，他们[在 2016 年云铸造峰会](https://cfsummit2016.sched.org/event/6aQ2/chaos-heidi-vs-orchard-self-disruption-and-healing-in-a-cloud-foundry-based-service-environment-diego-zamboni-swisscom-bill-chapman-stark-wayne)上讨论了这个平台。混沌海蒂是 Cloud Foundry 的混沌狐猴和网飞的混沌猴的表亲。这些自我破坏平台是为了在你的应用程序曾经存在的地方留下一个闷烧的痕迹而构建的。拉姆奇接着解释说，任何人都可以访问[波什演示](https://github.com/strepsirrhini-army/chaos-lemur)来测试 Cloud Foundry 的恢复能力，利用混沌狐猴试图在波什起死回生之前炸毁他们自己的模拟堆栈。

“无论你的技术有多好或多差，你都可以做 BOSH 演示。上教程，你将建立 BOSH，启动 Cloud Foundry，然后你将试图杀死应用程序，并在 BOSH 可以把它带回来之前把它拿下来。你最终会和波什打起来。当你与复活者搏斗时，会发生令人惊讶的事情。”

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>