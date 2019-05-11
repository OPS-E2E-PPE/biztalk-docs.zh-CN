---
title: 验证传出 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e0afed109f3ea03e863e2813ca4f58d289eaa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295658"
---
# <a name="validation-of-outgoing-edi-messages"></a>验证传出 EDI 消息
当 EDI 发送管道处理要发送的消息时，它对信封和消息数据执行一系列验证。 始终执行这些过程的一些;一些执行只能在启用它们。 这些验证包括：  
  
-   针对消息架构进行的事务集数据元素架构验证。 始终执行此操作。  
  
-   跨字段验证对事务集数据元素 （仅 X12 编码消息）。 如果启用消息架构中，执行此操作。  
  
-   对事务集数据元素执行 EDI 验证。 如果协议中启用属性，执行此操作。  
  
-   对事务集数据元素执行扩展的验证。 如果协议中启用属性，执行此操作。  
  
-   验证事务集内基于事务集-组映射，根据 X12 的单个组标准。 执行此操作时，才**入站批处理选项**属性设置为**保留交换-出错时挂起交换**或**保留交换-挂起事务出错时设置**。  
  
## <a name="see-also"></a>请参阅  
 [EDI 结构验证](../core/edi-structural-validation.md)   
 [协议属性验证](../core/agreement-properties-validation.md)   
 [EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)   
 [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)   
 [架构验证](../core/schema-validation2.md)   
 [跨字段-段验证](../core/cross-field-segment-validation.md)