---
title: EDI 消息结构 |Microsoft 文档
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
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239629"
---
# <a name="edi-message-structure"></a><span data-ttu-id="9ad0c-102">EDI 消息结构</span><span class="sxs-lookup"><span data-stu-id="9ad0c-102">EDI Message Structure</span></span>
<span data-ttu-id="9ad0c-103">EDI 消息由信封和一系列分层结构元素组成。</span><span class="sxs-lookup"><span data-stu-id="9ad0c-103">EDI messages consist of an envelope and a hierarchical series of structural elements.</span></span> <span data-ttu-id="9ad0c-104">信封包含一组头部和尾部，每组都描述并包含一个结构元素。</span><span class="sxs-lookup"><span data-stu-id="9ad0c-104">The envelope contains a set of headers and trailers, each set of which describes and contains a structural element.</span></span> <span data-ttu-id="9ad0c-105">这些结构元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ad0c-105">These structural elements are as follows:</span></span>  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 <span data-ttu-id="9ad0c-106">EDI 消息的层次结构允许对事务集/消息和组进行批处理。</span><span class="sxs-lookup"><span data-stu-id="9ad0c-106">The hierarchical structure of an EDI message enables transaction sets/messages and groups to be batched.</span></span> <span data-ttu-id="9ad0c-107">即使一个交换只包含一个事务集/消息和一个组，该交换也具有与批处理时完全相同的基本结构元素，不同的是，它不会有多个事务集/消息或组元素。</span><span class="sxs-lookup"><span data-stu-id="9ad0c-107">Even if an interchange contains only one transaction set/message and only one group, that interchange is structured with the same basic structural elements that it would have if it were batched, with the exception that there would not be multiple transaction set/message or group elements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ad0c-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="9ad0c-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9ad0c-109">EDI 标头和拖车安排</span><span class="sxs-lookup"><span data-stu-id="9ad0c-109">EDI Headers and Trailers</span></span>](../core/edi-headers-and-trailers.md)  
  
-   [<span data-ttu-id="9ad0c-110">EDI 交换结构化元素</span><span class="sxs-lookup"><span data-stu-id="9ad0c-110">EDI Interchange Structural Element</span></span>](../core/edi-interchange-structural-element.md)  
  
-   [<span data-ttu-id="9ad0c-111">EDI 组结构化元素</span><span class="sxs-lookup"><span data-stu-id="9ad0c-111">EDI Group Structural Element</span></span>](../core/edi-group-structural-element.md)  
  
-   [<span data-ttu-id="9ad0c-112">EDI 事务集消息结构化元素</span><span class="sxs-lookup"><span data-stu-id="9ad0c-112">EDI Transaction Set-Message Structural Element</span></span>](../core/edi-transaction-set-message-structural-element.md)  
  
-   [<span data-ttu-id="9ad0c-113">EDI 段结构化元素</span><span class="sxs-lookup"><span data-stu-id="9ad0c-113">EDI Segment Structural Element</span></span>](../core/edi-segment-structural-element.md)  
  
-   [<span data-ttu-id="9ad0c-114">EDI 数据元素结构化元素</span><span class="sxs-lookup"><span data-stu-id="9ad0c-114">EDI Data Element Structural Element</span></span>](../core/edi-data-element-structural-element.md)