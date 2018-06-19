---
title: EDI 消息结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239629"
---
# <a name="edi-message-structure"></a>EDI 消息结构
EDI 消息由信封和一系列分层结构元素组成。 信封包含一组头部和尾部，每组都描述并包含一个结构元素。 这些结构元素如下所示：  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 EDI 消息的层次结构允许对事务集/消息和组进行批处理。 即使一个交换只包含一个事务集/消息和一个组，该交换也具有与批处理时完全相同的基本结构元素，不同的是，它不会有多个事务集/消息或组元素。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 标头和拖车安排](../core/edi-headers-and-trailers.md)  
  
-   [EDI 交换结构化元素](../core/edi-interchange-structural-element.md)  
  
-   [EDI 组结构化元素](../core/edi-group-structural-element.md)  
  
-   [EDI 事务集消息结构化元素](../core/edi-transaction-set-message-structural-element.md)  
  
-   [EDI 段结构化元素](../core/edi-segment-structural-element.md)  
  
-   [EDI 数据元素结构化元素](../core/edi-data-element-structural-element.md)