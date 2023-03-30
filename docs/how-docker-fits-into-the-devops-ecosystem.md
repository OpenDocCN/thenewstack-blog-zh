# Docker 如何融入 DevOps 生态系统

> 原文：<https://thenewstack.io/how-docker-fits-into-the-devops-ecosystem/>

对我来说，很难不写 Docker 容器技术，因为有这么多的发展要跟进。所以我会继续张贴我在那里看到的东西。

今晚，我遇到了对 T2 的采访，他是 Docker 的高级工程师，讨论了 Docker 与 DevOps technologies 的契合度。在采访中，他讨论了 Docker 如何适应人们当前使用的工具集，以及何时作为主要或补充工具最有用。

关于如何使用 Docker 没有很深的知识。与[厨师、](https://www.chef.io/products/chef-infra/) [木偶、](http://puppetlabs.com/) [盐](http://www.saltstack.com/community/)或 [Ansible](http://www.ansible.com/home) 如何契合？Petazzoni 说，Docker 不是这些技术的替代品，该组织也不希望它成为替代品。

相反，例如，Docker 像 Puppet 一样抽象了配置管理的复杂性。Shell 脚本变得没有必要。相反，Docker 可用于小型或大型部署:

> 但你不必再过早地进行投资，也不必面对陡峭的学习曲线。而不是说:“我只是要写一些 shell 脚本，因为 Puppet 太复杂了！”可以用 Docker，因为不会比那些 shell 脚本难。不要说，“我不想用 Puppet 来做我正在做的那种小规模的部署”，而是说，“好吧，现在我有一百台服务器，所以使用 Puppet 是有意义的。”你乐于使用它，而不是将其视为负担。

当我在关于配置管理技术的会议上与开发人员和操作人员交谈时，对易用性和简单性的需求已经成为我经常听到的呼声。这些工具相当复杂，管理起来也很复杂。许多问题源于复杂的集成。

> …你必须确保你使用的是相同的发行版，相同的库。确保所有这些环境完全一致可能需要大量的工作。Docker 解决了这个问题，因为你是从一个给定的基本图像开始的，而且它保证在任何地方都是相同的图像。

Docker 使新的堆栈变得更加有形。但是 Docker 并不是万能的。更重要的是，它是向轻量级服务转移的催化剂，轻量级服务比重量级的遗留技术更适用于这个新的堆栈世界。这在 Petazzoni 如何看待 Docker 与 DevOps 产品的契合度中显而易见。

这里有一个关于 Docker 如何诞生的采访第一部分的链接。第三部分将于下周出版。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>