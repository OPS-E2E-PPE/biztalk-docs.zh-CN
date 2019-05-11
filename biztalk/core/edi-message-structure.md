---
title: EDI 消息结构 |Microsoft Docs
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
ms.openlocfilehash: a8584f0c002fac052f5ed6a0cb2b8885587821e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389208"
---
# <a name="edi-message-structure"></a>EDI 消息结构
EDI 消息由信封和一系列分层结构元素组成。 该信封包含一组标头和尾部，每个集都描述并包含一个结构元素。 这些结构元素如下所示：  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 EDI 消息的层次结构使事务集/消息和用户组要进行批处理。 即使交换包含只能有一个事务集/消息和一个组，该交换的结构具有相同的基本结构元素，它将具有批处理，出现异常，将不会有多个事务集 /在消息或组的元素。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 的标头和尾部](../core/edi-headers-and-trailers.md)  
  
-   [EDI 交换结构元素](../core/edi-interchange-structural-element.md)  
  
-   [EDI 组结构元素](../core/edi-group-structural-element.md)  
  
-   [EDI 事务集-消息结构元素](../core/edi-transaction-set-message-structural-element.md)  
  
-   [EDI 段结构元素](../core/edi-segment-structural-element.md)  
  
-   [EDI 数据元素结构元素](../core/edi-data-element-structural-element.md)