---
title: SAP 中的 SELECT 语句的语法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f57cac0673a6520de4b0d881527bbc7b670ca1b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-a-select-statement-in-sap"></a>SAP 中的 SELECT 语句的语法
以下各节描述了用于实现针对选择查询的语法规范[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 请注意，在某些情况下，语法是基本 TRANSACT-SQL 语法的稍有不同。  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 其中：  
  
-   **<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`  
  
-   **<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`  
  
-   **\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`  
  
 支持的条件和表达式是：  
  
-   **\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`  
  
-   **\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`  
  
 其中 **\<const\>** = `integer | real | string | ? | NULL | xml_element`。  
  
 **选项关键字的值**  
  
 你可以指定作为选项`OPTION '<option>'`，其中 `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`  
  
-   **No_conversion**选项：  
  
    -   如果**no_conversion**使用选项，然后使用等效的.NET 类型公开表中的字段。 有关 SAP 数据类型的.NET 等效项的信息，请参阅[基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)。  
  
    -   如果**no_conversion**不使用选项，并且如果字段没有转换退出定义，然后使用等效的.NET 类型公开表中的这些字段。 有关 SAP 数据类型的.NET 等效项的信息，请参阅[基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)。  
  
    -   当**no_conversion**不使用选项，如果字段具有转换和退出定义然后.NET 字符串作为公开表中的这些字段。  
  
-   当设置为**batchsize\<大小\>**，SELECT 语句的执行将导致多个调用，以使到 SAP 系统，并在每个调用中，仅\<大小\>数记录检索。 例如，如果你指定 batchsize 100，SELECT 查询检索仅在 SAP 系统每次调用中的 100 条记录。 如果**batchsize\<大小\>**未指定，则默认值为 10000 假设批次大小。 请注意，应指定批次大小基于计算机和的行数的物理内存中 SAP 系统的最佳值。 指定批大小的最佳值中的失败可能会导致内存不足异常。  
  
-   当设置为**disabledatavalidation**、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证 DAT、 TIMS 和 NUMC 列中存在的值，但改为将它们作为字符串进行公开。  
  
     这是 ADO.NET 客户端无法从 DAT、 TIMS 和 NUMC 列中具有无效的数据的 SAP 表中检索数据的方案中十分有用。 由于 SAP 允许无效的数据必须存在于 DAT、 TIMS 和 NUMC 列，ADO.NET 客户端尝试读取的数据将不能分析无效的数据，并将引发异常。 如果**disabledatavalidation**上 SELECT 查询中，设置选项[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会分析无效的数据，但字符串形式提取它们。  
  
> [!IMPORTANT]
>  你必须始终提供值选项关键字在单引号中，例如，*disabledatavalidation*。  
  
 有关示例语句，请参阅[SELECT 语句示例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)。  
  
## <a name="predicates-syntax"></a>谓词语法  
 以下示例指定在 SELECT 语句中使用谓词的语法：  
  
 `Predicate`：  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 `Condition`：  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 `Expr`：  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 `LExpr`：  
  
```  
ColumnName  
```  
  
 `RExpr`：  
  
```  
Const | PlaceHolder  
```  
  
 `ColumnName`：  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 `Tablename`：  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a>调用的 SELECT 语句时的注意事项  
 本部分列出你必须使用在 SELECT 语句时需要牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
-   当在参数或查询中指定日期时间值，以字符串形式提供的值。 提供的 SAP 日期时间格式的日期时间字符串。  
  
    -   `SAP date format`: YYYYMMDD  
  
         例如，日期 2004 年 11 月月 10 日 SAP 查询中是明示"20041110"。  
  
         日期 2004 年 11 月月 10 日 SAPParameter p1 中是字符串 p1。值 ="20041110"。  
  
    -   `SAP time format`: HHMMSS  
  
         例如，时间 10:34:32 SAP 查询中是明示"103432"。  
  
         时间 10:34:32 SAPParameter p2 中是字符串 p2。值 ="103432"。  
  
     对于 SELECT 语句中，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`DATE`字段值作为.NET`System.DateTime`对象，并返回`TIME`字段值作为`System.TimeSpan`对象。 如果 SAP 的值`DATE`对象是否小于允许 SQL Server 最小值 (`1/1/1753`)，则[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回此最小值`1/1/1753`。  
  
-   在 TOP 子句的 SELECT 查询，当使用特殊字符"#"、"^"，"&"和"%"之前或之后一个整数，将忽略特殊字符，尽管不引发任何错误消息。 例如，以下将忽略 TOP 子句的 SELECT 查询中：  
  
     \#5，5 ^，%5%，或 & 5  
  
     但是，使用这些字符之间整数，如下所示 5 5 美元，会引发错误。  
  
-   在表的架构中返回的列名称将返回为所有大写字符。 例如，将查询结果集的字段上`Last Name`返回的列标题`LAST NAME`。 若要避免唯一性建议冲突，使用 SELECT 语句中全部大写。  
  
-   LIKE 子句的 SELECT 查询中的百分号、"%"（对于零个或多个字符的任意字符串） 和下划线， **"_"** （适用于任何单个字符），都是允许的特殊字符。 所有其他特殊字符被视为字符串值，并将忽略。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用 Z_EXTRACT_DATA_OO RFC SAP 系统上执行 SELECT 查询。 RFC 支持满足以下条件的表中读取数据：  
  
    -   为表的 TabClass 是 TRANSP、 群集或池。  
  
    -   TabClass 是视图且 ViewClass 是 D 或 P.  
  
     请确保 SELECT 语句满足这些条件的表中读取数据。  
  
-   可能需要超过 255 个字符，例如字符串、 RAWSTRING、 LRAW、 VARC 和 LCHAR 的数据类型的值不能在 SELECT 查询。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用随自定义 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，Z_EXTRACT_DATA_OO，SAP 系统上执行 SELECT 查询。 此自定义的 RFC 不支持任何可能需要超过 255 个字符的数据类型。  
  
-   列或多个在 SELECT 语句中支持的字段的最大数目为 1000年。  
  
-   支持的 WHERE 子句中谓词的最大数目为 100。  
  
-   不支持在同一 SELECT 语句中多次选择的相同字段。 自定义 RFC (Z_EXTRACT_DATA_OO) 由[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从之前执行的语句中删除重复的字段。 例如，此语句：  
  
     `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
     执行，就好像写入形式与此语句类似：  
  
     `SELECT BUKRS from T001`  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 在 SELECT 语句中不支持重复的别名名称。 因此，以下 SELECT 语句将引发错误：  
  
    ```  
    SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 不支持具有重复列名的 SELECT 语句。 因此，以下 SELECT 语句将引发错误：  
  
    ```  
    SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
    ```  
  
-   SAP 不存储在表中的 NULL 值。 因此，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持在 SELECT 语句中的"IS NULL"值。 因此，以下 SELECT 语句将引发错误：  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 不支持在 SELECT 语句中的 ORDER BY 子句。 因此，以下 SELECT 语句将引发错误：  
  
    ```  
    SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 不支持指定星号 （*） 以在 SAP 表中选择所有字段。 因此，以下 SELECT 语句将引发错误：  
  
    ```  
    SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     若要选择所有字段，你必须单独指定字段名称。  
  
-   作为 SELECT 语句的一部分，你可以指定 SELECT 语句的输出将写入的文件。 但是，如果输出文件位于网络共享上，确保在其下运行 SAP 服务的 SAP 服务帐户具有的网络共享的写入权限。 例如：  
  
    ```  
    SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     在前面的示例中，SAP 服务帐户必须具有名称"共享。"的网络共享的写入权限  
  
-   SELECT 语句使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SELECT 查询中支持的自变量值的参数名称。 但是，请确保你遵循这些规则与参数名称：  
  
    -   在选择的查询中，"@"符号必须位于之前的参数名称。  
  
    -   "@"符号后面必须跟一个字母字符 （A 到 Z 或 a 到 z）。  
  
    -   参数名称只能包含字母数字字符 (A-Z、 a 到 z 或 0-9) 和特殊字符。 可以包含参数名称中的唯一特殊字符是下划线"_"和哈希"#"。  
  
-   对视图运行 SELECT 查询时，请确保基表的所有主键列也会呈现在视图中。 此外，作为一种做法，你必须将列也标记为在视图中的主键列。  
  
     如果主键列不存在的视图中，选择查询视图上的将导致异常。  
  
-   选择字段类型 LRAW 的表运行 SELECT 查询时，请确保选择相应的 PREC 字段。 此外，PREC 字段必须紧跟在 SELECT 子句中的 LRAW 字段之前显示。  
  
     在表中的每个 LRAW 字段均 LRAW 字段中存储的数据的长度的相应 PREC 字段。 而无需 PREC 字段的 SELECT 子句中指定只 LRAW 字段可能会导致不正确所提取的数据。  
  
-   在 SAP 系统中，字符比较是区分大小写。 因此，以下两个查询可能返回不同的结果。  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
    ```  
  
     And  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
    ```  
  
     请确保您在组帧 select 查询时使用正确的情况。 此外，在 SAP 系统中，并非所有列可以都包含小写或大写字符。 SAP GUI 可用于找出是否表中的列存储小写或大写字符。 有关使用 SAP GUI 的说明，请参阅[确定是否列存储小写或大写值](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)。  
  
-   仅支持使用的某个数据值，一个字段值的比较 WHERE 条件和*不*使用某些其他表的字段值。 因为[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持只有一个表 SELECT 查询，表中联接条件的字段查询应使用的联接条件来支持相同。  
  
-   联接条件必须包含一个表名称。  
  
     下面是正确的选择语句  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     下面是不正确的选择语句  
  
    ```  
    select A.x, B.y from A inner join B on m = n  
    ```  
  
-   联接条件中的左的表中联接条件应为条件，左侧和右侧表的联接条件应指定的联接条件右侧。  
  
     下面是指定的联接条件的正确方法：  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     下面是指定的联接条件的正确方法：  
  
    ```  
    select A.x, B.y from A inner join B on B.n = A.m  
    ```  
  
-   SELECT 语句只能包含对 JOIN 子句中的"等于"条件。 例如：  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
-   SELECT 语句并不从 SAP 系统中检索属于字符串类型的列。  
  
-   SELECT 语句必须包含仅的单一联接。 例如：  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)