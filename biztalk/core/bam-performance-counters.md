---
title: BAM 性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad0502e27bfaefb25d03e88b6d1730d0495cc189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358461"
---
# <a name="bam-performance-counters"></a><span data-ttu-id="279b1-102">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="279b1-102">BAM Performance Counters</span></span>
<span data-ttu-id="279b1-103">性能计数器可以监视 BAM 事件总线服务执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="279b1-103">Performance counters allow you to monitor specific aspects of work performed by the BAM Event Bus Service.</span></span> <span data-ttu-id="279b1-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="279b1-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="279b1-105">下表列出了业务活动监视中可用的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="279b1-105">The following table lists the performance counters available in Business Activity Monitoring.</span></span>  
  
|<span data-ttu-id="279b1-106">计数器</span><span class="sxs-lookup"><span data-stu-id="279b1-106">Counter</span></span>|<span data-ttu-id="279b1-107">Description</span><span class="sxs-lookup"><span data-stu-id="279b1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="279b1-108">正在处理的事件</span><span class="sxs-lookup"><span data-stu-id="279b1-108">Events being processed</span></span>|<span data-ttu-id="279b1-109">BAM 事件总线服务当前正在处理的事件数</span><span class="sxs-lookup"><span data-stu-id="279b1-109">The number of events the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="279b1-110">正在处理的批处理</span><span class="sxs-lookup"><span data-stu-id="279b1-110">Batches being processed</span></span>|<span data-ttu-id="279b1-111">BAM 事件总线服务当前正在处理的批数</span><span class="sxs-lookup"><span data-stu-id="279b1-111">The number of batches the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="279b1-112">已提交的事件</span><span class="sxs-lookup"><span data-stu-id="279b1-112">Events Committed</span></span>|<span data-ttu-id="279b1-113">BAM 事件总线服务在最近一秒提交给 SQL Server 的事件数。</span><span class="sxs-lookup"><span data-stu-id="279b1-113">The number of events the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="279b1-114">已提交的记录</span><span class="sxs-lookup"><span data-stu-id="279b1-114">Records Committed</span></span>|<span data-ttu-id="279b1-115">BAM 事件总线服务在最近一秒提交给 SQL Server 的记录数。</span><span class="sxs-lookup"><span data-stu-id="279b1-115">The number of records the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="279b1-116">已提交的批</span><span class="sxs-lookup"><span data-stu-id="279b1-116">Batches Committed</span></span>|<span data-ttu-id="279b1-117">BAM 事件总线服务在最近一秒提交给 SQL Server 的批数。</span><span class="sxs-lookup"><span data-stu-id="279b1-117">The number of batches the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="279b1-118">Total Events</span><span class="sxs-lookup"><span data-stu-id="279b1-118">Total Events</span></span>|<span data-ttu-id="279b1-119">BAM 事件总线服务自从您启动以来已处理的事件数。</span><span class="sxs-lookup"><span data-stu-id="279b1-119">The number of events the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="279b1-120">记录总数</span><span class="sxs-lookup"><span data-stu-id="279b1-120">Total Records</span></span>|<span data-ttu-id="279b1-121">然后启动 BAM 事件总线服务自从已处理的记录数。</span><span class="sxs-lookup"><span data-stu-id="279b1-121">Then number of records the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="279b1-122">总批</span><span class="sxs-lookup"><span data-stu-id="279b1-122">Total Batches</span></span>|<span data-ttu-id="279b1-123">然后启动 BAM 事件总线服务自从已处理的批数。</span><span class="sxs-lookup"><span data-stu-id="279b1-123">Then number of batches the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="279b1-124">失败的批处理的总数</span><span class="sxs-lookup"><span data-stu-id="279b1-124">Total Failed Batches</span></span>|<span data-ttu-id="279b1-125">然后批处理失败 BAM 事件总线服务自从启动后处理的数。</span><span class="sxs-lookup"><span data-stu-id="279b1-125">Then number of batches the BAM Event Bus Service has failed to process since you started it.</span></span>|  
|<span data-ttu-id="279b1-126">失败事件总数</span><span class="sxs-lookup"><span data-stu-id="279b1-126">Total Failed Events</span></span>|<span data-ttu-id="279b1-127">然后事件失败 BAM 事件总线服务自从启动后处理的数。</span><span class="sxs-lookup"><span data-stu-id="279b1-127">Then number of events the BAM Event Bus Service has failed to process since you started it.</span></span>|  
  
 <span data-ttu-id="279b1-128">性能计数器都位于 biztalk: Tdds 性能对象下的性能监视器 (perfmon)。</span><span class="sxs-lookup"><span data-stu-id="279b1-128">The performance counters are located in the Performance Monitor (perfmon) under the BizTalk:TDDS performance object.</span></span> <span data-ttu-id="279b1-129">性能计数器的实例名称是源服务器名称和源数据库的名称的组合。</span><span class="sxs-lookup"><span data-stu-id="279b1-129">The instance name of the performance counters are a combination of the source server name and the name of the source database.</span></span> <span data-ttu-id="279b1-130">如果两个 BAM 事件总线服务在对两个不同的源数据库在同一台计算机上运行，您将看到两个 BAM 事件总线服务计数器实例。</span><span class="sxs-lookup"><span data-stu-id="279b1-130">If two of the BAM Event Bus Services are running on the same computer against two different source databases, you will see two instances of the BAM Event Bus Service counters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279b1-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="279b1-131">See Also</span></span>  
 <span data-ttu-id="279b1-132">[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="279b1-132">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="279b1-133">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="279b1-133">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="279b1-134">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="279b1-134">Managing BAM</span></span>](../core/managing-bam.md)