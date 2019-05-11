---
title: 在 Siebel EXEC 语句的语法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094161f866b12f656dd42e3eddbaba7c56a6ff01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370490"
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a>在 Siebel EXEC 语句的语法
使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端还可以根据执行 EXEC 操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 EXEC 语句的语法是：  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 在上述语法中，`\<value 1..n\>`表示一组未命名参数。 这些是硬编码值。 它们通常代表参数中。  它们可以表示 INOUT 参数。 但是，如果硬编码值用于 INOUT 参数，在 EXEC 语句执行后不能检索到该参数与关联的输出值。  
  
 `@parameter 1..n`语法表示一组的命名参数，这些可以是 IN、 INOUT 参数或 OUT 参数。 输出参数必须后跟**输出**关键字。  
  
> [!NOTE]
>  **输出**关键字必须仅可用于 OUT 参数而不是与 INOUT 参数。  
  
 若要指定内联参数值，请使用`@parameter 1..n = <value>`语法。  
  
 所有参数必须都是以逗号分隔。  
  
 EXEC 语句的示例如下：  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  每个参数的名称 (如`@In`前面的示例中) 的 Siebel 业务服务方法中的相应参数名称必须匹配。  
  
## <a name="see-also"></a>请参阅  
 [使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)