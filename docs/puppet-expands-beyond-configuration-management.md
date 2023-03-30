# Puppet 扩展到配置管理之外

> 原文：<https://thenewstack.io/puppet-expands-beyond-configuration-management/>

周二，在三藩市的联合广场希尔顿酒店(Union Square Hilton)上，[木偶](https://puppet.com/)展示了它是如何将产品线从配置管理扩展到软件生命周期的。

该公司[推出了一套新产品](https://puppet.com/blog/introducing-puppets-largest-set-product-innovations-ever)，以配合其同名的[配置管理系统](https://github.com/puppetlabs/puppet)面向企业的现有发行。这些新产品包括用于持续集成和持续部署的管道、 [Puppet Bolt](https://puppet.com/products/puppet-bolt) 和用于在特定机器上运行任意配置管理任务的 Puppet Tasks，以及可以执行与审计和跟踪系统控制模式相关的治理和合规性任务的 Puppet Discovery。

Puppet 首席技术策略师 Nigel Kersten 说，虽然 Puppet 新发布的主题是其产品线的重大扩展，但这些公告也是为了模糊传统开发和管理领域之间的界限。当被问及 Puppet 现在是否是一家持续集成/持续部署(CI/CD)公司时，他回答说，“我认为我们看到了这些界限的模糊。它们都很模糊:以任务形式进行配置的配置管理模糊了 CI/CD 的界限。”

## 十年过去了

据 Puppet 的创造者、前系统管理员和工程师 Luke Kanies 所说，Puppet 是出于“恐惧和绝望”而被创造出来的。在经过几家公司后，Kanies 非常渴望工作，并担心十年后世界可能仍在使用 CFEngine 来配置服务器。

最初，Kanies 成为 CFEngine 的最大贡献者之一，甚至将其派生到他自己的版本 CFNG 中。尽管如此，他对自己想要什么，以及他知道其他管理人员需要什么有一个清晰的认识。这个愿景是建立一个系统模型，然后用一个工具在所述系统上实现这个模型。机器、操作系统、软件，这些东西对这个工具来说都不重要:它会处理异构性，如果一个系统上线时因为一个变化出了问题而与模型不匹配，你只需再次运行这个过程，它最终会与模型匹配。

即使没有别的，Puppet 仍然忠实于它最初的愿景，也许是它自己的错。多年来，自动化配置管理的福音传播开来，用户蜂拥至该平台。支持数百种操作系统。随着 DevOps 的普及和自动化的流行，配置管理空间开始远离 Puppet 和它的主要竞争对手， [Chef](https://www.chef.io) 。 [Ansible](https://www.ansible.com/) 也声名鹊起，很快被[红帽](https://www.redhat.com/en)收购，一夜之间给了 Puppet 一个巨大的、资金雄厚的竞争对手。

## 新木偶大师

随着本周新产品的推出，这个难题已经远远超出了配置管理。Puppet 首席建筑师 Deepak Giridharagopal 说，Puppet Discovery 是“基于我们现有技术的核心优势。如果你想以一种幂等的方式管理一件事情——一种安全的方式——第一步是获得你想要管理的事情的当前状态。不要从“这是人们对理想状态的想法”开始，让我们用同样的代码做相反的事情。难道我们不能对一个我们一无所知的系统说，‘一切事物的当前状态是什么？’如果您想要一个现代化的发现工具，光说‘这是网络扫描，这是 IPs’是不够的。从一串数字中你真的能做什么？更有价值的是，如果你可以说，'这是系统，现在我们可以深入所有的系统。Giridharagopal 说:“这是对这些目标进行更有趣的检查。

这与最近傀儡[收购 Distelli](https://thenewstack.io/puppet-will-extend-infrastructure-automation-capabilities-distelli-acquisition/) 相吻合，Distelli 是一家提供管道和集装箱注册的 CI/CD 公司。将该注册表添加到这个新的 Puppet 工具链中，可以确保该公司的企业产品能够清晰地展示整个环境，并帮助这些系统相互跟踪。这还支持在发现过程中发现的跨这些系统的治理、法规遵从性管理和策略实施的制定，傀儡团队期望这将在受监管的市场中赢得许多更大的合同。

一旦机器通过审核， [Puppet Enterprise](https://puppet.com/products/puppet-enterprise) 就可以利用 Puppet Bolt 新的“现在就做”功能，通过基于网络的管理系统中的一系列下拉菜单来实施更改。这些菜单可以由管理员用 Puppet DSL(特定于域的语言)来描述，从而确保没有可能的坏状态可供选择。这也意味着，随着 Puppet Discovery 跟踪指挥链，企业可以立即了解其控制流程的自动化程度。因此，Bolt 不仅仅是对配置市场需求的反应，它还是更广泛的管理平台的推动者。

“我们的方法是模型驱动的、声明性的方法。Puppet 营销和业务发展副总裁[蒂姆·宗卡](https://www.linkedin.com/in/timzonca/)说:“虽然这对于大规模管理全球基础设施来说非常棒，但它需要你知道你想要什么样的模型，以及你希望它看起来是什么样的。”。

这些不断变化的需求也使得在木偶语言中加入动词成为必要。Puppet Tasks 是 Puppet Enterprise 和 Puppet Bolt 的组合，它支持使用这些动词，并使用除 Puppet DSL 之外的语言来支持它们。Giridharagopal 说，“在模型驱动方面，你可以独立编写木偶代码。对于像任务这样的事情，我们想给人们一种不同的方式去做。假设您有一个要配置的数据库:名词会说，‘我’想创建一个如下所示的数据库。动词应该伴随着它。“我想刷新缓存”，或“刷新权限”，或“我想进行模式升级，这是我需要应用的 SQL 脚本。”那些是动词。这是第一阶段。你可以用任何语言写任务，从 Bash 到 Powershell Python，用 Go 或 Rust 编译二进制。"

[主厨](https://www.chef.io/)、[木偶](https://puppet.com/)和[红帽](https://www.openshift.com/)是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>