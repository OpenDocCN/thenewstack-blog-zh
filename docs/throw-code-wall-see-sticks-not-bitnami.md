# Bitnami 跟踪软件包更新，所以你不必

> 原文：<https://thenewstack.io/throw-code-wall-see-sticks-not-bitnami/>

随着云平台的持续增长，开发人员在为其依赖项选择特定的发行版时面临着比以往更多的选择。使用一个 [Bitnami](https://bitnami.com/) 包，开发人员不仅可以获得最新的稳定版本，而且不用担心维护所有的细节，让他们专注于编码，而不是更新依赖项或过时的库。

用户可以从应用程序或开发环境中进行选择，将其安装在本地、虚拟机或任何主要的云平台上，而 Bitnami 将对其进行维护和更新。采取细粒度的方法来解决开发者在大规模运行时面临的一致性问题，只是 Bitnami 开源努力的一部分。

在这一集的[中，新堆栈制造商](https://thenewstack.io/podcasts/)嵌入下面，新堆栈创始人 Alex Williams 和[软件工程日报](http://softwareengineeringdaily.com/)播客的联合主持人 [Jeff Meyerson](https://twitter.com/the_prion) 与 [Erica Brescia](https://twitter.com/ericabrescia) ，Bitnami 联合创始人兼首席运营官以及[Bitnami 营销副总裁 David Dennis](https://twitter.com/davidpdennis) 。在他们的讨论中，他们强调了[从虚拟机到容器的转变](https://thenewstack.io/container-lifecycle-management-part-one-not-fathers-vms/)对开发人员的影响，Bitnami 在大规模运营时保持环境一致性的努力[，以及该公司推进](https://thenewstack.io/qa-erica-brescia-bitnami/)[新开源项目的努力](https://thenewstack.io/bitnami-rethinks-meaning-application/)。

[向集装箱转移:大卫·丹尼斯、埃里卡·布雷西亚在奥斯丁的 OSCON](https://thenewstack.simplecast.com/episodes/the-shift-to-containers-david-dennis-erica-brescia-at-oscon-in-austin)

对话[也可以在 YouTube 上欣赏](https://youtu.be/leD_ZSrNTBo)。

尽管在测试和生产中使用容器无疑是一个强有力的理由，但是 Dennis 指出，对于一些组织来说，尽管开发人员很喜欢它们，但是它们并不实用。“并不是所有的应用程序——开源或其他——都适合容器。对于有些事情，没有任何意义。如果我的 IT 环境中有一个现有的应用程序堆栈，我如何将容器放入更大的旧的或古老的东西的生态系统中？我如何把它卷在一起？我将在有意义的地方使用容器。”

保持容器最新是许多开发人员面临的一个挑战，在大规模运行应用程序时更是如此。Brescia 接着解释了 Bitnami 如何提供其工具 [Stacksmith](https://stacksmith.bitnami.com/) 来解决围绕组成容器堆栈的组件的组成问题。

“Stacksmith 不仅仅是建立一个 Docker 文件，而是保持所有内容都是最新的。最大的挑战是如何让所有这些容器保持最新？因为 Stacksmith 知道你使用了什么，所以如果某个东西出现了问题，你需要重新部署，它可以通过 webhook、API 甚至 over Slack 让你知道，”布雷西亚说。

然而，Bitnami 并没有把所有的乐趣都留给自己。有计划在不久的将来将它的一些项目引入开源社区。布雷西亚指出，这些项目将在未来三到六个月内公布。他们在从事这些项目的过程中不断收到来自开源社区的反馈，Brescia 解释说这是 Bitnami 作为一个整体的关键焦点。

“你不能只拿着代码，然后用开源许可证把它扔到墙外，就这样。你必须在文档上花很多心思，是否为外界做好了准备，以及你是否准备好在某个时候接受反馈和贡献。我们不能掉以轻心。否则，你只是把代码放在那里，没人会在意。”

布雷西亚还指出，在企业内部工作的组织应该努力在自己的团队中培养这种坦诚的透明度。

“此外，对于开源内容，当你参与打包和提供企业内容源时，需要透明地说:‘看，我们可能永远不会修改开源内容，但我们希望确保你这样做的方式符合我们的安全准则。’这也为考虑将 Bitnami 用于内部的人提供了一个舒适的水平。"

[Bitnami](https://bitnami.com/) 和 Capital One 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>