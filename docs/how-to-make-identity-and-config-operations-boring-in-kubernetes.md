# 如何让 Kubernetes 中的身份和配置操作变得乏味

> 原文：<https://thenewstack.io/how-to-make-identity-and-config-operations-boring-in-kubernetes/>

几乎所有的软件工程师都会告诉你:如果他们不得不多次做同样的事情，他们会寻找一种自动化的方法。管理或部署到 Kubernetes 时也是如此。没有人希望一天登录系统超过一次。谈到配置模板，没有人想重新发明轮子。没有人希望手动更新配置文件中的图像引用，或者确保图像是按照正确的操作顺序构建的。没有人希望手动跟踪他们对配置文件所做的更改。

好消息是，在几个不同的项目中有工具可以帮助解决这个问题。

## 鳍状的

 [尼基塔·拉古纳特

Nikhita 是 VMware 技术部门的高级成员，也是 Kubernetes 指导委员会的成员，负责 Kubernetes 项目的整体管理。她还是云计算原生计算基金会(CNCF)大使和国际公共演讲人。](https://www.linkedin.com/in/nikinath/) 

假设您想要将一个应用程序部署到工作中的 Kubernetes 集群。要部署应用程序，您首先需要访问集群。由于群集归您的雇主所有，因此访问群集可能需要您输入凭据，并且可能需要执行多因素身份验证。但是，您不希望每次运行`kubectl get pods`时都输入凭证。那会很繁琐的！那么，如何避免这样做呢？

[来自 VMware 的开源项目 Pinniped](https://github.com/vmware-tanzu/pinniped) ，通过允许集群管理员将外部身份提供者(IDP)插入到 Kubernetes 集群中，使这一点变得容易。它简化了所有集群的登录流程。一旦在集群上安装了 Pinniped，第一次运行 kubectl 命令时，它会提示您点击一个 URL。浏览器中的 URL 将重定向您，以交互方式登录到您的上游 IDP 并完成身份验证。现在，如果您运行另一个 kubectl 命令，它将“正常工作”,直到您的会话到期。即使您跨多个地区、提供商或环境访问多个集群，也只需登录一次。

Pinniped 简化了从外部 IDP 获取身份并在多个集群中使用这些身份的过程。管理员可以通过 Kubernetes 自定义资源配置外部 IDP。这意味着管理员可以使用 GitOps 和标准 Kubernetes 工具管理 Pinniped。目前，唯一受支持的 IDPs 是实现了 [Kubernetes TokenReview API](https://kubernetes.io/docs/reference/access-authn-authz/authentication/#webhook-token-authentication) 的 webhooks。对更多 IDP 类型的支持即将推出，该项目的完整路线图已经[公开](https://github.com/vmware-tanzu/pinniped/discussions/144)。

## 卡沃尔

好了，现在你可以访问你的 Kubernetes 集群了。但是你仍然需要部署你的应用。 [Carvel](https://carvel.dev/) 是一套开源工具——[ytt](https://get-ytt.io/)(YAML 模板工具) [kbld](https://get-kbld.io/) 和[kapp](https://get-kapp.io/)——让这个过程变得毫不费力。卡沃尔的妙处在于每个工具都有单一的用途和明确的界限。你可以选择使用哪一个；工具之间没有依赖关系。因此，让我们看看 Carvel 如何帮助简化部署工作流。

首先，您有一个包含部署和服务配置的 [config.yaml](https://github.com/k14s/k8s-simple-app-example/blob/develop/config-step-1-minimal/config.yml) 配置文件。为了确保您的应用程序是可扩展的，并且可以接受多个数据值，假设您决定定制配置。这就是 ytt 证明有用的地方。Ytt 允许通过[带注释的 YAML 文件](https://get-ytt.io/#example:example-load-data-values)进行模板化。针对 YAML 结构——如地图、数组等——使用注释进行标注。如果您想使用条件和循环进行强制性定制，ytt 允许您用一种叫做 [Starlark](https://github.com/bazelbuild/starlark) 的类似 python 的语言来指定。您还可以通过在 Starlark 中设置断言来验证输入数据。因为 ytt 使用结构感知模板而不是文本模板，所以您不再需要为与缩进或转义相关的挑战而绞尽脑汁。

在开发您的应用程序时，假设您在互联网上发现了一个您想要使用的 Kubernetes 部署配置。为了确保配置与您的应用程序无缝地工作，您可能需要调整这个第三方配置文件中的一些旋钮(例如，副本)。但是，您不希望失去对这种底层第三方配置的跟踪。Ytt 强大的[覆盖](https://github.com/k14s/ytt/blob/develop/docs/lang-ref-ytt-overlay.md)特性使这变得非常容易，通过用任意的改变修补配置文件。Ytt 允许第三方配置文件的副本保持原样，不被修改。如果你不确定你正在做的改变(模板化和修补很难！)，你也可以在[互动游乐场](https://get-ytt.io/#playground)里尝试一下。

如果您的配置文件中指定了任何图像，它们可能需要被构建和发布。你可以使用 [kbld](https://get-kbld.io/) 来实现这一点。kbld 在您的配置文件中查找映像，通过 Docker 构建映像(您也可以插入其他构建器)并将其推送到您选择的注册表中。它甚至更新配置文件中的图像引用，将这些引用解析为不可变的摘要。为了使将来的调试更容易，它还用图像元数据注释了 Kubernetes 资源。

现在您的配置文件已经准备好了，您需要部署您的应用程序。要部署您的应用程序，您可以直接使用`kubectl apply`——但是 kubectl 不会告诉您将对集群中的资源进行哪些更改。为了让部署过程更加透明，您可以使用 [kapp](https://get-kapp.io/) 。Kapp 是一个轻量级的 CLI 工具，它可以计算您的配置和实时集群状态之间的变化；并且只应用您批准的更改。Kapp 还具有依赖性意识。如果您打乱了配置文件中资源的顺序，kapp 会正确地对它们进行排序(例如，CRD 在需要它们的定制资源之前)。Kapp 还基于唯一生成的标签来跟踪资源，因此您可以使用一个`kapp delete`命令一次性删除所有资源。

## 了解更多信息并加入我们！

如果您想了解更多关于 Pinniped 和 Carvel (ytt、kbld 和 kapp)的信息，我们希望在虚拟 [KubeCon+CloudNativeCon](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 北美 2020 大会的 VMware 展台上见到您。

您可以通过参与[pinnipped](https://github.com/vmware-tanzu/pinniped/discussions)和 [Carvel](https://github.com/k14s/) 的 GitHub 问题和[讨论](https://github.com/vmware-tanzu/pinniped/discussions)页面来关注我们的工作并参与正在进行的讨论。要投稿，请查看好的第一期。如果您或您的团队想要一个演示，请在 Kubernetes Slack 上的[# pinnipped](https://kubernetes.slack.com/messages/pinniped)和 [#carvel](https://kubernetes.slack.com/messages/carvel) 中创建一个问题或与我们联系。我们非常友好，希望收到您的来信！

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 11 月 17 日至 20 日举行的 [KubeCon + CloudNativeCon 北美 2020](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>