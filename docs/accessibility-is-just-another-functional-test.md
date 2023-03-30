# 可访问性只是另一个功能测试

> 原文：<https://thenewstack.io/accessibility-is-just-another-functional-test/>

***编者按**:以下帖子已由 Evinced 提供。 [Insight Partners](https://www.insightpartners.com/) 是 Evinced 和 New Stack 的投资者。*

多年来，可访问性倡导者一直要求更易访问的网站和移动应用程序。此外，据估计，全球 15%的人口患有残疾，大多数企业都在努力让他们的数字体验对不同能力的人无障碍。

那么，如果每个人都想要可访问性，为什么要花这么长时间才能实现呢？

为什么公司在开发周期结束时检查可访问性——或者更糟，在发布几个月后？

在[演示](https://www.evinced.com/)中，我们一直在问这个问题:为什么可访问性不能仅仅是另一个自动化的功能测试？

事实是，做这件事太难了，时间太长了。

## **设置和维护测试太难了**

传统工具只进行静态扫描，迫使开发人员对扫描进行编程，使其在测试中的特定点运行，以确保他们彻底检查应用程序。

对此有两种方法，坦率地说，这两种方法都不好:

**选项 1:直接添加扫描。**遍历测试的每一行，并在每次交互时添加静态扫描，可能会产生更多需要在每次测试中添加的扫描。对于成百上千次的测试来说并不实用。

```
//Original Test
@Test
public void trvlHomePage()  {
driver.get(demoPage);
// Click "Accommodation Type" dropdown
driver.findElement(By.cssSelector("div.filter-container &gt; div:nth-child(1)")).click();
// Click "City" dropdown
driver.findElement(By.cssSelector("div.filter-container &gt; div:nth-child(2)")).click();
// Click "When" date picker
driver.findElement(By.cssSelector(".react-date-picker")).click();
}

//Test with legacy accessibility scans
@Test
public void trvlHomePageLegacy()  {
driver.get(demoPage);
scanForAccessibility();
// Click "Accommodation Type" dropdown
driver.findElement(By.cssSelector("div.filter-container &gt; div:nth-child(1)")).click();
scanForAccessibility();
// Click "City" dropdown
driver.findElement(By.cssSelector("div.filter-container &gt; div:nth-child(2)")).click();
scanForAccessibility();
// Click "When" date picker
driver.findElement(By.cssSelector(".react-date-picker")).click();
scanForAccessibility();
}

```

选项 2:将单个测试的静态扫描抽象到您的页面对象或助手方法中。这种方法只在页面改变之前有效。维护页面并确保静态扫描在正确的位置，以维持可访问性覆盖率，这产生了太多的工作。

```
  public void homePageLogin(String username,  String password)  {
driver.findElement(By.id("username")).sendKeys(username);
driver.findElement(By.id("password")).sendKeys(password);
driver.findElement(By.id("loginBtn")).click();
scanForAccessibility();
}

```

使用传统工具时，会有很多噪音——有成百上千个问题和许多重复的报告。

例如，当使用 aXe 这样的遗留工具测试可访问性时，开发人员需要为测试中的每个元素添加可访问性检查和结果报告。之后，他们必须手动消除报告中的重复数据。虽然单页面站点是可以管理的，但是如果您喜欢重复报告，那么它对于涉及多个元素、用户交互和页面的测试来说是不实际的。

## **手动检查不可伸缩，跟不上构建周期**

在过去的十年中，功能测试已经变得自动化，但是易访问性测试仍然严重依赖于开发周期结束时的人工审计和审查。这些审查会中断生产周期，造成昂贵的延误。在版本发布之后进行的审核可能会导致活的 bug。

## **新方法**

我们需要这些问题的解决方案和一个有凝聚力的方法来帮助开发人员将易访问性测试向左移动，并像对待其他功能测试一样对待它。

简而言之:什么会使易访问性测试更容易？

这里有一个想法:如果您可以在运行第一个测试之前，在您公司的测试框架内建立一个易访问性 SDK，会怎么样？

例如，也许您可以在设置期间简单地实例化和调用一个测试自动化 SDK，只需几行代码，即使您正在处理 10 或 10，000 个测试。如果易访问性测试实现起来如此简单，难道不是更容易吗？

```
import com.evinced.EvincedWebDriver;

@BeforeClass
private void driverSetup()  {
driver  =  new EvincedWebDriver(new ChromeDriver());
driver.evStart();
}

```

## **支持大多数框架**

当然，最好的可访问性测试解决方案应该包括对最常用的 web 和移动自动化框架的内置支持——Selenium、Cypress、剧作家、WebdriverIO、Ruby、XCUITest、Espresso、Appium 等等。

此外，您可能希望 SDK 能够与 Jenkins、CircleCI 等持续集成系统直接集成。，并支持各种输出格式— JSON、HTML、SARIF 等。(这也增加了基于每个构建的可访问性的条件门控的可能性。)

## **还有两个要求**

为了真正地将它们结合在一起，在 UI 测试运行和测试各种 UI 元素时，不断地扫描文档对象模型(DOM)的变化是很重要的。

accessibility SDK 可以自动发现问题，而不是要求您为每个页面和交互编写一个测试和报告。理想情况下，根本不会有预先测试代码。然后，您会收到一份针对整个测试套件的已消除重复数据的报告。

这就是简化的可访问性测试，简单的测试是可持续的。

## **走向自动化——增强专业技能**

易访问性测试并不新鲜，但它确实需要改变。

我们上面建议的模型是关键。将易访问性测试向左转移，使测试更容易和更可持续，将确保更多的用户得到服务，开发人员不再因沮丧而放弃，专家可以专注于真正需要专家的地方。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>