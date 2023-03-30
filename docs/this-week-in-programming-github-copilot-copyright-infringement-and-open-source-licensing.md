# 本周编程:GitHub Copilot，版权侵犯和开源许可

> 原文：<https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/>

本周早些时候，GitHub [推出了 GitHub Copilot](https://github.blog/2021-06-29-introducing-github-copilot-ai-pair-programmer/) ，这是一项新功能，它被称为“你的人工智能配对程序员”，但也可能被恰当地称为“类固醇上的智能感知”。OpenAI Codex 是一个新系统，该公司称其“在代码生成方面比 GPT-3 强得多”，该工具不仅可以自动完成代码行，还可以提供完整的代码块，以响应您键入的代码和自然语言。

经过“数十亿行公共代码的训练”，关于 Copilot 出现的第一个问题集中在版权问题上，特别指向了病毒式 [GPL 许可证](https://www.gnu.org/licenses/gpl-3.0.en.html)的想法，这要求所有衍生作品都带有相同的许可证。

现在，虽然 Twitter 上有很多对话，也有一些[黑客新闻帖子](https://news.ycombinator.com/item?id=27687450)，但正如你所料，大部分都属于“我不是律师”免责声明的范畴。然而，GitHub 首席执行官 Nat Friedman 的一篇[黑客新闻评论](https://news.ycombinator.com/item?id=27678354)对这些问题提供了一点回应。

“一般来说，”弗里德曼写道，“(1)在公共数据上训练 ML 系统是合理的使用(2)输出属于操作者，就像编译器一样。”然后他提供了一个链接到 [OpenAI 对训练机器学习模型的立场](https://www.uspto.gov/sites/default/files/documents/OpenAI_RFC-84-FR-58141.pdf)，该立场认为“训练 AI 系统构成合理使用”，而且“合理使用原则背后的政策考虑支持训练 AI 系统构成合理使用的发现。”

当然，我们觉得你可能会这么说，纳特。

但是 Friedman 并不孤单——几个真正的律师和知识产权法专家开始讨论这个问题，至少在他们的初步分析中，倾向于同意 Friedman 的观点。首先， [Neil Brown](https://www.linkedin.com/in/neilandrewbrown/) 从英国法律的角度审视了这个创意，虽然他不太确定这个创意是否在美国以外被采用，但他简单地指出 [GitHub 的服务条款](https://docs.github.com/en/github/site-policy/github-terms-of-service)足以证明该公司可能会做它正在做的事情。布朗提到了 D4 条款，该条款授予 GitHub“存储、存档、解析和显示你的内容的权利，并在必要时制作附带副本，以提供服务，包括随着时间的推移改进服务。”

“许可证的措辞很宽泛，我相信有争论的余地，但如果事实证明 Github 的活动不需要许可证，那么，就 Github 上托管的代码而言，我怀疑它可以提出一个合理的理由，强制许可条款涵盖了针对上传者的这一点，”布朗写道。不过，总的来说，布朗说他的“问题多于答案。”

苏塞克斯大学(University of Sussex)知识产权法高级讲师、《世界知识产权杂志》(Journal of World Intellectual Property)主编安德烈斯·瓜达穆兹(Andres Guadamuz)给出了一个更明确的答案，他提出了 GitHub Copilot 是否侵犯版权的问题，并总结道:“这既不是侵犯版权，也不是违反许可，但我很高兴能被说服做出相反的结论。”

关于侵犯版权的观点，Guadamuz 首先指出 GitHub 发表的 Alber Ziegler 的一篇研究论文，该论文研究了 Copilot 复制精确文本的情况，并发现这些情况非常罕见。在原始论文中，齐格勒指出，“当一个建议包含从训练集复制的片段时，用户界面应该简单地告诉你它是从哪里引用的，”作为对侵权索赔的解决方案。

关于 GPL 许可和“衍生”作品的想法，Guadamuz 再次表示不同意，认为手头的问题归结为 GPL 如何定义修改的作品，以及“衍生、修改或改编(取决于你的管辖范围)在法律和许可中有特定的含义。”

Guadamuz 写道:“如果你修改作品，你只需要遵守许可证，而且只有当你的代码是基于需要版权许可的原始代码时，才需要遵守许可证，否则就不需要许可证。”“正如我所解释的，我发现以这种方式复制的类似代码极不可能达到侵犯版权的门槛，没有足够的代码被复制，即使有，也似乎大多是其他项目常见的非常基本的代码。”

虽然 Copilot 确实偶尔会吐出一字不差的代码，但这种情况并不常见，这似乎让 Guadamuz 确信，该工具不会有被成功起诉的危险。在对他的文章的一个评论中，他写道，“这一切最终都将由 Codex 来解决，Codex 是一个提供相似性工具的副驾驶，程序员可以在其中检查他们的代码中是否有任何背诵，”这可能有助于这样的场景:

当我们在这里的时候，如果侵犯版权和开源许可对你来说不那么重要，而你更感兴趣的是 GitHub Copilot 这样的工具有多酷和有用，请一定要去阅读 Darryl Taft 对 Copilot 的分析，他称之为“[一个强大的、有争议的自动完成工具，供开发人员使用](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/)。

## 本周的节目中

*   **【令人不安的问题】关于 Windows 的安卓应用:**上周，我们报道了微软如何通过[向 Windows 添加安卓应用](https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/)而再次导致地狱跌入冰点以下。微软为 Android 使用亚马逊 AppStore，而不是谷歌的 Play Store，感觉有点…可疑…Android 开发者、作者和开发者马克·墨菲在他的博客文章“ [Windows 11、亚马逊和不舒服的问题](https://commonsware.com/blog/2021/06/26/windows-11-amazon-uncomfortable-questions.html)”中指出了原因。墨菲在他的帖子中写道，“亚马逊开创了谷歌在应用签名中使用的‘替换开发者签名’方法。而且，亚马逊这样做是为了能够修改他们分发的每一个 Android 应用程序，”他指出，这可能不仅仅是收集分析数据，这已经够麻烦的了，而且还可能修改应用程序，以绕过端到端加密。确实是令人不安的问题。

*   **Docker Desktop 3.5:**Docker Desktop 的最新版本 [Docker Desktop 3.5](https://www.docker.com/products/docker-desktop) 已经到来，带来了[改进的卷管理、Docker 开发环境以及更多](https://www.docker.com/blog/improved-volume-management-docker-dev-environments-and-more-in-desktop-3-5/)。除了我们上周讨论的[开发环境](https://www.docker.com/blog/tech-preview-docker-dev-environments/)之外，Docker Desktop 3.5 还为用户提供了更好地管理其卷中文件的能力，并继续推出 Docker Compose V2 测试版，该测试版将 Compose 命令引入了 Docker CLI。除此之外，Docker Desktop 3.5 还为与苹果硅机不兼容的图像添加了警告，并从用户反馈中获得提示，使反馈请求稍微“不那么具有破坏性”。要查看这一切，请下载或更新到 [Docker Desktop 3.5](https://www.docker.com/products/docker-desktop) 。
*   **Quarkus 2.0 下降:**红帽已经[推出了 Quarkus 2.0](https://developers.redhat.com/articles/2021/07/01/resteasy-reactive-and-more-quarkus-20) ，突出了其中的新特性[持续测试](https://www.infoq.com/news/2021/05/quarkus-2-0-continous-testing/)、 [DevServices](https://quarkus.io/guides/datasource#devservices-configuration-free-databases) ，一个新的[开发者 UI](https://quarkus.io/guides/dev-ui) 和[开发者 CLI](https://quarkus.io/version/main/guides/cli-tooling) ，以及改进了性能的【lightning-fast】[rest easy Reactive](https://quarkus.io/blog/resteasy-reactive/)。Quarkus 是 Red Hat 的 Kubernetes 原生 Java 框架，为 OpenJDK HotSpot 和 GraalVM 量身定制，或被称为“超音速亚原子 Java”，这种向 2.0 的迁移“标志着该项目的成熟度达到了一个新水平，”他们写道。要了解所有这些新内容，请前往 [Quarkus 2.0 发射场](https://quarkus.io/quarkus2/)或 [code.quarkus.io](https://code.quarkus.io/) 进行尝试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>