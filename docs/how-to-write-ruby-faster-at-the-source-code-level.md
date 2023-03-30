# 如何在源代码层面更快地编写 Ruby

> 原文：<https://thenewstack.io/how-to-write-ruby-faster-at-the-source-code-level/>

优化可以采取许多不同的形式，但是程序员可以在项目开发过程中战略性地考虑在哪里以及如何进行优化。在 RubyConf India 2015 的这个演讲中，柏林的 SoundCloud 开发者 Erik Michaels-Ober([Twitter](https://twitter.com/sferik)和 [Github](https://github.com/sferik) )讲述了如何通过在源代码层面提升性能优化来编写更快的 Ruby。

[书写快速的红宝石](https://thenewstack.simplecast.com/episodes/writing-fast-ruby)

Michaels-Ober 首先指出，大多数开发人员都反对过早进行性能优化。他引用了斯坦福大学教授、算法设计和分析之父 Donald Knuth 在 1974 年所说的“过早优化是万恶之源”Michaels-Ober 指出，意图良好但不合时宜的优化确实有使代码“更难看、更难阅读和更复杂”的趋势，因此最好只在有需要或时机合适时优化代码。

那么什么时候应该进行优化呢？在这里，Michaels-Ober 再次引用了 Knuth，他制定了这两个标准:第一，在容易获得时进行优化；第二，当有显著收益时进行优化(Knuth 给出了 12%的数字作为显著性阈值)。Michaels-Ober 增加了第三个标准，借用 Ruby 首席设计师[Matz(Yukihiro Matsumoto)](https://twitter.com/yukihiro_matz)的话:Ruby 是为了让程序员开心而创建的，所以优化也应该让程序员开心——无论这意味着让代码“更漂亮”还是性能更好。

## 优化水平

[![Erik Michaels-Ober](img/76413c9c1f196fc929507929c97a5622.png)](https://thenewstack.io/wp-content/uploads/2015/05/Erik-Michaels-Ober-e1431636942911.jpeg)

埃里克·迈克尔斯-奥博

Michaels-Ober 然后概述了任何语言和项目都可能实现的各种级别的优化:在设计、源代码、构建、编译和运行时级别。Michaels-Ober 在这里关注的是源代码优化。他再一次从 Knuth 那里引入了一些智慧，Knuth 认识到，当涉及到预测计算机将如何实际解释代码时，程序员的人类直觉可能会失败，无论代码是否经过优化。“对于什么会快什么会慢，我们没有很好的直觉，”迈克尔斯-奥伯说。“我们经常犯错误，所以如果你过早地进行优化，你可能真的认为你在优化它，但你可能真的在编写一个不太优化的版本。”

那么，您如何知道哪个版本是最佳的呢？“你必须对它进行基准测试，”迈克尔斯-奥伯说。Ruby 的内置基准库允许你运行方法预定的次数。然而，Michaels-Ober 指出，内置基准库的问题是，您必须猜测它要运行多少次才能有意义。

相反，Michaels-Ober 推荐使用 [benchmark-ips](https://github.com/evanphx/benchmark-ips) (每秒迭代次数)，它扩展了 Ruby 的库以显示每秒迭代次数，而不是每秒迭代次数。当每个版本的代码仅运行五秒钟时，将生成一个报告，指示每个版本能够运行的次数。“这个想法是，五秒钟是足够长的时间，它消除了任何统计方差；一旦你运行那么多次，方差就会相对较低，所以你不必担心噪音。”

## 在源代码级别编写更快的 Ruby

Michaels-Ober 随后展示了一些如何简化代码以使其运行更快、更易读的例子(你可以参考[演讲台上的幻灯片](https://speakerdeck.com/sferik/writing-fast-ruby))。

*Symbol#to_proc* 比 block 快 20 倍，因为优化是在 Ruby 解释器内部进行的。 *Symbol#to_proc* 最初是作为 RAILS 中的简写发明的，后来被添加到 Ruby 中。Ruby 知道如何高效运行 *Symbol#to_proc* ，并在内部优化。

```
Enumerable#map and Array#flatten vs. Enumerable#flat_map

```

一个新的映射将返回一个数组，如果你想要一个数组，调用*映射*，然后*展平(1)* 。你可以用一个声明性更强的 *flat_map* 来替换 *map* 和 *flatten(1)* ，它会以同样的方式工作，而且它会快 4.5 倍，因为它遍历代码一次，而不是两次。

```
Enumerable#reverse and Enumerable#each vs. Enumerable#reverse_each

```

*Reverse_each* 不会复制数组，只会反向迭代数组，只需用 *reverse_each* 替换前者，就能使速度提高 17%。

```
Hash#keys and Enumerable#each vs. Hash#each_key

```

Ruby 有一个内置的方法来创建一个数组，该数组只包含散列的键。更快的方法不会创建中间数组，而是只返回键，速度提高了 33%。

```
Array#shuffle and Array#first vs. Array#sample

```

当你有一个数组，你想从数组中选取一些随机值，一种方法是打乱数组，用 *array.shuffle.first —* 去掉第一个元素，或者你可以用 *array.sample，*让它快 15 倍。

```
Hash#merge vs. Hash#merge!

```

修改散列的可变版本与创建散列的副本然后进行合并和复制的不可变版本。因为您在更小的范围内修改散列，所以速度快了 3 倍。同样的概念也适用于 *hash#[]* ，速度是原来的两倍。

```
Hash#fetch vs. Hash#fetch with block

```

为块获取第二个参数比直接传递块的结果快两倍。

```
<span class="s1"><i></i>String#gsub vs. String#sub</span>

```

*gsub*会用第二个字符串全局替换第一个字符串中的每个实例。如果您只想进行一次替换，而不想扫描其他实例，那么使用速度快 50%的 *sub* 。

```
String#gsub vs. String#tr

```

你总是可以用 *tr* 替换 *gsub* ，但是如果你想替换代码中的任何地方，使用 *tr* 会快 5 倍。

```
<span class="s1">Parallel vs.  sequential assignment</span>

```

并行赋值通过分配数组来工作，但它使代码更难阅读。当交换值时，并行赋值是有用的，否则，使用顺序赋值，这样读起来更快，快 40%。

与使用异常相比，对控制流使用 *throw/catch* 有助于跳过代码，使速度提高五倍。

Michaels-Ober 说，尽管其他优化可以在编译器的下一级完成，但上面提到的这些源代码优化技术今天可以轻松快速地实现，让你的 Ruby 代码更快、性能更好、读起来更漂亮。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>