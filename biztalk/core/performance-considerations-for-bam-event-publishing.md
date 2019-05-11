---
title: 有关 BAM 事件发布的性能注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e01292443316088986ee0897cf180b1e26b103ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395295"
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="a8797-102">有关 BAM 事件发布的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="a8797-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="a8797-103">BAM 支持两种形式的业务事件发布：</span><span class="sxs-lookup"><span data-stu-id="a8797-103">BAM supports two forms of business event publishing:</span></span>  
  
- <span data-ttu-id="a8797-104">同步</span><span class="sxs-lookup"><span data-stu-id="a8797-104">Synchronous</span></span>  
  
- <span data-ttu-id="a8797-105">异步</span><span class="sxs-lookup"><span data-stu-id="a8797-105">Asynchronous</span></span>  
  
  <span data-ttu-id="a8797-106">下图演示了两个模型。</span><span class="sxs-lookup"><span data-stu-id="a8797-106">The following diagram illustrates the two models.</span></span>  
  
  <span data-ttu-id="a8797-107">![](../core/media/bam-topologies.gif "bam_topologies")</span><span class="sxs-lookup"><span data-stu-id="a8797-107">![](../core/media/bam-topologies.gif "bam_topologies")</span></span>  
  <span data-ttu-id="a8797-108">BAM 拓扑</span><span class="sxs-lookup"><span data-stu-id="a8797-108">BAM Topologies</span></span>  
  
  <span data-ttu-id="a8797-109">同步方法是要简单得多的管理和使用在代码中，而异步方法可提高性能。</span><span class="sxs-lookup"><span data-stu-id="a8797-109">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8797-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="a8797-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a8797-111">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="a8797-111">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="a8797-112">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="a8797-112">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)