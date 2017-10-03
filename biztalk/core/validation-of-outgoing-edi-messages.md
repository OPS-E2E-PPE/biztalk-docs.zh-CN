---
title: "验证对传出的 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-outgoing-edi-messages"></a>传出 EDI 消息的验证
EDI 发送管道处理要发送的消息时，将对信封和消息数据执行一系列验证。 其中一些处理将始终执行，而有些处理将仅在您启用的情况下才执行。 这些验证包括  
  
-   针对消息架构进行的事务集数据元素架构验证。 该验证将始终执行。  
  
-   对事务集数据元素进行跨字段验证（仅限 X12 编码消息）。 如果在消息架构中启用了此验证，则执行此验证。  
  
-   对事务集数据元素执行 EDI 验证。 如果启用协议中的属性，执行此操作。  
  
-   对事务集数据元素执行扩展验证。 如果启用协议中的属性，执行此操作。  
  
-   按照 X12 标准验证基于事务集的单个组（组映射）内的事务集。 执行此操作仅当**入站批处理选项**属性设置为**保留交换-出错时暂停交换**或**保留交换-挂起事务在错误上设置**。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 结构验证](../core/edi-structural-validation.md)   
 [协议属性验证](../core/agreement-properties-validation.md)   
 [EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)   
 [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)   
 [架构验证](../core/schema-validation2.md)   
 [交叉字段段验证](../core/cross-field-segment-validation.md)