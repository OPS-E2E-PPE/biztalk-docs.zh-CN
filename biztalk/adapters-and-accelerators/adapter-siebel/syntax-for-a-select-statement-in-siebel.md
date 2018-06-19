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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3eeb0a6d4a1fceebe7e16b3f71566f848e4a20f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25964155"
---
# <a name="syntax-for-a-select-statement-in-siebel"></a>Siebel 中的 SELECT 语句的语法
使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端可以通过指定 WHERE 子句表示有效的 Siebel 搜索规范 Siebel 业务组件上执行 SELECT 查询。 SELECT 语句的语法是：  
  
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
  
 在上述语法中，ViewMode 选项对应于 Siebel 系统视图模式，这是一种限制的与查询匹配的记录集的筛选机制。 允许的值集，请参阅 Siebel 文档。  
  
> [!NOTE]
>  如果 WHERE 子句中的字段名称包含特殊字符或空格，请确保你始终将括在方括号中的字段名称。  
  
> [!NOTE]
>  在包含带有特殊字符的别名名称的 SELECT 查询，请确保包括方括号内的别名名称。  
  
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]别名支持为表的名称，在 SELECT 子句，但不是在 WHERE 子句。  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a>搜索和排序数据的数据提供程序用于 Siebel  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持基于搜索规范 Siebel 系统支持的 SQL 语句中的筛选条件。  
  
 搜索规范的规则包括：  
  
-   必须使用标准的比较运算符来比较字段设置为常量或对另一个域的一个字段。 其中包括 =、 ！ =、 >，<>、 =、 和 < =。  
  
    ```  
    Example: [Revenue] > 5000  
    ```  
  
-   字符串常量必须用双引号括起来，并且字符串值必须是区分大小写。  
  
    ```  
    Example: [Type] != "COST LIST"  
    ```  
  
-   逻辑运算符 AND、 OR 和必须使用 negate 或将表达式组合。 在这些运算符; 中忽略大小写区分功能例如，"和"等同于"AND"。  
  
    ```  
    Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
    ```  
  
-   在搜索规范中的字段名称必须括在方括号中。  
  
    ```  
    Example: [Conflict Id] = 0  
    ```  
  
-   LIKE 运算符可用于创建字段相比常量，比较表达式的文本字符串或到另一个字段的前几个字符匹配字段是必填。 通配符"*"和"？" 必须使用任意数量的字符和单个字符，以分别指示。  
  
-   ADO.NET 客户端可以指定原始 Siebel 业务对象、 业务组件和业务组件字段名称。 这些名称必须括在方括号中，如果它们所包含的任何特殊字符或空格。 支持的查询的示例包括：  
  
    ```  
    SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
    SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
    SELECT * FROM [Admin Price List].[Price Book Items]  
    ```  
  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持排序根据排序规范 Siebel 支持的 SQL 语句中的规范。 排序规范的规则包括：  
  
-   使用逗号分隔的排序规范; 中的字段名称例如，名称、 位置  
  
-   若要指示按降序进行排序列表中的字段，包括 (DESC) 字段名称之后，如下所示"开始日期 (DESC)"。 如果不指定任何排序顺序，则使用升序。 若要显式指定按升序进行排序，请使用关键字 (ASC)。  
  
-   排序规范表达式必须为 255 个字符或更少。  
  
## <a name="see-also"></a>另请参阅  
 [使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)