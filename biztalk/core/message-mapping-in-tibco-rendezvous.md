---
title: "消息映射中 TIBCO 会合 |Microsoft 文档"
description: "消息字段和 TIBCO 会合到 BizTalk 适配器中的 XML 消息映射"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="message-mapping-in-tibco-rendezvous"></a>TIBCO Rendezvous 中消息映射
TIBCO Rendezvous 消息由标头信息和一组消息字段组成。 标头信息直接映射到消息上下文属性。  
  
## <a name="message-field-elements"></a>消息字段元素  
 消息字段由下列元素组成：  
  
|元素|Description|  
|-------------|-----------------|  
|**名称**|字符的字符串。 在消息中不必唯一。|  
|**Identifier**|短整数。 在消息中唯一。 隐式限制到 65535 之间的消息字段数。 标识符的范围为消息 （或 sub 消息）。 相同的标识符可以用于两个子消息中，它们自身属于包含消息。|  
|**值**|消息字段数据。|  
|**Count**|项目数（数组情况下）|  
|**类型**|消息字段的类型。|  
  
### <a name="mapping-process"></a>映射进程  
 TIBCO Rendezvous 结构化消息按以下方式映射到 XML 元素：  
  
-   **名称**用作元素名称。 TIBCO Rendezvous 字段名称可能包含在 XML 元素名称中使用时无效的字符。 适配器在 XML 和 TIBCO Rendezvous 结构化消息之间生成有效的字符映射。  
  
-   **标识符**放入 'id' 属性。  
  
-   **值**包含正文的元素的字符串表示形式。  
  
-   **计数**将被忽略。  
  
-   **类型**信息放入所生成元素的 xsi: type 属性。  
  
     有关详细信息，请参阅[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 会合概念](../core/tibco-rendezvous-concepts.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)