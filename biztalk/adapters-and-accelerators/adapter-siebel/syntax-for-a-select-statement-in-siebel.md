---
title: 在 Siebel 中的 SELECT 语句的语法 |Microsoft Docs
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
ms.openlocfilehash: 3e25e8af2bd192495108204ded53b682333d64f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370497"
---
# <a name="syntax-for-a-select-statement-in-siebel"></a>在 Siebel 中的 SELECT 语句的语法
使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端可以通过指定 WHERE 子句表示有效的 Siebel 搜索规范 Siebel 业务组件上执行的 SELECT 查询。 SELECT 语句的语法是：  
  
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
  
 在上述语法中，ViewMode 选项对应于 Siebel 系统视图模式，这是一种筛选机制来限制与查询匹配的记录集。 允许的值集，请参阅 Siebel 文档。  
  
> [!NOTE]
>  如果在 WHERE 子句中的字段名称包含特殊字符或空格，请确保你始终将括在方括号内的字段名称。  
> 
> [!NOTE]
>  在 SELECT 查询包含带有特殊字符的别名名称，请确保包括在方括号内的别名名称。  
> 
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持别名的表的名称，在 SELECT 子句中，但不是在 WHERE 子句。  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a>搜索和排序的数据提供程序用于 Siebel 的数据  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持基于搜索规范 Siebel 系统支持的 SQL 语句中的筛选条件。  
  
 搜索规范的规则包括：  
  
- 必须使用标准的比较运算符比较字段为常量或对另一个域的一个字段。 其中包括 =、 ！ =、 >、 <>、 =、 和 < =。  
  
  ```  
  Example: [Revenue] > 5000  
  ```  
  
- 字符串常量必须用双引号引起来，并且字符串值必须是区分大小写。  
  
  ```  
  Example: [Type] != "COST LIST"  
  ```  
  
- 逻辑运算符 AND、 OR 和必须使用以将表达式组合或使其失效。 在这些运算符; 将被忽略区分大小写例如，"和"等同于"AND"。  
  
  ```  
  Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
  ```  
  
- 搜索规范中的字段名称必须括在方括号中。  
  
  ```  
  Example: [Conflict Id] = 0  
  ```  
  
- LIKE 运算符可能用于创建在其中一个字段进行比较的常量，比较表达式的文本字符串或与另一个字段上的前几个字符匹配字段为必填项。 通配符"*"和"？" 必须使用任意数量的字符和单个字符，以分别指示。  
  
- ADO.NET 客户端可以指定原始 Siebel 业务对象、 业务组件和业务组件字段名称。 这些名称必须括在方括号中，如果它们包含任何特殊字符或空格。 支持的查询的示例包括：  
  
  ```  
  SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
  SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
  SELECT * FROM [Admin Price List].[Price Book Items]  
  ```  
  
  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持排序根据排序规范支持的 Siebel 的 SQL 语句中的规范。 指定的排序规则包括：  
  
- 使用逗号分隔的排序规范; 中的字段名称例如，名称、 位置  
  
- 若要指示按降序进行排序的字段列表中，包括 (DESC) 后的字段名称，如下所示"开始日期 (DESC)"。 如果未不指定任何排序顺序，则使用升序排序。 若要显式指定按升序排列，请使用关键字 (ASC)。  
  
- 排序规范表达式必须为 255 个字符或更少。  
  
## <a name="see-also"></a>请参阅  
 [使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)