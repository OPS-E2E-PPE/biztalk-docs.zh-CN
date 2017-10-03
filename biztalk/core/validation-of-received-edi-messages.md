---
title: "验证收到的 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc48b343332ea6b402841ec5ed1f5c9af49b2dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-received-edi-messages"></a>验证收到的 EDI 消息
EDI 接收管道处理传入的消息时，将对信封和消息数据执行一系列验证。 其中一些处理将始终执行，而有些处理将仅在您启用的情况下才执行。 这些验证包括  
  
-   **始终执行验证**:  
  
    -   验证交换信封的结构。  
  
    -   针对贸易合作伙伴协议（如果未定义任何协议，则为后备协议）进行的信封验证。  
  
    -   根据控制架构执行信封的架构验证。  
  
    -   针对消息架构进行的事务集数据元素架构验证。  
  
    -   根据 X12 标准提供的事务集-组映射验证单个组内事务集的类型。  
  
-   **仅当启用时，才执行验证**:  
  
    -   对事务集数据元素执行 EDI 验证。 如果在协议属性中启用了此验证，则执行此验证。  
  
    -   对事务集数据元素执行扩展验证。 如果在协议属性中启用了此验证，则执行此验证。  
  
    -   对事务集数据元素进行跨字段验证（仅限 X12 编码消息）。 如果启用消息架构中，执行此操作。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 结构验证](../core/edi-structural-validation.md)   
 [协议属性验证](../core/agreement-properties-validation.md)   
 [EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)   
 [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)   
 [架构验证](../core/schema-validation2.md)   
 [交叉字段段验证](../core/cross-field-segment-validation.md)