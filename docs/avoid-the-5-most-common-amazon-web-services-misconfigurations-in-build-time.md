# 在构建时避免 5 种最常见的亚马逊网络服务错误配置

> 原文：<https://thenewstack.io/avoid-the-5-most-common-amazon-web-services-misconfigurations-in-build-time/>

[](https://www.linkedin.com/in/nimrod-kor-928332137/)

 [尼姆罗德·科尔

尼姆罗德·科尔是 Bridgecrew 的解决方案架构师和创始团队成员，他在 bridge crew 领导云安全研究项目并帮助团队采用成文的云安全。](https://www.linkedin.com/in/nimrod-kor-928332137/) [](https://www.linkedin.com/in/nimrod-kor-928332137/)

基础设施即代码(IaC)使云配置更快、更简单、更具可扩展性。它还让我们有机会做出相对简单的改变，这些改变可以对我们的云安全状况产生持久的影响。

为了证明这一点，我们分析了跨 IaC 模块的最常见的 Amazon Web Services (AWS)安全错误。在本帖中，我们将关注最常见的不合规 AWS 政策以及与之相关的风险。我们还将分享修复每个错误所需的简单构建时 Terraform 配置。

## 确保存储在 S3 存储桶中的所有数据都在静态下安全加密

S3 支持使用 AES-256 加密标准的简单、免费的加密。我相信我们都知道，[静态 S3 桶加密](https://docs.bridgecrew.io/docs/s3_14-data-encrypted-at-rest)对于防止您的数据暴露给任何可能访问存储您数据的硬盘的人非常重要。

为了符合 PCI-DSS 和 NIST-800 所要求的这一策略，需要在相关存储桶上默认设置加密。这将导致保存到该 S3 存储桶的所有后续项目被自动加密。

将以下块添加到 Terraform S3 资源，以添加 AES-256 加密:

```
server_side_encryption_configuration  {
  rule  {
    apply_server_side_encryption_by_default  {
      sse_algorithm  =  "AES256"
    }
  }
}

```

## 确保发布配置 EBS 中存储的所有数据都已安全加密

[亚马逊弹性块存储](https://aws.amazon.com/ebs/) (EBS)卷支持内置加密，但默认不加密。EBS 启动配置指定 Amazon EC2 自动缩放启动配置，自动缩放组可以使用该配置来配置 Amazon EC2 实例。

当整个 EBS 卷被加密时，存储在该卷上的静态数据、磁盘 I/O、从该卷创建的快照以及 EBS 和 EC2 之间传输的数据都被加密。

对静态数据进行加密可以确保没有未经授权的实体能够访问这些数据。PCI-DSS 也需要遵守此政策。为了防止在您的 Terraform 模块中出现此 AWS 错误，请确保为 EBS 启动配置启用了加密:

```
resource  "aws_launch_configuration"  "as_conf"  {
  name_prefix  =  "terraform-lc-example-"
  image_id  =  data.aws_ami.ubuntu.id
  instance_type  =  "t2.micro"
+  encrypted  =  enabled

```

## 确保启用客户创建的 cmk 的轮换

AWS [密钥管理服务](https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html) (KMS)允许客户轮换备份密钥。这是 KMS 内存储密钥材料的位置，并与客户主密钥(CMK)的密钥 ID 相关联。备份密钥用于执行加密操作，如加密和解密。自动密钥轮换目前保留所有以前的备份密钥，允许加密数据透明地解密。

一个密钥不旋转的时间越长，用它加密的数据就越多，它被泄露的可能性就越大。暴露这样的密钥会暴露使用该密钥加密的所有数据，因此强烈建议每年轮换加密密钥。

默认情况下，自动 [CMK 旋转](https://docs.bridgecrew.io/docs/logging_8#procedure)是不启用的(这是在谷歌云！)，但建议这样做有助于降低泄密密钥的潜在影响。这也是支持 PCI-DSS、CSI 和 ISO27001 合规性的一项要求。

要修复地形中的错误配置，请打开按键旋转:

```
resource  "aws_kms_key"  "kms_key_1"  {
  description  =  "kms_key_1"
  deletion_window_in_days  =  10
  key_usage  =  "ENCRYPT_DECRYPT"
  is_enabled  =  true
  +  enable_key_rotation  =  true
}

```

## 确保 DynamoDB 时间点恢复(备份)已启用

[亚马逊 DynamoDB 的时间点恢复](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/PointInTimeRecovery_Howitworks.html) (PITR)允许您只需点击一下鼠标就可以恢复 DynamoDB 表数据。这为您挖掘数据泄露和数据损坏攻击提供了一个故障保险，并且是 PIC-DSS、CIS 和 ISO27001 的一个要求。

但是，要创建和访问 DynamoDB 备份，您需要启用 PITR，它提供可以使用各种编程参数控制的连续备份。

通过在 DynamoDB 表上配置 point_in_time 配置来修复这个错误配置

```
resource  "aws_dynamodb_table"  "basic-dynamodb-table"  {
  name  =  "GameScores"
  billing_mode  =  "PROVISIONED"
  read_capacity  =  20
  write_capacity  =  20
  hash_key  =  "UserId"
  range_key  =  "GameTitle"
+  point_in_time-recovery  =  enabled

```

## 确保启用推送时 ECR 图像扫描

[Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html) 支持使用通用漏洞和暴露(CVEs)数据库扫描容器图像中的漏洞。建议您在每次推送时启用 ECR，以帮助识别不良映像和映像中引入漏洞的特定标记。

[作为 ISO27001 合规性的一部分，需要在每次推送时启用 ECR 扫描](https://docs.bridgecrew.io/docs/general_8)。要修复构建时资源，请将`scan_on_push`设置为`true` :

```
resource  "aws_ecr_repository"  "foo"  {
  name  =  "bar"
  image_tag_mutability  =  "MUTABLE"

  image_scanning_configuration  {
+  scan_on_push  =  true
  }
}

```

## 确保存储在 SQS 队列中的所有数据都是加密的

[亚马逊简单队列服务](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)(亚马逊 SQS)允许加密通过每个队列发送的消息。这允许另一个级别的数据访问管理，通过基于消息加密拒绝对特定数据的访问，并通过加密保护敏感数据。

如果您在受监管的市场中运营，例如针对医疗保健的 HIPAA、针对金融的 PCI DSS 以及针对政府的 FedRAMP，您需要确保在此服务中传递的敏感数据消息在静态时是加密的。

通过指定 SQS 应该用来加密 SQS 配置块上的数据的 KMS 密钥来避免[这种错误配置](https://docs.bridgecrew.io/docs/general_16-encrypt-sqs-queue)。

在 Terraform 中，以秒为单位设置亚马逊 SQS 在再次调用 AWS KMS 之前可以重用数据密钥来加密或解密消息的时间长度。

```
resource  "aws_sqs_queue"  "terraform_queue"  {
  name  =  "terraform-example-queue"
+  kms_master_key_id  =  "alias/aws/sqs"
+  kms_data_key_reuse_period_seconds  =  300
}

```

## 结论

正如您所看到的，修复 IaC 错误配置通常需要向已经存在的块添加简单的缺失配置参数，或者将不正确的值更改为符合状态。然而，做出这些小小的改变会产生重大的影响，因为它们会影响未来的部署。

通过在构建时在 IaC 模板和模块中实施通用的安全策略，您可以修复现有的问题并防止部署新的错误配置。这也是一种节省时间的好方法，可以在新的基础设施启动时发现生产中不断出现的问题。这就是为什么我们在 [Bridgecrew](https://bridgecrew.io) 认为 IaC 对于在云环境中不断发展的组织来说是必不可少的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>