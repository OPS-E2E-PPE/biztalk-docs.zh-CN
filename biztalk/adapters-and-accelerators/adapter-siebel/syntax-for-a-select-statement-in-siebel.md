---
title: Siebel 中的 SELECT 语句的语法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, searching and sorting data using
- Data Provider for Siebel, SELECT statement
- SELECT statement, syntax for
ms.assetid: 8528b115-d6f3-420d-8617-0e56dc8922bf
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3eeb0a6d4a1fceebe7e16b3f71566f848e4a20f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-a-select-statement-in-siebel"></a><span data-ttu-id="8a793-102">Siebel 中的 SELECT 语句的语法</span><span class="sxs-lookup"><span data-stu-id="8a793-102">Syntax for a SELECT Statement in Siebel</span></span>
<span data-ttu-id="8a793-103">使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端可以通过指定 WHERE 子句表示有效的 Siebel 搜索规范 Siebel 业务组件上执行 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="8a793-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can perform a SELECT query on Siebel business components by specifying a WHERE clause that represents a valid Siebel search specification.</span></span> <span data-ttu-id="8a793-104">SELECT 语句的语法是：</span><span class="sxs-lookup"><span data-stu-id="8a793-104">The syntax for the SELECT statement is:</span></span>  
  
```  
SELECT  
<column name 1> AS <column alias 1>,  
<column name 2> AS <column alias 2>,  
…  
FROM  
<Business object name>.<Business component name> AS <table alias>  
WHERE  
<filter condition>  
OPTION  
'ViewMode <value>'  
```  
  
 <span data-ttu-id="8a793-105">在上述语法中，ViewMode 选项对应于 Siebel 系统视图模式，这是一种限制的与查询匹配的记录集的筛选机制。</span><span class="sxs-lookup"><span data-stu-id="8a793-105">In the above syntax, the ViewMode option corresponds to the Siebel system View Modes, which is a filtering mechanism to restrict the set of records that match the query.</span></span> <span data-ttu-id="8a793-106">允许的值集，请参阅 Siebel 文档。</span><span class="sxs-lookup"><span data-stu-id="8a793-106">For the allowed set of values, see the Siebel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a793-107">如果 WHERE 子句中的字段名称包含特殊字符或空格，请确保你始终将括在方括号中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="8a793-107">If the field names in the WHERE clause contain special characters or empty spaces, make sure you always enclose the field names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a793-108">在包含带有特殊字符的别名名称的 SELECT 查询，请确保包括方括号内的别名名称。</span><span class="sxs-lookup"><span data-stu-id="8a793-108">In SELECT queries containing alias names with special characters, make sure you include the alias names within square brackets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a793-109">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]别名支持为表的名称，在 SELECT 子句，但不是在 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="8a793-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause but not in the WHERE clause.</span></span>  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a><span data-ttu-id="8a793-110">搜索和排序数据的数据提供程序用于 Siebel</span><span class="sxs-lookup"><span data-stu-id="8a793-110">Searching and Sorting Data Using the Data Provider for Siebel</span></span>  
 <span data-ttu-id="8a793-111">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持基于搜索规范 Siebel 系统支持的 SQL 语句中的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="8a793-111">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports a filter condition in SQL statements based on the search specifications supported by the Siebel system.</span></span>  
  
 <span data-ttu-id="8a793-112">搜索规范的规则包括：</span><span class="sxs-lookup"><span data-stu-id="8a793-112">The rules for the search specification are:</span></span>  
  
-   <span data-ttu-id="8a793-113">必须使用标准的比较运算符来比较字段设置为常量或对另一个域的一个字段。</span><span class="sxs-lookup"><span data-stu-id="8a793-113">Standard comparison operators must be used to compare a field to a constant, or one field to another field.</span></span> <span data-ttu-id="8a793-114">其中包括 =、 ！ =、 >，<>、 =、 和 < =。</span><span class="sxs-lookup"><span data-stu-id="8a793-114">These include =, !=, >, <, >=, and <=.</span></span>  
  
    ```  
    Example: [Revenue] > 5000  
    ```  
  
-   <span data-ttu-id="8a793-115">字符串常量必须用双引号括起来，并且字符串值必须是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8a793-115">String constants must be enclosed in double quotation marks, and the string values must be case-sensitive.</span></span>  
  
    ```  
    Example: [Type] != "COST LIST"  
    ```  
  
-   <span data-ttu-id="8a793-116">逻辑运算符 AND、 OR 和必须使用 negate 或将表达式组合。</span><span class="sxs-lookup"><span data-stu-id="8a793-116">The logical operators AND, OR, and NOT must be used to negate or combine expressions.</span></span> <span data-ttu-id="8a793-117">在这些运算符; 中忽略大小写区分功能例如，"和"等同于"AND"。</span><span class="sxs-lookup"><span data-stu-id="8a793-117">Case sensitivity is ignored in these operators; for example, “and” is the same as “AND”.</span></span>  
  
    ```  
    Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
    ```  
  
-   <span data-ttu-id="8a793-118">在搜索规范中的字段名称必须括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="8a793-118">A field name in a search specification must be enclosed in square brackets.</span></span>  
  
    ```  
    Example: [Conflict Id] = 0  
    ```  
  
-   <span data-ttu-id="8a793-119">LIKE 运算符可用于创建字段相比常量，比较表达式的文本字符串或到另一个字段的前几个字符匹配字段是必填。</span><span class="sxs-lookup"><span data-stu-id="8a793-119">The LIKE operator may be used to create text string comparison expressions in which a field is compared to a constant, or a field to another field and a match on only the first several characters is required.</span></span> <span data-ttu-id="8a793-120">通配符"\*"和"？"</span><span class="sxs-lookup"><span data-stu-id="8a793-120">The wildcard characters “\*” and “?”</span></span> <span data-ttu-id="8a793-121">必须使用任意数量的字符和单个字符，以分别指示。</span><span class="sxs-lookup"><span data-stu-id="8a793-121">must be used to indicate any number of characters, and a single character, respectively.</span></span>  
  
-   <span data-ttu-id="8a793-122">ADO.NET 客户端可以指定原始 Siebel 业务对象、 业务组件和业务组件字段名称。</span><span class="sxs-lookup"><span data-stu-id="8a793-122">ADO.NET clients can specify original Siebel business objects, business components, and business component field names.</span></span> <span data-ttu-id="8a793-123">这些名称必须括在方括号中，如果它们所包含的任何特殊字符或空格。</span><span class="sxs-lookup"><span data-stu-id="8a793-123">These names must be enclosed in square brackets if they contain any special characters or white space.</span></span> <span data-ttu-id="8a793-124">支持的查询的示例包括：</span><span class="sxs-lookup"><span data-stu-id="8a793-124">Examples of queries that are supported are:</span></span>  
  
    ```  
    SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
    SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
    SELECT * FROM [Admin Price List].[Price Book Items]  
    ```  
  
 <span data-ttu-id="8a793-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持排序根据排序规范 Siebel 支持的 SQL 语句中的规范。</span><span class="sxs-lookup"><span data-stu-id="8a793-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports sort specifications in SQL statements based on the sort specification supported by Siebel.</span></span> <span data-ttu-id="8a793-126">排序规范的规则包括：</span><span class="sxs-lookup"><span data-stu-id="8a793-126">The rules for the sort specification are:</span></span>  
  
-   <span data-ttu-id="8a793-127">使用逗号分隔的排序规范; 中的字段名称例如，名称、 位置</span><span class="sxs-lookup"><span data-stu-id="8a793-127">Use commas to separate field names in a sort specification; for instance, Name, Location</span></span>  
  
-   <span data-ttu-id="8a793-128">若要指示按降序进行排序列表中的字段，包括 (DESC) 字段名称之后，如下所示"开始日期 (DESC)"。</span><span class="sxs-lookup"><span data-stu-id="8a793-128">To indicate that a field in the list sorts in descending order, include (DESC) after the field name, as in “Start Date (DESC).”</span></span> <span data-ttu-id="8a793-129">如果不指定任何排序顺序，则使用升序。</span><span class="sxs-lookup"><span data-stu-id="8a793-129">If no sort order is specified, ascending order is used.</span></span> <span data-ttu-id="8a793-130">若要显式指定按升序进行排序，请使用关键字 (ASC)。</span><span class="sxs-lookup"><span data-stu-id="8a793-130">To explicitly specify ascending order, use the keyword (ASC).</span></span>  
  
-   <span data-ttu-id="8a793-131">排序规范表达式必须为 255 个字符或更少。</span><span class="sxs-lookup"><span data-stu-id="8a793-131">The sort specification expression must be 255 characters or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a793-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a793-132">See Also</span></span>  
 [<span data-ttu-id="8a793-133">使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8a793-133">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)