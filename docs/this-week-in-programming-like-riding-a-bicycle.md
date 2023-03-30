# 本周编程:像骑自行车一样

> 原文：<https://thenewstack.io/this-week-in-programming-like-riding-a-bicycle/>

一个几乎编程的个人故事本周开始我们的悲哀。几周前，我有一个半个人的任务想要完成，我认为拼凑一点代码是解决办法。镇上有一条待定的自行车道，我们被告知，也许当地官员需要一些温和的刺激来完成这项工作。

我想，还有什么比建立一个简单的表单更好的方式呢，收集一些用户输入——姓名、电子邮件、他们希望从列表中选择自行车道的原因，或者他们自己的一些文字——然后解析并组合成一封电子邮件，发送给市长和其他感兴趣的人。

超级简单，对吧？我也这么认为。

现在，我已经没有个人网络服务器了，所以我用一个脚本拼凑了一个 Google 表单，该脚本将在表单提交时运行。经过反复试验和调整——这是标准的开发过程——我得到了运行相当可靠的东西。只有一个问题——这些邮件来自我的个人邮箱。这就是事情变得奇怪的地方。我把它全部复制到一个不同的、不那么个人化的谷歌账户上，不知何故，它不再那么可靠了。填好表格，点击提交，突然…两封邮件，一封空白，一封已填好。或者根本没有邮件。

在这个过程的开始，我像这些天一样，通过谷歌搜索我的基本情况，找到了看起来符合我需求的博客文章。那是编程吧？它把我送上了正确的轨道，但一旦我到了那里，我发现自己处于一个奇怪的迟钝的地方，那里有相互联系的表单和脚本，没有可以来回追踪的可见连接。虫子？当然，有错误跟踪，但是有时，在从一个帐户到另一个帐户共享表单和脚本之后，我甚至不能确定我正在处理的脚本是否与我创建的表单有关联。

看来，简单编码的新简化抽象世界就到此为止了。

嗯，上周我摔断了脚，发现自己被困在家里，因此决定回到我去年秋天报名的 Python Udemy 课程。如果我不能使用谷歌的基于网络的工具方便快捷地完成这些事情，我就只能回到最基本的东西——我的 Linux 盒子。

不到几分钟，我再次发现自己陷入了困境，突然将命令复制并粘贴到我的终端，绝望地试图让我的版本的 [Jupyter 笔记本](https://jupyter.org/)运行 Python 3 而不是 Python 2。现在，继续用谷歌搜索，你会得到一长串似乎适用于其他所有人的解决方案，但是尽我所能让我的个人开发环境模仿用于 Python 课程的环境…不行。

也许我需要采纳 Kelsey Hightower 的建议，尝试类似于无服务器的方法来完成这些任务，因为我还没有完成为本 Python 教程设置环境的第三步。或者，我可能需要上一门关于设置 Python 环境的单独的 Udemy 课程来学习 Python 教程。不管是什么，总是这样或那样，不是吗？这就是作为一名开发人员的真正意义——坚韧不拔地克服这类事情。

或许这就是我成为作家的原因。

[https://www.youtube.com/embed/8QGm24BZ6nk?feature=oembed](https://www.youtube.com/embed/8QGm24BZ6nk?feature=oembed)

视频

## 本周的节目中

*   **看马，没有手！**为了继续保持在聚光灯下，GitLab 上周在其 GitHub 卫星会议上对 GitHub 最近的声明进行了又一次反驳，其[GitHub 新功能的 GitLab 用户指南](https://about.gitlab.com/2019/05/23/gitlab-features-compared-github/)。最近几周你可能已经注意到了，我是 GitHub 和 GitLab 之间这种来回的粉丝。我们又来了——GitHub 宣布了一堆东西，GitLab 说，“哦？你是说这样？”“指南”提供了一个有两栏的表格:“GitHub 在 5 月 23 日宣布了什么”在左边，“类似的&相关的 GitLab 功能”在右边，链接和所有。为了避免现有用户群被 GitHub 卫星上展示的闪亮东西所吸引，GitLab 写道:“如果你是 GitLab 用户，这里有一个 GitHub 今天宣布的快速备忘单，以及它与 GitLab 已经存在或在[公共 GitLab 方向页面](https://about.gitlab.com/direction/)上的功能的关系。该公司还向竞争对手表示了一轮祝贺，写道“由于 GitLab 本身是一个开源项目，我们也是 GitHub 上托管的许多其他开源项目的贡献者，我们很高兴地看到 GitHub 正在通过 [GitHub 赞助商](https://github.com/sponsors)和 [GitHub 赞助商匹配基金](https://help.github.com/en/articles/about-github-sponsors)寻找使开源项目更加安全和获得更多资金的方法。干得好，GitHub！"
*   **用无人机做好事:** IBM 正在寻找一些开发人员用无人机做好事，它正在通过[IBM 开发人员无人机空投](https://developer.ibm.com/blogs/win-a-drone-program-a-drone-change-the-world/)实现这一目标，该竞赛将在未来五周内向英国、西班牙、美国和加拿大的居民分发 1500 架 DJI·泰洛无人机。除了无人机，幸运的获奖者将获得“代码模式，以释放其在视觉识别、人工智能和机器学习方面的潜力和新技能。”该挑战将持续到 6 月 16 日，新的获胜者将于每周二公布，最终目标是编写“一些令人惊叹的开源模式[……]使用 Node-RED 和 IBM Watson 视觉识别、Watson IoT、IBM Cloud 和 IBM Data and Analytics 等工具，创建一个让您的社区变得不同的无人机应用程序。”IBM 提到了自学成才的开发人员 Pedro Cruz，他在波多黎各赢得了 DroneAID 的[代码号召](https://developer.ibm.com/callforcode/)黑客马拉松，drone aid 是一种自然灾害防备无人机解决方案，灵感来自他的祖母在他们波多黎各的家中，在飓风 Maria 之后。(查看 DroneAID 上克鲁兹的采访视频。)

https://youtu.be/9fRcis-5Zuc

*   **TypeScript 3.5 下降:**没错，您最喜欢的静态类型 Javascript 替代方案刚刚[推出了 TypeScript 3.5](https://devblogs.microsoft.com/typescript/announcing-typescript-3-5/) ，它带来了许多改进，主要是“新的类型检查和增量构建优化，旨在提高速度，”根据 [SD Times](https://sdtimes.com/msft/typescript-3-5-now-available-with-speed-improvements/) 。显然，类型检查速度的提高是 TypeScript 3.4 的一个缺陷修复，它“引入了回归并增加了类型检查器的工作”详情请阅读，但请务必查看[突破性变化](https://devblogs.microsoft.com/typescript/announcing-typescript-3-5/#breaking-changes)。
*   **让文档写作开始:**谷歌继续进行它的[文档季](https://developers.google.com/season-of-docs/)，将作者与开源项目配对以创建文档的努力现在已经开始[接受技术作者申请](http://opensource.googleblog.com/2019/05/season-of-docs-now-accepting-technical.html)。感兴趣的技术作者应该查看[参与组织](https://developers.google.com/season-of-docs/docs/participants/)的列表，并创建一个技术作者应用程序，它可以在 [Google 表单](https://forms.gle/Fxr2nW4TCiyESHbo8)中获得。这一步的截止时间是 6 月 28 日 18:00 UTC，以免你认为谷歌在寻找完全免费的工作，有一个可选的津贴提供给被接受的技术作家。
*   **ML Text&AWS 的数据提取:** SD Times 为我们带来了 [Textract](https://aws.amazon.com/textract/) 的[故事](https://sdtimes.com/ai/aws-announces-machine-learning-text-and-data-extraction-solution/)，这是一种从扫描文档中自动提取文本和数据的服务，它“超越了简单的光学字符识别(OCR)，还可以识别表单中的字段内容和表格中存储的信息。”根据这篇报道，“亚马逊希望更容易地从表格、表单和几乎任何文档中提取文本和数据。该公司宣布了新的完全管理的 Textract 服务，该服务消除了手动审查或定制代码文本和机器学习数据提取的需要。亚马逊表示，标准文本提取通常使用手动数据输入或 OCR，并需要“一个耗时且往往不准确的过程，产生的输出需要大量的后期处理，才能被其他应用程序使用，”它表示，这一问题通过这一新的解决方案得到了解决。Textract“获取存储在亚马逊 S3 桶中的扫描文件，读取它们，并以 JSON 文本的形式返回数据，并标注页码、节、表单标签和数据类型”，开发人员可以“将 Textract 与机器学习服务集成，如:亚马逊理解、亚马逊理解医疗、亚马逊翻译和亚马逊 SageMaker。”

来自国会图书馆的特征图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>