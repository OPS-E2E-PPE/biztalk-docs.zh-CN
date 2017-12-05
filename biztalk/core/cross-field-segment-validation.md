---
title: "交叉字段段验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e757b4f-71fe-44d5-9580-c8b1c8eb2366
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd3a0b5f68ded39fbf5cc88a4ba8aac6725602e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="cross-field-segment-validation"></a>交叉字段段验证
EDI 接收管道和 EDI 发送管道可对 X12 编码消息中的事务集数据元素执行跨字段/段验证。 在 X12 中这种验证称为关系条件。 跨字段验证通过批注表示，因此它与 EDI 验证有关。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持 EDIFACT 依赖规则。  
  
 对于 X12 编码的消息，可通过将消息架构中的 X12ConditionDesignator_Check 标记设置为“Yes”来启用此验证。 该标记位于该架构“appinfo”部分的批注中。 默认情况下，该标记设置为“No”，且不为 X12 架构启用跨字段/段验证。 对于 HIPAA 架构默认值设置为"是"并验证启用跨 field\segment。  
  
> [!NOTE]
>  跨字段/段验证与 EDI 数据元素验证和扩展 (BTS-XSD) 验证都不同。 可在不执行跨字段/段验证的情况下执行 EDI 数据元素验证和/或扩展验证，也可在不执行 EDI 数据元素验证和/或扩展验证的情况下执行跨字段/段验证。  
  
 X12 的可选性包括必需 (M)、可选 (O) 和关系 (R)（跨字段验证）。 如果可选性为必需，则必须至少对复合类型中的一个组件数据元素赋值。  
  
## <a name="x12-optionality"></a>X12 可选性  
 在 X12 中，针对关系可选性的跨字段/段验证包括架构的规则中列出的一系列检查。 每个规则由以下元素中\<xs:annotation\>元素：  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 "规则"元素中的关系条件表示什么进行了验证，该规则。 该元素包含对其执行跨字段验证的主题的列表。 这些主题包括在下面的节点中：  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 下表显示了 X12 关系条件：  
  
|子分类|关系条件|Description|  
|-----------------------|--------------------------|-----------------|  
|成对|X12ConditionDesignatorX_Paired|如果存在在关系条件中指定的任何主题元素，则指定的所有主题元素都必须存在。|  
|必需|X12ConditionDesignatorX_Required|必须至少存在一个在关系条件中指定的主题元素。|  
|排除|X12ConditionDesignatorX_Exclusion|可以至多存在一个在关系条件中指定的主题元素。|  
|条件|X12ConditionDesignatorX_Conditional|如果存在在关系条件中指定的第一个主题元素，则所有其他主题元素都必须存在。 任何或所有未指定为条件中第一个元素的元素都可以在不要求存在第一个元素的情况下出现。 条件中的元素的顺序不需要与数据段中的数据元素的顺序相同。|  
|列表条件|X12ConditionDesignatorX_List Conditional|如果存在在关系条件中指定的第一个主题元素，则必须至少存在一个其他主题元素。 任何或所有未指定为条件中第一个元素的元素都可以在不要求存在第一个元素的情况下出现。 条件中的元素的顺序不需要与数据段中的数据元素的顺序相同。|  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)