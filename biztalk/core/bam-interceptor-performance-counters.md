---
title: BAM 侦听器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a8d3cc2f6ab4eb0945f6f7d8563ad675e1c69de
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530574"
---
# <a name="bam-interceptor-performance-counters"></a><span data-ttu-id="77e2d-102">BAM 侦听器性能计数器</span><span class="sxs-lookup"><span data-stu-id="77e2d-102">BAM Interceptor Performance Counters</span></span>
<span data-ttu-id="77e2d-103">性能计数器可以监视 BAM 侦听器执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="77e2d-103">Performance counters allow you to monitor specific aspects of work performed by the BAM interceptors.</span></span> <span data-ttu-id="77e2d-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="77e2d-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="77e2d-105">下表列出可用的性能计数器的 BAM 侦听器。</span><span class="sxs-lookup"><span data-stu-id="77e2d-105">The following table lists the performance counters available for the BAM interceptors.</span></span> <span data-ttu-id="77e2d-106">性能计数器的类别为"BAM 侦听器"。</span><span class="sxs-lookup"><span data-stu-id="77e2d-106">The performance counters category is “BAM Interceptor.”</span></span>  
  
|<span data-ttu-id="77e2d-107">计数器</span><span class="sxs-lookup"><span data-stu-id="77e2d-107">Counter</span></span>|<span data-ttu-id="77e2d-108">Description</span><span class="sxs-lookup"><span data-stu-id="77e2d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77e2d-109">Avg.失败的 BAM 事件/刷新 Avg</span><span class="sxs-lookup"><span data-stu-id="77e2d-109">Avg. Failed BAM Events/Flush Avg</span></span>|<span data-ttu-id="77e2d-110">过程的数据刷新到主导入数据库中发生的失败 BAM 事件平均数。</span><span class="sxs-lookup"><span data-stu-id="77e2d-110">The average number of failed BAM events that occurred during a flush of data to the Primary Import database.</span></span>|  
|<span data-ttu-id="77e2d-111">成功的 BAM 事件/刷新</span><span class="sxs-lookup"><span data-stu-id="77e2d-111">Successful BAM Events/Flush</span></span>|<span data-ttu-id="77e2d-112">过程数据刷新到主导入数据库中发生的成功 BAM 事件平均数。</span><span class="sxs-lookup"><span data-stu-id="77e2d-112">The average number of successful BAM events that occurred during a data flush to the Primary Import database.</span></span> <span data-ttu-id="77e2d-113">如果事务回滚，这些事件可能不会保留到数据库。</span><span class="sxs-lookup"><span data-stu-id="77e2d-113">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
|<span data-ttu-id="77e2d-114">Avg.提取秒/BAM 事件</span><span class="sxs-lookup"><span data-stu-id="77e2d-114">Avg. Extraction sec/BAM Event</span></span>|<span data-ttu-id="77e2d-115">提取 BAM 事件所用的平均时间量。</span><span class="sxs-lookup"><span data-stu-id="77e2d-115">The average amount of time spent extracting BAM events.</span></span>|  
|<span data-ttu-id="77e2d-116">Avg.刷新秒/BAM 事件</span><span class="sxs-lookup"><span data-stu-id="77e2d-116">Avg. Flush sec/BAM Event</span></span>|<span data-ttu-id="77e2d-117">刷新 BAM 事件所用的平均时间量。</span><span class="sxs-lookup"><span data-stu-id="77e2d-117">The average amount of time spent flushing BAM events.</span></span>|  
|<span data-ttu-id="77e2d-118">将失败 BAM 事件总数在刷新过程</span><span class="sxs-lookup"><span data-stu-id="77e2d-118">Total Failed BAM Events During Flush</span></span>|<span data-ttu-id="77e2d-119">数据刷新过程中发生的失败 BAM 事件总数</span><span class="sxs-lookup"><span data-stu-id="77e2d-119">The total number of failed BAM events that occurred during the data flush</span></span>|  
|<span data-ttu-id="77e2d-120">在刷新期间的总的成功 BAM 事件</span><span class="sxs-lookup"><span data-stu-id="77e2d-120">Total Successful BAM Events During Flush</span></span>|<span data-ttu-id="77e2d-121">到主导入数据库刷新的成功 BAM 事件总数。</span><span class="sxs-lookup"><span data-stu-id="77e2d-121">The total number of successful BAM events flushed to the Primary Import database.</span></span> <span data-ttu-id="77e2d-122">如果事务回滚，这些事件可能不会保留到数据库。</span><span class="sxs-lookup"><span data-stu-id="77e2d-122">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77e2d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="77e2d-123">See Also</span></span>  
 [<span data-ttu-id="77e2d-124">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="77e2d-124">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)