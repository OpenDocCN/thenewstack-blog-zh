# 使用 AWS 机密管理器管理 Kubernetes 机密

> 原文：<https://thenewstack.io/managing-kubernetes-secrets-with-aws-secrets-manager/>

在这个系列的[的最后一部分，我介绍了 GoDaddy 的 Kubernetes 外部秘密管理器。在这一期中，我们将利用它来配置由](https://thenewstack.io/godaddys-innovative-project-to-secure-and-rotate-kubernetes-secrets/)[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)的秘密管理器支持的秘密。

GoDaddy 在很大程度上依赖亚马逊网络服务 EKS 来运行他们的 Kubernetes 基础设施。GoDaddy 的工程团队意识到，EKS 和其他托管服务(如 Amazon Secrets Manager 和 AWS Systems Manager)之间没有集成。为了弥合这两者之间的差距，他们构建了一个 Kubernetes 定制控制器和一个名为 External Secrets 的定制资源定义，它可以管理和轮换来自任何 Kubernetes 部署的 AWS Secrets Manager 的密钥。

让我们看看 Kubernetes 的外部秘密在行动。

**先决条件:**

1.主动 AWS 订阅
2。AWS CLI
3。库伯内特星团

首先，我们将创建一个 AWS 身份访问管理(IAM)策略和一个 AWS IAM 用户，该用户拥有从 AWS Secrets Store 读取机密的足够权限。在下一步中，我们将部署与 IAM 用户凭证相关联的 Kubernetes 外部机密管理器 Helm 图表。之后，我们在 [AWS Secrets 存储中创建一个秘密，并将其指向在本地集群中创建的 Kubernetes 外部秘密](https://thenewstack.io/7-tips-for-cutting-down-your-aws-kubernetes-bill/)。最后，我们更新基于云的秘密，并验证它是否在 Kubernetes 集群中被刷新。

## 步骤 1:创建 AWS IAM 策略和 IAM 用户来访问机密存储

让我们从定义访问机密所需的 IAM 策略开始。用以下内容创建一个 JSON 文件，并保存在`extsecpol.json`文件中。

```
{
    "Version":  "2012-10-17",
    "Statement":  [
        {
            "Effect":  "Allow",
            "Action":  [
                "secretsmanager:GetRandomPassword",
                "secretsmanager:GetResourcePolicy",
                "secretsmanager:GetSecretValue",
                "secretsmanager:DescribeSecret",
                "secretsmanager:ListSecretVersionIds",
                "secretsmanager:ListSecrets"
            ],
            "Resource":  "*"
        }
    ]
}

```

定义环境变量并继续创建 IAM 策略和角色。

```
POLICYNAME="ExternalSecurityPolicy"
IAMUSERNAME="SecretReader"

```

```
aws iam create-policy  \
  --policy-name  $POLICYNAME  \
  --policy-document file://extsecpol.json

```

在环境变量中检索并存储策略的 Amazon 资源名称(ARN)。

```
export POLICYARN=$(aws iam list-policies  --query  'Policies[?PolicyName==`ExternalSecurityPolicy`].{ARN:Arn}'  --output text)

```

确保用正确的策略名称替换`ExternalSecurityPolicy`。

基于上述策略创建 IAM 用户。

```
aws iam create-user  --user-name  $IAMUSERNAME
aws iam attach-user-policy  --user-name  $IAMUSERNAME  --policy-arn  $POLICYARN
aws iam create-access-key  --user-name  $IAMUSERNAME

```

从最后一个命令的输出中，检索与用户相关联的访问密钥和秘密密钥。

![](img/b04ede21168681cf3928a97e6d6469a8.png)

## 第二步:安装 Kubernetes 外部秘密掌舵图表

在部署 Kubernetes 外部秘密定制控制器之前，我们需要将 AWS AccessKey 和 SecretAccessKey 注册为 Kubernetes 秘密，注册在定制控制器运行的同一个名称空间中。

让我们从创建名称空间开始。

```
kubectl create namespace external-secrets

```

将 AccessKey 和 SecretAccessKey 编码成 base64，变成 Kubernetes 的秘密。

```
echo  -n  "AKIATWRVOGK5V3ZITMWO"  |  base64
echo  -n  "6nGIROhIkZGFFvvhkTFWefX5ONFCZyvZZdTIDllR"  |  base64

```

用 base64 编码值创建一个名为`aws-secrets.yaml`的文件，并用`kubectl`命令应用它。

```
apiVersion:  v1
kind:  Secret
metadata:
  name:  aws-credentials
type:  Opaque
data:
  id:  QUtJQVRXUlZPR0s1VjNaSVRNV08=
  key:  Nm5HSVJPaElrWkdGRnZ2aGtURldlZlg1T05GQ1p5dlpaZFRJRGxsUg==

```

```
kubectl apply  -f  aws-secrets.yaml  -n  external-secrets

```

让我们通过定义下面的`values.yaml`文件:
将秘密与舵图联系起来

```
env:
  AWS_REGION:  ap-south-1
  AWS_DEFAULT_REGION:  ap-south-1

envVarsFromSecret:
  AWS_ACCESS_KEY_ID:
    secretKeyRef:  "aws-credentials"
    key:  "id"
  AWS_SECRET_ACCESS_KEY:
    secretKeyRef:  "aws-credentials"
    key:  "key"

```

用您创建密码的区域替换 AWS_REGION。

现在，我们准备安装 Kubernetes 外部秘密舵图。

```
helm repo add external-secrets https://external-secrets.github.io/kubernetes-external-secrets/
helm repo update

```

```
helm install  \
  --generate-name  \
  --namespace external-secrets  \
  external-secrets/kubernetes-external-secrets  \
  --values values.yaml

```

验证部署并确保没有错误。

```
kubectl get pods  -n  external-secrets

```

### ![](img/e2325ea03b6f30d0c32a23a0284fb973.png)

## 步骤 3:在 AWS 秘密管理器中创建秘密

Kubernetes 集群通过外部 Secrets 控制器连接到 AWS Secrets Manager 后，我们就可以在云中创建秘密并将它们传播到本地集群。

```
aws secretsmanager create-secret  \
  --region ap-south-1  \
  --name edgesecrets/dbcred  \
  --secret-string  '{"username":"admin","password":"password@1234"}'

```

![](img/c96bededa3cef77043e974b984641d3c.png)

在下一步中，我们将创建一个外部秘密，指向在 AWS Secrets Manager 中创建的秘密。

## 步骤 4:在 Kubernetes 中创建一个外部秘密资源

让我们创建一个名为`dbcred`的外部秘密定制资源，它与上一步在默认名称空间中创建的基于云的秘密相关联。

```
apiVersion:  "kubernetes-client.io/v1"
kind:  ExternalSecret
metadata:
  name:  dbcred
spec:
  backendType:  secretsManager
  region:  ap-south-1
  dataFrom:
    -  edgesecrets/dbcred

```

```
kubectl create  -f  dbcred-external.yaml

```

验证外部机密和 Kubernetes 机密是否已成功创建。

![](img/fcaa456af106e64a3f6fc2057b9766d0.png)



让我们通过解码 base64 值来检索秘密的值。

```
kubectl get secret dbcred  -o  yaml

```

T32

```
echo  " YWRtaW4="  |  base64  -d

```

```
echo  "cGFzc3dvcmRAMTIzNA=="  |  base64  -d

```

![](img/486fe95dfedcd9aded4a1ecc5716914a.png)

访问 AWS 管理控制台以检索机密值。

![](img/f51b39417745971c96b72f75324faee1.png)
如您所见，在 AWS 控制台中显示的相同值在 Kubernetes 集群中也可用。

## 步骤 5:旋转/刷新秘密

现在让我们修改存储在 AWS Secrets Store 上的秘密，看看它是否会自动传播到 Kubernetes 集群。

运行以下命令将密码更改为新值:

```
aws secretsmanager update-secret  \
        --region ap-south-1  \
        --secret-id edgesecrets/dbcred  \
        --secret-string  '{"username":"admin","password":"password@0000"}'

```

从 Kubernetes 集群中检索密码值。

```
kubectl get secret dbcred  -o  yaml

```

![](img/662deb299b23716e66dfa8ed45511a2f.png)

```
echo  "cGFzc3dvcmRAMDAwMA=="  |  base64  -d

```



正如我们所看到的，更新后的密码在 Kubernetes 集群中立即可用。

### 步骤 6:清理资源

删除 Kubernetes 资源:

```
kubectl delete  -f  dbcred-external.yaml
helm ls  -n  external-secrets
helm delete RELEASE_NAME
kubectl delete  -f  aws-secrets.yaml  -n  external-secrets

```

删除 AWS IAM 策略:

```
IAMUSERNAME=SecretReader
export POLICYARN=$(aws iam list-policies  --query  'Policies[?PolicyName==`ExternalSecurityPolicy`].{ARN:Arn}'  --output text)
aws iam detach-user-policy  --user-name  $IAMUSERNAME  --policy-arn  $POLICYARN

```

删除 AWS IAM 用户:

```
export ACCESSKEYID=$(aws iam list-access-keys  --user-name SecretReader  --query  'AccessKeyMetadata[0].AccessKeyId'  --output text)
aws iam delete-access-key  --user-name  $IAMUSERNAME  --access-key-id  $ACCESSKEYID

aws iam delete-user  --user-name  $IAMUSERNAME
aws iam delete-policy  --policy-arn  $POLICYARN

```

删除 AWS 秘密管理器秘密:

```
aws secretsmanager delete-secret  --secret-id edgesecrets/dbcred

```

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>