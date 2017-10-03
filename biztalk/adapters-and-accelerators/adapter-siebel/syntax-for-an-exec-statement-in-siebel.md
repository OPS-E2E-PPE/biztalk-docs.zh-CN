---
title: "为 Siebel 中 EXEC 语句的语法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d18481b206b1be7e0062762c1844305fc36e10f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a>Siebel 中 EXEC 语句的的语法
使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端还可以在执行运算 EXEC [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 EXEC 语句的语法是：  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
\<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 在前面的语法中，`\<value 1..n>`表示一组未命名参数。 这些是硬编码值。 它们通常表示参数中。  它们还可以表示 INOUT 参数。 但是，如果硬编码的值用于 INOUT 参数，执行 EXEC 语句后无法检索到该参数与关联的输出值。  
  
 `@parameter 1..n`语法表示一组命名的参数，可以为 IN、 INOUT 或 OUT 参数。 输出参数的后面必须跟**输出**关键字。  
  
> [!NOTE]
>  **输出**OUT 参数而不是与 INOUT 参数关键字必须仅与一起使用。  
  
 若要指定参数值内联，使用`@parameter 1..n = <value>`语法。  
  
 所有参数必须都是以逗号分隔。  
  
 EXEC 语句的示例如下：  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  每个参数的名称 (如`@In`在前面的示例) Siebel 业务服务方法中的相应自变量名称必须匹配。  
  
## <a name="see-also"></a>另请参阅  
 [.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)