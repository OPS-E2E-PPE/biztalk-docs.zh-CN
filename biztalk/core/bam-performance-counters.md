---
title: "BAM 性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4307f72f149405fbc04e4e6cc51efe87229c2bff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-performance-counters"></a><span data-ttu-id="785bb-102">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="785bb-102">BAM Performance Counters</span></span>
<span data-ttu-id="785bb-103">使用性能计数器可以监视 BAM 事件总线服务执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="785bb-103">Performance counters allow you to monitor specific aspects of work performed by the BAM Event Bus Service.</span></span> <span data-ttu-id="785bb-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="785bb-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="785bb-105">下表列出了业务活动监视中可用的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="785bb-105">The following table lists the performance counters available in Business Activity Monitoring.</span></span>  
  
|<span data-ttu-id="785bb-106">计数器</span><span class="sxs-lookup"><span data-stu-id="785bb-106">Counter</span></span>|<span data-ttu-id="785bb-107">Description</span><span class="sxs-lookup"><span data-stu-id="785bb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="785bb-108">Events being processed</span><span class="sxs-lookup"><span data-stu-id="785bb-108">Events being processed</span></span>|<span data-ttu-id="785bb-109">BAM 事件总线服务当前处理的事件数。</span><span class="sxs-lookup"><span data-stu-id="785bb-109">The number of events the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="785bb-110">Batches being processed</span><span class="sxs-lookup"><span data-stu-id="785bb-110">Batches being processed</span></span>|<span data-ttu-id="785bb-111">BAM 事件总线服务当前处理的批数。</span><span class="sxs-lookup"><span data-stu-id="785bb-111">The number of batches the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="785bb-112">Events Committed</span><span class="sxs-lookup"><span data-stu-id="785bb-112">Events Committed</span></span>|<span data-ttu-id="785bb-113">BAM 事件总线服务在最近一秒提交给 SQL Server 的事件数。</span><span class="sxs-lookup"><span data-stu-id="785bb-113">The number of events the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="785bb-114">Records Committed</span><span class="sxs-lookup"><span data-stu-id="785bb-114">Records Committed</span></span>|<span data-ttu-id="785bb-115">BAM 事件总线服务在最近一秒提交给 SQL Server 的记录数。</span><span class="sxs-lookup"><span data-stu-id="785bb-115">The number of records the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="785bb-116">Batches Committed</span><span class="sxs-lookup"><span data-stu-id="785bb-116">Batches Committed</span></span>|<span data-ttu-id="785bb-117">BAM 事件总线服务在最近一秒提交给 SQL Server 的批数。</span><span class="sxs-lookup"><span data-stu-id="785bb-117">The number of batches the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="785bb-118">Total Events</span><span class="sxs-lookup"><span data-stu-id="785bb-118">Total Events</span></span>|<span data-ttu-id="785bb-119">BAM 事件总线服务自从启动后处理的事件数。</span><span class="sxs-lookup"><span data-stu-id="785bb-119">The number of events the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="785bb-120">Total Records</span><span class="sxs-lookup"><span data-stu-id="785bb-120">Total Records</span></span>|<span data-ttu-id="785bb-121">BAM 事件总线服务自从启动后处理的记录数。</span><span class="sxs-lookup"><span data-stu-id="785bb-121">Then number of records the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="785bb-122">Total Batches</span><span class="sxs-lookup"><span data-stu-id="785bb-122">Total Batches</span></span>|<span data-ttu-id="785bb-123">BAM 事件总线服务自从启动后处理的批数。</span><span class="sxs-lookup"><span data-stu-id="785bb-123">Then number of batches the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="785bb-124">Total Failed Batches</span><span class="sxs-lookup"><span data-stu-id="785bb-124">Total Failed Batches</span></span>|<span data-ttu-id="785bb-125">BAM 事件总线服务自从启动后处理失败的批数。</span><span class="sxs-lookup"><span data-stu-id="785bb-125">Then number of batches the BAM Event Bus Service has failed to process since you started it.</span></span>|  
|<span data-ttu-id="785bb-126">Total Failed Events</span><span class="sxs-lookup"><span data-stu-id="785bb-126">Total Failed Events</span></span>|<span data-ttu-id="785bb-127">BAM 事件总线服务自从启动后处理失败的事件数。</span><span class="sxs-lookup"><span data-stu-id="785bb-127">Then number of events the BAM Event Bus Service has failed to process since you started it.</span></span>|  
  
 <span data-ttu-id="785bb-128">这些性能计数器都位于 BizTalk:TDDS 性能对象下的性能监视器 (perfmon) 中。</span><span class="sxs-lookup"><span data-stu-id="785bb-128">The performance counters are located in the Performance Monitor (perfmon) under the BizTalk:TDDS performance object.</span></span> <span data-ttu-id="785bb-129">这些性能计数器的实例名称是源服务器名称和源数据库名称的组合。</span><span class="sxs-lookup"><span data-stu-id="785bb-129">The instance name of the performance counters are a combination of the source server name and the name of the source database.</span></span> <span data-ttu-id="785bb-130">如果有两个 BAM 事件总线服务运行在同一个计算机上，但针对两个不同的源数据库，则您将看到两个 BAM 事件总线服务计数器实例。</span><span class="sxs-lookup"><span data-stu-id="785bb-130">If two of the BAM Event Bus Services are running on the same computer against two different source databases, you will see two instances of the BAM Event Bus Service counters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785bb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="785bb-131">See Also</span></span>  
 <span data-ttu-id="785bb-132">[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="785bb-132">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="785bb-133">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="785bb-133">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="785bb-134">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="785bb-134">Managing BAM</span></span>](../core/managing-bam.md)