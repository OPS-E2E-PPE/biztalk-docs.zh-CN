---
title: 侦听器 BamActivity 元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d9929e1122f00ede80c1d3e7c9efff5a2f3fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382056"
---
# <a name="interceptor-bamactivity-element"></a>侦听器 BamActivity 元素
**BamActivity**元素定义单个 BAM 活动。  
  
## <a name="format"></a>格式  
 `BamActivity`元素包含**名称**属性，包含一个或多个`OnEvent`元素。  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a>特性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|“属性”|用户定义的 BAM 活动名称。|  
  
## <a name="example"></a>示例  
 下面的示例包含具有单个 OnEvent 的"MyOrderWorkflow"的示例 BamActivity。  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器 EventSource 元素](../core/interceptor-eventsource-element.md)   
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)