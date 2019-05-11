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
# <a name="interceptor-bamactivity-element"></a><span data-ttu-id="6f27c-102">侦听器 BamActivity 元素</span><span class="sxs-lookup"><span data-stu-id="6f27c-102">Interceptor BamActivity Element</span></span>
<span data-ttu-id="6f27c-103">**BamActivity**元素定义单个 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="6f27c-103">The **BamActivity** element defines a single BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="6f27c-104">格式</span><span class="sxs-lookup"><span data-stu-id="6f27c-104">Format</span></span>  
 <span data-ttu-id="6f27c-105">`BamActivity`元素包含**名称**属性，包含一个或多个`OnEvent`元素。</span><span class="sxs-lookup"><span data-stu-id="6f27c-105">The `BamActivity` element includes a **Name** attribute and contains one or more `OnEvent` elements.</span></span>  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a><span data-ttu-id="6f27c-106">特性</span><span class="sxs-lookup"><span data-stu-id="6f27c-106">Attributes</span></span>  
  
|<span data-ttu-id="6f27c-107">属性名称</span><span class="sxs-lookup"><span data-stu-id="6f27c-107">Attribute name</span></span>|<span data-ttu-id="6f27c-108">Description</span><span class="sxs-lookup"><span data-stu-id="6f27c-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6f27c-109">“属性”</span><span class="sxs-lookup"><span data-stu-id="6f27c-109">Name</span></span>|<span data-ttu-id="6f27c-110">用户定义的 BAM 活动名称。</span><span class="sxs-lookup"><span data-stu-id="6f27c-110">User-defined name of the BAM activity.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6f27c-111">示例</span><span class="sxs-lookup"><span data-stu-id="6f27c-111">Example</span></span>  
 <span data-ttu-id="6f27c-112">下面的示例包含具有单个 OnEvent 的"MyOrderWorkflow"的示例 BamActivity。</span><span class="sxs-lookup"><span data-stu-id="6f27c-112">The following example contains a sample BamActivity for "MyOrderWorkflow" with a single OnEvent.</span></span>  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f27c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f27c-113">See Also</span></span>  
 <span data-ttu-id="6f27c-114">[侦听器 EventSource 元素](../core/interceptor-eventsource-element.md) </span><span class="sxs-lookup"><span data-stu-id="6f27c-114">[Interceptor EventSource Element](../core/interceptor-eventsource-element.md) </span></span>  
 [<span data-ttu-id="6f27c-115">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="6f27c-115">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)