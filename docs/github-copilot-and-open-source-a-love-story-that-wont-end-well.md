# GitHub Copilot 和开源:不会有好结局的爱情故事？

> 原文：<https://thenewstack.io/github-copilot-and-open-source-a-love-story-that-wont-end-well/>

[](https://www.linkedin.com/in/sasha-medvedovsky-10b2381)

[Sasha medvedevsky](https://www.linkedin.com/in/sasha-medvedovsky-10b2381)

[Sasha 是一名拥有 20 多年经验的软件工程师，也是提供开源源代码控制管理软件的 Diversion 的联合创始人。他已经经历了足够长的时间，目睹了编程语言和开发工具的演变。他热衷于利用当前的技术来构建开发人员生产力和协作的下一代工具，以创造一个软件开发更快、更轻松的世界。](https://www.linkedin.com/in/sasha-medvedovsky-10b2381)

[](https://www.linkedin.com/in/sasha-medvedovsky-10b2381)[](https://www.linkedin.com/in/sasha-medvedovsky-10b2381)

GitHub 已经成为软件开发世界的重要组成部分，尤其是开源软件。它为开源项目提供免费托管服务(几年前，Apache Software Foundation 将其整个运营转移到 GitHub 中)，并在将开源 git 转变为现在流行的源代码控制管理(SCM)系统中发挥了重要作用。

然而，随着[软件自由保护协会](https://techcrunch.com/2022/07/01/open-source-developers-urged-to-ditch-github-following-copilot-launch/) (SFC)加入[自由软件基金会](https://www.fsf.org/blogs/licensing/fsf-funded-call-for-white-papers-on-philosophical-and-legal-questions-around-copilot)的建议，在 [GitHub Copilot](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/) 的创建问题上与 GitHub 断绝关系，这种合作现在似乎突然而丑陋地结束了。

GitHub 最近商业化的 Copilot 产品(直到最近都是免费的)提供了人工智能驱动的代码合成/自动完成，建立在 GitHub 托管的数百万开源项目的代码来源上。不用说，并非所有开源项目都是平等的，有许多不同的许可证(了解更多关于 [OSS 许可证](https://opensource.org/licenses))，其中一些不支持代码的重用或“版权所有”，尽管在 GitHub 上可以公开获得。

> 的确，使用代码来训练一个人工智能模型与简单地按原样使用代码有些不同。但是难道不应该至少咨询一下代码的创造者是否同意这样使用他们的作品吗？

对于许多开源开发者来说，这构成了对他们作品的未授权使用，并且违背了他们的信任。显然，如果不从 GitHub 获取数百万个代码样本，Copilot 就无法工作，所以可以肯定地说，开源代码是它不可或缺的一部分。此外，Copilot 创建的任何代码都可以被视为这种开源代码的衍生物(在某些情况下，开源代码的完整片段可以进入闭源代码库)。

的确，使用代码来训练一个人工智能模型与简单地按原样使用代码有些不同。但是难道不应该至少咨询一下代码的创造者是否同意这样使用他们的作品吗？

如果最近 GitHub 和开源组织之间的分离看起来令人惊讶，那也不应该。它确实源于目标和理想的错位。

## GitHub 是一个商业组织

从一开始，GitHub 就是一个将开源软件(git)转化为商业的商业组织。虽然这样做没有错——许多公司已经通过开源技术的商业产品建立了繁荣的业务——但我们必须不要混淆，并认为 GitHub 是一个开源公司或项目。都不是。这种混乱在于它的商业模式，在这种模式下，生产级的托管 git 向商业组织收费提供，而对开源项目免费。

就像有人说过的，“如果产品是免费的，你就是产品。”这句话用在 GitHub 身上再恰当不过了。2018 年[微软以 75 亿美元收购 GitHub](https://techcrunch.com/2018/06/04/microsoft-has-acquired-github-for-7-5b-in-microsoft-stock/) 大家普遍的理解是，(2018 年的)高价不是为了 GitHub 的技术(还是那句话，它没有开发 git，竞争对手很多，比如 BitBucket 和[git lab](https://about.gitlab.com/?utm_content=inline-mention))；而是为了它的开发者社区，当时有 2800 万人。

如果微软为 OSS 社区付费，微软最终会利用这个社区来盈利。微软是一个有股东的商业实体，有义务赚取尽可能多的利润。副驾驶就是一个完美的例子。微软拥有 GitHub 和 [OpenAI](https://openai.com/) 的大量股份，OpenAI 是一家训练 Copilot 人工智能模型的人工智能公司。这种合作意义重大，可以总结为:他们拥有世界上所有最流行的 OSS 项目，以及令人惊叹的人工智能能力。利用协同效应制造商业上成功的产品是有意义的。

这种思路只有一个问题:*托管代码并不意味着微软拥有代码*。这不是该公司第一次做出这种错误的假设。

## Marak faker.js 的惨败

最近发生的一次说明性交流指出了潜在的危险。

一个名为 [Marak](https://mobile.twitter.com/marak) 的开发者故意破坏了他的开源 [Faker](https://fakerjs.dev/) 模拟数据生成器的代码，因为他声称[觉得他的工作](https://mobile.twitter.com/marak/status/1479200803948830724)吃力不讨好。他抱怨他的热门项目缺乏资金，包括被数百家公司使用的 Faker。

这打开了谁真正拥有开源代码的整个潘多拉魔盒。如果公司在生产中使用代码会怎么样？开发人员可以直接破解代码…就这样？

GitHub 参与进来，恢复了修改，[拒绝马拉克访问他自己的项目](https://javascript.plainenglish.io/open-source-a-horror-story-c14caba386a8)(大约 100 个)。

[NPM](https://www.npmjs.com/) (顺便说一句，也是微软所有)也将他的回购恢复到以前的版本——有效地控制了他的代码。

想象一下这种情况:一个程序员创建了一个非常有用的开源项目。他们已经为数百家公司免费维护和提供了它。然后他们决定做出公司不喜欢的改变。然后微软(通过 GitHub 和 NPM)接管了他们的代码库并恢复了他们的变更。

这看起来像是微软理解开发者拥有代码，还是他们认为微软拥有代码？

## 结论

我认为开源运动不应该切断与商业组织的所有联系，或者停止使用商业产品。合作是好事。这不是零和游戏，它有助于造福整个人类。

但是界限要明确。如果开发者不希望他们的代码被用于商业应用，他们应该被赋予拒绝的权利。如果他们同意，那就没有问题。但是，公司(无论是微软、谷歌还是亚马逊网络服务公司)不应该认为，如果他们免费提供一些东西，他们就可以得到其他东西作为回报。

在我共同创立的公司 [Diversion](https://diversion.dev/) ，我们开发了自己的 SCM。我们计划将它作为开源(在我们自己的平台上，而不是在 GitHub 上)发布，我们希望它对数百万开发者有用。

我们还将为开源和独立开发者提供免费托管，作为我们对那些为全人类的进步付出时间和努力的了不起的人的感谢和回馈，而不要求任何回报。

鉴于这些最近的发展，我觉得有必要作出承诺:我们在此保证，尊重软件创作者的许可协议，不以他们不同意的方式使用他们的代码。

对我来说，这是不言而喻的；但显然，这需要明确地说出来。

*注:[沙隆·齐兹曼](https://thenewstack.io/author/sharone-zitzman/)对本文有贡献。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>