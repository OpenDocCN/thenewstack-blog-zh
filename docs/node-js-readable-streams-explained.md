# Node.js 可读流解释

> 原文：<https://thenewstack.io/node-js-readable-streams-explained/>

*《溪涧难行》*

…在你之前，很多 Node.js 开发人员，甚至专家都这么说。在写[尾文件](https://www.npmjs.com/package/@logdna/tail-file)的时候和他们一起工作了一段时间后，我发现他们并不是真的很难，只是有很多移动的部分。关于这个主题的 [Node.js 文档](https://nodejs.org/dist/latest-v12.x/docs/api/stream.html)相当分散——这是一个很大的特点——真正重要的细节有时可以在一个非常大的文档中用一句话的几句话来表达。所以，这使得把所有这些放在一起相当困难。

流也是非常有状态的，所以它们如何工作有时取决于它们所处的模式。希望我能解开这篇文章的一些困惑。注意，可写流，甚至文件系统流，对于相同的概念有不同的实现，所以在本文中，我们将讨论实现读流。
[](https://www.linkedin.com/in/darin-spivey/)

[Darin Spivey](https://www.linkedin.com/in/darin-spivey/)

[Darin 是 LogDNA 的高级软件工程师，从事产品架构和性能、高级测试框架以及 LogDNA 的开源项目。当他不埋头写代码时，你会发现他在摆弄他的智能家居技术，和家人一起旅行。](https://www.linkedin.com/in/darin-spivey/)

[](https://www.linkedin.com/in/darin-spivey/)[](https://www.linkedin.com/in/darin-spivey/)

## **什么是流实现？**

可读的实现是一段扩展`Readable`的代码，它是 read streams 的 Node.js 基类。如果您想要一个自定义流而不定义自己的类，也可以简单地调用 [`new Readable()`](https://nodejs.org/dist/latest-v12.x/docs/api/stream.html#stream_new_stream_readable_options) 构造函数。我确信你们中的很多人都使用过从 HTTP `res`处理程序到`fs.createReadStream`文件流的流。然而，一个实现需要尊重流的规则，也就是说，当系统为流情况调用某些函数时，它们会被覆盖。让我们来谈谈其中的一些是什么样子的。

```
const  {Readable}  =  require('stream')

// This data can also come from other streams :]
let dataToStream  =  [
  'This is line 1\n'
,  'This is line 2\n'
,  'This is line 3\n'
]

class  MyReadable  extends  Readable  {
  constructor(opts)  {
    super(opts)
  }

  _read()  {
    // The consumer is ready for more data
    this.push(dataToStream.shift())
    if  (!dataToStream.length)  {
      this.push(null)  // End the stream
    }
  }

  _destroy()  {
    // Not necessary, but illustrates things to do on end
    dataToStream  =  null
  }
}

new MyReadable().pipe(process.stdout)

```

从中可以得出以下几点:

*   当然，打电话给`super(opts)`或者什么都不会起作用。
*   `_read`是必需的，当需要新数据时自动调用。
*   调用`push(<some data>)`将导致数据进入内部缓冲区，当某个东西，比如管道可写流，需要它时，它将被消耗。
*   `push(null)`是正确结束读取流所必需的。
    *   在此之后将发出一个`'end'`事件。
    *   除非在构造函数中设置了`emitClose: false`，否则还会发出一个`'close'`事件。
*   `_destroy`可选用于清理东西。**永不**覆盖破坏；对于这个和`_read`，始终使用下划线方法。

对于这样一个简单的实现，不需要这个类。一个类更适合底层数据资源更复杂的东西，比如 [TailFile](https://github.com/logdna/tail-file-node/blob/ee0389ba34cb2037de776541f800842bb98df6b3/lib/tail-file.js#L22) 。这个特殊的例子也可以通过[构造一个`Readable`内联](https://nodejs.org/dist/latest-v12.x/docs/api/stream.html#stream_new_stream_readable_options) :
来完成

```
const  {Readable}  =  require('stream')

// This data can also come from other streams :]
let dataToStream  =  [
  'This is line 1\n'
,  'This is line 2\n'
,  'This is line 3\n'
]

const myReadable  =  new  Readable({
  read()  {
    this.push(dataToStream.shift())
    if  (!dataToStream.length)  {
      this.push(null)  // End the stream
    }
  }
,  destroy()  {
    dataToStream  =  null
  }
})

myReadable.pipe(process.stdout)

```

然而，这段代码有一个主要问题。例如，如果数据集较大，来自文件流，则此代码重复了节点流的一个常见错误:

*这不考虑背压。*

## **什么是背压？**

还记得我上面提到的内部缓冲区吗？这是一种内存中的数据结构，用于保存流数据块—对象、字符串或缓冲区。其大小由`highWaterMark`属性控制，默认为 16KB 字节数据，或者如果流处于[对象模式](https://nodejs.org/dist/latest-v12.x/docs/api/stream.html#stream_new_stream_readable_options)，则为 16 个对象。当通过可读流推送数据时，`push`方法可能会返回`false`。如果是，这意味着`highWaterMark`接近或已经超过，这称为[背压](http://nodejs.org/en/docs/guides/backpressuring-in-streams/)。

如果发生这种情况，由实现决定停止推送数据并等待`_read`调用的到来，这意味着消费者准备好接收更多数据，因此`push`调用可以恢复。这是很多人无法正确实现流的地方。以下是一些关于通过读取流推送数据的技巧:

*   只要考虑背压，就不必等待调用`_read`来推送数据。可以持续推送数据，直到达到背压。如果数据量不是很大，有可能永远达不到背压。
*   在数据流处于[读取模式](https://nodejs.org/dist/latest-v12.x/docs/api/stream.html#stream_two_reading_modes)之前，不会消耗缓冲器中的数据。如果正在推送数据，但是没有`'data'`事件和`pipe`，那么如果数据大小超过默认的缓冲区大小，则肯定会达到背压。

这是摘自`TailFile`的一段话，它从底层资源读取数据块，直到达到背压或者所有数据都被读取。出现背压时，存储流，并在调用`_read`时恢复读取。

```
async _readChunks(stream)  {
    for await  (const chunk of stream)  {
      this[kStartPos]  +=  chunk.length
      if  (!this.push(chunk))  {
        this[kStream]  =  stream
        this[kPollTimer]  =  null
        return
      }
    }
    // Chunks read successfully (no backpressure)

    return
  }

  _read()  {
    if  (this[kStream])  {
      this._readChunks(this[kStream])
    }
    return
  }

```

## **总之**

还有更多的内容，尤其是当您谈到写流时，但是概念都是相同的。如上所述，流的信息是丰富的，但是分散的。

当我写这篇文章时，我找不到我学到的'`push`可以被连续调用'的地方，但相信我，这是一个东西，即使下面的背压文档总是建议等待`_read`。事实是，根据您试图实现的内容，代码会变得不那么清晰，但是只要遵循背压规则，并根据需要覆盖方法，那么您就在正确的轨道上！

## **有用的资源**

这些是我真正从中学到一些东西的文件。看看他们！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>