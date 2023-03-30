# 当心 ChatGPT:莎士比亚式的语言模型

> 原文：<https://thenewstack.io/beware-chatgpt-a-language-model-in-the-shape-of-shakespeare/>

" ChatGPT 是一个大型语言模型."无论这些话被重复的有多频繁，它们都被忽略了，因为我们更希望真正的人工智能存在。相信我们站在友好机器人和安全自动驾驶汽车的最前沿将是令人兴奋的。

但是仅仅因为一个 6 岁的人类小孩可以重复事情，我们通常不会被说服他们值得被倾听。大型语言模型掌握上下文，但不掌握它所代表的文本的含义。

这是一只随机鹦鹉。但是这些笼中鸟的表现却令人吃惊。我们可以看到 ChatGPT 是多么擅长用“y”的形式写“x”，以及有多少老师在抱怨他们的学生交的综合论文的数量。经检查，文本中几乎没有准确性，但形状是好的。

你现在可能应该听说过变形金刚，它们在深度学习模型中发挥了主导作用。理解语言模型仍然是一个学术追求，即使许多[工具是可用的](https://www.youtube.com/watch?v=kCc8FmEb1nY)。

我将会看到一种模拟探索文本结构的底层基础的非常低保真度的方法——不需要接近当前模型的保真度，也不需要使用任何特殊知识。所以让我们从莎士比亚开始。

## **小心三月十五日**

这条短线因其熟悉而具有独特的感觉。这种结构也许不是特别的莎士比亚式的，而且用词也是出自该剧(朱利叶斯·凯撒)。

我们下面这个短代码项目的目标是产生一些无意义的文本，但却是莎士比亚的形式，足以证明挤压结构的技巧并不是真正的智慧。

预言家对凯撒的警告中的词序可能并不重要，但我们可以简单地通过注意词序统计来确定权重。首先，我们将看前面的单词，这样我们就可以记录后面的单词。然后，我们可以利用这一点向前发展，并产生我们捏造的莎士比亚。

我们将按顺序查看两个单词，并尝试“计算”第三个单词。这意味着我们要收集足够多的例子来说明哪些单词最常跟随前一个单词。因此，如果我们考虑“当心 Ides”，我们会注意到“Ides”跟在“the”后面一个单词，“当心”后面两个单词。我随意地使用了两个单词的深度，但是也可以使用三个或更多的单词。我们不仅要看下一个单词，还要看下一个单词的原因是为了确保我们抓住了一点句子结构。

这意味着当我们继续创建无意义的文本时，我们可以问“根据前面的例子，下一个单词应该是什么？”

在我写“+1”和“+2”的地方，我指的是一个在前面，或者两个在前面，我在这里称之为“深度”。

## **首先，准备一个语料库**

十四行诗更容易处理形式，因为它们只是一连串的句子。所以我选择用这些来借鉴。我在网上找到了前 100 首十四行诗，并使用简单的 [regex](https://thenewstack.io/taming-text-search-with-the-power-of-regular-expressions/) 表达式去掉了编号十四行诗之间的换行符和空格，以便生成一个文本文件。莎士比亚并不以重复他自己而闻名——即使在这个小语料库中，他也使用了非常广泛的语言。标点对格律也是至关重要的，我们可以把它作为结构的一部分保留下来。所以我们希望足够多的抄袭能给我们原创的结果。

现在，C#不一定是用于文本处理的正确语言，但是一旦在 Visual Studio 中编写，它就很容易管理。[这里是项目](https://github.com/eastmad/TheNewStack2)。您将看到项目使用的[语料库文件](https://raw.githubusercontent.com/eastmad/TheNewStack2/main/Shakespeare/shakespearecorpus.txt)。

## **什么是代币**

虽然我们这里的食物和饮料是单词，但我们机械地处理它们，很少涉及语法。这是因为我们希望这个结构是由意志塑造的，而不是由我们对英语的了解来塑造的。所以我们认为“the”是一个不同于“The”的实体，因为它出现在句子中的位置。同样地，我们把**当作一种象征，与**【无逗号】的爱分开，尽管我们意识到逗号与这个词是分开的。这就是为什么当我只是在谈论一个词的时候，我会使用“记号”这个术语。****

 ****## **正向参考**

这完全是在我的非常简单的模型中，我们将下一个令牌视为深度 1，将第二个令牌视为深度 2。

请记住，我们对莎士比亚实际上写了什么并不特别感兴趣，相反，什么最符合他的结构偏见。

运行代码时，您可以看到所有“the”的前向引用的一个示例。下面来看看其中的一些

```
'The'  -  {bounteous One  X  1}  {largess Two  X  1}  {lovely One  X  1}  {gaze Two  X  1}  {eyes One  X  1}  {(fore Two  X  1}  {world One  X  2}  {will Two  X  2}  {age One  X  1}  {to Two  X  1}  {perfect One  X  1}  {ceremony Two  X  1}  {painful One  X  1}  {warrior Two  X  1}  {dear One  X  1}  {respose Two  X  1}  {one One  X  2}  {by Two  X  1}  {sad One  X  1}  {account Two  X  1}  {region One  X  1}  {of Two  X  7}  ..

```

你可以这样理解

*   有一个直接跟在“the”后面的单词“bounteous”的例子；即深度 1。这只有在我们开始的时候“The”是第二个词的时候才会考虑。
*   在“the”后面的两个单词后面有两个“will”的例子。只有当“The”是第一个单词时，才会考虑这一点。

它们最初是成对记录的，但当一个令牌重复时，这种情况就会消失。最常见的是深度为 2 英寸。您可以使用一点正则表达式来检查语料库中的所有这些内容。

下面是项目中的代码，它读取语料库文本，然后为语料库中的第一个、第二个单词添加引用，然后转移到下一个单词并重复这个过程，直到文本被使用。

```
string[]?  tokens  =  BackEnd.FileServices.ReadCorpus();

..

for  (int  i  =  2;  i  &lt;  tokens?.Length;  i++)
{
  string currentToken  =  tokens[i];
  ForwardReference.Add(tokens[i  -  2],  ForwardReference.Depth.Two,  currentToken);
  ForwardReference.Add(tokens[i  -  1],  ForwardReference.Depth.One,  currentToken);
}

```

## **做一首十四行诗**

我们从语料库中的任意两个单词开始，让系统选择下一个单词。然后，我们用这个新单词作为第二个单词，旧的第二个单词作为第一个单词，只要我们觉得可以，就这样继续下去。

在第一次运行时，我添加了这些约束:

*   没有重复的单词，除非它们是两个字母或更少
*   与深度为 2 的字相比，深度为 1 的字的偏差为 5:2
*   在 25 个单词后停止，或者如果我们用完了绳子就更少

以上由代码中的常量或`const`**命令控制。**

 **如果没有良好的反馈机制，我们将无法接近 ChatGPT 文本，但是我们会看到什么呢？下面是主循环的代码，准备好了前两个词:

```
..
MakeSonnetWord ms  =  new MakeSonnetWord("A",  "rose");
newwords.Add(ms.firstword);
newwords.Add(ms.secondword);

for  (short  i  =  0;  i  &lt;  MAXWORDS;  i++)
{
    ForwardReference fr  =  ms.EvaluteBestReference(newwords);
    newwords.Add(fr.referencetoken);
    ms  =  new MakeSonnetWord(ms.secondword,  fr.referencetoken);
}

Console.Write($"nNew sonnet! nn {string.Join("  ", newwords)}");

```

从《一朵玫瑰》开始:

```
A  rose might never die,  
But that  I  am not to the world of thy sweet self dost thou art so fair as  a  
look,  
of my

```

这是相当令人愉悦的，尽管我们显然陷入了废话的漩涡。现在让我们以随机数的形式添加一些噪声，这样我们可以在重复之后得到不同的结果:

```
A  rose in the world of thy this self to my love to his  
And you in their of my  
But  I  am thee for

```

这也很好，但显然需要更多的调整，否则它将准确无误地崩溃。可以在定义了`const`**的任何地方进行调整。实际 AI 使用了很多微调整。**

 **最后一个例子，同样的起始词:

```
A  rose in the world of my love to my self and all in my love,  to my  
But that  I  in my verse 
And for

```

这是首相当够折磨人的打油诗。感觉就像一只猴子真的在输入莎士比亚，但它确实显示了捕捉这个结构需要多么少的东西——没有以任何方式接近有用的东西。

我留给你一个适合新吟游诗人的努力，使用两个开始词“智慧”:

```
The intelligence,  of thy love  
And for my self and all my love,  
But thou art the world of my love's  breast,  
where-through plead that

```

好了，现在停止。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>********