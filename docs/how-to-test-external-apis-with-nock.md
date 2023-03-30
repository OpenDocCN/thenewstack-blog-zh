# 如何用 Nock 测试外部 API

> 原文：<https://thenewstack.io/how-to-test-external-apis-with-nock/>

测试外部 API 可能很棘手，尤其是如果您的公司不拥有服务/端点的话。然而，这种测试是良好集成测试的重要组成部分。模拟对于测试这样的东西从来都不是好事，因为它做了太多的假设，这些假设可能并且将会在以后改变，从而导致测试在应该失败的时候通过。那么，有哪些测试外部 API 的好方法呢？

*只需在本地提升服务即可。*

最彻底的方法是使用 Docker 镜像在本地提升服务。当然，设置有点复杂，但是正确的方法很少是最简单的。这样做可以确保调用是真实的，唯一需要关注的是定期改变映像以保持与主映像同步。
[](https://www.linkedin.com/in/darin-spivey/)

[Darin Spivey](https://www.linkedin.com/in/darin-spivey/)

[Darin 是 LogDNA 的高级软件工程师，他在 LogDNA 从事产品架构和性能、高级测试框架以及 LogDNA 的开源项目的工作。](https://www.linkedin.com/in/darin-spivey/)

[](https://www.linkedin.com/in/darin-spivey/)[](https://www.linkedin.com/in/darin-spivey/)

## 诺克，诺克，谁在那里？

如果您不能使用实际的服务，那么下一个最好的方法就是拦截 HTTP 流量，并将控制权交给编写测试的人。我喜欢的一个包叫做 [nock](https://www.npmjs.com/package/nock) ，它可以让你做到这一点。使用`nock`，您的 HTTP 调用将由代码的 HTTP 代理处理；唯一的区别是，它实际上不是在和任何真实的东西说话。这允许用户控制返回的状态代码、检查 POST 主体、查询字符串以及一个好的测试想要做的任何事情。对我来说，真正的代理实际上是一个大胜利。来自`axios`的响应与来自`request`的响应有很大不同，因此`nock`允许用户看到代理如何处理测试人员创建的情况，以便可以编写正确的断言。

## 它是如何工作的

给定一个 URL(或 URI ),然后告诉使用链式方法拦截哪些模式。注意，路径参数和查询字符串必须完全匹配，否则`nock`将不起作用。令人欣慰的是，nock 接受正则表达式和函数处理程序来帮助实现这一点，测试人员可以根据需要灵活或严格地进行设置。我的观点是，如果在 API 调用中有类似查询字符串的东西，它不能被忽略，必须为它设置一个`query`处理程序。为了增加保护，可以使用`nock.disableNetConnect()`来关闭所有外部调用，以防出现错误，进行真正的 HTTP 调用。

## 真实的例子

最近，我在我们的一些客户代码上工作，在这些代码中，成批的日志行被发送到 ingester。由于这是一个公共包，出于安全原因，旋转服务不是一个选项，但我仍然需要测试如何将行发送到我们的服务。使用`nock`，我能够测试诸如重试、HTTP 超时、错误条件以及是否发送了正确的有效负载，同时使用`axios`代理处理响应。

这是一个快乐路径测试。注意，有一个`query`处理程序来接受任何东西，因为查询字符串包含的值会随着每次测试而改变。返回`true`意味着这是一个有效的匹配。在这里，我们检查负载是否如预期的那样，然后我们用 200 success 进行回复。回复也可以 JSON！

```
nock(logger.url)  
    .post('/',  (body)  =>  {  
      const payload  =  body.ls[0]  
      t.equal(payload.line,  'Hi there',  'Log text was passed in body')  
      t.equal(payload.level,  'INFO',  'Default level was used')  
      return true  
    })  
    .query(()  =>  {  return true  })  
    .reply(200,  'Ingester response')

  logger.log('Hi there')

```

对于该客户端，用户错误不被视为故障，并且不会使用指数回退。使用`persist()`让拦截器持续不止一个调用(默认)。

```
nock(logger.url)
    .post('/',  ()  =>  {
      t.equal(
        logger[Symbol.for('isLoggingBackedOff')]
      ,  false
      ,  'User errors did not cause logger to back off'
      )
      return true
    })
    .query(()  =>  {  return true  })
    .reply(400,  {
      error:  'Nope, your line was invlalid somehow'
    })
    .persist()

  logger.log('Something is invalid about this line')
  logger.log('Something else is wrong with this line too')

```

现在，让我们开始幻想吧！在获得 HTTP 超时时测试指数后退逻辑怎么样？

```
const delay  =  1000

  // Fail 3 times, then succeed
  nock(logger.url)
    .post('/',  ()  =>  {
      t.equal(
        logger[Symbol.for('isLoggingBackedOff')]
      ,  false
      ,  'Logger is not backed off prior to the first failure'
      )
      return true
    })
    .query(()  =>  {  return true  })
    .delayConnection(delay  +  1)
    .reply(200,  'Will Not Happen')  // Not used, but still needed
    .post('/',  ()  =>  {
      t.equal(
        logger[Symbol.for('isLoggingBackedOff')]
      ,  true
      ,  'Logger is backed off'
      )
      return true
    })
    .query(()  =>  {  return true  })
    .delayConnection(delay  +  1)
    .reply(200,  'Will Not Happen')
    .post('/',  ()  =>  {  return true  })
    .query(()  =>  {  return true  })
    .delayConnection(delay  +  1)
    .reply(200,  'Will Not Happen')
    .post('/',  ()  =>  {  return true  })
    .query(()  =>  {  return true  })
    .reply(200,  'Success')

  logger.log('This will cause an HTTP timeout')

```

## **最佳实践**

*   `nock`将返回对拦截器定义的引用。`.isDone()` (返回一个布尔值)可以用来很容易地判断它是否在测试中使用过。您可以使用`scope.done()`来完成同样的事情，但是如果没有调用它，那么断言将会测试失败。
*   默认情况下每个拦截器只会被使用一次，但是`.persist()`可以用来让它们保持活动状态。因此，每个测试可能应该清除所有拦截器，以避免测试的交叉污染。`t.on('end', async () => { nock.cleanAll() })`
*   如果你需要更底层的东西(比如测试 TCP 流量)，中间人(mitm) 包可以帮助你。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>