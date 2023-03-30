# Ruby，程序员最好的朋友入门

> 原文：<https://thenewstack.io/ruby-a-programmers-best-friend/>

编者按:

*The New Stack is a sponsor for [RubyConf India](http://rubyconfindia.org/2015/). Leading up to the conference, The New Stack will feature posts by the speakers on topics about Ruby on Rails. We try to do this for all the conferences we sponsor. For example, we have been featuring posts by speakers from [GopherCon](https://thenewstack.io/events/), scheduled for February in Bangalore.*

当我第一次被介绍给 Ruby 时，我问:“为什么是 Ruby？”我得到了两个常见的回答:

*   它让你以不同的方式思考编程(特别是如果你来自非 OOP 背景)。
*   它让你快乐。

Ruby 是从程序员的角度为生产力而设计的。它的语法很优雅，是真正面向对象的。

Ruby 是一种动态的、反射式的、面向对象的、通用的编程语言。它是由日本的松本幸宏(Yukihiro“Matz ”)在 20 世纪 90 年代中期设计和开发的。

Matz 对 Ruby 的想法可以从下面的陈述中清楚地看出:

我和我的同事讨论了面向对象脚本语言的可能性。我知道 Perl (Perl4，不是 Perl5)，但我并不真正喜欢它，因为它有一种玩具语言的味道(现在仍然有)。面向对象语言似乎很有前途。那时我知道 Python。但是我不喜欢它，因为我认为它不是真正的面向对象语言——面向对象的特性似乎是这种语言的附加物。作为一个 15 年的语言狂热者和 OO 爱好者，我真的想要一种真正的面向对象的、易于使用的脚本语言。我找了找，但是没有找到。所以我决定去做。

在这里，我将向您介绍 Ruby。

让我们从基础开始。
 **琴弦:**

```
2.1.2  :001  &gt;  name  =  "Matz"
=&gt;  "Matz"
2.1.2  :002  &gt;  puts  "Hello, #{name}"
Hello,  Matz
=&gt;  nil
2.1.2  :003  &gt;  puts  "Hello, "  +  "#{name}"
Hello,  Matz
=&gt;  nil
2.1.2  :004  &gt;  "I l"  +  "o"  *  5  +  "ve Ruby!"
=&gt;  "I looooove Ruby!"

```

这里发生了一些好事。基本的字符串插值如您所料。您可以使用+方法将字符串连接在一起。你甚至可以“乘”字符串。

那么什么是酷的东西呢？它的实现方式。例如，+ *方法*作用于字符串*对象*“Hello，”。+的含义取决于接收该方法的对象。在这里，它是一个 String 类型的对象，意思是“将 String 'Matz '添加到 String 'Hello '中”。

*一切*都是对象，包括整数和浮点数。我们一会儿将回到这一点。对于熟悉面向对象编程的人来说，很高兴看到一切都是面向对象的，甚至是像数字相加这样的基本操作。

还要注意，对于每一条语句，Ruby 解释器都会返回一些东西，即使这些东西是空的。在 Ruby 中，每条语句都是一个表达式，并且会产生一个值。

回到我们的字符串例子，如果 a +的左边有一个整数，那么+将导致这个数和右边的数相加。因为 Ruby 允许你重新打开类，你可以打开 Fixnum 类并重新定义+方法来表示…减法！虽然你可能会被解雇，但我相信这对你的整个团队来说都是很有趣的。Lol。

```
Greet
2.1.2  :001  &gt;  class Greet
2.1.2  :002?&gt;    attr_accessor  :name
2.1.2  :003?&gt;
2.1.2  :004  &gt;    def initialize(name="Nobody")
2.1.2  :005?&gt;      @name  =  name
2.1.2  :006?&gt;    end
2.1.2  :007?&gt;
2.1.2  :011?&gt;
2.1.2  :012  &gt;    def say_goodbye(another)
2.1.2  :013?&gt;      "Goodbye, #{another}"
2.1.2  :014?&gt;    end
2.1.2  :015?&gt;
2.1.2  :023?&gt;    def say_hello(another)
2.1.2  :024?&gt;      "Hey %s! I'm %s"  %  [  another,  @name  ]
2.1.2  :025?&gt;      end
2.1.2  :019?&gt;    end
=&gt;  :say_hello

```

*Greet* 是一个简单的类，里面有一堆方法。

### 变量作用域

有四个变量作用域:
–Global($)
全局变量可以在整个程序中使用。
–类(@@)
类变量可用于类的所有实例(对象)。
–实例(@)
实例变量只在当前实例内部可用，即。，每个实例都有自己的副本。
–局部
局部变量的范围被限制在一个方法或块内。

*attr_accessor* 方法为变量列表设置 *getter* 和 *setter* 方法。简单的事情，但是它节省了你做这些事情的时间:

```
def foo
@foo
end

def foo=(new_value)
@foo  =  new_value
end

```

对于每一个该死的变量。

你有没有注意到 *attr_accessor* 是如何接受 *:name* 的？那是一个*符号*。它像一个字符串，但它像一个标识符一样使用。它们不同于字符串，所有同名的符号共享相同的内存。

类中的 initialize 方法在实例化时运行，即。创建对象时。对象是用。在类常量上定义的新方法。

等等，你可以在类上使用方法？！记得我告诉过你一切都是物体吗？你的类定义恰好是一个类型为 *Class* 的对象，常量 Greet 指向它。不相信我？你自己试试吧。

```
2.1.2  :041  &gt;  Greet.class
=&gt;  Class
2.1.2  :043  &gt;  Greet.methods.sort
=&gt;  [:!,  :!=,  :!~,  :&lt;,  :&lt;=,  :&lt;=&gt;,  :==,  :===,  :=~,  :&gt;,  :&gt;=,  :__id__,  :__send__,  :allocate,  :ancestors,  :autoload,  :autoload?,  :class,  :class_eval,  :class_exec,  :class_variable_defined?,  :class_variable_get,  :class_variable_set,  :class_variables,  :clone,  :const_defined?,  :const_get,  :const_missing,  :const_set,  :constants,  :define_singleton_method,  :display,  :dup,  :enum_for,  :eql?,  :equal?,  :extend,  :freeze,  :frozen?,  :hash,  :include,  :include?,  :included_modules,  :inspect,  :instance_eval,  :instance_exec,  :instance_method,  :instance_methods,  :instance_of?,  :instance_variable_defined?,  :instance_variable_get,  :instance_variable_set,  :instance_variables,  :is_a?,  :kind_of?,  :method,  :method_defined?,  :methods,  :module_eval,  :module_exec,  :name,  :new,  :nil?,  :object_id,  :prepend,  :private_class_method,  :private_constant,  :private_instance_methods,  :private_method_defined?,  :private_methods,  :protected_instance_methods,  :protected_method_defined?,  :protected_methods,  :public_class_method,  :public_constant,  :public_instance_method,  :public_instance_methods,  :public_method,  :public_method_defined?,  :public_methods,  :public_send,  :remove_class_variable,  :remove_instance_variable,  :respond_to?,  :send,  :singleton_class,  :singleton_class?,  :singleton_method,  :singleton_methods,  :superclass,  :taint,  :tainted?,  :tap,  :to_enum,  :to_s,  :trust,  :untaint,  :untrust,  :untrusted?]

```

新方法接受提供给 initialize 方法的参数。方法参数的默认值可以在方法定义中使用 param=default_value 来指定。

g 是 Greet 的一个实例。

```
2.1.2  :020  &gt;  g  =  Greet.new
=&gt;  #&lt;Greet:0x00000001992e50 @name="Nobody"&gt;

```

我们的 getter 和 setter 方法在起作用:

```
2.1.2  :032  &gt;  g.name  =  "Tom"
=&gt;  "Tom"

2.1.2  :033  &gt;  g.name
=&gt;  "Tom"

2.1.2  :034  &gt;  g.say_hello("Jim")
=&gt;  "Hey Jim! I'm Tom"

```

最后一个方法展示了如何使用格式说明符和一个值数组来组成一个字符串。

### 数组和散列

Ruby 中使用数组和散列来存储相关数据。你可以用
创建一个新的数组或散列

```
i_am_an_array  =  Array.new
i_am_a_hash  =  Hash.new

```

当然，它们经常被使用，可以按字面意思这样创建:

```
new_array  =  []  # an empty array.
new_hash  =  {}  # an empty hash

```

```
2.1.2  :013  &gt;  foo  =  "hex"
=&gt;  "hex"
2.1.2  :014  &gt;  bar  =  [10,  3.14,  foo,  ["I'm",  "a",  "nested",  "array"]]
=&gt;  [10,  3.14,  "hex",  ["I'm",  "a",  "nested",  "array"]]

```

数组只不过是对对象的引用的集合。所以它们可以存储你想要的任何东西，包括其他数组。

```
2.1.2  :015  &gt;  foo.reverse!
=&gt;  "xeh"
2.1.2  :016  &gt;  bar
=&gt;  [10,  3.14,  <b>"xeh"</b>,  ["I'm",  "a",  "nested",  "array"]]

```

只是对对象的引用。
你可以任意分割一个数组:

```
2.1.2  :030  &gt;  bar[0]
=&gt;  10
2.1.2  :031  &gt;  bar[-1]
=&gt;  ["I'm",  "a",  "nested",  "array"]
2.1.2  :032  &gt;  bar[2..-1]  # This is a range. More on this later
=&gt;  ["xeh",  ["I'm",  "a",  "nested",  "array"]]

```

哈希是关联数组(像字典一样),包含键值对。键和值可以是任何类型的对象。

```
2.1.2  :028  &gt;  a_hash  =  {:name  =&gt;  "NASA",  4  =&gt;  "four",  "array"  =&gt;  bar  }
=&gt;  {:name=&gt;"NASA",  4=&gt;"four",  "array"=&gt;[10,  3.14,  "xeh",  ["I'm",  "a",  "nested",  "array"]]}

```

通常，它们和符号一起作为键使用，以至于它们有自己的速记语法:

```
2.1.2  :029  &gt;  another_hash  =  {  organization:  "NASA",  country:  "USA"  }
=&gt;  {:organization=&gt;"NASA",  :country=&gt;"USA"}

```

可以这样访问值:

```
2.1.2  :037  &gt;  a_hash[:name]
=&gt;  "NASA"

```

### 打印对象

如果我想打印一个 Greet 实例该怎么办？Ruby 怎么知道要打印什么？记住数字也只是对象，所以我可以输入 puts 23，它输出字符串“23”。Ruby 是如何知道如何转换 Fixnum 的一个对象并把它做成一个字符串的？如果查看 Fixnum 类中的所有方法，有一个 to_s 方法。puts 简单地调用数字 23 上的 to_s 方法。

因此，要使 Greet 的实例可打印，我们需要做的就是定义一个 to_s 方法。让我们重新打开 Greet 并添加一个 to_s 方法。

```
2.1.2  :054  &gt;  class Greet
2.1.2  :055?&gt;    def to_s
2.1.2  :056?&gt;      "My name is #{@name}"
2.1.2  :057?&gt;    end
2.1.2  :058?&gt;  end
=&gt;  :to_s
2.1.2  :059  &gt;  puts  g
My name is Tom
=&gt;  nil

```

### 如果，除非，当，直到，为了

```
if condition
# do something
elsif
# do another
else
# do something else

```

你也可以这样做:

```
puts  "I'm true today"  if condition

```

如果条件为真，当您不想执行某个操作时，可以使用 unless 关键字来代替 if。

Ruby 中的循环通常使用迭代器来完成，但是该语言确实提供了 while 和 for 循环。

```
i  =  0
while  i  &lt;  5
print  "#{i}, "
i  +=  1
end

0,  1,  2,  3,  4,

```

对于循环:

```
fruits  =  ["apples",  "grapes",  "pineapples",  "oranges"]
for fruit in fruits
puts fruit
end

```

### 范围

Ruby 中的范围用于定义一组有开始和结束的值。因此，如果我想循环从 0 到 5 的值，我会这样做:

```
2.1.2  :035  &gt;  for  i  in  (0..5)
2.1.2  :036?&gt;    print  "#{i}, "
2.1.2  :037?&gt;  end
0,  1,  2,  3,  4,  5,   =&gt;  0..5

```

也可以有字符范围。

```
2.1.2  :039  &gt;  ('a'..'e').to_a
=&gt;  ["a",  "b",  "c",  "d",  "e"]
2.1.2  :040  &gt;  ('a'...'e').to_a
=&gt;  ["a",  "b",  "c",  "d"]

```

两个点:包括最后一个值。
三点:不含最后一个值。

### 块和迭代器

对象不应该知道如何迭代自身吗？就像一根弦应该知道它有多长。

“我三十一字长”。长度

Ruby 中的块和迭代器非常强大，非常有用。大多数时候，您真的对在外部维护数组索引不感兴趣。你只是想把这该死的东西翻一遍！在 Ruby 中，你可以这样做:

```
2.1.2  :009  &gt;  fruits  =  ["apples",  "grapes",  "pineapples",  "oranges"]
=&gt;  ["apples",  "grapes",  "pineapples",  "oranges"]
2.1.2  :010  &gt;  fruits.each do  |fruit|
2.1.2  :011  &gt;    puts  "I like #{fruit}"
2.1.2  :012?&gt;  end
I  like apples
I  like grapes
I  like pineapples
I  like oranges
=&gt;  ["apples",  "grapes",  "pineapples",  "oranges"]

```

它基本上接受数组 fruits 中的每个元素，并将其作为 fruit 提供给 do … end 之间的代码块。这是一个*块*。

块基本上是传递给方法的一段代码，与将数据作为参数传递没有什么不同。让我们来看一下如何创建你自己的迭代器，让你有更好的理解。

让我们制作一个迭代器，它只处理每隔一个元素。

```
2.1.2  :001  &gt;  class Array
2.1.2  :002?&gt;    def every_other
2.1.2  :003?&gt;      current_index  =  0
2.1.2  :004?&gt;      new_array  =  []
2.1.2  :005?&gt;      while current_index  &lt;  self.size
2.1.2  :006?&gt;        new_array  &lt;&lt;  <b>yield</b>(self[current_index])
2.1.2  :007?&gt;        current_index  +=  2
2.1.2  :008?&gt;      end
2.1.2  :009?&gt;      return new_array
2.1.2  :010?&gt;   end
2.1.2  :011?&gt;  end
=&gt;  :every_other
2.1.2  :012  &gt;  [1,  2,  3,  4,  5].every_other  {  |i|  i  **  2  }
=&gt;  [1,  9,  25]

```

这可能有点让人不知所措，所以让我们来分析一下。

我们重新打开数组类，在第 5 行创建了一个 while 循环。只要 current_index 小于原始数组的大小，它就会循环。

第 6 行是奇迹发生的地方。我们可以使用 yield 和任何参数调用传递给 every_other 的块。这里，我们在每个循环中传递一个替换元素。同样，元素通过我们传递的代码块传递，我们将代码块返回的值追加到 new_array。

一旦完成，我们就返回 new_array。

在第 12 行，我们调用数组[1，2，3，4，5]上的 every_other，并向它传递一个带一个参数的块。这是我们在方法定义中提供的参数。

基本上，我们采用了每一个替代元素，并通过块 i ** 2 运行它们中的每一个。

要更深入地了解 blocks、procs 和 lambdas，可以看看这篇关于 Ruby Blocks、Procs 和 Lambdas 的精彩文章。

### 可比较的

假设你定义了一个新的类，你想对这些对象的数组进行排序。想象一下你要做的工作量。Ruby 有一个优雅的解决方案。

```
2.1.2  :024  &gt;  class Person
2.1.2  :025?&gt;    attr_accessor  :name,  :age
2.1.2  :026?&gt;
2.1.2  :027  &gt;    include Comparable
2.1.2  :028?&gt;    def initialize(name,  age)
2.1.2  :029?&gt;      @name,  @age  =  name,  age
2.1.2  :030?&gt;    end
2.1.2  :031?&gt;
2.1.2  :032  &gt;    def  &lt;=&gt;  other
2.1.2  :033?&gt;      self.age  &lt;=&gt;  other.age
2.1.2  :034?&gt;    end
2.1.2  :035?&gt;  end
=&gt;  :&lt;=&gt;
2.1.2  :036  &gt;  people  =  []
=&gt;  []
2.1.2  :037  &gt;  people.push(Person.new("Ram",  30),  Person.new("James",  40),  Person.new("Angela",  28))
=&gt;  [#&lt;Person:0x0000000122de30 @name="Ram", @age=30&gt;, #&lt;Person:0x0000000121ff38 @name="James", @age=40&gt;, #&lt;Person:0x0000000121fb78 @name="Angela", @age=28&gt;]

2.1.2  :038  &gt;  people.sort
=&gt;  [#&lt;Person:0x0000000121fb78 @name="Angela", @age=28&gt;, #&lt;Person:0x0000000122de30 @name="Ram", @age=30&gt;, #&lt;Person:0x0000000121ff38 @name="James", @age=40&gt;]

```

好的，我们有一个人类。每个人都有名字和年龄。你包括了一整套好的可比较的模块。它只需要你定义一个方法，⇔，对于小于、等于或大于的情况，返回-1、0 或+1。

在第 32 行，我们就是这样做的。Other 是另一个具有年龄属性的对象。我们比较这个人和另一个人的年龄值。既然⇔方法已经为数字定义好了，我们就不需要为其他的东西费心了。

我们创建一个人员列表，并对其进行排序。瞧啊。所有的人都按年龄分类。

类似地，您可以使您的类可枚举，但是我们将在另一个时间讨论这个问题。

### 构成与继承

泽德·肖有一个精彩的章节专门讨论这个问题。虽然继承是有用的，但是组合通常是实现相同功能的更好方法，而不需要两个紧密耦合并且可能难以测试的类。

Ruby 只有单一继承，所以即使你使用继承，你也不会遇到钻石问题。

当我们将 comparable 模块包含到我们的类中时，您已经看到了 Ruby 是如何使用组合的。

```
module Foo
# a bunch of methods
end

module Bar
# some more methods
end

class Baz
include Foo
end

```

an_object = Baz.new # an_object 现在附带了 Foo 中的所有方法。

an _ object . extend(Bar)# an _ object 现在拥有 Bar 中的方法，但是 Baz 的所有其他实例不受影响

你可以使用 respond_to？检查对象是否响应特定的方法。

### 正则表达式

Ruby 有一个类似 Perl 的 regex 语法，使用/…/语法编写正则表达式文字。

很多编程都涉及到处理文本字符串，所以正则表达式非常有用

```
if filename  =~  /.+\.rb$/
puts  "This is a Ruby file."
else
puts  "This isn't a Ruby file."
end

```

Ruby 文档写得非常好，所以如果你想了解 Ruby 的某个特定部分，那应该是你首先要看的地方。

### 宝石

Ruby 自带包管理器。项目中的 gem 文件维护着代码所依赖的 gem(包)列表，一个命令就可以安装程序运行所需的所有包。可以包括版本号

你甚至可以有不同的宝石组用于开发和生产！

### 供电轨和 DSL

Rails 是 Ruby 的杀手级应用，也是它在 2006 年左右成为最酷的应用的原因。从那时起，Ruby 作为一种语言已经成熟，Rails 作为一个框架也已经成熟。如果没有 Ruby，Rails 就不会是现在的样子。Ruby 允许 Rails 优雅地使用它的语法和结构。如果你是一名 web 开发人员，你必须亲自尝试 Rails。努夫说。

Rails 和其他应用程序利用了*领域特定语言*,而最好是将编程语言放在后台。Ruby 以其对元编程的强大支持，允许你改变原本混乱的局面。

这里有更多关于如何创建你自己的内部 DSL。

### 结论

Ruby 是一种出色的语言…

最终，即使你在日常生活中不使用 Ruby，学习它也会让你的思维开阔到一些绝妙的概念，并且肯定会改变你对编程的看法。

“不影响你思考编程方式的语言是不值得了解的”——Alan Perlis

Ruby 名副其实地成为了程序员的语言。不会让你想拔头发。你只会想写更多的 Ruby 代码。

对于那些已经熟悉 Ruby 的人来说，一些非常有趣的文章，你应该看看[这一页](http://www.rubyinside.com/7-ruby-articles-to-read-over-the-holiday-season-1420.html)。

Darshan 是一名工程系学生和网络开发人员，对计算机、飞行和黑客技术充满热情。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>