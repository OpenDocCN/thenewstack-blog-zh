# 如何使用协议并开始使用 ActivityPub

> 原文：<https://thenewstack.io/how-to-work-with-protocols-and-get-started-with-activitypub/>

本文强调了针对协议进行编码所需的一些准备工作，并以查看 [ActivityPub](https://thenewstack.io/devs-are-excited-by-activitypub-open-protocol-for-mastodon/) 作为例子来结束本文。我们还浏览了我之前发表的一组关于假设的[去中心化社交媒体模型](https://thenewstack.io/how-to-build-your-own-decentralized-twitter/)的文章。

协议出现在整个计算过程中。如果你在学术上研究过计算，你会记得 [OSI 7 层模型](https://en.wikipedia.org/wiki/OSI_model)，它将 TCP/IP 和 HTTP 放入整个互联网的上下文中。然而，我更感兴趣的是，作为一项工作任务，需要立即着手一项新的协议。

由于术语**协议**和 **API** 有时会相互混淆，我将定义它们通常的含义。认为协议可以提供 API 是完全合理的，但在这种情况下，协议是第一位的。

想象一下，你和隔壁房间的某个人只通过一根小管子相连，并且只能通过滚动彩球来和他们交流。你的第一个观察可能是“但是如果我们两个同时试着把球滚下管道呢？”这就是为什么协议首先被视为一个工程问题。

当然，这个例子中的球代表了一个系统信息。一个协议可以用多种格式进行通信，JSON 就是一个典型的例子。因此，为了读取和写入消息，需要适当的库来将消息格式转换为系统对象。

一个协议通常定义一个更大的系统中的通信，特别是两个子系统之间传递的消息。在大多数情况下，这些系统的实现细节是一个单独的问题——通常留给第三方库来完成。这实质上是首先设计管道。

相比之下，API 将软件系统或库变成了更像自动售货机的东西，它从颜色鲜艳的按钮接收指令，然后在你期望的时间和地点小心、整洁地发出任何输出。

让我们回到舞会上。自然地，当你的管道伙伴想要交流时，你可能不在管道旁，所以你需要一个“注意力”球。因此，向下滚动一个白色的球可能意味着“我要发送一些信息。”当一条消息被传送到管道之后，来自另一个管道伙伴的某种形式的确认也是有用的。

HTTP 可能是目前最广为人知的协议。它并不真正知道连接到管道的系统在做什么，所以它必须竭尽全力做到全面。这方面的线索可以从偶尔被错误实现的大量错误代码中看出。错误代码 **404** 众所周知，它实际上是一个迷因，但它意味着什么呢？

> 找到了服务器本身，但服务器无法检索请求的页面。

请注意，本质上这并不意味着任何事情真的出错了。定义这一点需要管道背后的系统达成一致。类似地，通常返回的状态代码 **200** (或‘OK’)有一些更具体的变化——例如，如果一个请求成功并导致一个新的资源被创建，则应该返回一个 **201** 。当您实现一个协议时，您可能最终要负责处理比您最初设想的更多种多样的结果。

当你在房间里醒来时(这开始听起来像某种非法演奏)，你可能会发现地板上有球，你不知道它们是什么时候或以什么顺序从管子里出来的。正如您所看到的，在一个真实的系统中，对**消息队列**和/或**消息代理**的需求应该是显而易见的。虽然我不认为流行的 RabbitMQ 会在他们的网站上有“保持你的彩色信号球有序”,但这在这种情况下会有所帮助。

## 活动 Pub

抛开我们越来越奇怪的室友，让我们最后来看看一个流行协议的真实例子， **ActivityPub** 。

> ActivityPub 协议是一个基于 [ActivityStreams](https://www.w3.org/TR/activitypub/#bib-ActivityStreams) 的分散式社交网络协议。它提供了用于创建、更新和删除内容的客户端到服务器 API，以及用于传递通知和内容的联邦服务器到服务器 API。

我将利用我之前关于[去中心化社交媒体模型](https://thenewstack.io/how-to-build-your-own-decentralized-twitter/)的帖子作为跳板，浏览一下 [ActivityPub](https://www.w3.org/TR/activitypub/) 协议，并从对白皮书的冷读中评估实现该协议需要考虑的事项。

第一个问题是，我的蛋蛋是什么做的？嗯，有很多关于 JSON 的 URL 和提及，所以很可能设计者依赖于对 HTTP 的一些理解。管道似乎被称为**活动流**。URL 最好被认为是**端点。**

好像我们两个分开的管友现在都叫**演员了。他们有一个收件箱和发件箱，感觉就像是在排队。看看我的项目，我们为每个 tweeter 有一个[标识文件](https://thenewstack.io/how-to-build-your-own-decentralized-twitter/)——activity pub 有一些类似的东西，描述各种端点和 **ActivityStreams** 。**

这是 Alyssa P. Hacker 的记录，见白皮书:

```
{
  "@context":  "https://www.w3.org/ns/activitystreams",
  "type":  "Person",
  "id":  "https://social.example/alyssa/",
  "name":  "Alyssa P. Hacker",
  "preferredUsername":  "alyssa",
  "summary":  "Lisp enthusiast hailing from MIT",
  "inbox":  "https://social.example/alyssa/inbox/",
  "outbox":  "https://social.example/alyssa/outbox/",
  "followers":  "https://social.example/alyssa/followers/",
  "following":  "https://social.example/alyssa/following/",
  "liked":  "https://social.example/alyssa/liked/"
}

```

有趣的是为不同的活动定义了不同类型的端点。

在我们的项目模型中，我们使用 JSON 来存储一条“tweet”，所以我们来比较一下 Alan 的 tweet:

```
{
    "Text":  "Hi there, anyone listening?",
    "Replyto":  0,
    "Time":  1668435369
},

```

以 Alyssa 向 Ben 发布的 ActivityPub 为例:

```
{
    "@context":  "https://www.w3.org/ns/activitystreams",
  "type":  "Note",
  "to":  ["https://chatty.example/ben/"],
  "attributedTo":  "https://social.example/alyssa/",
  "content":  "Say, did you finish reading that book I lent you?"
}

```

通过阅读 JSON，我们可以立即看到,“to”字段可以是一个集合，因此我们可以向多个参与者发布。这也意味着它需要处理代码。我们还注意到，这是从 Alyssa 到 Ben 的直接消息，而不是对话的明确部分(与 Alan 一样，他只是在回复 message-id)。这条消息被设计成首先从 Alyssa 传送到她的服务器，然后从她的服务器传送到 Ben 的服务器，最后到达他的收件箱。

还有一个“类型”字段，它有一个我们需要注意的值“注释”。虽然 JSON 认为这是一个字符串，但我们知道它很可能是一个名词，我们需要将其翻译成更原子的东西。例如，在 C#中我们可能会有:

```
enum  ActivityType  {Note,  Create,  Like,  Article,  Person,  Collection}

```

这些其他术语是在阅读白皮书的其余部分时获得的。这些名词对于为信息的其余部分设置上下文非常有用。

现在还有其他需要注意的地方，因为以后可能需要详细了解。例如，“活动”的定义它是否定义了会影响实现的东西？或者它更像是设计的人性化表达？

我们还需要评估消息的哪些部分是强制性的——这将帮助我们发现错误，以及帮助创建第一个 MVP(最小可行产品)。如果没有必要，也许我们可以省去它。

另一个有趣的比较:ActivityPub 在消息中没有时间戳。这很好，只要我们记得把这个责任转嫁到其他地方。这是我们关注的最后一个地方 ActivityPub 希望实现者处理哪些可能的问题领域？看来，对于实施者来说，重复数据删除肯定是个问题。

即使您打算使用或选择一个预构建的库来处理实现细节，您仍然需要了解总体问题，以便有希望很好地配置它，并有效地运行它。

## 摘要

这里总结了使用协议时需要注意的事项，其中一些我们在上面已经遇到过。对于有经验的开发人员来说，在管道后面工作是一个很好的挑战。

*   您需要熟悉消息将使用的数据格式，以及适当的转换库。
*   与 API 使用的干净的调用/响应开发相反，协议要求对工程概念有更多的理解。
*   使用协议需要对系统中发生的事情有更深的了解，因为完全理解发送和接收的信息是开发人员的责任。
*   为您的项目扩展实现可能需要仔细检查协议没有处理的内容，但是您可能需要以某种方式合并哪些内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>