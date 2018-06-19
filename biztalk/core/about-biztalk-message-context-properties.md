---
title: 有关 BizTalk 消息上下文属性 |Microsoft 文档
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
ms.openlocfilehash: 49d802ad2ca50538c25182311c68604c26d5a832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225493"
---
# <a name="about-biztalk-message-context-properties"></a>关于 BizTalk 消息上下文属性
当 BizTalk Server 适配器接收到某文档时，适配器将为该文档创建 BizTalk 消息。 BizTalk 消息包含所接收的文档以及消息上下文。 消息上下文为 BizTalk Server 处理该文档时所使用的各种属性的容器。 消息上下文中的每个属性均由以下三个部分构成：名称、命名空间和值。 例如，以下消息上下文属性对文档的交换 ID 进行了说明：  
  
```  
<Property Name="InterchangeID" Namespace="http://schemas.microsoft.com/BizTalk/2003/system-properties" Value="{AC07BF30-2F1A-42B0-8390-191EF38BA839}"/>  
```  
  
 在消息的整个生存期内，只要该消息通过 BizTalk Server，便会将消息上下文属性添加到消息上下文中。  
  
 BizTalk 使用两种不同类型的消息上下文属性，如下所述：  
  
## <a name="property-fields"></a>属性字段  
 属性字段是 BizTalk 消息引擎所使用的消息上下文属性，用于文档路由、消息跟踪和业务流程中的评估。 你可以显式提升文档中的字段为消息上下文属性字段作为通过编辑文档在 BizTalk Server 架构编辑器中提供的架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 为了将文档中的字段作为属性字段写入消息上下文，该文档架构必须具有关联的属性架构。 属性字段限制在 255 个字符之内。 **IsPromoted**消息上下文中的属性字段的属性设置为**True**。  
  
## <a name="distinguished-fields"></a>可分辨的字段  
 可分辨字段是不需要单独的属性架构并且只能从业务流程进行访问的消息上下文属性。 可分辨字段不能用于路由或跟踪。 由于可分辨字段不需要单独的属性架构，因此业务流程引擎对可分辨字段进行的评估所产生的系统开销少于业务流程引擎对属性字段进行的评估。 属性字段的评估需要 XPath 查询，而可分辨字段的评估不需要 XPath 查询，因为管道拆装器在上下文中填充可分辨字段，并且业务流程引擎读取缓存的值。 但是，如果业务流程引擎在上下文中未找到该属性，则它会发起一个 XPath 查询以找到该值。 可分辨字段没有任何大小限制。 **IsPromoted**消息上下文中的可分辨字段的属性设置为**False**。  
  
## <a name="summary-of-differences-between-property-fields-and-distinguished-fields"></a>属性字段与可分辨字段之间区别的概括介绍  
 下表概括列出了属性字段与可分辨字段之间的区别和相似点：  
  
|**Attribute**|**属性字段**|**可分辨的字段**|  
|-------------------|------------------------|-----------------------------|  
|IsPromoted 属性|True|False|  
|大小限制|255 个字符|无限制|  
|用于路由|是|是|  
|用于跟踪|是|是|  
|在业务流程中使用|是|是|  
|需要属性架构|是|是|  
|可通过管道和端口进行访问|是|是|  
  
## <a name="see-also"></a>另请参阅  
 [使用与控件消息处理的消息内容的方法](../core/ways-to-use-message-content-to-control-message-processing.md)