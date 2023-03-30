# 亚马逊 AWS 支持 OCI 格式；现在会有混合容器注册吗？

> 原文：<https://thenewstack.io/amazon-aws-now-supports-oci-format-will-mixed-registry-now/>

上周，亚马逊网络服务在其工程博客上宣布[其](https://aws.amazon.com/about-aws/whats-new/2017/01/amazon-ecr-supports-docker-image-manifest-v2-schema-2/) [EC2 容器注册中心](https://aws.amazon.com/ecr/) (ECR)正在增加对 [OCI 容器格式](https://aws.amazon.com/ecr/)的草案规范的支持，此举受到了容器化领域一些顶级工程师的欢迎，几乎是对开放标准的皇家祝福。

AWS 高级软件工程师 Scott Windsor 告诉新的堆栈，此举非常重要，因为这是在公共云空间——隔离测试环境之外——向第一个真正的 OCI 图像推/拉注册表迈出的最大一步。

温莎写道:“还没有一个注册机构支持拉或推 OCI 图片。”。"结果，在注册之前，OCI 的一些开发工具都停滞不前了."

正如 Windsor 通过 Google Groups list 告诉开发者[的那样，尽管 CoreOS 的](https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/ajYuSUnHhXY)[**rkt**](https://coreos.com/rkt)container engine 确实支持 OCI 容器格式草案作为一个选项(代替最终的 1.0 标准)，但没有直接、自动的方式将 OCI 格式的图像推送到容器注册中心。争论的焦点是 JSON 映像清单，它详细描述了用于注册的容器内容。

Docker 的 image manifest format(AWS 上个月末开始支持该格式)的版本 2、模式 2 支持五种 MIME 格式的媒体类型，每种媒体类型都可以在 JSON 清单列表中的 **mediaType** 字段描述下输入。这个描述解释了图像中包含的内容类型:schema 1 组件、schema 2 组件、另一个清单列表、一个 gzipped TAR 文件或一个 JSON 文件。

目前，OCI 格式支持八种 MIME 格式的类型，包括 TAR 文件的四种排列(有或没有发布许可)，但另外列出了**。oci** 作为与**相对的属性标识符。码头工人**。这是主要的区别——在 OCI 有机会完成其漫长的酝酿阶段之前，这个区别目前确实无法弥合。

温莎指出，除非有足够多的人有机会与 OCI 合作解决所有的问题，否则这不可能真正发生。最终还是要有人咬紧牙关，最后成了 AWS。

“我们的客户今天主要使用 Docker(我认为这不会很快改变)，我们希望确保我们支持这些用例，”Windsor 告诉 New Stack。“如果 Docker 搬到 OCI 或允许 OCI 支持，我们将确保以 Docker 引擎使用它的方式支持它。在当前的 OCI 映像规范中，分发仍然不在范围之内，所以我们必须了解协议是如何定义的。”

[CoreOS](https://coreos.com/) 的首席执行官 Alex Polvi 立即通过社交媒体表达了对 AWS 举措的支持，并在给新堆栈的一份说明中重申了这一支持。

“在 OCI 这样的标准下工作，有点先有鸡还是先有蛋，”波尔维写道。“要实现互操作性，你需要标准的两个方面——消费者和生产者。在 AWS 的支持下，我们可以更快地围绕它创建生态系统。这是一个重要的里程碑，因为大多数产品都希望与 AWS 互操作。”

Polvi 指出，他的公司仍然完全投资于 OCI 标准的持续发展，CoreOS 首席技术官 [Brandon Philips](https://twitter.com/BrandonPhilips) 继续担任其[技术监督委员会](https://groups.google.com/a/opencontainers.org/forum/#!forum/tob)的主席。

至少有一位 Docker 贡献者对亚马逊的举动表示了感谢: [Stephen Day](https://github.com/stevvooe?language=go&tab=stars) ，他的项目是为 Go 语言实现一个[散列身份实现](https://github.com/cloudflare/gokeyless)，这个项目始于 Docker，上个月刚刚被 OCI 吸收。正如 Day [写给开发者小组](https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/ajYuSUnHhXY)的信中所说，Docker Inc .已经避免了将演进的 OCI 格式合并回其自身组织的过程，主要是因为 1.0 版本尚未最终确定，显然还有许多工作要做。

“在最终细节确定之前宣布支持注册还为时过早，”Day 写道。“不能保证 ECR 中的 OCI 图像不会出现问题。[*]OCI 图像规范很可能会围绕清单列表进行至少一次媒体类型调整。”*

 *“我希望通过与 OCI 集团合作，我们将能够支持按规格分配，”温莎说，在他给我们的说明。“随着定义的确定，我们今天支持 OCI 的方式可能会改变。我怀疑我们会在这里做出突破性的改变，但如果必须，我们会与客户沟通，并确保平稳过渡。”

特征图片:[白色和棕色的鸡蛋](https://commons.wikimedia.org/wiki/File:Brown_and_white_eggs.jpg)由 Linsenhejhej 创作，根据知识共享协议授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*