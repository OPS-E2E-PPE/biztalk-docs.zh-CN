---
title: "XLANG-s 数据类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ed77c5fdd56485514d17ed75e921c63a56212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-data-types"></a>XLANG-s 数据类型
XLANG/s 定义反映的 C# 的对应的标准值类型。 其中包括**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单个**，**字符串**， **UInt16**， **UInt32**，和**UInt64**。 XLANG/s 支持一维数组，但不支持数组文本。  
  
 XLANG/s 还具有用于消息处理的丰富支持。 消息可以基于架构、.NET 类，Web 消息类型 (WSDL) 或复杂的消息类型。 XLANG/s 支持以下的复杂数据类型：  
  
-   **messagetype。** 此数据类型定义多部分消息类型，这些类型作为数据元素、基于 XSD 的消息以及方法-消息类型（与类或接口的方法的签名格式相匹配的消息）的组合进行定义。  
  
-   **porttype。** 此数据类型定义该类型的端口实例可对其执行的端口操作的集合。  
  
-   **correlationsettype。** 此数据类型定义将在相关集变量的实例中使用的数据。 相关集数据是用于确保的移动到整个系统的消息调度到适当的运行实例的业务流程的路由机制。 例如，如果处理的情况下，采购订单发送到贸易合作伙伴，是命令性，其返回调用对应于该采购订单的业务进程的正确实例。  
  
-   **servicelinktype。** 此数据类型定义的一套**porttype**形成一个逻辑上一致的一组业务流程中使用的端口的值。 服务链接的用途是允许在运行时的动态分配到一组端口的强大机制。 这允许你定义用于与多个贸易合作伙伴进行交互的单个业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [XLANG-s 语句](../core/xlang-s-statements.md)   
 [XLANG-s 变量和运算符](../core/xlang-s-variables-and-operators.md)   
 [XLANG-s 表达式](../core/xlang-s-expressions.md)   
 [XLANG-s 保留字](../core/xlang-s-reserved-words.md)   
 [XLANG-s 的 BPEL4WS 类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)