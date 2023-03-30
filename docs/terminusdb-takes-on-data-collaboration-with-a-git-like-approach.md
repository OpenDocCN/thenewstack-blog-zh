# TerminusDB 采用类似 git 的方法进行数据协作

> 原文：<https://thenewstack.io/terminusdb-takes-on-data-collaboration-with-a-git-like-approach/>

虽然 [git](https://thenewstack.io/git-at-15-how-git-changed-the-way-we-code/) 已经彻底改变了团队在代码上的协作方式，但在数据上的相同级别的协作仍在进行中。爱尔兰初创公司 [TerminusDB](https://terminusdb.com/) 只是致力于创建“数据 git”系统的项目之一。

TerminusDB 的商业和运营主管[Luke fee ney](https://www.linkedin.com/in/luke-feeney/?originalSubdomain=ie)说:“机器学习团队和数据科学团队，即使是在最复杂的组织中，比如亚马逊，也会去云数据仓库，提取一堆他们感兴趣的[CSV](https://www.bigcommerce.com/ecommerce-answers/what-csv-file-and-what-does-it-mean-my-ecommerce-business/)[文件]，然后去那里工作，再也不回去。“因为它是高速数据，数据的变化非常快，所以会有一堆 CSV 到处流动，没有人确切知道最新的是什么。”

“我们希望为人们提供一个灵活的数据中心来存储和分发这些数据，然后协作处理它们。”

### 来自大型欧盟项目

TerminusDB 源于都柏林三一学院的工作。该团队最初名为 DataChemist，由 Kevin Feeney 和 Gavin Mendel-Gleason 领导，从欧盟委员会获得了 400 万欧元的资助，用于建立全球历史数据库的技术架构。这个多学科项目涉及一个研究机构联盟，以汇编所有人类历史的所有政治和社会数据集，然后以机器可读的格式提供它们，使人们能够进行高级分析、历史分析和其他项目。

TerminusDB 的商业和运营主管卢克·费尼(Luke Feeney)说:“我们开始时是一种数据质量层，试图确保良好的数据进入，但这些数据中存在大量的冲突。”要知道，有人说这个政体在公元前 600 年就消失了，还有人说是公元前 632 年。所以能够在数据集中表现不确定性对我们来说非常重要。…我们有一种基于数据类型的不确定性属性，允许它们的不确定性范围，因此我们可以表示数据库中的所有内容。

### 这项技术

TerminusDB 是一个开源的内存图形数据库，像 git 一样存储数据。它允许不同的人同时处理同一个项目的不同版本，使用一整套修订控制特性:分支、合并、挤压、回滚、责备和时间旅行。克隆/派生操作允许将数据移动到您的云或服务器。合并和分支操作允许您混合和匹配数据源，从而大大简化了集成任务。用户可以稍后将他们的工作重新同步回中央终端。

然后，同事可以处理合并的项目，而不必重新构建环境来运行相同的查询。

[https://www.youtube.com/embed/yWMwLhfB1cQ?feature=oembed](https://www.youtube.com/embed/yWMwLhfB1cQ?feature=oembed)

视频

Luke Feeney 解释说:“我们开始构建数据质量层，然后我们做了一个大型的概念验证项目，我们试图将整个波兰经济放在一个图表上，以便我们可以针对它运行高质量的查询，寻找商业数据中的冲突。”。“我们试图在 Postgres 的基础上建立一种数据版本层，我们发现它存在巨大的性能问题。”

“因此，我们在那时建立了数据库的原型。数据库实际上是用 [Prolog](https://www.britannica.com/technology/PROLOG) 编写的服务器，这是一个不寻常的选择。它是一种逻辑编程语言，从不同的角度看待事物。然后我们在一个名为 [HDT](https://github.com/rdfhdt/hdt-cpp) 的 C++库的背面实现。同样，我们发现我们和 HDT 有很多问题。我们遇到了 seg 故障之类的问题，我们在 [Rust](https://www.rust-lang.org/) 中重新实现了存储层。所以我们有一个基于铁锈的存储层用于位操作。我们有一个 Prolog 服务器，它运行查询和查询管理。”它使用 Web 本体语言(OWL)进行模式设计。

大学毕业后，他们想向企业销售大规模图形系统，但他们发现数据管理对我们合作的所有团队来说都是一个大问题。所以他们转向了版本控制的问题。

他说:“我们现在拥有的是一个只附加的数据结构，它使用了一些新的内存管理方法，这样我们就可以非常容易地共享增量。”“所以基本上，我们有一个分布式版本控制数据存储，它通过一个中心链接在一起，这是一个数据 GitHub。”

## 不同的方法

其他致力于为数据创建 Git 的项目包括 [Dolt](https://thenewstack.io/dolt-a-relational-database-with-git-like-cloning-features/) 、 [Pachyderm](https://www.pachyderm.com/) 和 [DVC](https://dvc.org/) 。

Dolt 的 Tim Sehn 描述了 Dolt 和 TerminusDB 如何相交:

Dolt 和 TerminusDB 都是版本化的数据库，您可以对它们进行分支、合并和区分。主要区别在于 Dolt 是标准的关系数据库，而 TerminusDB 是图形数据库。使用 Dolt，您可以与表和 SQL 交互，而使用 TerminusDB，您有节点和边，并且您可以使用自定义查询语言与它们交互。SQL 数据库比图形数据库部署得更广泛。Dolt 可以作为大多数 MySQL 数据库的替代产品，并与 MySQL 客户端一起工作，”他解释道。“我们喜欢 TerminusDB 正在建设的东西，但我们真的没有竞争力。我们在两种不同类型的数据库上提供相同的功能集。”

TerminusDB 和 Pachyderm 最近加入了一个名为[人工智能基础设施联盟](https://ai-infrastructure.org/)的组织，该组织专注于为机器学习构建规范的堆栈。

根据 Luke Feeney 的说法，DVC(数据版本控制)直接使用 git 对数据进行版本控制。“这意味着你可以将数据和代码一起版本化，这在某些情况下很好，但有时你只是想拥有一个数据库，因为你希望能够灵活地查询增量和查询不同的位，”他说。

他说，it 和 Pachyderm 似乎更专注于通过容器对整个管道进行版本控制。

Pachyderm 的联合创始人乔伊·兹维克(Joey Zwicker)说:

“这是一款与 Pachyderm 非常不同的产品，但我们在版本数据方面确实有重叠。Terminus 是一个数据库(它让我想起了 Attic Labs 的 NomsDB ),这极大地限制了它的用例，换来的可能是比 Pachyderm 这样的工具更高的性能和更复杂的关系跟踪。Terminus 似乎非常适合需要查询和存储复杂关系的图形数据，而像 Pachyderm 这样的工具是更通用的数据版本控制系统，更类似于 Git/Github。

“Pachyderm 面临的主要挑战是，对于特定的工作负载，它会更快更好。但它的通用性较差，因为并非所有数据都高度相关。它还要求程序员/数据科学家必须学习一种特定的语言来查询它，而不仅仅是用他们喜欢的任何语言编程。”

Terminus 使用一种基于 datalog 的查询语言，类似于 Datomic、Grakn 和其他数据库使用的语言，它通过 JavaScript 和 Python SDKs 呈现，“但我们试图将学习保持在最低限度，以允许人们只呆在熟悉的环境中，”Luke Feeney 说。

至于 Dolt，Luke Feeney 说，“我们不认为 SQL 是正确的方法。虽然它最初让编码人员感觉更舒服，但最终你要付出的代价是相当可观的。当你处于关系中时，描述数据库的两种状态之间的差异是非常非常复杂的，所以你必须有一个非常复杂的元语言来管理这两种状态之间的差异。在我们的世界中，因为在我们的基础上，都是 RDF 三元组，当我们说两个状态之间的差异时，我们所说的是这些三元组被去掉，这些三元组被加上。这使得一切变得非常简单，成本也更低。”

这个数据库已经有 110，000 次下载，它是在一月份[开源的](https://github.com/terminusdb)。他说，GitHub 等组织正在测试它，爱尔兰大型杂货批发商 [Musgrave Group](https://www.musgravegroup.com/) 正在使用它来运行机器学习管道。

## 接下来

迄今为止，该团队的工作主要集中在 Python 用户上，未来它希望与其他企业软件集成，特别是针对 Excel 用户，Luke Feeney 描述说他们在很大程度上被忽视了。

“我们希望允许 Excel 用户留在他们的环境中，在那里他们可以完成所有工作…所以 GUI 保持不变，但在幕后，他们可以获得现代化的工作流功能，他们可以将他们的更改发送给同事，或者从中央存储库中取出最新版本的 Excel 工作表，然后能够非常非常容易地返回到早期版本，并将所有版本保存在内存中。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>