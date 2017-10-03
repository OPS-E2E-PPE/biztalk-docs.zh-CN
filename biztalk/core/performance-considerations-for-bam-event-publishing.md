---
title: "有关 BAM 事件发布的性能注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebab873c94c0ae17abf9938883662ca8777cef36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="ef635-102">有关 BAM 事件发布的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="ef635-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="ef635-103">BAM 支持两种形式的业务事件发布：</span><span class="sxs-lookup"><span data-stu-id="ef635-103">BAM supports two forms of business event publishing:</span></span>  
  
-   <span data-ttu-id="ef635-104">同步</span><span class="sxs-lookup"><span data-stu-id="ef635-104">Synchronous</span></span>  
  
-   <span data-ttu-id="ef635-105">异步</span><span class="sxs-lookup"><span data-stu-id="ef635-105">Asynchronous</span></span>  
  
 <span data-ttu-id="ef635-106">下图说明了两个模型。</span><span class="sxs-lookup"><span data-stu-id="ef635-106">The following diagram illustrates the two models.</span></span>  
  
 ![](../core/media/bam-topologies.gif "bam_topologies")  
<span data-ttu-id="ef635-107">BAM 拓扑</span><span class="sxs-lookup"><span data-stu-id="ef635-107">BAM Topologies</span></span>  
  
 <span data-ttu-id="ef635-108">同步的方法是用于管理和使用从代码中，异步方法可以更好的性能时要简单得多。</span><span class="sxs-lookup"><span data-stu-id="ef635-108">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef635-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="ef635-109">In This Section</span></span>  
  
-   [<span data-ttu-id="ef635-110">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="ef635-110">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="ef635-111">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="ef635-111">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)