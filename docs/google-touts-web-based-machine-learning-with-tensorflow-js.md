# 谷歌用 TensorFlow.js 推销基于网络的机器学习

> 原文：<https://thenewstack.io/google-touts-web-based-machine-learning-with-tensorflow-js/>

[TensorFlow.js](https://www.tensorflow.org/js) 是一个 JavaScript 库，用于在浏览器和 Node.js 上训练和部署机器学习(ML)模型。它由谷歌在近五年前[推出](https://blog.tensorflow.org/2018/03/introducing-tensorflowjs-machine-learning-javascript.html)，但由于在编程中使用 ML 的实践，近年来它的受欢迎程度有所增加——这是目前席卷科技行业的[生成式人工智能](https://thenewstack.io/generative-ai-how-companies-are-using-and-scaling-ai-models/)趋势的一部分。

为了了解更多关于 TensorFlow.js 以及 web 开发者如何在他们的项目中使用它，我采访了 Google Web ML 开发者关系团队的负责人 Jason Mayes。“Web ML”是一个更广泛的术语，基本上意味着在浏览器内部(或在 Node.js 上)使用 ML。但是 Mayes 的主要职责是 TensorFlow.js 团队，所以我首先向他询问了 ML 在 web 上的主要用例。

## 为什么在网络上做 ML？

首先，他提到了隐私。一个常见的用例是处理 ML 工作负载中的传感器数据，例如来自网络摄像头或麦克风的数据。Mayes 说，使用 TensorFlow.js，“这些数据都不会传到云端[……]所有这些都发生在设备上、浏览器中、JavaScript 中。”他说，出于这个原因，TensorFlow.js 正在被从事远程医疗的公司使用。

另一个隐私用例是人机交互。“利用我们的一些模型，我们可以进行身体姿态估计，或身体分割，面部关键点估计，诸如此类的事情，”Mayes 说。

根据 Mayes 的说法，更低的延迟是在浏览器中进行 ML 的另一个原因。“其中一些型号在浏览器中每秒可以运行超过 120 帧，比如说在 NVIDIA 1070 上，”他说。“因此，这是一种(老一代)显卡，但它仍在推动一些像样的性能。”

成本是他的第三个原因，“因为你不必在云中雇佣和运行昂贵的 GPU 和 CPU，并让它们全天候运行来提供服务。”

“人们来找我们的第四个原因是 JavaScript，”他说，并指出这种语言显然很受欢迎。“以前，TensorFlow 的目标是学者和研究人员……这类东西在 Python-land 中。这很好，没有错！但我认为，接受 JS 方面的东西可以向比以往更多的人开放机器学习——更多的创意人员、艺术家和音乐家开始在 JS-land 使用我们。”

## JS ML 与 Python ML 的比较

然而，这就引出了一个问题，TensorFlow.js 与在其更熟悉的 Python 环境中使用 TensorFlow 相比如何？

“我刚才给你的所有好处在服务器端几乎都不可能实现，”Mayes 回答道。“即使你不想在客户端运行，我们也可以在服务器端的后端运行 Node.js。选择 Node.js 而不是 Python 的原因是，尽管 Node 和 Python 只是 C++的原始 TensorFlow 的包装器，但 JavaScript 的即时编译器可以加速模型执行的预处理和后处理部分。”

他提到，领先的 NLP 服务公司之一 HuggingFace 在 TensorFlow.js 中运行其 ML 工作负载，以获得速度优势。

“Python 实际上在运行方面效率不高，”他继续说道。“这对学术界和尝试新事物都有好处——它有许多现成的库可供使用。但我认为，随着时间的推移，我们将在自己的社区中复制同样的东西，您会看到性能优势。”

作为这方面的另一个例子，他提到了 LinkedIn。“如果你用手机访问 LinkedIn 的网页，那实际上是由运行在 Node 后端的 TensorFlow.js 模型提供的，”他说。这导致了“比他们的 Python 等效模型高 15%的性能增益，这意味着他们仅仅这样做一个月就节省了数百万美元。”

## 速度更快:WebGL 和 WebAssembly

与许多其他领先的 web 应用程序一样，TensorFlow.js 正在利用最新的硬件加速技术。WebGL 和 WebAssembly 都在生产，而 WebGPU 在测试。

“我们让 WebGL 做显卡加速，”他解释道。“本质上，使用纹理和着色器来进行数学运算——这有点麻烦，但很有效。此外，我们还让 WebAssembly 在 CPU 上运行得更快。我们也有新出现的 WebGPU 标准，它目前在 Chrome Canary 和其他浏览器中处于领先地位，但最终，它将成为浏览器中使用的东西。我认为我们在 WebGPU 中看到了大约 2 倍以上的性能[增益]——请记住，使用 WebGL，我们现在已经每秒获得数百帧。”

## 关于 Web ML 的更多信息

TensorFlow.js 显然是谷歌主要的基于网络的 ML 工具，但我问 Mayes“网络 ML”这个大术语下还有什么？

“因此，谷歌显然在 ML 上投入了大量资金，从我的角度来看，在 Web ML 方面工作，它为我们的(ML)生态系统提供了一个独特的卖点——如果你愿意的话……例如，目前还没有 PyTorch.js，”他说，指的是 Meta 的 ML 平台。

谷歌为机器学习提供了梅斯所说的“网络之路”，“研究人员和其他人可以接受，以获得我们之前谈到的那些好处。”

他还与“[谷歌的]其他团队合作，这些团队可能会涉及基于网络的机器学习部署，比如也能在网络浏览器中运行的 MediaPipe 模型。”他引用了一个名为 [MediaPipe](https://mediapipe.dev/) 的开源项目，在“直播和流媒体”中使用 ML。

## 未来增长

据 Mayes 称，TensorFlow.js 的年增长率为“3 倍”。随着人工智能和人工智能应用程序越来越受欢迎，它只会越来越大。事实上，就在本周，谷歌自己发布了 ChatGPT 的竞争对手 Bard。我问 Mayes 他认为像 Tensorflow.js 这样的基于网络的 ML 工具会有多大？

“我认为 Web ML 是真正的 Web3，”他说，呼应了他一直在社交媒体上使用的一句口头禅[。“我并不是说 crypto 不好或什么的，但我认为[……]它就像一个青少年现在试图找到自己。我认为 Web ML 现在可以对行业[和]公司*产生影响*](https://twitter.com/jason_mayes/status/1616317718193647616)

“我相信，如果我们继续以 3 倍的速度增长，我们将成为 TensorFlow 生态系统中未来最广泛使用的 ML 形式。这是我个人的信念。但如果我们继续向上增长，我看不出有何不可——因为现在有更多的 JS 开发者。”

为了保持这一势头，梅斯说，谷歌“一直在寻找有趣的模型，我们可以从谷歌研究移植到网络上，使其更容易使用。”

如果你是一个对学习更多基于网络的 ML 感兴趣的开发者，看看 Jason Mayes 的这个[系列教程](https://www.youtube.com/playlist?list=PLOU2XLYxmsILr3HQpqjLAUkIPa5EaZiui)。

[https://www.youtube.com/embed/TuYbgZ59Kpg?feature=oembed](https://www.youtube.com/embed/TuYbgZ59Kpg?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>