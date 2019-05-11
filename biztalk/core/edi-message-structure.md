---
title: EDI 消息结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8584f0c002fac052f5ed6a0cb2b8885587821e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389208"
---
# <a name="edi-message-structure"></a><span data-ttu-id="4205e-102">EDI 消息结构</span><span class="sxs-lookup"><span data-stu-id="4205e-102">EDI Message Structure</span></span>
<span data-ttu-id="4205e-103">EDI 消息由信封和一系列分层结构元素组成。</span><span class="sxs-lookup"><span data-stu-id="4205e-103">EDI messages consist of an envelope and a hierarchical series of structural elements.</span></span> <span data-ttu-id="4205e-104">该信封包含一组标头和尾部，每个集都描述并包含一个结构元素。</span><span class="sxs-lookup"><span data-stu-id="4205e-104">The envelope contains a set of headers and trailers, each set of which describes and contains a structural element.</span></span> <span data-ttu-id="4205e-105">这些结构元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="4205e-105">These structural elements are as follows:</span></span>  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 <span data-ttu-id="4205e-106">EDI 消息的层次结构使事务集/消息和用户组要进行批处理。</span><span class="sxs-lookup"><span data-stu-id="4205e-106">The hierarchical structure of an EDI message enables transaction sets/messages and groups to be batched.</span></span> <span data-ttu-id="4205e-107">即使交换包含只能有一个事务集/消息和一个组，该交换的结构具有相同的基本结构元素，它将具有批处理，出现异常，将不会有多个事务集 /在消息或组的元素。</span><span class="sxs-lookup"><span data-stu-id="4205e-107">Even if an interchange contains only one transaction set/message and only one group, that interchange is structured with the same basic structural elements that it would have if it were batched, with the exception that there would not be multiple transaction set/message or group elements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4205e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="4205e-108">In This Section</span></span>  
  
-   [<span data-ttu-id="4205e-109">EDI 的标头和尾部</span><span class="sxs-lookup"><span data-stu-id="4205e-109">EDI Headers and Trailers</span></span>](../core/edi-headers-and-trailers.md)  
  
-   [<span data-ttu-id="4205e-110">EDI 交换结构元素</span><span class="sxs-lookup"><span data-stu-id="4205e-110">EDI Interchange Structural Element</span></span>](../core/edi-interchange-structural-element.md)  
  
-   [<span data-ttu-id="4205e-111">EDI 组结构元素</span><span class="sxs-lookup"><span data-stu-id="4205e-111">EDI Group Structural Element</span></span>](../core/edi-group-structural-element.md)  
  
-   [<span data-ttu-id="4205e-112">EDI 事务集-消息结构元素</span><span class="sxs-lookup"><span data-stu-id="4205e-112">EDI Transaction Set-Message Structural Element</span></span>](../core/edi-transaction-set-message-structural-element.md)  
  
-   [<span data-ttu-id="4205e-113">EDI 段结构元素</span><span class="sxs-lookup"><span data-stu-id="4205e-113">EDI Segment Structural Element</span></span>](../core/edi-segment-structural-element.md)  
  
-   [<span data-ttu-id="4205e-114">EDI 数据元素结构元素</span><span class="sxs-lookup"><span data-stu-id="4205e-114">EDI Data Element Structural Element</span></span>](../core/edi-data-element-structural-element.md)