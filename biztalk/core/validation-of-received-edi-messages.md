---
title: 验证收到的 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af8946cf94747f74db25d1854d2157a36370cbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292594"
---
# <a name="validation-of-received-edi-messages"></a>验证收到的 EDI 消息
当 EDI 接收管道处理传入的消息时，它对信封和消息数据执行一系列验证。 始终执行这些过程的一些;一些执行只能在启用它们。 这些验证包括：  
  
-   **始终执行的验证**:  
  
    -   验证交换信封的结构。  
  
    -   针对贸易合作伙伴协议 （或如果未定义协议的后备协议） 的信封验证。  
  
    -   针对控制架构进行的信封架构验证。  
  
    -   针对消息架构进行的事务集数据元素架构验证。  
  
    -   验证类型的事务集内基于事务的单个组设置-组映射提供的 X12 标准。  
  
-   **仅当启用时，才会执行的验证**:  
  
    -   对事务集数据元素执行 EDI 验证。 如果在协议属性中启用了，执行此操作。  
  
    -   对事务集数据元素执行扩展的验证。 如果在协议属性中启用了，执行此操作。  
  
    -   跨字段验证对事务集数据元素 （仅 X12 编码消息）。 如果启用消息架构中，执行此操作。  
  
## <a name="see-also"></a>请参阅  
 [EDI 结构验证](../core/edi-structural-validation.md)   
 [协议属性验证](../core/agreement-properties-validation.md)   
 [EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)   
 [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)   
 [架构验证](../core/schema-validation2.md)   
 [跨字段-段验证](../core/cross-field-segment-validation.md)