# 本周编程:Golang 中泛型的时代终于到来了吗？

> 原文：<https://thenewstack.io/this-week-in-programming-has-the-time-finally-come-for-generics-in-golang/>

围绕[将泛型](https://thenewstack.io/this-week-in-programming-specifically-generic/)添加到 Go 编程语言的[争论](https://thenewstack.io/week-programming-go-2-0-question-complexity/)已经[持续](https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/)多年了，经常遇到很多阻力，但是现在看起来[一个提议](https://go.googlesource.com/proposal/+/refs/heads/master/design/go2draft-type-parameters.md)终于得到了更大的 Go 社区的一些支持和[普遍接受](https://twitter.com/bradfitz/status/1273341443172478978)——这让一些参与者非常惊讶。

本周由 [Golang](https://golang.org/) 团队成员 [Ian Lance Taylor](https://research.google/people/author37504/) 和 [Robert Griesemer](https://github.com/griesemer) 撰写的博客文章《展望[仿制药的下一步》中介绍，近一年来](https://blog.golang.org/generics-next-step)关于该主题的第一次更新解释说，之前提交反馈的[仿制药设计草案](https://go.googlesource.com/proposal/+/refs/heads/master/design/go2draft-contracts.md)已经过改进，产生了[更新的设计草案](https://go.googlesource.com/proposal/+/refs/heads/master/design/go2draft-type-parameters.md)。作者总结了这两种方案的主要区别:

最大的变化是我们放弃了合同的想法。契约和接口类型之间的区别令人困惑，所以我们正在消除这种区别。类型参数现在受接口类型的约束。接口类型现在被允许包含类型列表，尽管只是在作为约束使用的时候；在以前的设计草案中，类型列表是合同的一个特征。更复杂的情况将使用参数化接口类型。

目前，该团队已经推出了一个实验工具,通过将泛型代码翻译成普通的 Go 代码,“允许人们键入检查并运行使用设计草案中描述的泛型版本编写的代码”。它的目的是让用户感受到，如果被接受的话，所提议的设计将会如何工作，并且他们会注意到，如果这样的话，它将会以不同的方式实现。

至于提案本身，它提供了几个层次的细节，从摘要到高层次的概述，再到你可能从这样一份文件中期待的全部细节。与 Go 的一切一样，该设计旨在完全向后兼容 Go 1，作者指出“由于术语泛型在 Go 社区中被广泛使用，我们将在下面使用它作为一种速记，表示采用类型参数的函数或类型。不要将本设计中使用的术语泛型与其他语言中的相同术语混淆，如 C++、C#、Java 或 Rust 它们有相似之处，但并不相同。”

该团队表示，像往常一样，他们正在寻找来自 Go 社区的反馈，最好的方法是使用[golang-nuts@googlegroups.com](mailto:golang-nuts@googlegroups.com)邮件列表。在这项工作中，他们希望了解两件主要的事情:

“首先，泛型代码有意义吗？是不是感觉像 Go？人们会遇到哪些惊喜？错误信息有用吗？

第二，我们知道很多人说过 Go 需要泛型，但是我们不一定知道到底是什么意思。这个设计草案以一种有用的方式解决了这个问题吗？如果有一个问题让你想到‘如果 Go 有泛型我就能解决这个问题’，那么你在使用这个工具时能解决这个问题吗？"

## 本周的节目中

*   **Go 包库开始开源:**在我们继续之前，该团队还在本周宣布 [pkg.go.dev 现在开源](https://blog.golang.org/pkgsite)，并接受贡献。对于那些有兴趣参与的人来说，这个库位于[go.googlesource.com/pkgsite](https://go.googlesource.com/pkgsite)，镜像到[github.com/golang/pkgsite](https://github.com/golang/pkgsite)，鼓励你阅读[投稿指南](https://go.googlesource.com/pkgsite/+/refs/heads/master/CONTRIBUTING.md)。目前，设计问题是接下来要解决的首要问题，包括更具凝聚力的搜索和导航体验。
*   **GitHub 获得“超级 Linter”:**GitHub 已经[推出了它的“一个 Linter 来统治所有人”](https://github.blog/2020-06-18-introducing-github-super-linter-one-linter-to-rule-them-all/),[GitHub 超级 Linter](https://github.com/github/super-linter) ，它最初是在内部构建的，以保持其自己的文档和代码的一致性。该团队已经开源了该工具，它有助于防止损坏的代码被上传到主分支，建立跨多种语言的编码最佳实践，建立代码布局和格式的指南，并自动化该过程以帮助简化代码审查。超级 Linter 本身被打包到一个 Docker 容器中，由 GitHub Actions 调用，允许 GitHub.com 上的任何存储库调用它。要了解全部细节，请查看 [README.md](https://github.com/github/super-linter/blob/master/README.md) 。

*   **Azure 提供机器学习的免费课程和奖学金:**微软 Azure 与 Udacity 合作[宣布了 Azure 机器学习奖学金和课程](https://azure.microsoft.com/blog/announcing-azure-machine-learning-scholarships-and-courses-with-udacity/)，称这将有助于满足对人工智能(AI)和数据科学角色不断增长的需求。免费的入门课程基于 Azure Machine Learning，使用 Azure Machine Learning 的自动化 ML 和拖放功能提供低代码体验。这些公司还将提供一个新的机器学习纳米学位项目，在该项目中，学生将使用 PyTorch、TensorFlow、scikit-learn 和 ONNX 等工具和框架来构建和部署 ML 解决方案。免费入门课程中的前 300 名学生将获得纳米学位项目的奖学金，更多详情请访问[课程页面](https://aka.ms/udacityAML)。
*   **AWS 为 Lambda 函数添加了 EFS:**AWS 推出了用于 Lambda 函数的共享文件系统[，它能够“挂载一个](https://aws.amazon.com/blogs/aws/new-a-shared-file-system-for-your-lambda-functions/)[亚马逊弹性文件系统(EFS)](https://aws.amazon.com/efs) ，这是一个可扩展的弹性 NFS 文件系统，在多个可用性区域(AZ)内和跨多个可用性区域(AZ)存储数据，以实现高可用性和持久性。”该特性将允许您在 Lambda 函数的所有并发执行环境中存储和共享数据，并从多个函数访问同一个 EFS 文件系统。用户还将能够与[亚马逊弹性计算云(EC2)](https://aws.amazon.com/ec2/) 实例、使用[亚马逊 ECS](https://aws.amazon.com/ecs/) 和 [AWS Fargate](https://aws.amazon.com/fargate/) 的容器化应用以及本地服务器共享相同的 EFS 文件系统。

*   **Flash 即将停产:** SDTimes 写道 [Adobe 提醒其用户，Flash 的生命周期将于 2020 年底结束](https://sdtimes.com/softwaredev/adobe-reminds-users-end-of-life-for-flash-is-coming-up/)，该公司将停止分发和更新。我不知道你是怎么想的，但我很高兴我对 Flash 的追求在大约 15 年前就结束了——Flash 的真正流行也是如此，因为 SDTimes notes 是随着不支持 Flash 的 iPhone 的发布而开始的。Adobe 在 2017 年宣布结束 Flash back，引用了 HTML5、WebGL 和 WebAssembly 等开放标准。在其 [Flash Player 生命周期结束](https://www.adobe.com/products/flashplayer/end-of-life.html)页面上，Adobe 表示，它不仅将删除所有版本的下载，而且“基于 Flash 的内容将在 EOL 日期后被阻止在 Adobe Flash Player 中运行。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>