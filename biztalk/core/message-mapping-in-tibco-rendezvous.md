---
title: 消息 TIBCO Rendezvous 中的映射 |Microsoft Docs
description: 消息字段和 TIBCO Rendezvous 的 BizTalk 适配器中的 xml 消息映射
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8d3b287bc1475227231301275500fca32e90da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326205"
---
# <a name="message-mapping-in-tibco-rendezvous"></a>TIBCO Rendezvous 中消息映射
TIBCO Rendezvous 消息由标头信息和一组消息字段组成。 标头信息直接映射到消息上下文属性。  
  
## <a name="message-field-elements"></a>消息字段元素  
 消息字段组成的以下元素：  
  
|元素|Description|  
|-------------|-----------------|  
|**名称**|字符的字符串。 无需一条消息中是唯一的。|  
|**Identifier**|短整数。 在消息中是唯一的。 隐式限制到 65535 之间的消息字段数。 标识符的作用域为消息 （或子消息）。 相同的标识符可以使用其自身是两个子消息中包含消息的一部分。|  
|**ReplTest1**|消息字段数据。|  
|**Count**|（数组情况下） 的项目数|  
|**类型**|消息字段的类型。|  
  
### <a name="mapping-process"></a>映射过程  
 TIBCO Rendezvous 结构化消息按以下方式映射到 XML 元素：  
  
-   **名称**用作元素名称。 TIBCO Rendezvous 字段名称可能包含无效的 XML 元素名称中使用的字符。 适配器生成有效的字符 XML 和 TIBCO Rendezvous 之间的映射的结构化消息。  
  
-   **标识符**置于 id 属性中。  
  
-   **值**包含元素的正文的字符串表示形式。  
  
-   **计数**将被忽略。  
  
-   **类型**信息放入生成的元素的 xsi: type 属性。  
  
     有关详细信息，请参阅[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)