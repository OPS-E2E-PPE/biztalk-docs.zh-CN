---
title: 在 SAP 中的 SELECT 语句的语法 |Microsoft Docs
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6086f39f3976e481d910dd5f83cd0a648696c9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372733"
---
# <a name="syntax-for-a-select-statement-in-sap"></a><span data-ttu-id="a0262-102">在 SAP 中的 SELECT 语句的语法</span><span class="sxs-lookup"><span data-stu-id="a0262-102">Syntax for a SELECT Statement in SAP</span></span>
<span data-ttu-id="a0262-103">以下各节介绍用于实现对 SELECT 查询的语法规范[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0262-103">The following sections describe grammar specifications for implementing SELECT queries against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="a0262-104">请注意，在某些情况下，该语法的基本 TRANSACT-SQL 语法稍有不同。</span><span class="sxs-lookup"><span data-stu-id="a0262-104">Notice that in several cases, the syntax is somewhat different from the base Transact-SQL syntax.</span></span>  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 <span data-ttu-id="a0262-105">其中：</span><span class="sxs-lookup"><span data-stu-id="a0262-105">Where:</span></span>  
  
- <span data-ttu-id="a0262-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span><span class="sxs-lookup"><span data-stu-id="a0262-106">**<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`</span></span>  
  
- <span data-ttu-id="a0262-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span><span class="sxs-lookup"><span data-stu-id="a0262-107">**<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`</span></span>  
  
- <span data-ttu-id="a0262-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span><span class="sxs-lookup"><span data-stu-id="a0262-108">**\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`</span></span>  
  
  <span data-ttu-id="a0262-109">支持的条件和表达式是：</span><span class="sxs-lookup"><span data-stu-id="a0262-109">The supported conditions and expressions are:</span></span>  
  
- <span data-ttu-id="a0262-110">**\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span><span class="sxs-lookup"><span data-stu-id="a0262-110">**\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`</span></span>  
  
- <span data-ttu-id="a0262-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span><span class="sxs-lookup"><span data-stu-id="a0262-111">**\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`</span></span>  
  
  <span data-ttu-id="a0262-112">其中 **\<const\>** = `integer | real | string | ? | NULL | xml_element`。</span><span class="sxs-lookup"><span data-stu-id="a0262-112">Where **\<const\>** = `integer | real | string | ? | NULL | xml_element`.</span></span>  
  
  <span data-ttu-id="a0262-113">**OPTION 关键字的值**</span><span class="sxs-lookup"><span data-stu-id="a0262-113">**Values for the OPTION Keyword**</span></span>  
  
  <span data-ttu-id="a0262-114">您可以指定作为选项`OPTION '<option>'`，其中 `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span><span class="sxs-lookup"><span data-stu-id="a0262-114">You can specify the options as `OPTION '<option>'`, where `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`</span></span>  
  
- <span data-ttu-id="a0262-115">**No_conversion**选项：</span><span class="sxs-lookup"><span data-stu-id="a0262-115">The **no_conversion** option:</span></span>  
  
  -   <span data-ttu-id="a0262-116">如果**no_conversion**使用选项，然后使用等效的.NET 类型公开表中的字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-116">If the **no_conversion** option is used then the fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="a0262-117">SAP 数据类型的.NET 等效项的信息，请参阅[基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a0262-117">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
  -   <span data-ttu-id="a0262-118">如果**no_conversion**不使用选项，并且如果字段没有转换退出定义，然后使用等效的.NET 类型公开这些表中的字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-118">If the **no_conversion** option is not used, and if a field does not have a conversion exit defined then those fields in the table are exposed using the equivalent .NET types.</span></span> <span data-ttu-id="a0262-119">SAP 数据类型的.NET 等效项的信息，请参阅[基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a0262-119">For information about the .NET equivalent of the SAP data types, see [Basic SAP Data Types](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).</span></span>  
  
  -   <span data-ttu-id="a0262-120">当**no_conversion**不使用选项，并且如果字段具有转换退出定义然后表中的这些字段会公开作为.NET 字符串。</span><span class="sxs-lookup"><span data-stu-id="a0262-120">When the **no_conversion** option is not used, and if a field has a conversion exit defined then those fields in the table are exposed as .NET String.</span></span>  
  
- <span data-ttu-id="a0262-121">如果设置为**batchsize\<大小\>**，SELECT 语句的执行会导致多个调用到 SAP 系统，并在每个调用中，仅进行\<大小\>的记录数检索。</span><span class="sxs-lookup"><span data-stu-id="a0262-121">When set to **batchsize \<size\>**, the execution of the SELECT statement causes multiple calls to be made to the SAP system, and in each call, only \<size\> number of records are retrieved.</span></span> <span data-ttu-id="a0262-122">例如，如果指定 batchsize 100，SELECT 查询检索仅在每次调用到 SAP 系统中的 100 条记录。</span><span class="sxs-lookup"><span data-stu-id="a0262-122">For example, if you specify 'batchsize 100', the SELECT query retrieves 100 records only in each call to the SAP system.</span></span> <span data-ttu-id="a0262-123">如果**batchsize\<大小\>** 未指定，默认值为 10000 的假定代表批大小。</span><span class="sxs-lookup"><span data-stu-id="a0262-123">If **batchsize \<size\>** is not specified, the default value of 10,000 is assumed for the batch size.</span></span> <span data-ttu-id="a0262-124">请注意，应指定批大小基于计算机和行数的物理内存中 SAP 系统的最佳值。</span><span class="sxs-lookup"><span data-stu-id="a0262-124">Note that you should specify an optimum value for the batch size based on the physical memory of the computer and the number of rows in the SAP system.</span></span> <span data-ttu-id="a0262-125">指定批大小的最佳值中的故障可能会导致内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="a0262-125">Failure in specifying an optimum value for batch size may result in out of memory exceptions.</span></span>  
  
- <span data-ttu-id="a0262-126">如果设置为**disabledatavalidation**，则[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证 DATS、 TIMS 和 NUMC 列中存在的值，但改为将它们显示为字符串。</span><span class="sxs-lookup"><span data-stu-id="a0262-126">When set to **disabledatavalidation**, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values present in the DATS, TIMS, and NUMC columns but instead exposes them as string.</span></span>  
  
   <span data-ttu-id="a0262-127">这是对 ADO.NET 客户端无法从 SAP 表将无效数据放在 DATS、 TIMS 和 NUMC 列中检索数据的情况非常有用。</span><span class="sxs-lookup"><span data-stu-id="a0262-127">This is useful in scenarios where ADO.NET clients fail to retrieve data from an SAP table having invalid data in DATS, TIMS, and NUMC columns.</span></span> <span data-ttu-id="a0262-128">SAP 允许将 DATS、 TIMS 和 NUMC 列中存在无效数据，因为尝试读取数据的 ADO.NET 客户端将不能以分析无效的数据，并且将引发异常。</span><span class="sxs-lookup"><span data-stu-id="a0262-128">Because SAP allows invalid data to be present in DATS, TIMS, and NUMC columns, ADO.NET clients attempting to read the data will not be able to parse the invalid data and will throw an exception.</span></span> <span data-ttu-id="a0262-129">如果**disabledatavalidation**在 SELECT 查询中设置选项[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]未分析的无效数据，但将其提取以字符串形式。</span><span class="sxs-lookup"><span data-stu-id="a0262-129">If the **disabledatavalidation** option is set on the SELECT query, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not parse the invalid data but extracts them as strings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a0262-130">您必须始终提供值选项关键字在单引号中，例如，'*disabledatavalidation*。</span><span class="sxs-lookup"><span data-stu-id="a0262-130">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="a0262-131">有关示例语句，请参阅[的 SELECT 语句示例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a0262-131">For example statements, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
## <a name="predicates-syntax"></a><span data-ttu-id="a0262-132">谓词语法</span><span class="sxs-lookup"><span data-stu-id="a0262-132">Predicates Syntax</span></span>  
 <span data-ttu-id="a0262-133">以下示例指定在 SELECT 语句中使用的谓词的语法：</span><span class="sxs-lookup"><span data-stu-id="a0262-133">The following specifies the grammar for using predicates in a SELECT statement:</span></span>  
  
 <span data-ttu-id="a0262-134">`Predicate`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-134">`Predicate`:</span></span>  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 <span data-ttu-id="a0262-135">`Condition`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-135">`Condition`:</span></span>  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 <span data-ttu-id="a0262-136">`Expr`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-136">`Expr`:</span></span>  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 <span data-ttu-id="a0262-137">`LExpr`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-137">`LExpr`:</span></span>  
  
```  
ColumnName  
```  
  
 <span data-ttu-id="a0262-138">`RExpr`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-138">`RExpr`:</span></span>  
  
```  
Const | PlaceHolder  
```  
  
 <span data-ttu-id="a0262-139">`ColumnName`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-139">`ColumnName`:</span></span>  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 <span data-ttu-id="a0262-140">`Tablename`设置用户帐户 ：</span><span class="sxs-lookup"><span data-stu-id="a0262-140">`Tablename`:</span></span>  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a><span data-ttu-id="a0262-141">调用 SELECT 语句时的注意事项</span><span class="sxs-lookup"><span data-stu-id="a0262-141">Considerations When Calling a SELECT Statement</span></span>  
 <span data-ttu-id="a0262-142">本部分列出了使用带有 SELECT 语句时必须牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0262-142">This section lists the points that you must keep in mind when using the SELECT statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="a0262-143">当在参数或查询中指定日期时间值，以字符串形式提供的值。</span><span class="sxs-lookup"><span data-stu-id="a0262-143">When specifying date-time values in parameters or queries, provide the values as a string.</span></span> <span data-ttu-id="a0262-144">提供 SAP 日期时间格式的日期时间字符串。</span><span class="sxs-lookup"><span data-stu-id="a0262-144">Provide date-time strings in the SAP date-time format.</span></span>  
  
  - <span data-ttu-id="a0262-145">`SAP date format`设置用户帐户 ：YYYYMMDD</span><span class="sxs-lookup"><span data-stu-id="a0262-145">`SAP date format`: YYYYMMDD</span></span>  
  
     <span data-ttu-id="a0262-146">例如，日期 2004 年 11 月 10 个 SAP 查询中是表示"20041110"。</span><span class="sxs-lookup"><span data-stu-id="a0262-146">For example, the date 2004 November 10 in a SAP query is expressed '20041110'.</span></span>  
  
     <span data-ttu-id="a0262-147">日期 2004 年 11 月 10 个 SAPParameter p1 中是字符串 p1。值 ="20041110"。</span><span class="sxs-lookup"><span data-stu-id="a0262-147">The date 2004 November 10 in a SAPParameter p1 is the string p1.Value='20041110'.</span></span>  
  
  - <span data-ttu-id="a0262-148">`SAP time format`设置用户帐户 ：HHMMSS</span><span class="sxs-lookup"><span data-stu-id="a0262-148">`SAP time format`: HHMMSS</span></span>  
  
     <span data-ttu-id="a0262-149">例如，时间 10:34:32 SAP 查询中是表示"103432"。</span><span class="sxs-lookup"><span data-stu-id="a0262-149">For example, the time 10:34:32 in a SAP query is expressed '103432'.</span></span>  
  
     <span data-ttu-id="a0262-150">时间 10:34:32 SAPParameter p2 中为字符串 p2。值 ="103432"。</span><span class="sxs-lookup"><span data-stu-id="a0262-150">The time 10:34:32 in a SAPParameter p2 is the string p2.Value='103432'.</span></span>  
  
    <span data-ttu-id="a0262-151">SELECT 语句[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`DATE`字段的值作为.NET`System.DateTime`对象，并返回`TIME`字段值作为`System.TimeSpan`对象。</span><span class="sxs-lookup"><span data-stu-id="a0262-151">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `DATE` field values as .NET `System.DateTime` objects, and returns `TIME` field values as `System.TimeSpan` objects.</span></span> <span data-ttu-id="a0262-152">如果将 sap 值`DATE`对象是否允许 SQL Server 最小值小于 (`1/1/1753`)，则[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回此最小值`1/1/1753`。</span><span class="sxs-lookup"><span data-stu-id="a0262-152">If the value of the SAP `DATE` object is less than the minimum allowable SQL Server value (`1/1/1753`), the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns this minimum value, `1/1/1753`.</span></span>  
  
- <span data-ttu-id="a0262-153">在 TOP 子句的 SELECT 查询中时使用特殊字符"#"、"^"，"&"和"%"之前或之后一个整数，将忽略特殊字符，尽管不引发任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="a0262-153">In the TOP clause of a SELECT query, when using the special characters "#", "^", "&", and "%" before or after an integer, the special characters are ignored, although no error message is raised.</span></span> <span data-ttu-id="a0262-154">例如，以下将忽略 TOP 子句的 SELECT 查询中：</span><span class="sxs-lookup"><span data-stu-id="a0262-154">For example, the following are ignored in the TOP clause of a SELECT query:</span></span>  
  
   <span data-ttu-id="a0262-155">\#5，5 ^，%5%或) (& 5</span><span class="sxs-lookup"><span data-stu-id="a0262-155">\#5, 5^, %5%, or &5</span></span>  
  
   <span data-ttu-id="a0262-156">但是，使用整数，如下所示 5 之间的这些字符 $5，会引发错误。</span><span class="sxs-lookup"><span data-stu-id="a0262-156">However, using these characters between integers, as in 5$5, does throw an error.</span></span>  
  
- <span data-ttu-id="a0262-157">返回一个表的架构中的列名称返回为所有大写字符。</span><span class="sxs-lookup"><span data-stu-id="a0262-157">Column names returned in a schema for a table are returned as all uppercase characters.</span></span> <span data-ttu-id="a0262-158">例如，查询结果集的字段`Last Name`返回的列标题`LAST NAME`。</span><span class="sxs-lookup"><span data-stu-id="a0262-158">For example, a query result set on the field `Last Name` returns the column heading `LAST NAME`.</span></span> <span data-ttu-id="a0262-159">若要避免唯一性冲突，使用 SELECT 语句中全部大写建议。</span><span class="sxs-lookup"><span data-stu-id="a0262-159">To avoid uniqueness conflicts, using all uppercase in SELECT statements is recommended.</span></span>  
  
- <span data-ttu-id="a0262-160">在 LIKE 子句中的 SELECT 查询中的百分号，"%"（适用于零个或多个字符的任意字符串） 和下划线 **"_"** （适用于任何单个字符），是允许的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="a0262-160">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, **"_"** (for any single character), are allowable special characters.</span></span> <span data-ttu-id="a0262-161">所有其他特殊字符被视为字符串值，将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a0262-161">All other special characters are considered string values and are ignored.</span></span>  
  
- <span data-ttu-id="a0262-162">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC 用于 SAP 系统上执行的 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="a0262-162">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the Z_EXTRACT_DATA_OO RFC to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="a0262-163">RFC 支持满足以下条件的表中读取数据：</span><span class="sxs-lookup"><span data-stu-id="a0262-163">The RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
  - <span data-ttu-id="a0262-164">表 TabClass 是 TRANSP、 群集或池。</span><span class="sxs-lookup"><span data-stu-id="a0262-164">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
  - <span data-ttu-id="a0262-165">TabClass 是视图且 ViewClass 是 D 或 p。</span><span class="sxs-lookup"><span data-stu-id="a0262-165">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
    <span data-ttu-id="a0262-166">请确保满足这些条件的表中的 SELECT 语句读取数据。</span><span class="sxs-lookup"><span data-stu-id="a0262-166">Make sure the SELECT statement reads data from tables that satisfy these conditions.</span></span>  
  
- <span data-ttu-id="a0262-167">可能需要超过 255 个字符，例如字符串、 RAWSTRING、 LRAW、 VARC 和 LCHAR 的数据类型的值不能使用 SELECT 查询中。</span><span class="sxs-lookup"><span data-stu-id="a0262-167">Values of data types that can take more than 255 characters, for example STRING, RAWSTRING, LRAW, VARC, and LCHAR cannot be used in a SELECT query.</span></span> <span data-ttu-id="a0262-168">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用随附的自定义 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，Z_EXTRACT_DATA_OO，SAP 系统上执行的 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="a0262-168">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC shipped with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], Z_EXTRACT_DATA_OO, to perform SELECT queries on the SAP system.</span></span> <span data-ttu-id="a0262-169">此自定义 RFC 不支持任何可能需要超过 255 个字符的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a0262-169">This custom RFC does not support any data type that can take more than 255 characters.</span></span>  
  
- <span data-ttu-id="a0262-170">列或多个 SELECT 语句中支持的字段的最大数目为 1000年。</span><span class="sxs-lookup"><span data-stu-id="a0262-170">The maximum number of columns or fields that are supported in a SELECT statement is 1000.</span></span>  
  
- <span data-ttu-id="a0262-171">在 WHERE 子句中支持的谓词的最大数目为 100。</span><span class="sxs-lookup"><span data-stu-id="a0262-171">The maximum number of predicates supported in a WHERE clause is 100.</span></span>  
  
- <span data-ttu-id="a0262-172">不支持在同一 SELECT 语句中多次选择相同的字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-172">Selecting the same field multiple times in the same SELECT statement is not supported.</span></span> <span data-ttu-id="a0262-173">自定义 RFC (Z_EXTRACT_DATA_OO) 由[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从之前执行的语句中删除重复的字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-173">The custom RFC (Z_EXTRACT_DATA_OO) used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] removes the duplicate fields from the statement before executing.</span></span> <span data-ttu-id="a0262-174">例如，此语句：</span><span class="sxs-lookup"><span data-stu-id="a0262-174">For example, this statement:</span></span>  
  
   `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
   <span data-ttu-id="a0262-175">执行编写的类似于此语句：</span><span class="sxs-lookup"><span data-stu-id="a0262-175">executes as though written like this statement:</span></span>  
  
   `SELECT BUKRS from T001`  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a0262-176">不支持在 SELECT 语句中的重复别名名称。</span><span class="sxs-lookup"><span data-stu-id="a0262-176">does not support duplicate alias names in a SELECT statement.</span></span> <span data-ttu-id="a0262-177">因此，以下 SELECT 语句将引发错误：</span><span class="sxs-lookup"><span data-stu-id="a0262-177">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a0262-178">不支持重复的列名称带的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="a0262-178">does not support a SELECT statement with duplicate column names.</span></span> <span data-ttu-id="a0262-179">因此，以下 SELECT 语句将引发错误：</span><span class="sxs-lookup"><span data-stu-id="a0262-179">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
  ```  
  
- <span data-ttu-id="a0262-180">SAP 不存储在表中的 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="a0262-180">SAP does not store NULL values in the tables.</span></span> <span data-ttu-id="a0262-181">因此，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持在 SELECT 语句中的"IS NULL"值。</span><span class="sxs-lookup"><span data-stu-id="a0262-181">As a result, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support an "IS NULL" value in a SELECT statement.</span></span> <span data-ttu-id="a0262-182">因此，以下 SELECT 语句将引发错误：</span><span class="sxs-lookup"><span data-stu-id="a0262-182">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a0262-183">不支持 ORDER BY 子句中 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="a0262-183">does not support an ORDER BY clause in a SELECT statement.</span></span> <span data-ttu-id="a0262-184">因此，以下 SELECT 语句将引发错误：</span><span class="sxs-lookup"><span data-stu-id="a0262-184">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="a0262-185">不支持指定一个星号 （\*） 来选择 SAP 表中的所有字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-185">does not support specifying an asterisk (\*) to select all the fields in an SAP table.</span></span> <span data-ttu-id="a0262-186">因此，以下 SELECT 语句将引发错误：</span><span class="sxs-lookup"><span data-stu-id="a0262-186">Therefore, the following SELECT statement throws an error:</span></span>  
  
  ```  
  SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   <span data-ttu-id="a0262-187">若要选择的所有字段，必须单独指定的字段名称。</span><span class="sxs-lookup"><span data-stu-id="a0262-187">To select all the fields, you must specify the field names individually.</span></span>  
  
- <span data-ttu-id="a0262-188">作为 SELECT 语句的一部分，可以指定 SELECT 语句的输出将写入的文件。</span><span class="sxs-lookup"><span data-stu-id="a0262-188">As part of the SELECT statement, you can specify a file to which the output of the SELECT statement will be written.</span></span> <span data-ttu-id="a0262-189">但是，如果输出文件在网络共享上，请确保 SAP 服务运行的 SAP 服务帐户具有对网络共享的写入权限。</span><span class="sxs-lookup"><span data-stu-id="a0262-189">However, if the output file is on a network share, make sure the SAP service account under which the SAP service is running has write permission to the network share.</span></span> <span data-ttu-id="a0262-190">例如：</span><span class="sxs-lookup"><span data-stu-id="a0262-190">For example:</span></span>  
  
  ```  
  SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   <span data-ttu-id="a0262-191">在前面的示例中，SAP 服务帐户必须具有名称"共享。"的网络共享的写入权限</span><span class="sxs-lookup"><span data-stu-id="a0262-191">In the preceding example, the SAP service account must have write permission to the network share with the name "share."</span></span>  
  
- <span data-ttu-id="a0262-192">SELECT 语句使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SELECT 查询中支持的参数值的参数名称。</span><span class="sxs-lookup"><span data-stu-id="a0262-192">A SELECT statement using [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports parameter names for argument values in a SELECT query.</span></span> <span data-ttu-id="a0262-193">但是，请确保您遵循这些规则与参数名称：</span><span class="sxs-lookup"><span data-stu-id="a0262-193">However, make sure you follow these rules with respect to parameter names:</span></span>  
  
  -   <span data-ttu-id="a0262-194">在 SELECT 查询中，"\@"符号必须位于之前的参数名称。</span><span class="sxs-lookup"><span data-stu-id="a0262-194">In the SELECT query, an "\@" symbol must precede the parameter name.</span></span>  
  
  -   <span data-ttu-id="a0262-195">"\@"符号后面必须跟字母字符 （A 到 Z 或 a 到 z）。</span><span class="sxs-lookup"><span data-stu-id="a0262-195">The "\@" symbol must be followed by an alphabetic character (A-Z or a-z).</span></span>  
  
  -   <span data-ttu-id="a0262-196">参数名称只能包含字母数字字符 (A-Z、 a 到 z 或 0-9) 和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="a0262-196">The parameter name can contain alphanumeric characters (A-Z, a-z, or 0-9) and special characters.</span></span> <span data-ttu-id="a0262-197">可以包含在参数名称的唯一特殊字符是下划线"_"和哈希"#"。</span><span class="sxs-lookup"><span data-stu-id="a0262-197">The only special characters that can be included in the parameter name are underscore "_" and hash "#".</span></span>  
  
- <span data-ttu-id="a0262-198">对视图运行 SELECT 查询时，请确保基础表的所有主键列也会存在于该视图。</span><span class="sxs-lookup"><span data-stu-id="a0262-198">When you run a SELECT query on a View, make sure that all the primary key columns of the base table are also present in the View.</span></span> <span data-ttu-id="a0262-199">此外，作为一种做法，你必须将列也标记为在视图中的主键列。</span><span class="sxs-lookup"><span data-stu-id="a0262-199">Also, as a practice, you must mark the columns as primary key columns in the View also.</span></span>  
  
   <span data-ttu-id="a0262-200">如果主键列不在视图中提供，在视图上的 SELECT 查询将导致异常。</span><span class="sxs-lookup"><span data-stu-id="a0262-200">If the primary key columns are not present in the View, a SELECT query on the View will result in an exception.</span></span>  
  
- <span data-ttu-id="a0262-201">选择字段类型 LRAW 对表运行 SELECT 查询时，请确保选择相应的 PREC 字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-201">When you run a SELECT query on a table to select fields of type LRAW, make sure you select the corresponding PREC field.</span></span> <span data-ttu-id="a0262-202">此外，PREC 字段必须紧跟在 SELECT 子句中的 LRAW 字段。</span><span class="sxs-lookup"><span data-stu-id="a0262-202">Also, the PREC field must appear immediately before the LRAW field in the SELECT clause.</span></span>  
  
   <span data-ttu-id="a0262-203">在表中的每个 LRAW 字段有一个相应的 PREC 字段 LRAW 字段中存储的数据的长度。</span><span class="sxs-lookup"><span data-stu-id="a0262-203">Every LRAW field in a table has a corresponding PREC field that stores the length of data in the LRAW field.</span></span> <span data-ttu-id="a0262-204">而无需 PREC 字段在 SELECT 子句中指定只是 LRAW 字段可能会导致不正确的数据提取。</span><span class="sxs-lookup"><span data-stu-id="a0262-204">Specifying just the LRAW field in the SELECT clause without the PREC field may result in incorrect data being extracted.</span></span>  
  
- <span data-ttu-id="a0262-205">在 SAP 系统中，字符比较不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a0262-205">In an SAP system, character comparisons are case sensitive.</span></span> <span data-ttu-id="a0262-206">因此，以下两个查询可能返回不同的结果。</span><span class="sxs-lookup"><span data-stu-id="a0262-206">So, the following two queries may return different results.</span></span>  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
  ```  
  
   <span data-ttu-id="a0262-207">And</span><span class="sxs-lookup"><span data-stu-id="a0262-207">And</span></span>  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
  ```  
  
   <span data-ttu-id="a0262-208">请确保分帧的 select 查询时使用正确的情况。</span><span class="sxs-lookup"><span data-stu-id="a0262-208">Make sure you use the right cases when framing a select query.</span></span> <span data-ttu-id="a0262-209">此外，在 SAP 系统中，并非所有列可以都包含小写或大写字符。</span><span class="sxs-lookup"><span data-stu-id="a0262-209">Also, in an SAP system, not all columns can contain lowercase or uppercase characters.</span></span> <span data-ttu-id="a0262-210">可以使用 SAP GUI 来找出是否列在表中的存储小写或大写字符。</span><span class="sxs-lookup"><span data-stu-id="a0262-210">You can use the SAP GUI to find out whether a column in a table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="a0262-211">有关使用 SAP GUI 的说明，请参阅[确定是否列存储小写或大写值](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)。</span><span class="sxs-lookup"><span data-stu-id="a0262-211">For instructions on using the SAP GUI, see [Determining Whether a Column Stores Lowercase or Uppercase Values](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md).</span></span>  
  
- <span data-ttu-id="a0262-212">仅支持具有某个数据值的字段值的比较 WHERE 条件并*不*与其他表字段值。</span><span class="sxs-lookup"><span data-stu-id="a0262-212">The WHERE condition is supported only for comparison of a field value with some data value, and *not* with some other table field value.</span></span> <span data-ttu-id="a0262-213">因为[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持只有一个表 SELECT 查询中表的联接条件中的字段查询应使用的联接条件来支持相同。</span><span class="sxs-lookup"><span data-stu-id="a0262-213">Because the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports only one table SELECT query, table field queries in join conditions should use the join condition to support the same.</span></span>  
  
- <span data-ttu-id="a0262-214">联接条件必须包含表名称。</span><span class="sxs-lookup"><span data-stu-id="a0262-214">A join condition must contain a table name.</span></span>  
  
   <span data-ttu-id="a0262-215">下面是正确的选择语句</span><span class="sxs-lookup"><span data-stu-id="a0262-215">The following is a correct SELECT statement</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   <span data-ttu-id="a0262-216">下面是不正确的选择语句</span><span class="sxs-lookup"><span data-stu-id="a0262-216">The following is an incorrect SELECT statement</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on m = n  
  ```  
  
- <span data-ttu-id="a0262-217">在联接条件中，联接条件中的左的表应位于左侧和右侧的条件，并右表的联接条件应指定联接条件右侧。</span><span class="sxs-lookup"><span data-stu-id="a0262-217">In a join condition, the left table in a join condition should be on the left side of the condition, and the right table of the join condition should be specified on the right side of the join condition.</span></span>  
  
   <span data-ttu-id="a0262-218">下面是指定联接条件的正确方式：</span><span class="sxs-lookup"><span data-stu-id="a0262-218">The following is the correct way of specifying a join condition:</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   <span data-ttu-id="a0262-219">下面是指定联接条件的不正确方式：</span><span class="sxs-lookup"><span data-stu-id="a0262-219">The following is an incorrect way of specifying a join condition:</span></span>  
  
  ```  
  select A.x, B.y from A inner join B on B.n = A.m  
  ```  
  
- <span data-ttu-id="a0262-220">SELECT 语句只能包含对 JOIN 子句中的"等于"条件。</span><span class="sxs-lookup"><span data-stu-id="a0262-220">A SELECT statement can only contain an “equal to” condition in a JOIN clause.</span></span> <span data-ttu-id="a0262-221">例如：</span><span class="sxs-lookup"><span data-stu-id="a0262-221">For example:</span></span>  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
- <span data-ttu-id="a0262-222">SELECT 语句不会从 SAP 系统中检索字符串类型的列。</span><span class="sxs-lookup"><span data-stu-id="a0262-222">A SELECT statement does not retrieve columns of type STRING from the SAP system.</span></span>  
  
- <span data-ttu-id="a0262-223">SELECT 语句必须包含单一联接。</span><span class="sxs-lookup"><span data-stu-id="a0262-223">A SELECT statement must contain only a single JOIN.</span></span> <span data-ttu-id="a0262-224">例如：</span><span class="sxs-lookup"><span data-stu-id="a0262-224">For example:</span></span>  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="a0262-225">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0262-225">See Also</span></span>  
 [<span data-ttu-id="a0262-226">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="a0262-226">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
