---
title: 跨字段-段验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e757b4f-71fe-44d5-9580-c8b1c8eb2366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e842c9376a6f143bb0979930c3d4239a355904c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389842"
---
# <a name="cross-field-segment-validation"></a>跨字段-段验证
EDI 接收管道和 EDI 发送管道可以对 X12 编码消息中的事务集数据元素执行跨字段/段验证。 在 X12 中，此验证称为关系条件。 跨字段验证通过批注表示，并因此，与 EDI 验证。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持 EDIFACT 依赖规则。  
  
 对于 X12 编码的消息，X12ConditionDesignator_Check 标志设置为"是"消息架构中启用此验证。 此标志为批注的架构"appinfo"部分中。 默认情况下，此标志设置为"否"，并跨字段/段验证未启用适用于 X12 架构。 对于 HIPAA 架构默认值设置为"是"并启用跨字段/段验证。  
  
> [!NOTE]
>  跨字段/段验证是不同于 EDI 数据元素验证和扩展 (BTS-XSD) 验证。 而不执行跨字段/段验证，可以执行 EDI 数据元素验证和/或扩展的验证，而不执行 EDI 数据元素验证和/或扩展的验证，可以执行跨字段/段验证。  
  
 在 X12 的可选性包括必需 (M)、 可选 (O) 和关系 (R) （跨字段验证）。 如果可选性为必需，复合类型中的至少一个组件数据元素必须是值。  
  
## <a name="x12-optionality"></a>X12 可选性  
 在 X12 中，跨字段/段验证针对关系可选性包括一系列检查架构中的规则中列出。 每个规则由以下元素中标识\<xs:annotation\>元素：  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 "规则"元素中的关系条件指示什么进行了验证，该规则。 此元素包括在其执行跨字段验证的使用者的列表。 这些主题包括以下节点中：  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 下表显示了 X12 关系条件：  
  
|细分类|关系条件|Description|  
|-----------------------|--------------------------|-----------------|  
|配对|X12ConditionDesignatorX_Paired|如果存在任何关系条件中指定的主题元素，则必须存在所有指定的主题元素。|  
|Required|X12ConditionDesignatorX_Required|至少一个在关系条件中指定的主题元素必须存在。|  
|排除|X12ConditionDesignatorX_Exclusion|不能超过一的关系条件中指定的主题元素可能会出现。|  
|条件|X12ConditionDesignatorX_Conditional|如果存在在关系条件中指定的第一个主题元素，则所有其他主题元素必须存在。 未指定在条件中的第一个元素的元素的任意或全部可能出现不带要求的第一个元素必须存在。 在条件中元素的顺序不需要的数据段中的数据元素的顺序相同。|  
|列表条件|X12ConditionDesignatorX_List 条件|如果存在在关系条件中指定的第一个主题元素，则必须存在至少一个其他主题元素。 未指定在条件中的第一个元素的元素的任意或全部可能出现不带要求的第一个元素必须存在。 在条件中元素的顺序不需要的数据段中的数据元素的顺序相同。|  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)