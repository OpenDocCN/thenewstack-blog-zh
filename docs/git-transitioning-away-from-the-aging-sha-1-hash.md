# Git 从老化的 SHA-1 哈希中脱离出来

> 原文：<https://thenewstack.io/git-transitioning-away-from-the-aging-sha-1-hash/>

无处不在的 git 软件版本控制系统的开发者宣布他们现在开始从 T2 SHA-1 哈希算法过渡到 T3。

这种转变将被证明是一个挑战，因为 SHA-1 自从 [Linus Torvalds](https://github.com/torvalds) 最初在 2005 年开发版本系统以来就已经是 git 的一部分了。Git 使用 SHA-1 生成的[哈希](https://techterms.com/definition/hash)来识别修改并保护代码免受破坏。不幸的是，在代码库中发现的一系列漏洞[削弱了 SHA-1 的基础，并被认为已经崩溃。事实上，远离 SHA-1 的主要原因之一是哈希算法的糟糕状态可能会被用来危害 git 存储库。](https://www.computerworld.com/article/3173616/the-sha1-hash-function-is-now-completely-unsafe.html)

换句话说，这种过时的加密哈希函数不再被认为是安全的。根据[官方 Git 哈希函数过渡文档](https://github.com/bk2204/git/blob/transition-stage-4/Documentation/technical/hash-function-transition.txt)，SHA-1 的不安全已经为人所知有一段时间了。该文件称，“随着时间的推移，安全研究人员已经发现了 SHA-1 的一些漏洞。2017 年 2 月 23 日[粉碎攻击](https://shattered.io)演示了一次实际的 SHA-1 哈希碰撞。”

## 为什么这么有挑战性？

有人会认为这只是将 git 移植到更新、更安全的散列算法的一种简单方式。不幸的是，情况并非如此。为什么？Git 存储了很多对象。每次对一个对象进行哪怕是最轻微的更改，都会创建一个新的 SHA-1 哈希，然后该对象会以不同的名称存储。因为这是一个版本控制系统，这意味着每一个对象都被保存。

现在，想象一下将存储在 git 上的每个对象的总和迁移到一个新的散列算法中。一个 git 存储库可能有数千个对象。2018 年，git 上有超过 1 亿个存储库。再加上提交也有 SHA-1 散列，迁移的任务变得非常艰巨。

但是随着其他开发者(比如 Mozilla 的开发者)已经离开 SHA-1，迁移的时间已经过去了。

## 新的散列

Git 计划从 SHA-1 迁移到 SHA-265。这将发生在所有的存储库，显然将分阶段完成。根据迁移文档，“默认情况下，Git v2.13.0 和更高版本随后转移到一个加固的 SHA-1 实现，该实现不容易受到破坏性攻击。”当然，这不足以确保存储在 Git 上的对象的安全性。因此迁移到新算法。

Git 共享的一些过渡目标包括:

*   不需要 git 之外的任何一方采取行动。
*   SHA-256 存储库可以与 SHA-1 git 服务器通信(用于推/取)。
*   用户可以选择 SAH-1 或 SHA-256 标识符。
*   新的签名对象将使用新的、更强的哈希函数。
*   允许完全脱离 SHA-1(包括删除本地元数据，如果不再需要与 SHA-1 兼容)。
*   对象格式保持了简单性和一致性。
*   创建存储库转换工具。

目前，过渡没有时间表或截止日期。这个计划最初是由 git 开发人员 Brian Carlson 在 2017 年提出的。关于这个过渡的工作已经进行了一段时间，代码现在处于 alpha 阶段。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>