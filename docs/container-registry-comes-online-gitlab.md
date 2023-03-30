# GitLab 现在附带了一个 Docker 容器注册表

> 原文：<https://thenewstack.io/container-registry-comes-online-gitlab/>

GitLab 已经推出了新的软件，用于在 GitLab 开发生命周期堆栈中设置 Docker 容器注册表，这可能会使 GitLab 用户更容易构建、测试和部署 Docker 容器映像。

GitLab 新的 Docker 注册表 GitLab 容器注册表有 GitLab CE(社区版)和 GitLab EE(企业版)两个版本。GitLab 是一款免费软件，提供 Git 库管理、代码审查、问题跟踪、活动提要和维基。

Docker 的开源 [GitLab 容器注册很容易与 GitLab 服务的其余部分集成。](https://github.com/docker/distribution)

“开发人员可能希望为私人、公司图像或仅在测试中使用的一次性图像维护他们自己的注册表。GitLab 产品负责人[在一篇博客文章](https://about.gitlab.com/2016/05/23/gitlab-container-registry/)中写道[马克·彭萨克](https://twitter.com/markpundsack)。设置容器注册表的选项来自于 GitLab 的最新版本，8.8.1 版本，于周一发布。

Pundsack 说，在这个版本之前，一个使用 Git 的典型公司为每个项目都有一个存储库托管、基础设施构建和容器映像注册。公司需要许可、配置、连接和维护三个独立的应用程序。每个新项目都需要从头开始配置所有这些应用程序。

此外，微服务的兴起使得公司有必要管理更多的存储库。

GitLab repository manager 简化了这种设置，它提供了一个集成的容器映像注册表，将容器开发完全集成到应用程序开发生命周期中。

## **如何实现**

在一个平滑的系统中，Docker 容器在创建后会自动更新，只要代码发生变化。Docker 注册表是存储和标记图像的地方，所以当你调用 **docker run** 时，它知道调用哪个图像。

使用新的 GitLab 容器注册中心消除了设置和管理另一个服务或使用公共注册中心的需要。它还让开发人员可以灵活地维护他们的私有、公司图像或仅用于测试的图像的注册表。

该注册表包含用户身份验证，因此所有用户和组定义都受到尊重。注册表中已经定义了存储库。GitLab 中同样已经定义了项目。虽然每个项目都可以有一个图像

这里有一个 GitLab CI 配置文件(`**.gitlab-ci.yml**`)的例子，它构建一个映像，标记并上传构建到容器注册表。

```
  build_image:
  image:  docker:git
  services:
  -  docker:dind
  script:
  -  docker login  -u  gitlab-ci-token  -p  $CI_BUILD_TOKEN gitlab.com:5005
  -  docker build  -t  my-group/my-project  .
  -  docker run my-group/my-project  /script/to/run/tests
  -  docker tag my-group/my-project gitlab.com:5005/my-group/my-project:latest
  -  docker push gitlab.com:5005/my-group/my-project:latest
  only:
  -  master

```

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>