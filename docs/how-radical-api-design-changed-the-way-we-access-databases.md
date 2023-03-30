# 激进的 API 设计如何改变我们访问数据库的方式

> 原文：<https://thenewstack.io/how-radical-api-design-changed-the-way-we-access-databases/>

[](https://www.mongodb.com/developer/author/john-page/)

 [约翰·佩奇

约翰·佩奇是一名文档数据库老手，在为情报界构建全栈文档数据库技术 18 年后，加入了 MongoDB。他现在制造机器人是为了好玩，并测试和编写数据库来支付机器人零件的费用。](https://www.mongodb.com/developer/author/john-page/) [](https://www.mongodb.com/developer/author/john-page/)

API 设计始于了解谁是你的消费者，他们将如何使用你的 API，以及他们期望它如何工作。但是很多时候，API 设计更类似于忠实地遵循已建立的模式和长期的约定。

当我们在 2007 年开始开发 MongoDB 时，我们希望重新想象开发人员与数据库交互的方式。我们创建的服务 API MongoDB Query API 是一种激进的方法，因为它允许开发人员通过使用对象而不是伪英语文本字符串来访问数据库。MongoDB 的纯对象 API 在 2007 年是革命性的。自那以后，MongoDB 查询 API 激发了大量的模仿者，尽管我们认为他们映射到一个功能不太丰富的底层数据库。

## **回头看看 SQL**

几十年来，开发人员不得不使用 SQL 在数据库中请求操作，SQL 是为关系数据库构建的结构化查询语言。当客户机-服务器应用程序出现时，SQL 被包装在薄层中，如数据访问对象(DAO)和开放式数据库连接(ODBC ),旨在向数据库发送 SQL 语句并解析响应。

SQL 出现在用户界面设计发生巨大变化的时代。电传打印机让位于黑底绿字的阴极射线管显示器，一个全新的编辑器诞生了，它可以让开发者同时查看和编辑多行代码。这个编辑器叫做**可视化**，后来简称为 **vi** ，演变为 **Vim** 。

与此同时，创建了一个用于访问数据的新 UI，以允许没有经过数学或编程正式培训的用户构建复杂的查询。这个用户界面被称为结构化英语查询语言(SEQUEL)，它允许用户用形式化的英语与计算机对话，以查看和修改数据。(后来因为商标原因简称为 SQL。)

SQL 的最初设计者 Donald Chamberlin 和 Ray Boyce 认为，它将被规划者和其他专业人员(而不是数据库管理专家)用来执行即席查询。Chamberlin 写道，他惊讶地看到 SQL 如此频繁地被训练有素的数据库专家用于重复的事务。(博伊斯 26 岁就去世了，就在一篇介绍续集的论文发表之后。)

无论是编写分析请求还是让您的应用程序代码与数据库交互，如果您是一名理解命令式编码的开发人员，SQL 都不是访问数据库的最佳方式。

同时，SQL 也不仅仅是声明性的，尤其是当您考虑到执行相同任务的好的和坏的 SQL 查询之间的性能差异与查询的编写方式直接相关时。

## **心态的改变**

我们在 MongoDB 做出的早期设计决策之一是使用纯基于对象的 API 关注与数据库的交互。就不会有查询语言。相反，对数据库的每个请求都将被描述为一组对象，这些对象既可以由计算机构造，也可以由人来构造(在许多情况下，更常见的是由计算机来构造)。

这种方法允许程序员像创建命令性代码一样处理复杂的查询。想要检索数据库中所有只有两条腿的动物吗？然后创建一个对象，将成员“legs”设置为 2，并在数据库中查询匹配的对象。你得到的是一个对象数组。这种模式甚至可以扩展到最复杂的操作。

这种方法使开发人员能够以代码的形式构建数据库查询*——*这是从查询语言思维到程序员思维的一次飞跃*。*这将显著加快开发时间并提高查询性能。这种数据库操作的 API 方法帮助 kickstart MongoDB 在我们早期的快速采用和发展。

对表格数据库使用面向对象编程的挑战多年来一直是摩擦的根源。对象关系映射器(ORM)像创可贴一样激增，模糊了最终开发人员对于基本用例的表格模型。但是 ORM 的繁荣是以牺牲开发人员对性能的理解和影响为代价的，而优化总是受制于表格数据库的固有摩擦。

## **面向对象编程的实践**

用物体思考并不总是显而易见的。许多第一次使用 MongoDB 的用户在交互式客户端 JavaScript REPL(读取、评估、打印、循环)中使用基于 JavaScript 的 shell。虽然您实际上是在编写程序，但是这种体验是如此的直接，以至于您可能会将其误认为是 SQL 提示符，而不是代码开发平台。这可能会让您认为 MongoDB 查询与您调用的 API 是分开的——您可能会将它们想象成 JavaScript，即使您的代码的其余部分是用其他语言编写的。要掌握 MongoDB，重要的是不要把查询看作语言本身，而是看作对象模型。

我甚至可以说，最强大的查询不是手写的，而是由高级函数生成的，强大的聚合查询应该被视为命令式编码，更像 Apache Spark 而不是 SQL。

例如，这里有两种方法来编写相同的请求，一种是用查询语言的思维方式，另一种是用程序员的思维方式。在这两种风格中，我都使用经典的程序员面试问题 [FizzBuzz](https://en.wikipedia.org/wiki/Fizz_buzz) 作为分析查询。

```
let pipeline  =  {
  $project:  {
    number:  {
      $switch:  {
        branches:  [
          {  case:  {  $eq:  [{  $mod:  ["$n",  3*5]  },  0]  },  then:  "FIZZBUZZ"  },
          {  case:  {  $eq:  [{  $mod:  ["$n",  3]  },  0]  },  then:  "FIZZ"  },
          {  case:  {  $eq:  [{  $mod:  ["$n",  5]  },  0]  },  then:  "BUZZ"  }
        ],
        default:  "$n"  
      }
    }
  }
}

db.numbers.aggregate([pipeline])

```

```
function divisibleBy(value,  divisor)  {
  return  {  $eq:  [{  $mod:  [value,  divisor]  },  0]  }
}

function buildbranches(field,words){
  rval  =  []
  for  (word in words)  {
 rval.push({case:  divisibleBy(field,words[word]),  then:  word})
  }
  return rval
}

pipeline  =  {
  $project:  {
    number:  {
      $switch:  {
        branches:  buildbranches("$n",{FIZZBUZZ:3*5,FIZZ:3,BUZZ:5}),
        default:  "$n"
      }
    }
  }
}

db.numbers.aggregate([pipeline])

```

虽然这个示例中的代码总长度大致相同，但是像这样分解代码会使它更容易阅读、编写、调试和维护。对于一个不太重要的例子，它也使得查询代码小得多。

## **结论**

就像 MongoDB 重新构想了与数据交互的概念并与开发人员保持一致一样，我敦促您审视自己的服务 API，并确保您不只是盲目地遵循既定的模式。关注谁是你的消费者，他们将如何使用它，以及他们将如何使用它。

而且，虽然您的 API 最初应该简单易用，但是想想它们如何在以后的版本中既可扩展又向后兼容。最重要的是，不要陷入害怕打破长期以来的惯例来最好地支持你的用户的境地。记住，第一辆汽车是用杠杆操纵的，而不是方向盘。重新思考最常见的服务 API 类之一是 MongoDB 策略的关键部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>