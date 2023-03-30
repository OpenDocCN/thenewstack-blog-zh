# 拥抱脸说，机器学习就像 API 一样简单

> 原文：<https://thenewstack.io/machine-learning-is-as-easy-as-an-api-says-hugging-face/>

人工智能现在似乎是精英专家的领域，但初创公司[humping Face](https://huggingface.co/)计划通过让它像部署 [REST API](https://thenewstack.io/how-to-automate-and-scale-your-rest-api-tests/) 一样简单来“民主化好的机器学习”。

这家初创公司的产品和增长主管[杰夫·布迪尔](https://www.linkedin.com/in/jeffboudier/)解释说，这不是理论上的——现在有了前端和网络应用的用例，这是可能的。拥抱脸提供在其社区网站上免费开放源代码机器学习(ML)模型，同时对基础设施和服务支持收费。

“首先，我们让它非常容易使用，所以如果你的应用程序中有机器学习的用例，那么非常容易找到拥抱脸，找到模型，部署 API，然后构建，”Boudier 告诉 New Stack。“第二件事是，我们希望让机器学习变得非常容易。”

## 人工智能在前端和移动设备上的应用示例

Boudier 分享了医疗保健公司 [Phamily 如何使用拥抱脸](https://www.youtube.com/watch?v=20C9X5OYO2Q)。该公司帮助医疗集团管理内部慢性护理管理服务线，用于患者就诊之间。它需要利用机器学习模型来自动分类和筛选邮件。

当然，问题是建立模型，这是一个非常昂贵的提议，正如 Phamily 很快了解到的那样。到了需要组建基础架构团队或回家的时候了。

相反，Phamily 利用了 Hugging Face 的推理端点，这允许开发人员在完全托管的基础设施上部署机器学习模型。据 Phamily 的软件工程师 Bryce Harlan[说，在阅读了一个小时的文档后，Phamily 团队能够部署一个具有 Rest-ful API 的 transformer 模型，而这在以前需要一周的开发时间。](https://www.linkedin.com/in/bryce-harlan-38742b98/)

Boudier 估计，客户已经在他们的平台上部署了大约 20，000 个使用人工智能技术的项目。

“前端、后端、移动——这一切都是可行的，因为我们抽象出了所有的机器学习和围绕机器学习的基础设施，所以归根结底，它是一个 REST API，你可以向它发送请求——无论是来自你的前端 [JavaScript](https://thenewstack.io/2022-a-golden-year-as-javascript-moves-to-the-edge/) 还是你的后端，或者来自移动客户端，”Boudier 说。“我们有大量的开发人员和人工智能初创公司正在使用我们的模型和推理端点……来增强面向用户的体验。”

前端和移动 AI 使用的例子包括 [MusixMatch](https://huggingface.co/Musixmatch) ，将歌词匹配到 Spotify 歌曲；[松果](https://huggingface.co/pinecone)，利用机器学习进行语义搜索；Boudier 说，还有一个移动应用程序，可以确保病人遵循医生的处方。

## 简明人工智能词典:定义新模型

除了其产品之外，Hugging Face 还支持一个强大的开源社区，充当所有类型的人工智能模型(超过 12 万个)的免费存储库，以及探索模型做什么和潜在偏见信息的沙箱。

虽然拥抱脸始于自然语言处理，但开发者会在网站上发现两种较新类型的机器学习模型——变形金刚和扩散器。

**变形金刚**型号是由谷歌首创的[巴特型号](https://huggingface.co/docs/transformers/model_doc/bart)。斯坦福大学标记为[基础模型](https://crfm.stanford.edu/)的 Transformer 模型在大型数据集上进行了广泛的训练；例如，互联网数据或研究数据，或者开发者想要使用的任何大型数据集，Boudier 说。他补充说，这些模型可能需要数百万美元的计算能力来训练。例如， [ChatGPT](https://thenewstack.io/5-ways-chatgpt-could-supercharge-chatbots/) 基于基金会模型 [GPT3](https://thenewstack.io/5-ai-trends-to-watch-out-for-in-2022/) ，它是用互联网数据训练的， [NASA 正在与 IBM](https://thenewstack.io/nasa-and-ibm-to-speed-ai-creation-with-new-foundation-models/) 合作，使用 NASA 的海量数据集来建立开源基金会模型，供其他科学家利用。

一旦创建，这些模型提供了一个可以微调的基础，例如，可以使用个人自己的电子邮件归档进一步完善现有的基础模型，以便根据个人的独特需求对其进行更好的分类。

“关于变形金刚最重要的概念是转移学习，这是一个想法，你可以使用大量计算创建一个包含大量数据的大模型，它创建了我们所说的预训练模型，积累了大量知识，”他说。“然后，你可以在此基础上应用迁移学习，轻松地将其应用于更具体的领域、更具体的问题、不同的任务，等等。因此，这是一项更加通用的技术，使重复使用变得简单而重要。”

扩散器是另一种越来越受欢迎的相对新型的模型，这要归功于[稳定扩散器](https://stability.ai/blog/stable-diffusion-public-release)和 [DALL-E 2](https://openai.com/dall-e-2/) 。

“就过程而言，…想象一幅图片，它从一个有噪声的点图像开始，然后通过迭代，模型改进了噪声，使其从输入中变得有意义，”Boudier 解释道。

他说，因此，例如，你可以从一个骑着马在月球上的宇航员的文本输入开始，模型将从一个未定义的随机图像开始，然后迭代，直到一张图片变得清晰，类似于你所要求的。在 Photoshop 里用来做画；他补充说，周二，[谷歌展示了一种新模式](https://google-research.github.io/seanet/musiclm/examples/)，利用扩散从文本中创造音乐。

## 竞争

Boudier 不知道有任何公司与开源模式竞争，并认为拥抱脸的竞争对手是专有公司，如[谷歌](https://thenewstack.io/google-roadmap-flutter-to-integrate-with-javascript-wasm/)、 [AWS](https://thenewstack.io/machine-learning-aws-brings-data-training-to-community-historically-black-colleges/) 和 [OpenAI](https://thenewstack.io/how-open-ai-ruined-my-homework-assignment/) 。

“在所有这些情况下，你都无法接触到模型，所以你不能真正带来自己的模型，你不能改进模型，你不能在自己的环境中运行模型，”他说。

拥抱脸被拿来与 GitHub 进行比较，因为它联合了机器学习社区，就像 GitHub 联合了软件工程师社区一样。但是机器学习模型文件往往很大——它们被称为检查点文件，可以在 100 千兆字节的范围内——所以 GitHub 不是“这项工作的正确工具，”他说。

“通常情况下，当一个研究实验室发布一个新模型时，他们会在 arXiv 上发布论文，在 GitHub 上发布代码，在 Hugging Face 上发布模型、数据集和演示，”Boudier 说。

他说，这个社区被人工智能专家和数据科学家大量使用，越来越多的软件开发人员也在使用。为了帮助开发者学习更多关于模型和如何使用它们的知识，[拥抱脸提供了一个免费的在线课程](https://huggingface.co/course)。

“不要被吓倒，”Boudier 建议开发者。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>