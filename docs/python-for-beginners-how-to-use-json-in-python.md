# Python 初学者:如何在 Python 中使用 JSON

> 原文：<https://thenewstack.io/python-for-beginners-how-to-use-json-in-python/>

JSON 是一种优秀的存储和传输数据的方式。最近，我写了一篇关于如何使用 JSON 的[介绍，并且考虑到我们也已经深入](https://thenewstack.io/an-introduction-to-json/) [Python](https://thenewstack.io/python-for-beginners-how-to-build-a-gui-application/) 的[兔子洞](https://thenewstack.io/yet-more-python-for-beginners-saving-input-to-a-file/)中[了，我认为通过演示如何在 Python 中利用 JSON 的力量将所有这些结合起来是一个很好的方式。](https://thenewstack.io/an-introduction-to-python-for-non-programmers/)

Python 通过一个名为 JSON 的包内置了对 JSON 的支持，并将 JSON 视为类似于字典。在 Python 中，JSON 支持基本类型(比如字符串和数字)以及嵌套列表、元组和对象。

但是为什么要在像 Python 这样简单的语言中使用 JSON 呢？

简单。JSON 不仅易于理解，因为它的键:值对，而且它还经常被用作一种通用的数据格式，用于从 API 和配置文件中存储和获取数据。换句话说，很多其他系统、应用程序和服务已经使用 JSON 来存储和传输数据，那么为什么您不想在 Python 中使用它呢？

也就是说，让我们看看如何在 Python 代码中使用 JSON。

## 你好，世界！

是的，我们回到了我们最喜欢的应用程序，Hello world！我们将使用优秀的 Python 和 JSON 创建这个简单的应用程序。

我们要做的第一件事是创建我们的 Python 脚本。打开一个终端窗口(我在安装了 Python 的 Linux 上演示)，用以下命令创建新文件:

`nano hello-world.py`

要在您的 Python 代码中使用 JSON，我们必须做的第一件事是导入 JSON 库，其中包含条目:

我们的下一行包含实际的 JSON 条目，如下所示:

```
sample_json  =   '{ "name1":"Hello,", "name2":"World!"}'

```

因为我们使用 json，所以我们必须使用 JSON 库中的一个特殊函数，称为 *loads* 。这将从 *sample_json* 加载 JSON 数据，并将其分配给变量 *data* 。这一行看起来像这样:

```
data  =  json.loads(sample_json)

```

最后，我们打印存储在*数据*中的信息，代码为:

```
print(f'{data["name1"]} {data["name2"]}')

```

保存并关闭文件。使用命令运行应用程序:

您应该看到打印出来的:

`Hello, World!`

简单！让我们变得复杂一点。我们将创建一个简单的 Python 脚本，它使用 JSON 作为字典，然后我们将看到如何将数据打印为无格式和有格式的结果。

使用以下命令创建新脚本:

`nano dict.py`

显然，第一行将导入 JSON 库:

接下来，我们使用 JSON 键:值对构建我们的字典，如下:

```
my_dictionary  =  {
"name":  "Jack Wallen",
"job_title":  "Writer",
"company_name":  "The New Stack",
"speciality":  "Linux",
"emails":  [{"email":  "jack.wallen@example.com",  "type":  "work"}],
"my_neighbor":  False
}

```

接下来，我们将在 my_dictionary 对象上使用 JSON 中的 dumps 函数，代码如下:

```
unformatted_json  =  json.dumps(my_dictionary)

```

最后，我们将以无格式的方式打印 JSON 数据，代码如下:

我们的整个脚本看起来像这样:

```
import json

my_dictionary  =  {
    "name":  "Jack Wallen",
    "job_title":  "Writer",
    "company_name":  "The New Stack",
    "speciality":  "Linux",
    "emails":  [{"email":  "jack.wallen@example.com",  "type":  "work"}],
    "my_neighbor":  False
}

unformatted_json  =  json.dumps(my_dictionary)
print(unformatted_json)

```

保存并关闭文件。运行时使用:

`python3 dict.py`

这个应用程序的输出将看起来像这样:

```
{"name":  "Jack Wallen",  "job_title":  "Writer",  "company_name":  "The New Stack",  "speciality":  "Linux",  "emails":  [{"email":  "jack.wallen@example.com",  "type":  "work"}],  "my_neighbor":  false}

```

我们实际上可以用更标准的 JSON 格式打印出来，而不是打印出无格式的文本。为此，我们必须首先在 *my_dictionary* 部分下添加一个类似于
的部分

```
formatted_json  =  json.dumps(
  my_dictionary,
  indent  =  4,
  separators  =  (", ",  " = "),
  sort_keys  =  True
)

```

上面的部分所做的是使用 JSON 的 dumps 函数，然后用缩进和双引号分隔符格式化 *my_dictionary* ，并按关键字对输出字典进行排序(用 *sort_keys = True* )，同时将数据分配给 *formatted_json* 变量。

在该部分下，我们打印字典，行是:

我们的整个脚本看起来像这样:

```
import json  

my_dictionary  =  {
    "name":  "Jack Wallen",
    "job_title":  "Writer",
    "company_name":  "The New Stack",
    "speciality":  "Linux",
    "emails":  [{"email":  "jack.wallen@example.com",  "type":  "work"}],
    "my_neighbor":  False
}

formatted_json  =  json.dumps(
  my_dictionary,
  indent  =  4,
  separators  =  (", ",  " = "),
  sort_keys  =  True
)

print(formatted_json)

```

保存并关闭文件。如果使用以下命令运行新脚本:

`python3 dict.py`

输出应该是这样的:

```
{
    "company_name"  =  "The New Stack",
    "emails"  =  [
        {
            "email"  =  "jack.wallen@example.com",
            "type"  =  "work"
        }
    ],
    "job_title"  =  "Writer",
    "my_neighbor"  =  false,
    "name"  =  "Jack Wallen",
    "speciality"  =  "Linux"
}

```

## 从文件中读取 JSON

假设您有一个很长的 JSON 格式的员工数据文件。这个文件可能被命名为 **data.json** ，看起来像这样:

```
{
     "employee_details":  [
            {
               "employee_name"  :  "Jack Wallen",
               "employee_email"  :  "jack.wallen@example.com",
               "employee_title"  :  "writer"
            },
            {
               "employee_name"  :  "Olivia Nightingale",
               "employee_email"  :  "olivia.nightingale@example.com",
               "employee_title"  :  "editor"
            }
     ]
}

```

我们有两个员工的信息，以 JSON 格式显示。

现在，我们读入数据的 Python 应用程序(名为 read_data.py)可能看起来像这样(带有注释以供解释):

```
# Import the JSON library
import json

# Open our JSON file named data.json
f  =  open('data.json')

# returns JSON object as a dictionary
data  =  json.load(f)

# Iterate through the entire data.json list
for  i  in data['employee_details']:
    print(i)

# Close the data.json file
f.close()

```

保存并关闭文件。使用以下命令运行应用程序:

`python3 read_data.py`

应用程序的输出看起来会像这样:

```
{'employee_name':  'Jack Wallen',  'employee_email':  'jack.wallen@example.com',  'employee_title':  'writer'}
{'employee_name':  'Olivia Nightingale',  'employee_email':  'olivia.nightingale@example.com',  'employee_title':  'editor'}

```

这就对了！您已经在 Python 应用程序中使用了 JSON。正如你所想象的，这种并置的可能性是无限的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>