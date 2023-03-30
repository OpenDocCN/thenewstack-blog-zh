# 从 Python 代码库迁移后，Dropbox 开源 Go 库

> 原文：<https://thenewstack.io/dropbox-open-sources-go-libraries-following-migration-from-python-code-base/>

像许多公司一样，Dropbox 已经开始采用 Go 编程语言。昨天，公司[宣布](https://tech.dropbox.com/2014/07/open-sourcing-our-go-libraries/)它是 o pen 采购其图书馆，以帮助更广泛的社区建立大规模生产系统。

大约一年前，Dropbox 开始将其性能关键型系统从 Python 中迁移出来。该公司采用 Go 以更高效的方式扩展其系统。从那以后，该公司已经将大部分基础设施转移到了 T4。但是在这个过程中，它面临着一个关于 Go 的问题，这个问题更多的反映了这种编程语言的年轻。

Go 没有 Dropbox 构建更大系统所需的深度库。为了解决这个问题，Dropbox 团队开始构建自己的库，提供更好的抽象，比如连接管理和 memcache 客户端。

正如李雅达所描述的那样，以下是它为启动这一努力而提供的内容:

*   [缓存](https://godoc.org/github.com/dropbox/godropbox/caching):为构建缓存层提供一个通用的抽象。
*   [错误](https://godoc.org/github.com/dropbox/godropbox/errors):增强标准错误接口，公开堆栈跟踪信息。
*   [数据库/sqlbuilder](https://godoc.org/github.com/dropbox/godropbox/database/sqlbuilder) :允许开发者以编程方式生成 sql 语句。
*   [memcache](https://godoc.org/github.com/dropbox/godropbox/memcache) :实现了一个全功能的 memcache 客户端库，支持连接池和灵活的分片。
*   [net2](https://godoc.org/github.com/dropbox/godropbox/net2) :增加连接管理功能。
*   (我个人最喜欢的是， [hash2](https://godoc.org/github.com/dropbox/godropbox/hash2) ，它包含了一个空间高效的基于置换的一致性哈希算法)

Dropbox 表示将继续扩展其使用的库，并在 GitHub 上公开提供这些库。这些是 Dropbox 将在内部使用的相同库。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>