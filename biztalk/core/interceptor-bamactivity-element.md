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
# <a name="interceptor-bamactivity-element"></a><span data-ttu-id="6959c-102">侦听器 BamActivity 元素</span><span class="sxs-lookup"><span data-stu-id="6959c-102">Interceptor BamActivity Element</span></span>
<span data-ttu-id="6959c-103">**BamActivity**元素定义单个 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="6959c-103">The **BamActivity** element defines a single BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="6959c-104">格式</span><span class="sxs-lookup"><span data-stu-id="6959c-104">Format</span></span>  
 <span data-ttu-id="6959c-105">`BamActivity`元素包括**名称**属性，并包含一个或多个`OnEvent`元素。</span><span class="sxs-lookup"><span data-stu-id="6959c-105">The `BamActivity` element includes a **Name** attribute and contains one or more `OnEvent` elements.</span></span>  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a><span data-ttu-id="6959c-106">属性</span><span class="sxs-lookup"><span data-stu-id="6959c-106">Attributes</span></span>  
  
|<span data-ttu-id="6959c-107">属性名称</span><span class="sxs-lookup"><span data-stu-id="6959c-107">Attribute name</span></span>|<span data-ttu-id="6959c-108">Description</span><span class="sxs-lookup"><span data-stu-id="6959c-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6959c-109">Name</span><span class="sxs-lookup"><span data-stu-id="6959c-109">Name</span></span>|<span data-ttu-id="6959c-110">BAM 活动用户定义的名称。</span><span class="sxs-lookup"><span data-stu-id="6959c-110">User-defined name of the BAM activity.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6959c-111">示例</span><span class="sxs-lookup"><span data-stu-id="6959c-111">Example</span></span>  
 <span data-ttu-id="6959c-112">下面的示例包含具有单个 OnEvent 的“MyOrderWorkflow”的示例 BamActivity。</span><span class="sxs-lookup"><span data-stu-id="6959c-112">The following example contains a sample BamActivity for "MyOrderWorkflow" with a single OnEvent.</span></span>  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6959c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6959c-113">See Also</span></span>  
 <span data-ttu-id="6959c-114">[拦截器 EventSource 元素](../core/interceptor-eventsource-element.md) </span><span class="sxs-lookup"><span data-stu-id="6959c-114">[Interceptor EventSource Element](../core/interceptor-eventsource-element.md) </span></span>  
 [<span data-ttu-id="6959c-115">拦截器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="6959c-115">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)