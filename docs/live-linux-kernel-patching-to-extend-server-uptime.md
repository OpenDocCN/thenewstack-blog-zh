# 实时 Linux 内核修补可延长服务器正常运行时间

> 原文：<https://thenewstack.io/live-linux-kernel-patching-to-extend-server-uptime/>

在我的日常工作中，我不断收到客户的问题，他们希望了解更多关于使用 Linux 实时内核补丁来延长服务器正常运行时间的可能性。最近人们对 Linux 补丁很感兴趣，有两个项目(有点)在竞争提供这种功能。一个以红帽为首，名为 [kpatch](https://github.com/dynup/kpatch) ，一个以 Suse 为首，名为 [kgraft](https://www.suse.com/promo/kgraft.html) 。

到目前为止，这些工具的技术略有不同。人们至少希望这两个项目能够合作，并从双方创造的创新中挑选出一些。对于我的第一个测试，我决定演示 kpatch。我设计了一个稍微有趣的用例，利用了默认 Fedora 20 内核中的一个漏洞。然后，我成功地让内核“哎呀”了一声，并要求重启。之后，我获取一个源代码补丁，将其构建到一个活动的内核补丁模块中，并指示正在运行的内核加载它。你瞧，漏洞已经被堵住了！听着，妈，不需要重启。

[https://www.youtube.com/embed/Mftc80KyjA4?feature=oembed](https://www.youtube.com/embed/Mftc80KyjA4?feature=oembed)

视频

实时内核补丁总是很有趣，所以我认为新的堆栈阅读器肯定值得这样对待。有什么问题吗？下面给我拍个评论，或者发微博 [@ak_kim0](https://twitter.com/ak_kim0) 。

Ahmed Kamal (@ak_kim0)是 Cloud Niners([www.cloud9ers.com](http://www.cloud9ers.com))的云基础设施总监。Cloud Niners 专注于大规模 Linux 操作、私有云和公共云部署。DevOps 风格的自动化和咨询工作

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>