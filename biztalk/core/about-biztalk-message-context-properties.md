---
title: 关于 BizTalk 消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc700e43-a44c-482b-b91c-9f1d997a486a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eb7277ab741dc1a33dd7d905048db3d411c02d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362375"
---
# <a name="about-biztalk-message-context-properties"></a>关于 BizTalk 消息上下文属性
当 BizTalk Server 适配器接收到文档时，适配器会创建 BizTalk 消息的文档。 BizTalk 消息包含已接收到消息上下文以及文档。 消息上下文是处理文档时，BizTalk Server 所使用的各种属性的容器。 在消息上下文中的每个属性组成三项内容、 名称、 命名空间中和一个值。 例如，以下消息上下文属性描述文档的交换 ID:  
  
```  
<Property Name="InterchangeID" Namespace="http://schemas.microsoft.com/BizTalk/2003/system-properties" Value="{AC07BF30-2F1A-42B0-8390-191EF38BA839}"/>  
```  
  
 通过 BizTalk Server 消息上下文属性添加到在消息的整个生存期内的消息上下文。  
  
 有两种不同类型的使用如下所述的 biztalk 消息上下文属性：  
  
## <a name="property-fields"></a>属性字段  
 属性字段是由 BizTalk 消息引擎用于文档路由、 消息跟踪，并用于评估业务流程中的消息上下文属性。 您可以显式将提升在文档中的字段为消息上下文为属性字段通过编辑文档中 BizTalk Server 架构编辑器中提供的架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 为了在文档中的字段写入消息上下文为属性字段，文档架构必须具有关联的属性架构。 属性字段被限制为 255 个字符。 **IsPromoted**消息上下文中的属性字段的属性设置为**True**。  
  
## <a name="distinguished-fields"></a>可分辨的字段  
 可分辨的字段是不需要单独的属性架构和仅可从业务流程中访问消息上下文属性。 可分辨的字段不能用于路由或跟踪。 由于可分辨的字段不需要单独的属性架构，由业务流程引擎的可分辨字段的评估由业务流程引擎使用更少的开销比属性字段的评估。 属性字段的评估需要 XPath 查询，而可分辨字段的评估不需要 XPath 查询，因为管道拆装器填充的上下文中的可分辨的字段，并且业务流程引擎读取缓存的值。 但是，如果业务流程引擎在上下文中未找到该属性，它会发起一个 XPath 查询以查找的值。 可分辨的字段没有大小限制。 **IsPromoted**消息上下文中的可分辨字段的属性设置为**False**。  
  
## <a name="summary-of-differences-between-property-fields-and-distinguished-fields"></a>属性字段与可分辨字段之间的差异的摘要  
 下表总结了差异和属性字段与可分辨的字段之间的相似之处：  
  
|**Attribute**|**属性字段**|**可分辨的字段**|  
|-------------------|------------------------|-----------------------------|  
|IsPromoted 属性|True|False|  
|大小限制|255 个字符|无限制|  
|用于路由|是|否|  
|用于跟踪|是|否|  
|在业务流程中使用|是|是|  
|需要属性架构|是|否|  
|可通过管道和端口访问|是|否|  
  
## <a name="see-also"></a>请参阅  
 [使用消息内容控制消息处理的方法](../core/ways-to-use-message-content-to-control-message-processing.md)