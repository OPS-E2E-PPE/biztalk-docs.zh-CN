---
title: Xlang-s 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc0d20336169ec1198c21dcbe932ff5a823a568
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394713"
---
# <a name="xlang-s-data-types"></a>Xlang-s 数据类型
XLANG/s 定义反映的标准值类型及其C#对应项。 其中包括**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单一**，**字符串**， **UInt16**， **UInt32**，和**UInt64**。 XLANG/s 支持一维数组，但不支持数组文本。  
  
 XLANG/s 还提供消息处理的丰富支持。 消息可以基于架构、.NET 类，Web 消息类型 (WSDL) 或复杂的消息类型。 XLANG/s 支持以下复杂数据类型：  
  
-   **messagetype.** 此数据类型定义多部分消息类型定义为数据元素和基于 XSD 的消息的组合和方法消息类型 （类或接口的方法的签名格式匹配的消息）。  
  
-   **porttype.** 此数据类型定义该类型的端口实例可以对其执行操作的端口操作的集合。  
  
-   **correlationsettype.** 此数据类型定义相关集变量的任何实例中将使用的数据。 相关集数据是用于确保整个系统的消息将调度到相应正在运行的业务流程实例的路由机制。 例如，如果采购订单发送到贸易合作伙伴进行处理，则正确的对应于该采购订单的业务流程实例在其返回上调用命令性。  
  
-   **servicelinktype.** 此数据类型定义的一套**porttype**形成一个逻辑上一致的业务流程中使用的端口组的值。 服务链接的使用是强大的机制，允许在运行时动态分配到的端口组。 这样，您可以定义可用于与多个贸易合作伙伴进行交互的单个业务流程。  
  
## <a name="see-also"></a>请参阅  
 [Xlang-s 语句](../core/xlang-s-statements.md)   
 [Xlang-s 变量和运算符](../core/xlang-s-variables-and-operators.md)   
 [Xlang-s 表达式](../core/xlang-s-expressions.md)   
 [Xlang-s 保留字](../core/xlang-s-reserved-words.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)