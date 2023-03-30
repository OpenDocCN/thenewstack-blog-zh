# 重新思考 Kubernetes 中的 Java @Scheduled Tasks

> 原文：<https://thenewstack.io/rethinking-java-scheduled-tasks-in-kubernetes/>

从历史上看，我工作过的 Java 应用程序中的大多数调度任务都使用了 Spring 的调度[特性](https://docs.spring.io/spring-framework/docs/3.2.x/spring-framework-reference/html/scheduling.html#scheduling-annotation-support-scheduled)。Spring 在应用程序的后台处理您用`@Scheduled`注释的方法。如果只有一个应用程序实例在运行，这种方式很好。

然而，应用程序越来越容器化，并在容器编排平台(如 Kubernetes)上运行，以利用水平伸缩，从而运行一个应用程序的多个实例。这给历史上使用计划任务的方式带来了一个问题:因为计划任务是在应用程序的后台运行的，所以当我们水平扩展应用程序时，我们复制了(并且可能是竞争的)计划任务。

为了解决在 Kubernetes 中扩展 Java 调度任务的问题，我创建了一个新的模式，它可以与三个流行的开源依赖注入框架协同工作:Spring Boot、Micronaut 和 Guice with Java Spark。让我们通过下面的场景来理解这个模式。

## **场景**

假设我们有一个运行一些业务逻辑的需求，这些业务逻辑作为一个调度任务存在于 Spring Boot API 的服务层中。出于本文的目的，假设服务看起来像这样:

```
@Service
public  HelloService  {

    public String sayHello()  {
 return  "Hello World!";  
 }

}

```

过去，我们会通过在 Spring Boot API 中编写一个调用服务逻辑的类，并用`@Scheduled`注释一个方法来完成这个任务，就像这样:

```
@Component
@Slf4j
public  class  ScheduledTasks  {

 private final HelloService helloService;

    @Autowired
    public ScheduledTasks(HelloService helloService)  {
        this.helloService  =  helloService;
    }

    @Scheduled(cron  =  "0 8 * * MON-FRI")
    public void runHelloService()  {
        String hello  =  this.helloService.sayHello();
        log.info(hello);
    }
}

```

虽然这个解决方案很简单，但是它限制了我们在 Kubernetes 这样的现代容器编排平台中水平扩展应用程序的能力。当这个 API 水平扩展到 2、3、4 … n 个 pod 时，我们将有 2、3、4 … n 个计划任务复制相同的计划任务逻辑，这可能导致重复的逻辑、[竞争条件](https://thenewstack.io/how-to-deal-with-race-conditions/)和资源的低效使用。

有像 [ShedLock](https://github.com/lukas-krecan/ShedLock) 和 [Quartz](https://www.quartz-scheduler.org/) 这样的解决方案可以解决这个问题。ShedLock 和 Quartz 都使用一个外部数据库，在给定时间只允许 n 个 pods 中的一个调度任务执行。虽然这种方法可行，但它需要一个外部数据库。此外，计划任务的实例仍然在每个 pod 中运行，这会消耗应用程序/pod 内存，即使它们中只有一个会执行其业务逻辑。我们可以通过完全消除多个调度任务实例来改进这些解决方案。

## **在 Kubernetes 中有没有更好的任务调度方式？**

是的，和 Kubernetes [CronJob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/) 一起。我们可以通过分离运行调度任务和服务应用程序来克服这些缺点。这就要求我们通过编写一个调用服务逻辑的控制器，将服务逻辑公开为 API 端点，就像这样:

```
@RestController
public  MyController  {

    private final HelloService helloService;

 @Autowired
 public MyController(HelloService helloService)  {
 this.helloService  =  helloService;
 }

 @PostMapping("/hello")
 public ResponseEntity<String>  sayHello()  {
 String hello  =  this.helloService.sayHello();
 return ResponseEntity.ok(hello);
 }

}

```

接下来，我们创建一个`CronJob`资源，它将按照设定的时间表调用这个新端点:

```
apiVersion:  batch/v1
kind:  CronJob
metadata:
  name:  hello
spec:
  schedule:  "0 8 * * MON-FRI"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          -  name:  hello
            image:  busybox:1.28
            imagePullPolicy:  IfNotPresent
            command:
            -  /bin/sh
            -  -c
            -  curl  -X  POST http://path.to.the.java.api/hello
          restartPolicy:  OnFailure

```

现在我们有了一个可水平扩展的解决方案。

然而，如果我们有一个规定，阻止我们将 HelloService 公开为 API 端点，该怎么办？或者，如果安全团队说我们需要检索一个 JSON Web 令牌(JWT ),并在调用 API 端点之前将其放入 curl 请求的授权头中，该怎么办呢？在最好的情况下，这将需要比团队更多的时间和 shell 专业知识，在最坏的情况下，这将使上述解决方案不可行。

## 在 Kubernetes 中有没有更好的安排任务的方法？

是的。我们可以通过使用 Java 的多入口点特性来减轻这些担忧。

然而，我们案例中的独特挑战是服务逻辑存在于 Spring Boot API 中，因此需要执行某些 Spring 依赖注入逻辑，以便在执行替代入口点之前实例化服务层及其所有依赖。

在运行备选入口点之前，我们如何给 Spring Boot 足够的时间来配置应用程序呢？我发现下面的代码可以做到这一点:

```
@SpringBootApplication
public  class  SpringBootEntryPoint  {

    public static void main(String[]  args)  {
        ConfigurableApplicationContext applicationContext  =  SpringApplication.run(SpringBootEntryPoint.class,  args);

        /*
         * If an alternative entry point environment variable exists, then determine if there is business logic that is mapped to
         * that property.  If so, run the logic and exit.  If an alternative entry point property does not exist, then
         * allow the application to run as normal.
         */
        Optional.ofNullable(System.getenv("alternativeEntryPoint"))
                .ifPresent(
                        arg  ->  {
                            int exitCode  =  0;

                            try(applicationContext)  {
                                if  (arg.equals("sayHello"))  {
                                    String hello  =  applicationContext.getBean(HelloService.class).sayHello();
                                    System.out.println(hello);
                                }
                                else  {
                                    throw new IllegalArgumentException(
                                            String.format("Did not recognize alternativeEntryPoint, %s",  arg)
                                    );
                                }
                            }
                            catch  (Exception  e)  {
                                exitCode  =  1;
                                e.printStackTrace();
                            }
                            finally  {
                                System.out.println("Closing application context");
                            }

                        /*
                        If there is an alternative entry point listed, then we always want to exit the JVM so the
                        spring app does not throw an exception after we close the applicationContext.  Both the
                        applicationContext and JVM should be closed/exited to prevent exceptions.
                        */
                            System.out.println("Exiting JVM");
                            System.exit(exitCode);
                        });
    }

}

```

这种模式也适用于其他 [Java 框架](https://thenewstack.io/why-frameworks-define-javas-cloud-native-future/)比如 Micronaut 和 Guice with Java Spark，所以它相对来说是框架不可知的。下面是使用 Micronaut 的相同模式:

```
public  class  MicronautEntryPoint  {

    public static void main(String[]  args)  {
        ApplicationContext applicationContext  =  Micronaut.run(MicronautEntryPoint.class,  args);

        /*
         * If an alternative entry point environment variable exists, then determine if there is business logic that is mapped to
         * that property.  If so, run the logic and exit.  If an alternative entry point property does not exist, then
         * allow the application to run as normal.
         */
        Optional.ofNullable(System.getenv("alternativeEntryPoint"))
                .ifPresent(
                        arg  ->  {
                            int exitCode  =  0;

                            try(applicationContext)  {
                                if  (arg.equals("sayHello"))  {
                                    String hello  =  applicationContext.getBean(HelloService.class).sayHello();
                                    System.out.println(hello);
                                }
                                else  {
                                    throw new IllegalArgumentException(
                                            String.format("Did not recognize alternativeEntryPoint, %s",  arg)
                                    );
                                }
                            }
                            catch  (Exception  e)  {
                                exitCode  =  1;
                                e.printStackTrace();
                            }
                            finally  {
                                System.out.println("Closing application context");
                            }

                            /*
                            If there is an alternative entry point listed, then we always want to exit the JVM so the
                            spring app does not throw an exception after we close the applicationContext.  Both the
                            applicationContext and JVM should be closed/exited to prevent exceptions.
                            */
                            System.out.println("Exiting JVM");
                            System.exit(exitCode);
                        });
    }

}

```

唯一的主要区别是这个类不需要注释，并且使用了 Spring 方法的 Micronaut 等价物(例如:`Micronaut#run`)。

下面是使用 Guice 和 Java Spark 的相同模式:

```
public  class  GuiceEntryPoint  {

    private static Injector injector;

    public static void main(String[]  args)  {
        GuiceEntryPoint.injector  =  Guice.createInjector(new GuiceModule());

        /*
         * If an alternative entry point environment variable exists, then determine if there is business logic that is mapped to
         * that property.  If so, run the logic and exit.  If an alternative entry point property does not exist, then
         * allow the application to run as normal.
         */
        Optional.ofNullable(System.getenv("alternativeEntryPoint"))
                .ifPresent(
                        arg  ->  {
                            int exitCode  =  0;

                            try  {
                                if  (arg.equals("sayHello"))  {
                                    String hello  =  injector.getInstance(HelloService.class).sayHello();
                                    System.out.println(hello);
                                }
                                else  {
                                    throw new IllegalArgumentException(
                                            String.format("Did not recognize alternativeEntryPoint, %s",  arg)
                                    );
                                }
                            }
                            catch  (Exception  e)  {
                                exitCode  =  1;
                                e.printStackTrace();
                            }
                            finally  {
                                System.out.println("Closing application context");
                            }

                            /*
                            If there is an alternative entry point listed, then we always want to exit the JVM so the
                            spring app does not throw an exception after we close the applicationContext.  Both the
                            applicationContext and JVM should be closed/exited to prevent exceptions.
                            */
                            System.out.println("Exiting JVM");
                            System.exit(exitCode);
                        });

        /*
        Run the Java Spark RESTful API.
         */
        injector.getInstance(GuiceEntryPoint.class)
                .run(8080);
    }

    void run(final int port)  {
        final GoodByeService goodByeService  =  GuiceEntryPoint.injector.getInstance(GoodByeService.class);

        port(port);

        get("/",  (req,  res)  ->  {
            return goodByeService.sayHello();
        });
    }

}

```

主要的区别在于，您从 Guice `Injector`中检索 beans，而不是像 Spring 和 Micronaut 那样从一个`ApplicationContext`对象中检索，并且有一个`run`方法包含所有的控制器端点，而不是有一个控制器类。

你可以看到这些代码样本，并按照这个 repo 的 [README](https://github.com/aws-samples/multiple-entry-points-with-dependency-injection) 中的说明运行它们。

在每个例子中，您会注意到，我通过检查环境变量是否存在，以及如果存在，它的值是多少，来控制是否调用备选入口点的逻辑。如果环境变量不存在或者它的值不是我们所期望的，那么`HelloService` bean 将不会从`ApplicationContext`或`Injector`(取决于所使用的框架)中检索到，也不会被执行。虽然这不完全是一个替代的入口点，但它的功能是相似的。这种模式不像传统的替代入口点那样使用多个`main`方法，而是使用一个`main`方法，并使用环境变量来控制执行的逻辑。

注意，当使用 Spring 和 Micronaut 时，无论服务方法调用是成功执行还是抛出`Exception`，都使用带有资源的`try`来关闭`applicationContext`。这保证了如果指定了替代入口点，它将总是导致应用程序退出。这将阻止 Spring Boot 应用程序继续运行以服务控制器 API 端点的 HTTP 请求。

最后，如果检测到另一个入口点环境变量，我们总是退出 JVM。这可以防止 Spring Boot 抛出`Exception`，因为`ApplicationContext`已经关闭，但是 JVM 仍在运行。

实际上，这个解决方案允许依赖注入在入口点路由逻辑发生之前发生。

这个解决方案允许我们编写一个 Kubernetes `CronJob`资源，它使用与我们将 Spring Boot 应用程序作为 API 运行时使用的相同的 docker 映像，但是我们只是在规范中添加了一个环境变量，如下所示。

```
apiVersion:  batch/v1
kind:  CronJob
metadata:
  name:  my-service
spec:
  schedule:  "0 8 * * MON-FRI"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          -  name:  hello-service
            image:  helloImage:1.0.0  # This is the Java API image with the second entry point.
            imagePullPolicy:  IfNotPresent
            env:
            -  name:  alternativeEntryPoint
              value:  "helloService"
          restartPolicy:  OnFailure

```

通过使用 Kubernetes `CronJob`，我们可以保证在任何给定的时间只有一个调度的任务在运行(假设任务在调用之间有足够的调度时间)。此外，我们没有通过 API 端点公开`HelloService`,也不需要使用 shell 脚本——一切都用 Java 实现。我们还消除了重复的计划任务，而不是管理它们。

我喜欢将这种模式想象成让一个 jar 充当一把瑞士军刀:每个入口点就像瑞士军刀中的一个工具，以不同的方式运行 jar 的逻辑。正如瑞士军刀有不同的工具，如螺丝刀、小刀、剪刀等。这种模式是否让 jar 像 RESTful API、调度任务等一样在其嵌入的业务逻辑上发挥作用。

![](img/d43b0f557b2cfec460c382f371b74d14.png)

## **常见问题解答**

### **问题:**

编写一个@Scheduled 方法并根据一些配置属性禁用它不是更容易吗？

### **回答:**

首先，值得考虑的是，像 Micronaut 这样的其他框架不具备[禁用](https://docs.micronaut.io/latest/api/io/micronaut/scheduling/annotation/Scheduled.html)方法的能力。而且 Java Spark 不能调度任务。另一方面，本文描述的模式(我称之为瑞士军刀模式)不仅仅适用于 Spring，还适用于更多的框架。

但是，即使您的项目确实使用了 Spring，我发现使用`@Scheduled`的一个主要缺点是，我们要求 Spring 应用程序 24/7 运行，以便 Spring 任务调度程序运行并调用基于 cron 调度的@Scheduled 任务。这需要一个 24/7 运行的 Kubernetes pod，其中运行 Spring 应用程序。我认为这种资源(可能还有钱)的使用是不必要的，因为 Kubernetes 提供了自己的任务调度器，我们可以通过创建一个`CronJob`资源来利用它。Kubernetes 的资源将只用于`CronJob`的生命周期，而不是让一个包含`@Scheduled`任务的吊舱一直运行。

换句话说，我将`@Scheduled`和`CronJob`选项比作:我们不会运行 EC2 实例并在 EC2 实例上创建调用 Lambda 函数的 cronjob，因为我们可以使用 CloudWatch cron [规则](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html)调用 Lambda 函数。我们不这么做的原因之一是，与免费的 CloudWatch 规则相比，EC2 实例会更加昂贵。就像这个例子中的 EC2 实例一样，我认为`@Scheduled` pod 是不必要的资源供应，因为我们已经在 Kubernetes 的`CronJob`中提供了一个调度工具(就像 CloudWatch cron 规则)。

### **问题:**

这种模式适用于多集群环境吗？

### **答案:**

这种模式还没有在多集群环境中测试过，它可能不会工作，因为这种模式不包括集群 A 中运行的计划任务能够知道集群 b 中运行的计划任务的另一个实例的方法。Quartz 和 ShedLock 使用外部集中式数据库来编排这些多集群计划任务。这种模式不包括外部数据库。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>