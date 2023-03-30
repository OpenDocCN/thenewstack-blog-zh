# ScyllaDB 对用户定义函数的 WebAssembly

> 原文：<https://thenewstack.io/scylladbs-take-on-webassembly-for-user-defined-functions/>

[WebAssembly](https://webassembly.org/) ，也称为 Wasm，是一种用于表示可执行代码的二进制格式，旨在轻松嵌入到其他项目中。事实证明，Wasm 也是后端用户定义函数(UDF)的完美候选，这要归功于它的易集成性、性能和受欢迎程度。

[ScyllaDB，](https://www.scylladb.com/)用于需要高吞吐量和低延迟的数据密集型应用程序的数据库，支持以 WebAssembly 表示的用户定义函数，基于一个用 Rust 原生编写的开源运行时，名为 [Wasmtime](https://wasmtime.dev/) 。事实上，我们最近在构建系统中加入了 Rust 支持，使得未来的集成更加流畅。

本文介绍了我们如何以及为什么与 WebAssembly 集成。

## **选择合适的发动机**

WebAssembly 是一种用于可执行代码的格式，首先被设计成可移植和可嵌入的。顾名思义，它非常适合 web 应用程序。因为它非常快，所以它通常也是嵌入式语言的好选择。

WebAssembly 的核心特性之一是隔离。每个模块都在独立于主机应用程序的沙箱环境中执行。这种[有限信任环境](https://thenewstack.io/6-security-risks-to-consider-with-webassembly/)是嵌入式语言真正需要的，因为它极大地降低了有人从您的项目内部运行恶意代码的风险。

Wasm 是一种二进制格式，但它也指定了一种人类可读的文本格式，称为 [WebAssembly 文本格式](https://webassembly.github.io/spec/core/text/index.html)或 WAT。

![](img/84de86a31fd3789ac6a57fc92a6dac95.png)

要将 WebAssembly 集成到项目中，您需要选择一个引擎。最流行的引擎是 Google 的 [v8](https://v8.dev/) ，它是用 C++实现的，支持 JavaScript 和非常丰富的特性集。不幸的是，它也非常笨重，不太容易与异步框架集成，如 [Seastar](https://github.com/scylladb/seastar) ，这是一个用于现代硬件上高性能服务器应用程序的开源 C++框架，是 ScyllaDB 的一个构建块。

幸运的是，还有 [Wasmtime](https://wasmtime.dev/) ，一个更小的(但不小！)项目在 Rust 中实施。它支持 WebAssembly，但不支持 JavaScript，这使得它更加轻量级。它还很好地支持异步环境，并提供了 [C++](https://thenewstack.io/typemock-simplifies-net-c-unit-testing/) 绑定，这使得它非常适合注入到 ScyllaDB 中进行概念验证实现。

ScyllaDB 之所以选择 Wasmtime，是因为它比 v8 更轻，并且具有异步友好的潜力。虽然我们目前使用 Wasmtime 提供的现有 C++绑定，但我们计划在 Rust 中实现整个集成层，然后直接编译到 ScyllaDB 中。

## **web assembly 中的编码**

那么，如何创建一个 WebAssembly 程序呢？

### WebAssembly 文本格式

首先，模块可以直接以 WebAssembly 文本格式编码。至少对我来说，这不是最方便的方法，因为 Wasm 有限的类型系统和带有大量括号的特定语法。当然，这是可能的。在这种情况下，您只需要一个文本编辑器。爱上[Lisp](https://thenewstack.io/nasa-programmer-remembers-debugging-lisp-in-deep-space/)也不会有坏处。

```
```wat
(module
  (func  $fib  (param  $n  i64)  (result i64)
    (if
      (i64.lt_s  (local.get  $n)  (i64.const  2))
      (return  (local.get  $n))
    )
    (i64.add
      (call  $fib  (i64.sub  (local.get  $n)  (i64.const  1)))
      (call  $fib  (i64.sub  (local.get  $n)  (i64.const  2)))
    )
  )
  (export  "fib"  (func  $fib))
)
```

```

### C++

C 和 C++爱好者可以用 clang 编译器将他们选择的语言编译成 Wasm。

```
```cpp
int fib(int  n)  {                                  
    if  (n  <  2)  {
        return  n;
    }  
    return fib(n  -  1)  +  fib(n  -  2);
}
```
```sh
clang  -O2  --target=wasm32  --no-standard-libraries  -Wl,--export-all  -Wl,--no-entry fib.c  -o  fib.wasm
wasm2wat fib.wasm  >  fib.wat
```

```

二进制接口定义得很好，生成的二进制在底层也优化得很好。使用 LLVM 表示将代码编译成 WebAssembly，这使得许多优化成为可能。

### 锈

Rust 还能够减少其生态系统中的 Wasm 输出，官方 Rust 构建工具链 Cargo 已经支持一个`wasm32 target`。

```
```rust
use wasm_bindgen::prelude::*;

#[wasm_bindgen]
pub fn fib(n:  i32)  ->  i32  {
    if  n  <  2  {
        n
    }  else  {
        fib(n  -  1)  +  fib(n  -  2)
    }
}
```
```sh
rustup target add wasm32-unknown-unknown
cargo build  --target wasm32-unknown-unknown
wasm2wat target/wasm32-unknown-unknown/debug/fib.wasm  >  fib.wat
```

```

### 汇编脚本

还有 [AssemblyScript](https://www.assemblyscript.org/) ，一种类似类型脚本的语言，可以直接编译成 WebAssembly。AssemblyScript 特别适合快速实验，因为它是一种脚本语言。它也是唯一一种将 WebAssembly 作为编译目标而发明和设计的语言。

```
```assemblyscript
export function fib(n:  i32):  i32  {
  if  (n  <  2)  {
    return  n
  }
  return fib(n  -  1)  +  fib(n  -  2)
}
```
```sh
asc fib.ts  --textFile fib.wat  --optimize
```

```

## **用户自定义函数**

ScyllaDB 为什么需要 WebAssembly？我们的第一个用例涉及用户定义函数(UDF)。UDF 是 Cassandra 查询语言(CQL)的一个特性，它允许你用给定的语言定义一个函数，然后在查询数据库时调用那个函数。该函数将由数据库本身应用于参数，然后才返回给客户端。UDF 还使得表达嵌套调用和其他更复杂的操作成为可能。

以下是在 CQL 中如何使用用户定义的函数:

```
```cql
cassandra@cqlsh:ks>  SELECT id,  inv(id),  mult(id,  inv(id))  FROM  t;

  id  |  ks.inv(id)  |  ks.mult(id,  ks.inv(id))
----+------------+-------------------------
  7  | 0.142857  | 1
  1  |          1  | 1
  0  | Infinity  | NaN
  4  | 0.25  | 1

(4  rows)
```

```

UDF 本身已经够酷了，但是更重要的目的是启用用户定义的*聚合*(uda)。uda 是定制的累加器，它将来自多个数据库行的数据组合成潜在的复杂输出。uda 包含两个函数:一个用于累积每个参数的结果，另一个用于最终确定结果并将其转换为输出类型。

下面的代码示例显示了一个计算所有请求字符串的平均长度的聚合。下面的函数是用 Lua 编写的，这是 ScyllaDB 支持的另一种语言。

首先，让我们创建所有的构建模块:用于累加部分结果和转换最终结果的函数:

```
```cql
CREATE FUNCTION accumulate_len(acc tuple<bigint,bigint>,  a  text)
  RETURNS NULL ON NULL INPUT
  RETURNS tuple<bigint,bigint>
  LANGUAGE lua as  'return {acc[1] + 1, acc[2] + #a}';
CREATE OR REPLACE FUNCTION present(res tuple<bigint,bigint>)
  RETURNS NULL ON NULL INPUT
  RETURNS text
  LANGUAGE lua as
  'return "The average string length is " .. res[2]/res[1] .. "!"';
```

```

接下来，让我们将它们组合成一个用户定义的聚合:

```
```cql
CREATE OR REPLACE AGGREGATE avg_length(text)
  SFUNC accumulate_len
  STYPE tuple<bigint,bigint>
  FINALFUNC present INITCOND  (0,0);
```

```

下面是创建聚合后的使用方法:

```
```cql
cassandra@cqlsh:ks>  SELECT *  FROM words;

  word
------------
 monkey
  rhinoceros
        dog
(3  rows)

cassandra@cqlsh:ks>  SELECT avg_length(word)  FROM words;

  ks.avg_length(word)
-----------------------------------------------
  The average string length is  6.3333333333333!
(1  rows)
```

```

一个函数通过存储所有长度的总和以及字符串的总数来累加部分结果。终结函数将一个除以另一个以返回结果。在这种情况下，结果是呈现文本的形式。

这里的潜力非常大——用户定义的聚合允许以更强大的方式使用数据库查询；例如，通过收集复杂的统计数据或将整个分区转换成不同的格式。

## 输入 WebAssembly

要在 WebAssembly 中创建一个用户自定义的函数，我们首先需要将函数编写或编译成 Wasm 文本格式。然后，函数体简单地注册在一个名为`create function`*的 CQL 语句中。就是这样！* 

```
```cql
CREATE FUNCTION ks.fib  (input bigint)
RETURNS NULL ON NULL INPUT
RETURNS bigint LANGUAGE xwasm
AS  '(module
  (func $fib (param $n i64) (result i64)
    (if
      (i64.lt_s (local.get $n) (i64.const 2))
      (return (local.get $n))
    )
    (i64.add
      (call $fib (i64.sub (local.get $n) (i64.const 1)))
      (call $fib (i64.sub (local.get $n) (i64.const 2)))
    )
  )
  (export "fib" (func $fib))
  (global (;0;) i32 (i32.const 1024))
  (export "_scylla_abi" (global 0))
  (data $.rodata (i32.const 1024) "\\01")
)'
```
```cql
cassandra@cqlsh:ks>  SELECT  n,  fib(n)  FROM numbers;
  n  |  ks.fib(n)
---+-----------
  1  | 1
  2  | 1
  3  | 2
  4  | 3
  5  | 5
  6  | 8
  7  |        13
  8  |        21
  9  |        34
(9  rows)
```

```

注意，这里声明的语言是 [xwasm](https://github.com/raphamorim/xwasm) ，代表“实验 wasm”。ScyllaDB 对这种语言的支持目前仍处于试验阶段。

当前的设计文档保存在这里。欢迎大家来看看:[https://github . com/scylladb/scylladb/blob/master/docs/dev/wasm . MD](https://github.com/scylladb/scylladb/blob/master/docs/dev/wasm.md)

## 我们的路线图

ScyllaDB 的 WebAssembly 支持正在积极开发中；以下是我们的一些最高目标。

### Rust 和 C++的助手库

直接以 WAT 格式编写函数并不简单，因为 ScyllaDB 希望函数遵循我们的应用程序二进制接口(ABI)规范。为了对开发人员隐藏这些细节，我们正在为 Rust 和 C++实现助手库，它们无缝地提供了 ScyllaDB 绑定。

有了我们的助手库，用您选择的语言编写用户定义的函数不会比编写常规的本机函数更难。

### 在 Rust 中重写用户自定义函数层

我们目前依靠 Wasmtime 的 C++绑定来为用户定义的函数提供 Wasm 运行时。但是，这些 C++绑定有一定的局限性。具体来说，它们缺乏对异步操作的支持，而异步操作存在于 Wasmtime 最初的 Rust 实现中。

选择非常明显——让我们用 Rust 重写吧！我们的精确计划是将整个用户定义函数层移到 Rust，在那里我们可以充分利用 Wasmtime 的潜力。有了这样的实现，我们将能够异步运行用户定义的函数，并有严格的延迟保证。

我们将只在 Seastar 和 Rust 的异步模型之间提供一个薄的兼容层，以便直接从 ScyllaDB 轮询 Rust 期货。将 Rust 期货直接绑定到 Seastar 的大致想法在这里解释[。](https://github.com/psarna/stepbystep)

我们已经[给我们的构建系统](https://github.com/scylladb/scylla/pull/10341)添加了铁锈支持。下一步是开始将用户定义的函数引擎重写为本机 Rust 实现，然后我们可以将它编译成 ScyllaDB。

## 利用 WebAssembly 降低用户定义函数的延迟

在最近的 [P99 CONF](https://www.p99conf.io/) 上，我分享了更多关于我们如何以一种延迟友好的方式将 WebAssembly 和 Wasmtime 集成到我们的项目中的细节，这是一个面向痴迷于低延迟的工程师的开源社区会议。演讲“[使用 WebAssembly](https://www.p99conf.io/session/keeping-latency-low-for-user-defined-functions-with-webassembly/) 保持用户定义函数的低延迟”可按需提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*