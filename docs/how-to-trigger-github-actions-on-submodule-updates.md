# 如何在子模块更新时触发 GitHub 动作

> 原文：<https://thenewstack.io/how-to-trigger-github-actions-on-submodule-updates/>

[](https://www.linkedin.com/in/kevin-luu-3485a01a/)

 [凯文·卢

凯文是 Release 的集成工程师。](https://www.linkedin.com/in/kevin-luu-3485a01a/) [](https://www.linkedin.com/in/kevin-luu-3485a01a/)

在这里的[发布](https://hubs.li/Q011Rfby0)，我们用短暂的环境来增强发布自动化。

我们最近与一个利用 git 子模块的客户合作，请求我们帮助在每次子模块更新时触发 [ReleaseHub](https://hubs.li/Q011Rfby0) 上的短暂环境。

如果您不知道子模块是什么并且很好奇，您可以在这里找到更多信息[。](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## **客户场景**

 [维基·科布林斯基

Vicky 是 Release 的创始工程师。](https://www.linkedin.com/in/vickykoblinski) 

客户有一个 GitHub 存储库，我们称之为父存储库，它使用了几个依赖的子模块。

这些子模块存储在一个`.gitmodules`文件中。

客户想要一个定制的 GitHub 动作，以便在任何子模块更新时触发，从而在父存储库上创建一个新的分支，针对主分支创建一个 pull 请求，从而构建一个新的临时环境来测试和验证新的更改。

## **如何在 GitHub 动作中使用子模块**

你可以在 GitHub 行动市场[这里](https://hubs.li/Q013qdRq0)找到我们发布的 GitHub 行动。

假设您已经在 GitHub 存储库中配置并运行了 [git 子模块](https://git-scm.com/docs/git-submodule)，要使用 GitHub 动作，我们必须首先创建一个 GitHub 令牌，它可以读取/写入父存储库并作为`RELEASE_HUB_SECRET`存储在 secrets 中。

如果您在创建 GitHub 令牌时需要帮助，您可以在此处查看文档:[https://docs . GitHub . com/en/authentic ation/keeping-your-account-and-data-secure/creating-a-personal-access-token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

要存储机密，可以在这里查看文档:[https://docs . github . com/en/actions/security-guides/encrypted-secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

接下来，您必须在中创建一个新文件。github/workflows/sub module-update . yml 并粘贴以下代码:

```
---
name:  Submodule Updates

#############################
# Start the job on all push #
#############################
on:
  push:
    branches-ignore:  [master,  main]
  pull_request:
    branches:  [master,  main]

###############
# Set the Job #
###############
jobs:
  build:
    name:  Submodule update
    runs-on:  ubuntu-latest
    env:
      PARENT_REPOSITORY:  'org/example-repository'
      CHECKOUT_BRANCH:  'main'
      PR_AGAINST_BRANCH:  'main'
      OWNER:  'org'

    steps:
      ##########################
      # Checkout the code base #
      ##########################
      -  name:  Checkout Code
        uses:  actions/checkout@v2

      ####################################
      # Run the action against code base #
      ####################################
      -  name:  run action
        id:  run_action
        uses:  releasehub-com/github-action-create-pr-parent-submodule@v1
        with:
          github_token:  ${{  secrets.RELEASE_HUB_SECRET  }}
          parent_repository:  ${{  env.PARENT_REPOSITORY  }}
          checkout_branch:  ${{  env.CHECKOUT_BRANCH}}
          pr_against_branch:  ${{  env.PR_AGAINST_BRANCH  }}
          owner:  ${{  env.OWNER  }}

```

现在，我们可以调整一些参数。

1.  首先，您可以选择 Github 动作的触发方式，是推还是拉。
2.  接下来是 env 块中的环境变量。
    1.  您需要更改`PARENT_REPOSITORY`来指向您的父存储库。
    2.  接下来，您可以指定想要在父`REPOSITORY`上检出哪个分支。
    3.  之后，您可以选择父存储库的哪个分支来创建一个 pull 请求。
    4.  最后但同样重要的是，我们需要更新`OWNER`字段。

现在，您应该能够提交和推送您的更改，并根据您配置的方式观察 GitHub 动作触发。

## **根据您的工作流程进行定制**

下面是 GitHub 资源库的链接:[https://GitHub . com/release hub-com/GitHub-action-create-pr-parent-sub module](https://github.com/releasehub-com/github-action-create-pr-parent-submodule)

以下是 GitHub 市场的链接:[https://GitHub . com/market place/actions/GitHub-action-sub module-updates](https://github.com/marketplace/actions/github-action-submodule-updates)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>