# JSON 简介

> 原文：<https://thenewstack.io/an-introduction-to-json/>

JSON 代表 JavaScript 对象符号。这是一种数据交换格式，这是一种存储和传输数据的方式。它已经被广泛部署到相当多的用例中。尽管这个名字暗示了 JavaScript，JSON 也被用于其他语言，比如 Python、Ruby、PHP 和 Java。然而，更重要的是，JSON 格式也用于 Docker 和 Kubernetes 清单，所以对于任何对云原生开发感兴趣的人来说，理解 JSON 如何工作是绝对重要的。

1999 年 12 月，当对象文字和数组文字被添加到 JavaScript 中时，JSON 作为 JavaScript 的子集出现了。JSON 很快变得独立于语言，因此几乎每种编程语言都能够解析 JSON 数据。

JSON 并不是由某个人发明的，因为许多不同的人都意识到了这个数据传输/存储系统的功能。然而，“JSON”这个术语是雅达利的员工道格拉斯·克洛克福特创造的。2002 年，克罗克福德继续注册了 json.org 域名。克罗克福德已经成为技术领域的一个非常重要的人物(在 Paypal 这样的公司工作)，所以他的声音有助于 JSON 的传播。

然而，直到单页面应用程序(SPA)的出现，JSON 的使用才真正爆发，因为移动和 web 应用程序都需要无缝的数据交换。这是因为与 XML 相比，JSON 数据的简洁格式在向服务器来回发送数据时要高效得多。原因之一是因为 JSON 是一种更加高效和简洁的语言。

这里有一个 XML 的例子:

```
&lt;colors&gt;
    &lt;color&gt;
        &lt;colorname&gt;Black&lt;/colorname&gt;  &lt;hex&gt;000000&lt;/hex&gt;
    &lt;/color&gt;
   &lt;color&gt;
        &lt;colorname&gt;White&lt;/colorname&gt;  &lt;hex&gt;FFFFFF&lt;/hex&gt;
     &lt;/color&gt;
     &lt;color&gt;
         &lt;colorname&gt;Red&lt;/colorname&gt;  &lt;hex&gt;FF0000&lt;/hex&gt;
     &lt;/color&gt;
&lt;/colors&gt;

```

上面的 JSON 代码应该是这样的:

```
{"colors":  [
   {"colorname"  :  "Black",  "hex"  :  "000000"},
   {"colorname"  :  "White",  "hex"  :  "FFFFFF"},
   {"colorname"  :  "Red",  "hex"  :  "FF0000"}
]}

```

正如您所见，JSON 不仅更容易编写，而且更容易阅读。

JSON 文件使用。json 扩展，但是不要误以为只能在。json 文件。事实上，所有的。yml 和。yaml 文件是以 JSON 格式编写的，这就是为什么理解 JSON 是什么以及它是如何构造的很重要(考虑到许多应用程序和服务都依赖于 YAML 文件)。如果您想将容器部署到 Kubernetes 集群，您将使用 JSON。想建一个 Dockerfile，没错，你用的是 JSON。甚至还有依赖于 JSON 格式的桌面和服务器应用程序的配置文件。

说到这个…

## JSON 结构

JSON 文件(不管它们是什么。json，。yaml(或任何依赖于 JSON 的文件)由两个主要组件构建:

*   名称/值对的集合。
*   值的有序列表。

JSON 文件的结构非常依赖于键值对。假设您想要构建一个包含用户信息的 JSON 结构化文件。该结构可能如下所示:

```
{
  "f_name"  :  "Jack",
  "l_name"  :  "Wallen",
  "gender"  :  "Male",
  "profession"  :  "Writer"
}

```

在上面的例子中，我们有四个键值对:

*   f _ name–杰克
*   l _ name–瓦伦
*   性别-邮件
*   职业-作家

每对总是以下列形式设置:

*“键”:“值”*

键和值都必须用双引号括起来。键总是在冒号的左边，值在右边。在每个对象中，每个键都必须是唯一的，并且可以包含空格。所以，你可以用“名字”来代替“名字”。然而，我总是避免在键中使用空格，因为这会让人感到困惑。

值位于冒号的右侧，并且必须是以下六种数据类型之一:

*   用线串
*   数字
*   目标
*   数组
*   布尔运算
*   空

还可以使用嵌套对象创建键值对。这样的结构可能看起来像这样:

```
"user"  :  {
"f_name"  :  "Jack",
"l_name"  :  "Wallen",
"gender"  :  "Male",
"profession"  :  "Writer"
}

```

上面我们有一个“user”键和一个嵌套的键-值对列表，由“f_name”、“l_name”、“gender”和“profession”组成。

我们也可以在键值对中使用数组。数组包含在[ ]中。让我们继续上面的例子，但是我们将用一个数组向“profession”键添加两个值。看起来像这样:

```
"user"  :  {
"f_name"  :  "Jack",
"l_name"  :  "Wallen",
"gender"  :  "Male",
"profession"  :  [  "Writer",  "Actor",  "Technologist"]
}

```

这两个例子都提出了非常重要的一点——缩进。使用 JSON 格式的一个注意事项是缩进必须完全一致。正如您在上面看到的，我的大括号和嵌套的键-值对是相互对齐的。如果您的缩进不一致，那么无论您使用 JSON 格式做什么都将不起作用。这通常是一个很难调试的问题，尤其是当 JSON 格式的清单变得越来越长、越来越复杂的时候。因此，从一开始就保持一致的订单总是很重要的。

JSON 格式也可以用一行写出来。让我们以“用户”对象为例。而不是这样写出来:

```
"user"  :  {
"f_name"  :  "Jack",
"l_name"  :  "Wallen",
"gender"  :  "Male",
"profession"  :  "Writer"
}

```

我们可以把它写成单行字符串，像这样:

```
"user"  :  {  "f_name"  :  "Jack",  "l_name"  :  "Wallen",  "gender"  :  "Male",  "profession"  :  "Writer"  }

```

虽然您可能认为上面的内容更容易写出，但是在非常长的文档中(尤其是当数组变得相当长时)，多行格式更容易管理。当制作非常复杂的容器清单时尤其如此。

如今，JSON 无处不在:在 spa 中，在本地应用程序配置中，在容器清单中，在云原生开发和 API 中。你说得出，JSON 很可能是其中的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>