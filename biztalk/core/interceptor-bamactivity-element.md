---
title: "拦截器 BamActivity 元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43869922e46187c8b2e06155d525e428edd905
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-bamactivity-element"></a>侦听器 BamActivity 元素
**BamActivity**元素定义单个 BAM 活动。  
  
## <a name="format"></a>格式  
 `BamActivity`元素包括**名称**属性，并包含一个或多个`OnEvent`元素。  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a>属性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|Name|BAM 活动用户定义的名称。|  
  
## <a name="example"></a>示例  
 下面的示例包含具有单个 OnEvent 的“MyOrderWorkflow”的示例 BamActivity。  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a>另请参阅  
 [拦截器 EventSource 元素](../core/interceptor-eventsource-element.md)   
 [拦截器 OnEvent 元素](../core/interceptor-onevent-element.md)