# OCI 期待已久的容器运行时和映像规范问世了

> 原文：<https://thenewstack.io/oci-specification-1-0-arrives/>

经过两年的努力，[开放容器倡议](https://www.opencontainers.org/)已经发布了针对容器映像和容器运行时格式的 [1.0 版本规范](https://github.com/opencontainers/runtime-spec)。由 [Linux 基金会](https://www.linuxfoundation.org/)支持的 OCI 试图确保整个行业的容器系统之间的兼容性，包括从主要的云提供商到 [Docker](https://www.docker.com/) 本身的每一个人。

OCI 执行董事 Chris Aniszczyk 说，OCI 的大部分工作最初是基于 Docker 的工作。该项目从 Docker 的 [Libcontainer](https://github.com/docker/libcontainer) 组件获得了代码捐赠，这成为了 OCI 的最小运行时规范 [runC](https://github.com/opencontainers/runc) 。OCI 图像格式源于 Docker 的 V2 图像格式。

OCI 和红帽公司的首席软件工程师 Vincent Batts 在过去的六个月里帮助完成了规范。他说，很多最后的工作都围绕着正确的措辞，以便所有相关方，包括那些代表微软 Windows 生态系统的人，甚至甲骨文的一些 Solaris 人员，都感到满意和兼容。

Batts 说，图像格式标准最终必须出现。“这是我认为没有人真的想要有一个规范或标准的事情之一。我认为生态系统中的许多人都希望出现一个事实上的标准，但是标准出现的问题是有很多不灵活的地方。Batts 说:“我们需要的用例没有一个听众来倾听他们如何需要所有的灵活性和特性，而这些都需要成为事实上的标准。

Docker 开源项目主管 Stephen Walli 表示同意，图像规范对可移植性尤为重要。“人们已经考虑虚拟机映像很长时间了。“我想你看到的是，当 Docker 的首席技术官 T2 说‘这是非常快速地构建容器的简单方法’时，那套开源项目成为了事实上的标准，”Walli 说。

“在很多方面，”Batts 说，“Docker 图像格式有某些事实上的标准，但事实是它是定制的，所以它只会存在于 Docker 生态系统中。如果您创建了自己的根文件系统构建器，并且有很多工具可以生成根文件系统，如果他们要将其定制为 Docker 映像，就会出现转换缺口，如果您不使用 Docker 工具来生成它，您就必须不断地跨越障碍，以使您的映像成为 Docker 容器映像。”

## Linux、Windows、Solaris

因此，OCI 1.0 规范应该允许多种工具产生兼容的容器。这也应该扩展到云中，供应商可以使用现有的兼容运行时，或者像[甲骨文的新轨道车](https://thenewstack.io/oracle-opens-oci-container-runtime/)一样，编写自己的运行时规范实现。

Batts 说:“对于还不存在的工具，我们需要更具体的东西。”“从很多方面来说，这已经够无聊的了，有些人可能不会去谷歌他们需要的 OCI 工装。他们只是要发现他们在用例中寻找的任何容器工具，理想情况下，它将支持 OCI 映像。他们将有一个兼容层，并重用更多的基础设施，而不仅仅是如果我们不使用工具“X”构建映像，我们必须将所有东西都取出来，使用其他东西。对于许多规避风险的公司来说，这可能是完全不可能的，”Batts 说。

OCI 1.0 规范是 40 多家公司合作的结晶，包括微软和 T2 的甲骨文。这也意味着该规范涵盖了 Windows 和 Solaris。[Docker 营销和社区高级副总裁 David Messina](https://www.linkedin.com/in/davidmessina/) 表示，微软和甲骨文“非常合作，对解决方案的成功至关重要，因为关注的焦点不仅仅是 Linux 容器。重点是 Windows、Linux 和 Solaris，这也是 1.0 规范中的最终内容。有许多供应商参与其中，但有一组核心的贡献者，由于一些真正伟大的跨公司合作，我们现在拥有 1.0 规范。”

至于最终用户，大多数参与该项目的人都希望最终用户不会注意到他们日常工作流程中的许多差异。

“人们应该期待什么？”巴茨问道。"理想情况下，我觉得总的来说，人们可能不会受到日常影响."他补充说，他预计 OCI 图像将成为大多数注册中心及其工具链的输出向量。“这正是亚马逊的 [EC2 容器注册中心](https://aws.amazon.com/ecr/)已经做的事情。你可以将一个图像放到他们的注册表中，然后从注册表中请求 OCI 图像的 MIME 类型。它会侧着身子翻译，然后推或拉。”

“最重要的是，你可以有各种各样的工具用于各种各样的用例，并且仍然有一些公共的工件或层，它们可以在那里进行通信。Batts 说:“这类似于多年来人们习惯于将 Qemu 映像用于虚拟机。

至于该规范的未来，CoreOS 的首席技术官 Brandon Philips 表示，已经有一些想法在下一个版本中得到解决。“有一些关于改进包装和运输方式的想法。我们如何更有效地传递差异和压缩内容？这有赖于对分配如何工作有真正好的规范。

Docker 的 Walli 说,“工作组面临的下一项重要工作是认证。规格终于在本周登陆，现在我们要证明这一点。接下来，我们将进行认证，使用 OCI 品牌来验证产品。”

CoreOS 、[Linux 基金会](https://www.linuxfoundation.org/)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

专题图片:[一艘船的陶土模型，公元前 6 世纪](http://www.metmuseum.org/Collections/search-the-collections/241305)，纽约大都会艺术博物馆，塞斯诺拉收藏。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>