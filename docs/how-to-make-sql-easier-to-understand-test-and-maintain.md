# 如何让 SQL 更容易理解、测试和维护

> 原文：<https://thenewstack.io/how-to-make-sql-easier-to-understand-test-and-maintain/>

我们都知道，SQL 通过给我们一种有效的方法来存储、操作和检索数据库中的数据，帮助我们构建更好的应用程序。但是我们也看到过长达数百行的 SQL 语句，这些语句实际上是无法测试和调试的。不要让这些使你远离 SQL。通过模块化代码，您可以使 SQL 更容易理解、更容易测试、更容易更新，甚至更好。

 [克里斯·萨克森

Chris 是 Oracle 数据库的开发人员，他的工作是帮助您充分利用 Oracle 数据库，享受 SQL 带来的乐趣。你可以在 Twitter 上找到他，@ChrisRSaxon，在他的博客上，都是 SQL 的东西。](https://uk.linkedin.com/in/saxonchris) 

模块化提取了 SQL 语句中经常出现的代码，并将它们转化为可重用的组件。每当需要使用这些代码时，只需访问该模块。

如果代码模块中出现 bug，您可以很容易地识别它，并在一个地方修复它。如果你找到一个更好的方法来编码一个模块，这也是适用的。您可以对其进行一次改进，整个 SQL 语句都将从这一变化中受益。在这个过程中，您可以使复杂的查询更简短、更清晰。

换句话说，模块让 SQL 变得更好。

大多数流行的云数据库，如 MySQL、PostgreSQL 和 SQL Server，使您能够用视图和公共表表达式(cte)模块化 SQL。对于下面的例子，我将使用 Oracle 数据库，它有许多选项可以将 [Oracle SQL](https://www.oracle.com/database/technologies/appdev/sql.html?source=:ex:pw:::::TNS_SQL2_A&SC=:ex:pw:::::TNS_SQL2_A&pcode=) 语句分割成可重用的部分。让我们通过一些例子来看看它是如何工作的。

## 将复杂的查询转换成函数

你的老板让你写一个复杂的查询。这必须返回每个拥有三名以上雇员的部门的总工资和平均工资，按地区分组。

第一步是找到至少有三名工作人员的部门。您需要保存每个雇员的工资来计算最终的平均值，所以这里按部门分组是行不通的。

相反，您可以将`count`转换成一个分析函数并过滤其结果。您必须使用子查询来实现这一点，因此您可以使用这样的内嵌视图:

```
select *  from  (
  select department_id,  salary,
 count(*)  over  (  partition by department_id  )  emp#
  from hr.employees  e
)
where  emp# > 3;

```

阅读下面的查询，您将从内到外有效地工作。像这样的简短查询很简单。但是要完成报告，您仍然需要添加连接来查找区域并计算总数。最好将这个子查询放在 with 子句中。

## 用公共表表达式重构查询

`with`子句在语句的顶部定义了 cte。这些是您可以引用的命名子查询——这是向模块化迈出的一步。将前面的查询重构为 CTE，如下所示

```
with employees_with_dept_counts as  (
  select  e.*,
 count(*)  over  (  partition by department_id  )  emp#
  from hr.employees  e
)
  select *  from employees_with_dept_counts
  where  emp# > 3;

```

与内嵌视图相比，这有几个优点:

*   该查询从上到下读取，而不是从内向外读取。这更接近自然语言，有助于可读性。
*   您可以为查询取一个有意义的名称，帮助其他人理解子查询的用途。
*   您可以在查询中重用 CTE，如果它包含您将在一条语句中多次访问的表达式，这将非常有用。

有了 CTE，接下来，您需要找到每个雇员所在的地区。这就需要通过一系列类似这样的表格加入部门:

```
select *  from hr.departments  d
join hr.locations  l
  using  (  location_id  )
join hr.countries  c
  using  (  country_id  )
join hr.regions  r
  using  (  region_id  );

```

此时，您可以将这些连接放在另一个 CTE 中。这样做会导致一个很长的语句，而且您可能还想在其他查询中重复这些连接。这突出了 cte 的两个缺点:

*   命名子查询是查询的本地查询。如果您想在其他 SQL 语句中重用它们，您必须复制并粘贴它们。
*   最后的语句仍然可以很大。虽然 cte 可以帮助您分解单一的查询，但是如果您正在访问许多表，它们仍然是很难理解的。

您可以通过将逻辑放在视图中来克服这两个缺点，这是向模块化迈进的又一步。[在这里，我要指出的是，您可以在我的 [Oracle 数据库世界演讲](https://www.youtube.com/watch?v=ilI5jNlzl1Q)的录音中看到这些实例，或者[您可以参加我和其他数据库专家于 10 月在拉斯维加斯](https://reg.rf.oracle.com/flow/oracle/cloudworld/session-catalog/page/catalog/?search.topic=1651238230807005ZheK&search=saxon&source=:ex:pw:::::TNS_SQL_2_CW_B&SC=:ex:pw:::::TNS_SQL_2_CW_B&pcode=) [Oracle 云世界](https://www.oracle.com/cloudworld/database/?source=:ex:pw:::::TNS_SQL_2_CW_F&SC=:ex:pw:::::TNS_SQL_2_CW_F&pcode=)举办的现场直播。要亲自尝试本文中的演示，请注册一个[永远免费的 Oracle Cloud 帐户](https://www.oracle.com/cloud/free/?source=:ex:pw:::::TNS_SQL_2_C&SC=:ex:pw:::::TNS_SQL_2_C&pcode=)并从 Live SQL 获得[脚本。]](https://livesql.oracle.com/apex/livesql/file/content_M8L62ZY8L3JQ284SNXEH0RKV0.html?source=:ex:pw:::::TNS_SQL_2_D&SC=:ex:pw:::::TNS_SQL_2_D&pcode=)

## 用视图定义可重用的查询

视图存储 SQL 语句的文本。查询视图与在视图中运行语句是一样的。这使您能够定义可以在其他查询中重用的公共连接、表达式或过滤器。您可以像引用常规表一样引用视图。

要将雇员行链接到他们的区域，将上面的连接包装在一个视图中，并将其链接到`employees_with_dept_counts` CTE:

```
create or replace view hr.department_country_details as
  select *  from hr.departments  d
  join hr.locations  l
  using  (  location_id  )
  join hr.countries  c
  using  (  country_id  )
  join hr.regions  r
  using  (  region_id  );

with employees_with_dept_counts as  (
  select  e.*,
 count(*)  over  (  partition by department_id  )  emp#
  from hr.employees  e
)
  select region_name,  salary
  from employees_with_dept_counts  e
  join hr.department_country_details  d
  using  (  department_id  )
  where  e.emp# > 3;

```

要完成报告，您需要按地区分组并添加总计。您可以在上面的最后一个`select`中完成所有这些工作，但是将这个子查询移到另一个 CTE 中将有助于提高可读性。

为了简化报告，最后将最后一个查询放在一个视图中:

```
create or replace view hr.region_summaries as
with employees_with_dept_counts as  (
  select  e.*,
 count(*)  over  (  partition by department_id  )  emp#
  from hr.employees  e
),  filtered_employee_regions as  (
  select region_name,  salary
  from employees_with_dept_counts  e
  join hr.department_country_details  d
  using  (  department_id  )
  where  e.emp# > 3
)
  select region_name,
 sum  (  salary  )  total_salary,
 round  (  avg  (  salary  )  )  mean_salary
  from filtered_employee_regions
  group  by region_name;

```

现在可以通过查询`region_summaries`生成报告。与它所使用的视图相比，这个概要视图有一个很大的缺点。人员计数过滤器被硬编码为三个。您可能希望允许用户在运行时更改这个值。为此，您需要向视图添加一个参数。遗憾的是，这是无效的语法！

无法创建参数化视图限制了它们的重用。为了使用户能够更改每个部门的最少雇员数，您别无选择，只能放弃视图，在需要的地方重新生成完整的查询。

Oracle 数据库有办法解决这个问题: [SQL 宏](https://docs.oracle.com/en/database/oracle/oracle-database/21/lnpls/sql_macro-clause.html?source=:ex:pw:::::TNS_SQL_2_D&SC=:ex:pw:::::TNS_SQL_2_D&pcode=)。让我们看看这在另一个模块化例子中是如何工作的。

## 使用 SQL 宏创建可重用的 SQL 表达式

SQL 宏是定义 SQL 表达式的函数。这些表达式可以是两种类型之一:表或标量。

*   表宏返回一个完整的`select`语句。您可以在查询的`from`子句中使用它们。这些在 Oracle 数据库 19c 和 [Oracle 自治数据库](https://www.oracle.com/autonomous-database/?source=:ex:pw:::::TNS_SQL_2_E&SC=:ex:pw:::::TNS_SQL_2_E&pcode=)中提供
*   标量宏返回一个公式。只要有可能使用 [PL/SQL 函数](https://www.oracle.com/database/technologies/appdev/plsql.html)，就可以使用它们。例如，`select`、`where`和`order by`条款。这些在 Oracle 数据库 21c 和 Oracle 自治数据库中提供

无论类型如何，宏总是以文本的形式返回表达式。您可以在返回字符串中命名函数的任何参数。这些是数据库在解析宏时替换的占位符。

这种解析发生在解析时。在此过程中，数据库用已解析的表达式替换查询中对 SQL 宏的所有调用。它用您在函数调用中为这些参数使用的实际文本替换字符串中的任何参数占位符。

这使您能够创建参数化视图。例如，您可以创建一个表宏来过滤每个部门的雇员:

```
create or replace function employees_filtered_by_dept_size  (
  min_emps integer
)  return clob sql_macro as
  stmt clob;
begin
  stmt  :=  '
with employees_with_dept_counts as (
  select e.*,
     count(*) over ( partition by department_id ) emp#
  from   hr.employees e
)
select  *
from	employees_with_dept_counts
where   emp# >= min_emps';

  return stmt;
end employees_filtered_by_dept_size;
/

```

当您调用这个宏时，数据库会用您传递给这个参数的值替换`min_emps`。以下是使用不同参数调用此函数时最后一个`where`子句的示例:

*   `employees_filtered_by_dept_size ( 3 )`变成了`where emp# >= 3`
*   `employees_filtered_by_dept_size ( :min_count_var )`变为`where emp# >= :min_count_var`
*   `employees_filtered_by_dept_size ( min_count_fn() )`变成了`where emp# >= min_count_fn()`

注意，当传递绑定变量和函数时，*变量或函数本身*成为语句的一部分。它是占位符的文本查找和替换(极客注意:它比这复杂得多，但将其视为对等交换就足够了)。

将 CTE `employees_with_dept_counts`替换为宏`employees_filtered_by_dept_size`是逻辑重用的巨大进步。但是 SQL 宏的威力甚至更大。

通过某一列的计数来过滤查询可能是您想要应用于任何表或列的逻辑。本质上，您有了这个查询模板，根据需要交换了`<source_table>`、`<group_column>`和`<min_count>`:

```
with tab_with_group_counts as  (
  select  t.*,
 count(*)  over  (  partition by  <group_column>  )  grp#
  from <source_table>  t
)
select  *
from tab_with_group_counts
where grp# >= <min_count>;

```

以前，这是动态 SQL 的任务。这很笨重，很难调试，并且很容易让你的应用程序容易受到 SQL 注入的攻击。

SQL 宏允许您将表名和列名作为参数传递，从而避免了这些问题。要做到这一点，使用这些类型首先用[引入多态表函数](https://www.slideshare.net/ChrisSaxon1/polymorphic-table-functions-in-sql):

*   `dbms_tf.table_t` —接受表格标识符
*   `dbms_tf.columns_t` —接受`columns`伪运算符，其中包含列标识符列表

将这些添加到宏中使您能够通过任何列的计数来过滤任何表:

```
create or replace function filter_by_column_count  (
  source_table dbms_tf.table_t,
  group_column dbms_tf.columns_t,
  min_count integer
)  return clob sql_macro as
  stmt clob;
begin
  stmt  :=  '
with tab_with_group_counts as (
  select t.*,
     count(*) over (
       partition by '  ||  group_column  (1)  ||  '
     ) grp#
  from   source_table t
)
select  *
from	tab_with_group_counts
where   grp# > min_count';

  return stmt;
end filter_by_column_count;
/

```

这揭示了表和列参数之间微妙而重要的差异。您将表参数直接放在字符串中，数据库会替您替换。但是 columns 参数是一个数组。SQL 中没有隐式的方法将数组转换成字符串。您必须显式连接中的值。

将原来的宏换成这个通用版本给出:

```
select  r.region_name,
 sum  (  salary  )  total_salary,
 round  (  avg  (  salary  )  )  mean_salary
from filter_by_column_count  (
  hr.employees,  columns  (  department_id  ),  :min_emps
)
join hr.department_country_details  r
using  (  department_id  )
group  by  r.region_name;

```

这比视图`region_summaries`中的原始查询更简洁。其中的每个“表”都封装了复杂的逻辑。

为了进一步简化最终的查询，您也可以将`region_summaries`转换成表格宏。这接受筛选部门所依据的最小员工数。

下面是完整的宏，以及如何调用它的例子:

```
create or replace function region_summaries  (  min_emps integer  )
  return clob sql_macro as
  stmt clob;
begin
  stmt  :=  '
select r.region_name,
   sum ( salary ) total_salary,
   round ( avg ( salary ) ) mean_salary
from   filter_by_column_count (
  hr.employees, columns ( department_id ), min_emps
)
join   hr.department_country_details r
using  ( department_id )
group  by r.region_name';
  return stmt;

end region_summaries;
/

/* Departments with > 1 staff */
select *  from region_summaries  (  1  );

/* Departments with > 4 staff */
select *  from region_summaries  (  4  );

/* Departments with > :min_emps staff */
select *  from region_summaries  (  :min_emps  );

```

## 查看完整的声明

至此，您已经创建了一个模块化、参数化的查询。但是一个重要的问题仍然存在:如何看到整个语句，包括所有被访问的底层表？

Oracle 数据库也有这样的功能。将您的疑问传递给`dbms_utility.expand_sql_text`。这将展开表宏和视图，以显示底层 SQL 中的所有基表和列。

```
declare
  l_clob clob;
begin
  dbms_utility.expand_sql_text  (
  input_sql_text  =>
 q'!select * from region_summaries ( :min_emps )!',
  output_sql_text  =>  l_clob  );
  dbms_output.put_line  (  l_clob  );
end;
/

```

## 结论

长期以来，视图一直是在 SQL 中定义通用逻辑并在其他语句中重用它的一种方式。但是它们不能接受参数限制了这种可能性，从而限制了您使用它们有效地模块化 SQL 代码的能力。

子查询分解(也称为 CTEs，也称为 with 子句)使得将大型查询分解成它们的组件变得更加容易。这也使您能够以与逻辑流相同的顺序编写 SQL。但是 cte 对于每个查询来说都是局部的，所以它们对于跨语句共享逻辑没有什么作用。

Oracle 数据库版本 19c 中 SQL 宏的引入解决了这两个问题。您可以定义完全可参数化的可重用逻辑单元，不仅使用基本数据类型，还使用表名和列名。这使您能够创建可应用于任何表的查询模板。结果是更容易理解、测试和改进的模块化代码。

如上所述，要想看到这些例子，请观看我在甲骨文数据库世界关于这个主题的演讲的录音，或者[参加我在甲骨文云世界的会议](https://reg.rf.oracle.com/flow/oracle/cloudworld/session-catalog/page/catalog/?search.topic=1651238230807005ZheK&search=saxon&source=:ex:pw:::::TNS_SQL_2_CW_B&SC=:ex:pw:::::TNS_SQL_2_CW_B&pcode=)。

如果您想亲自尝试本文中的演示，请注册一个[永远免费的 Oracle 云帐户](https://www.oracle.com/cloud/free/?source=:ex:pw:::::TNS_SQL_2_C&SC=:ex:pw:::::TNS_SQL_2_C&pcode=)，从 Live SQL 中获取[脚本，然后开始动手吧！](https://livesql.oracle.com/apex/livesql/file/content_M8L62ZY8L3JQ284SNXEH0RKV0.html?source=:ex:pw:::::TNS_SQL_2_D&SC=:ex:pw:::::TNS_SQL_2_D&pcode=)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>