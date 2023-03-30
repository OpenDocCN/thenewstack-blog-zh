# Python 中的 DeepL 语言翻译 API 入门

> 原文：<https://thenewstack.io/getting-started-with-the-deepl-language-translation-api-in-python/>

[](https://www.linkedin.com/in/danielrjones1/)

 [丹尼尔·琼斯

丹尼尔·琼斯是 DeepL 的开发者倡导者，致力于帮助其他开发者使用 DeepL API 创造伟大的东西。他拥有机电一体化工程背景，以及使用激光雷达进行自动驾驶的物体感知。2013 年，他从新西兰搬到了德国汉堡。](https://www.linkedin.com/in/danielrjones1/) [](https://www.linkedin.com/in/danielrjones1/)

如今几乎所有东西都有一个 API，语言翻译也不例外。在本教程中，我们将向您展示如何使用我们官方的[开源 Python 客户端库](https://github.com/DeepLcom/deepl-python)开始使用 DeepL 语言翻译 API。

在此之前，我们将回答几个问题:什么是 DeepL，语言翻译 API 的用例是什么？

DeepL 是我们的机器翻译公司，其使命是使用人工智能消除世界范围内的语言障碍。我们可能不是唯一的语言翻译 API，但我们感到自豪的是，根据盲测，我们在全球范围内获得了一些最佳翻译质量。如果你想了解我们，我们的[网络翻译](https://www.deepl.com/translator?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)是一个很好的开始。

这篇文章的其余部分将关注我们的 API，它支持 24 种源语言和目标语言，并使开发人员能够将翻译直接构建到他们的产品中。

像 DeepL 这样的 API 的常见用例包括但不限于:

*   网站翻译，尤其适用于电子商务公司或内容目录频繁变化的出版商
*   通过聊天应用或客户服务平台进行跨语言交流，内容由用户生成，需要即时翻译
*   构建在公司内部使用的定制文档翻译工具(除了文本，DeepL API 还允许您翻译 Microsoft Word、PowerPoint、HTML 和纯文本文档)

让我们开始吧。

## 第一步

 [迈克·温特斯

Mike Winters 在过去的七年里一直在 Apache Flink、Camunda、Garden.io 和现在的 DeepL 等产品背后的公司担任产品和社区管理职务。他花了大量时间思考和写作新兴技术对各种形式和规模的组织的影响。他是俄亥俄州人，目前居住在德国柏林。](https://www.linkedin.com/in/wints/?originalSubdomain=de) 

本教程旨在让你可以免费跟随——你只需要先[创建一个 DeepL API 帐户](https://www.deepl.com/pro?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial#developer),这样你就可以获得认证密钥(注意:此时，这些国家的用户可以创建 DeepL API 免费和专业帐户)。

我们选择在本教程中坚持基础知识，目标是介绍我们的语言翻译 API 的可能性，并希望激发一两个关于如何将它应用到您的用例中的想法。

我们将包括本教程每一步所需的代码片段，但在您工作时，您可能希望在单独的选项卡中打开几个页面:

*   Python 客户端库的 [GitHub repo(自述文件包括 Python 库的文档以及我们将在下面介绍的许多示例)](https://github.com/DeepLcom/deepl-python)
*   [DeepL API docs，](https://www.deepl.com/docs-api/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)涵盖了 Python 库围绕其构建的 REST 接口，如果您想尝试 Python 之外的语言，这会很有帮助

第一步:您需要使用 pip 从 [PyPI](https://pypi.org/project/deepl/) 安装库。

```
pip install  --upgrade deepl

```

从现在开始，我们将编写 Python 代码。创建一个名为`deepl_tutorial.py`的新文件(确保您的文件和父目录都不命名为 deepl)。

我们需要脚本做的第一件事是创建一个 translator 对象。这是你需要 DeepL 认证密钥的地方，你可以在你的账户中找到[。](https://www.deepl.com/en/pro-account/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial) 

```
import deepl 

translator  = deepl.Translator("YOUR_AUTH_KEY")

```

## 翻译文本

我们用一句“你好，世界！”来开场是再合适不过的了例如，所以我们要做的第一件事是翻译“你好，世界！”从英语到德语。

你会注意到我们使用`target_lang parameter`来设置我们的目标语言。DeepL 可以自动检测源语言，下面就不具体说明了。但是您也可以使用`source_lang parameter`显式地设置源语言。

```
result  = translator.translate_text("Hello, world!", target_lang="DE") 

print(result)  # “Hallo, Welt!”

```

也可以一次将多个文本翻译成同一种目标语言。这里，我们将把日语和西班牙语翻译成美国英语(再次依靠 DeepL 的语言检测功能来识别源语言)。

```
result  = translator.translate_text(["お元気ですか？",  "¿Cómo estás?"], target_lang="EN-US")

```

我们将打印结果，还将验证检测到的源语言。

```
print(result[0].text)  # "How are you?"
print(result[0].detected_source_lang)  # "JA" 

print(result[1].text)  # "How are you doing?"
print(result[1].detected_source_lang)  # "ES"

```

## 支持的源语言和目标语言

到目前为止，你已经看到 DeepL 可以翻译德语、美国英语、日语和西班牙语，但在简介中，我们承诺了 20 多种源语言和目标语言。

您可以在文档中找到支持的源语言和目标语言的完整列表以及两个字母的语言代码[。](https://www.deepl.com/docs-api/translating-text/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)

还可以使用 API 来获取受支持的源语言和目标语言的列表。

```
print("Here's a list of supported source languages:")  
for language in translator.get_source_languages():  
    print(f"{language.code} ({language.name})")  # Example: "DE (German)"

print("Here's a list of supported target languages:")  
for language in translator.get_target_languages():  
    print(f"{language.code} ({language.name})")  # Example: "DE (German)"

```

## 监控使用情况

你可能偶尔会想检查一下你翻译了多少个字符——我们的 API 免费计划允许每月 500，000 个字符，而我们的 API Pro 计划提供基于数量的定价，没有字符限制。

```
usage  =  translator.get_usage()  
if usage.character.limit_exceeded:  
    print("Character limit exceeded.")  
else:  
    print(f"Character usage: {usage.character}")

```

## 文件翻译(也包括形式)

我们提到过，DeepL API 还允许您翻译 Microsoft Word、PowerPoint、HTML 和纯文本文档。为了使教程简单，我们将使用一个带有文本文件的例子。

这里有一个假设的用例。作为居住在德国的非德语母语人士，我们可能需要用德语给房东发电子邮件。为了确保我们的翻译准确，我们想用 DeepL 检查它们。

(作为题外话:这是一个小规模的例子，为了教程的缘故。然而，这个特性对于更大的任务是有帮助的，比如翻译一个网站的 HTML 文件或者大量的 Word 文档。)

我要翻译一个文本文件，内容如下:

`Dear Sir or Madam, `

`I would like to inform you that we still do not have hot water in our apartment, now for five days in a row. Seeing as it's the middle of January, could you please send someone to repair the hot water heater? `

`Kind regards, `

`Your Favorite Tenant `

我正在翻译的文本文件叫做`email-to-landlord-en.txt`，我希望翻译后的文件叫做`email-to-landlord-de.txt`。

在翻译文档之前，我们将分享两个提示:

*   使用 API 翻译 PowerPoint 或 Microsoft Word 文档时，即使文档中的字符数少于 50，000，也至少会使用 50，000 个字符。如果你密切关注你的使用情况，记住这一点很重要。
*   在运行以下代码片段之前，请确保您正在翻译的文件位于您的工作目录中。

```
translator.translate_document_from_filepath(  

"email-to-landlord-en.txt",  

"email-to-landlord-de.txt",  

target_lang="DE",  

formality="more"  

)

```

瞧！我的翻译文件`email-to-landlord-de.txt`现在位于我的工作目录中，其翻译文本如下:

`Sehr geehrte Damen und Herren, `

`Ich möchte Sie darüber informieren, dass wir immer noch kein heißes Wasser in unserer Wohnung haben, nun schon fünf Tage in Folge. Da es Mitte Januar ist, könnten Sie bitte jemanden schicken, um den Warmwasserboiler zu reparieren? `

`Mit freundlichen Grüßen, `

`Ihr Lieblingsmieter `

您可能已经注意到，在翻译文本文件时，我引入了一个新的参数，称为 formality。让我们[查阅文档](https://www.deepl.com/docs-api/translating-text/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)看看它指的是什么:

*正式决定了译文应该倾向于正式语言还是非正式语言。此功能目前仅适用于目标语言" **DE "(德语)、" FR "(法语)、" IT "(意大利语)、" es "(西班牙语)、" NL "(荷兰语)、" PL "(波兰语)、" PT-PT" / "PT-BR "(葡萄牙语)和" RU "(俄语)**。*

*你可以为比较正式的语言设置“more”，为不太正式的语言设置“less”。*

当我联系我的房东要求维修时，我知道我想使用“更正式”的德语，幸运的是，DeepL 让这变得很容易。但是如果我翻译一封电子邮件给一个亲密的朋友，我可以很容易地选择“不太正式”的德语。

## 总结和后续步骤

感谢您加入我们，亲身体验 DeepL API！

我们希望本教程对您有所帮助，如果您对 Python 客户端库有任何反馈，我们鼓励您在 GitHub repo 中[创建一个问题](https://github.com/DeepLcom/deepl-python/issues)。这是一个开源项目，我们很想听听你的想法。

并且 [API 文档](https://www.deepl.com/docs-api/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)是了解支持的语言和文件格式的最佳地方，加上更高级的用例，比如[处理 XML](https://www.deepl.com/docs-api/handling-xml/?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial) 。

为了了解我们的最新进展，[我们建议查看我们的博客](https://www.deepl.com/en/blog?utm_source=the-new-stack&utm_medium=article&utm_campaign=python-tutorial)。

目前就这些。翻译愉快！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>