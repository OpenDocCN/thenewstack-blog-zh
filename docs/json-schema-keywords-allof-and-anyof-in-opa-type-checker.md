# OPA 类型检查器中的 JSON 模式关键字 AllOf 和 AnyOf

> 原文：<https://thenewstack.io/json-schema-keywords-allof-and-anyof-in-opa-type-checker/>

[](https://www.linkedin.com/in/jingchen10500/)

[景(音译)是纽约一名计算机专业的大三学生。她很高兴了解更多关于混合云领域的研究，并热衷于在技术领域学习更多知识。](https://www.linkedin.com/in/jingchen10500/)

[](https://www.linkedin.com/in/jingchen10500/)[](https://www.linkedin.com/in/jingchen10500/)

[开放策略代理(OPA)](https://www.openpolicyagent.org/) 是一个开源引擎，可在云原生堆栈中统一策略实施。这个项目包括对其减压阀类型检查器的最新增强，它在策略评估期间使用 JSON 模式作为输入。这种增强是通过“opa eval”命令和-s 标志在输入中包含一个模式来实现的。在策略评估期间作为输入提供的 JSON 模式实质上为正在编写的策略提供了一个蓝图，这使得类型检查更加容易和直接。这提供了更精确、信息更丰富的错误消息。

以前的[博客](https://blog.openpolicyagent.org/enhanced-type-checking-for-opa-with-json-schema-annotations-826acb0f575) [帖子](https://blog.openpolicyagent.org/type-checking-your-rego-policies-with-json-schema-in-opa-5f7ac4c8a958)介绍了具有一些限制的类型检查器，因为它不支持 JSON Schema [2019-09 版本](https://json-schema.org/draft/2019-09/release-notes.html)中可用的许多关键字。例如，这个类型检查器不支持“allOf”和“anyOf”关键字。

## allOf 和 any of——有什么区别？

要理解 anyOf 和 allOf 的含义，请考虑输入您的邮寄地址以便在线购物。输入您的地址行后，您可以指定州、城市和邮政编码，也可以指定国家和邮政编码。对于那些熟悉 JSON 模式语言的人来说，它可能是这样的:

```
{
    "$schema":  "http://json-schema.org/draft-04/schema#",
    "type":  "object",
    "title":  "My schema",
    "properties":  {
        "Address":  {  "type":  "string"  },
    },
    "required":  [  "Address"  ],
    "anyOf":  [
        {
          "allOf":[
 {
                  "type":  "object",
                  "properties":  {
                      "State": {  "type":  "string"  },
                      "City": {  "type":  "string"  },
                      "ZipCode":  {  "type":  "string"  }
                  },
 },
 {
                  "required":  [  “State”,  “City”,  "ZipCode"  ]
 }
 ]
        },
        {
          "allOf":[
 {
                  "type":  "object",
                  "properties":  {
                      "County": {  "type":  "string"  },
                      "PostCode":  {  "type":  "string"  }
                  },
 },
 {
                  "required":  [  “County”,  "PostCode"  ]
 }
            ]
        }
    ]
}

```

换句话说，在输入您的地址行后，系统会提示您输入(州和城市以及邮政编码)或(国家和邮政编码)(从技术上讲，您可以在“anyOf”下输入这两个选项，因为它是一个包含性的“or”)。

 [朱莉娅·弗里德曼

Julia 是弗吉尼亚大学的三年级学生，主修计算机科学，辅修工程商务。今年夏天，她在 IBM 云计算领域实习。](https://www.linkedin.com/in/julia-ann-friedman/) 

正如我们在描述您的地址行的两个选项中看到的，无论您选择哪一个，您都必须包括所有指定的信息，因为在所有列出的模式中都有一个包含“必需”属性的子模式。允许“anyOf”增加了选择不同邮寄地址选项的灵活性，而允许“allOf”确保了安全性，因为所有需要的信息都在那里(仅适用于本例)。

在 [0.32.0](https://github.com/open-policy-agent/opa/releases/tag/v0.32.0) 中，OPA 的类型检查器增加了对这些关键字的支持，因此用户现在可以包含使用这些关键字的模式。让我们假设你是一个购物网站的管理员，你想暂时拒绝加利福尼亚的购物者订购，因为当前的野火情况阻碍了运输。因此，您可以编写如下所示的 API 策略来访问用户信息并识别居住在加利福尼亚的访问者。

```
package shopper.mailingAddress 

deny  {                                                                
  input.States  ==  “California” 
}

```

作为人类，我们都会犯错，上面的政策包含了一个你可能注意到也可能没有注意到的错别字(如果你注意到了，干得好！).现在有了新实现的对“anyOf”和“allOf”的支持，OPA 会通知你可能的错误:

```
input.States
 ^
 have:  "States"
 want  (one of):  ["City"  "County"  "PostCode"  "State"  "ZipCode"]

```

实现对“allOf”和“anyOf”关键字的支持消除了 OPA 的类型检查器的限制，因此现在使用这些关键字的模式将在策略创建和评估期间呈现更有用的错误消息。这些关键字特别相关，因为 Kubernetes 准入控制是 OPA 的重要用例之一，并且许多 Kubernetes 发布的模式使用“allOf”和“any of”。有了这个新实现的对“allOf”和“anyOf”的支持，OPA 现在能够支持许多这些 Kubernetes 用例，并增强所编写的 API 策略的安全性和灵活性。您可以在 OPA 的文档页面[中了解更多关于这一增强的信息。](https://www.openpolicyagent.org/docs/latest/schemas/#supporting-json-schema-composition-keywords)

## 下一步是什么？

与这个项目相关的未来工作将包括实现对 OPA 的 JSON 模式减压阀类型检查器目前不支持的许多其他关键字的支持(enum、if/then/else 等等)。此外，我们希望通过 OPA 社区进行用户调查来评估类型检查器的有效性。让我们知道你的想法！

## 链接

1.  1.  [文档](https://www.openpolicyagent.org/docs/latest/schemas/)
    2.  [示例](https://github.com/aavarghese/opa-schema-examples/)
    3.  [JSON 到 JSON 模式在线工具](https://jsonschema.net/)
    4.  [JSON 模式参考](http://json-schema.org/understanding-json-schema/reference/index.html)

***注:**这篇文章的其他作者是 IBM 的首席研究人员 Mandana Vaziri 和 IBM 的研究软件工程师安苏·瓦格斯。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>