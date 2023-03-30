# 满足 Cadence:驯服复杂流程的工作流引擎

> 原文：<https://thenewstack.io/meet-cadence-workflow-engine-for-taming-complex-processes/>

[](https://www.linkedin.com/in/benbromhead/)

 [本·布罗姆黑德

本·布罗姆黑德是 Instaclustr 的联合创始人兼首席技术官，该公司提供一个围绕开源数据技术的平台。](https://www.linkedin.com/in/benbromhead/) [](https://www.linkedin.com/in/benbromhead/)

构建任何现代应用程序的开发人员都面临着与第三方 API、内部服务和长期运行的业务流程进行复杂交互的挑战。这些流程要求开发人员跟踪复杂的状态，支持对异步事件的响应，并实现与潜在不可靠的外部依赖项的通信。

开发人员经常用同样复杂的解决方案来处理这些复杂的需求——将涉及无状态服务、数据库、重试算法和调度作业队列的系统组装在一起。

 [艾姆拉·谢克尔

艾姆拉是优步公司的软件工程师。他的软件开发经验涵盖了从内核级编程到分布式 web 服务的广泛领域。他喜欢从事云计算和高度可扩展系统的工作。Emrah 之前的公司包括 Box、微软和西门子。](https://www.linkedin.com/in/emrahseker) 

然而，这些笨拙的系统将应用程序的业务逻辑隐藏在所有的复杂性之下，并且由于它们依赖于分散的和未经测试的组件而经常面临可用性问题。

最终，开发人员的生产力在维护这些庞大而繁重的系统的压力下受到损害。

[Cadence](https://cadenceworkflow.io/) 是一个开源的无故障状态代码平台和工作流引擎，专门设计用于解决这一开发挑战。Cadence 最初由优步开发并开源，现在被包括优步和 Instaclustr 在内的越来越多的公司采用和开发，它可以抽象出与开发大规模分布式应用程序相关的最困难的复杂性。

## Cadence 是如何工作的？

Cadence 将应用程序的整个状态保存在与任何特定进程无关的持久虚拟内存中。存储的应用程序状态包括所有调用参数和用户定义活动的返回结果。然后，它使用这些信息来跟踪和重放被中断的工作流。

Cadence 拥有一些库，使开发人员能够使用流行的语言(如 Java、Go、Python 和 Ruby)来创建和协调工作流。Cadence 服务(如 workers)在很大程度上是无状态的，并且利用数据存储来实现任务/工作流持久性。支持的存储选项包括开源 Cassandra 和 MySQL/PostgreSQL，适配器可用于任何具有多行单分片事务的数据库。多种服务部署模型也是可用的。例如，优步使用由数百个应用程序共享的多租户 Cadence 集群。

通过这种方式，Cadence 为开发人员提供了一种新的工具来编写和管理分布式应用程序，同时保持应用程序的持久性、可用性和可伸缩性。

## Cadence 如何帮助开发者？

Cadence 为使用基于微服务的架构的开发团队提供了大量价值，这些架构需要容错能力，也为包含无数多步并发工作流或与多个第三方 API 交互的应用程序提供了大量价值。

但是 Cadence 的多功能性几乎适用于任何涉及多个请求和回复的场景。开发人员可以使用 Cadence 创建用作工作流和编排平台的应用程序，并通过取代利用数据库和任务队列的传统策略，极大地提高开发人员的工作效率。

更具体地说，Cadence 的优势在以下使用案例中得到了展示:

*   **周期性执行(分布式 cron)。** Cadence 保证执行定期安排的业务逻辑，包括复杂的错误处理、重试策略和异步历史事件复制。重要的是，Cadence 支持大规模并行执行作业，能够同时执行数百万个工作流。

*   **微服务编排。**作为多个微服务调用实现的业务流程必须让所有这些调用成功，即使下游服务失败。Cadence 保证工作流代码的完成，支持无限重试，并使补偿逻辑易于开发，如 SAGA 模式。

*   **民意测验。**定期检查状态变化的轮询作业——通常用于监控或文件处理——特别适合 Cadence 对长期运行活动和无限重试的支持。

*   事件驱动的应用程序。 Cadence 直接支持异步事件，为开发者抽象出状态持久化的复杂性，使得实现监听多个事件源的应用变得简单。

*   **存储扫描。** Cadence 支持对大型分区数据集进行可扩展、弹性和完整的扫描，甚至跨越数十亿个文件。

*   **批量作业。**对于外部 API 调用可能失败的批处理作业，Cadence 保证持久性。

*   **基础设施供应。**长时间运行的配置操作可能会出现间歇性故障；Cadence 阻止了这种情况的发生。该平台还支持将活动执行路由到特定的进程或主机，以及可伸缩的容错锁定行为，以便一次在一个资源上执行一个单独的突变。

*   **CI/CD 管道和应用部署。**通过让开发人员专注于业务逻辑，Cadence 为构建部署解决方案提供了一个理想的平台。

*   **运营管理。** Cadence 支持自动管理和恢复，用于创建自运行数据库等。

*   **互动应用。** Cadence 的性能和可扩展性支持 UI 会话状态跟踪和同步后台操作执行。

*   **DSL 工作流程。**Cadence SDK 允许开发人员编写能够解释 DSL 流程定义的容错、可扩展、持久的应用程序。

*   **大数据与 ML。** Cadence 为大数据和机器学习解决方案提供了强大的控制平面，提供任务执行路由来控制 ML 模型和其他文件的分配方式。

## 怎么才能入门？

要开始使用 Cadence，请获取 Cadence 服务器的 [GitHub repo 或](https://github.com/uber/cadence) [Docker 映像](https://hub.docker.com/r/ubercadence/server)。

### **Cadence: Java Hello World 示例**

以下示例演示了如何使用 Java 在 Cadence 中创建和运行 Hello World 应用程序。首先，[在这里获得最新的 Cadence Java 客户端](https://mvnrepository.com/artifact/com.uber.cadence/cadence-client)。将它作为一个依赖项包含在您的 Java 项目中，在 [Gradle](https://gradle.org/) 中是这样的。

```
  compile group:  'com.uber.cadence',  name:  'cadence-client',  version:  '<latest_version>'

```

根据益华客户的要求，添加这些依赖关系。

```
compile group:  'commons-configuration',  name:  'commons-configuration',  version:  '1.9'
compile group:  'ch.qos.logback',  name:  'logback-classic',  version:  '1.2.3'

```

接下来，编译这段代码。

```
import com.uber.cadence.workflow.Workflow;

import com.uber.cadence.workflow.WorkflowMethod;

import org.slf4j.Logger;

public  class  GettingStarted  {

private static Logger logger  =  Workflow.getLogger(GettingStarted.class);

public  interface  HelloWorld  {

@WorkflowMethod

void sayHello(String name);

}

}

```

将这个日志回溯配置文件添加到您的类路径中。

```
<configuration>
    <appender name="STDOUT"  class="ch.qos.logback.core.ConsoleAppender">
        <!--  encoders are assigned the type
 ch.qos.logback.classic.encoder.PatternLayoutEncoder by  default  -->
        <encoder>
            <pattern>%d{HH:mm:ss.SSS}  [%thread]  %-5level  %logger{36}  -                                                %msg%n</pattern>
        </encoder>
    </appender>
    <logger name="io.netty"  level="INFO"/>
    <root level="INFO">
        <appender-ref ref="STDOUT"  />
    </root>
</configuration>

```

接下来，通过用`sayHello`方法添加`HelloWorldImpl`来实现 Hello World 工作流:

```
import com.uber.cadence.worker.Worker;
import com.uber.cadence.workflow.Workflow;
import com.uber.cadence.workflow.WorkflowMethod;
import org.slf4j.Logger;

public  class  GettingStarted  {

    private static Logger logger  =  Workflow.getLogger(GettingStarted.class);

    public  interface  HelloWorld  {
        @WorkflowMethod
        void sayHello(String name);
    }

    public  static  class  HelloWorldImpl  implements  HelloWorld  {

        @Override
        public void sayHello(String name)  {
            logger.info("Hello "  +  name  +  "!");
        }
    }
}

```

通过向连接到 Cadence 服务的工作器注册，将此工作流链接到 Cadence 框架(默认情况下，工作器连接到本地运行的服务)。

```
public static void main(String[]  args)  {
  WorkflowClient workflowClient  =
      WorkflowClient.newInstance(
          new WorkflowServiceTChannel(ClientOptions.defaultInstance()),
          WorkflowClientOptions.newBuilder().setDomain(DOMAIN).build());
  // Get worker to poll the task list.
  WorkerFactory factory  =  WorkerFactory.newInstance(workflowClient);
  Worker worker  =  factory.newWorker(TASK_LIST);
  worker.registerWorkflowImplementationTypes(HelloWorldImpl.class);
  factory.start();
}

```

现在，通过运行 worker 程序，使用 CLI 执行 Hello World 工作流。

```
>  docker run  --network=host  --rm ubercadence/cli:master  --do test-domain workflow start  --tasklist HelloWorldTaskList  --workflow_type HelloWorld::sayHello  --execution_timeout  3600  --input  \"World\"

Started Workflow Id:  bcacfabd-9f9a-46ac-9b25-83bcea5d7fd7,  run Id:  e7c40431-8e23-485b-9649-e8f161219efe

```

程序输出的最后一行现在类似于:

```
13:40:28.308  [workflow-root]  INFO  c.u.c.samples.hello.GettingStarted  -  Hello World!

```

查看工作流执行历史将进一步为开发人员提供有价值的信息，用于对他们的应用程序进行故障排除。

鉴于 Cadence 为组织和应用程序开发人员提供的优势，这些组织和应用程序开发人员准备从 Cadence 独特的优势及其作为免费开源软件的可用性中受益！—感兴趣的人应该很快就能发现该平台诱人的潜力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>