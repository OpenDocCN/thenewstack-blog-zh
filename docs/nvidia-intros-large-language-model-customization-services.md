# 英伟达推出大型语言模型定制，服务

> 原文：<https://thenewstack.io/nvidia-intros-large-language-model-customization-services/>

在今天举行的一年一度的 [GPU 技术大会](https://www.nvidia.com/gtc/) (GTC)开发者大会上，Nvidia 宣布了两款基于[大型语言模型(LLM)](https://thenewstack.io/5-ai-trends-to-watch-out-for-in-2022/) 技术的新云服务。一项服务让用户为他们自己的特定用例定制预训练的 LLM，另一项服务使用训练过的蛋白质模型来满足生物医学研究的需要。这些新服务建立在英伟达的 [NeMo 威震天](https://developer.nvidia.com/nvidia-nemo)框架之上，现在进入公开测试阶段。不到两个月前，Nvidia 宣布了对 Nemo 威震天的重大改进。

**必读:** [**Nvidia 剃头高达 7 折大型语言模型培训次数**](https://thenewstack.io/nvidia-shaves-up-to-30-off-large-language-model-training-times/)

## 参见提示

Nvidia 产品管理和营销高级总监 Paresh Kharya 向新的堆栈做了简要介绍。Kharya 解释说，LLM 基于谷歌发明的 transformer 架构。该架构的前提是“人工智能可以理解句子的哪些部分或图像的哪些部分，甚至是非常不同的数据点，彼此相关。”Kharya 还表示，变形金刚甚至可以在未标记的数据集上进行训练，这扩大了它们可以训练的数据量。

事实证明，即使是经过全面训练的逻辑逻辑模型也可以用于一系列用例(包括语言学习之外的用例)，只要它们的大规模基础训练得到一些额外的特殊训练的补充，就可以使用客户自己的数据。使用一种称为“即时学习”的新技术，LLM 可以简单地暴露于少量的示例数据——少至几百个样本——然后 LLM 可以用于客户的场景。培训生成一个“提示令牌”，实际上是一个提供上下文的伴随模型，然后与基础模型相结合，为特定于客户的用例提供更高的准确性。

Nvidia 的新 NeMo LLM 服务将允许这一点。用户将他们的数据提交给模型，然后将提示令牌定制的 LLM 用于他们自己的应用程序。Nvidia 表示，即时训练时间从几分钟到几小时不等，与 LLM 本身所需的几周到几个月的训练时间相比，这是一个微不足道的持续时间。除了即时学习，云服务还将允许其 LLM 直接用于推理。

另一项服务名为 BioNeMo，面向“数字生物学”，有助于制药和生物技术公司加快药物发现。它支持蛋白质、DNA 和生化数据，提供对四种开源蛋白质模型的便捷访问，即 EFM-1(由脸书母公司 Meta 创建，并由 Nvidia 重新培训)、 [OpenFold](https://openfold.io/) 、MegaMolBART 和 ProtT5(由慕尼黑工业大学 [RostLab](https://rostlab.org/) 领导并包括 Nvidia 在内的合作开发)。

## 早期访问和开发者乐园

这些云服务和 API 的用户无需拥有模型或任何 GPU 硬件，即可访问大规模 LLM，包括 Megatron 530B(如此命名是因为它有 5300 亿个训练参数)，无论是在内部还是在云中。而是全部由英伟达管理。开发人员只需要进行正确的 API 调用。

这两项服务将在下个月提前投入使用。在早期访问期间，它们的使用将是免费的。感兴趣的开发者可以向英伟达申请成为早期接入计划的一部分(尽管该公司没有提供申请过程的链接或细节)。Nvidia 甚至将为无代码实验和与模型的交互提供一个“操场”。

## 首席 LLM 爱好者

英伟达创始人兼首席执行官[黄仁勋](https://thenewstack.io/nvidia-ai-can-power-simulation-performance/)对这些新服务非常感兴趣。“大型语言模型有潜力改变每个行业，”黄说。“调整基础模型的能力使数百万开发人员能够获得 LLMs 的能力，他们现在可以创建语言服务并推动科学发现，而无需从头构建一个庞大的模型。”

支持大规模模型即服务(MMaaS？)对于 GPU 领域的领导者来说是一个聪明而合乎逻辑的举措，这些模型可以在这个领域得到最好的训练。事实上，Nvidia 也在 GTC 宣布其新的 H100 GPUs，内置变压器引擎，将大大加快 LLM 训练，现在正在全面生产。

所有这一切，特别是对 NeMo 云服务的早期访问，为开发人员提供了一个很好的机会来使用 LLM，几乎没有进入壁垒。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>