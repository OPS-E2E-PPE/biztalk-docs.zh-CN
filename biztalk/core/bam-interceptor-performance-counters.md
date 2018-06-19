---
title: BAM 拦截器性能计数器 |Microsoft 文档
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
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230493"
---
# <a name="bam-interceptor-performance-counters"></a><span data-ttu-id="c7798-102">BAM 侦听器性能计数器</span><span class="sxs-lookup"><span data-stu-id="c7798-102">BAM Interceptor Performance Counters</span></span>
<span data-ttu-id="c7798-103">使用性能计数器可以监视 BAM 侦听器执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="c7798-103">Performance counters allow you to monitor specific aspects of work performed by the BAM interceptors.</span></span> <span data-ttu-id="c7798-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="c7798-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="c7798-105">下表列出了可用于 BAM 侦听器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c7798-105">The following table lists the performance counters available for the BAM interceptors.</span></span> <span data-ttu-id="c7798-106">这些性能计数器的类别为“BAM 侦听器”。</span><span class="sxs-lookup"><span data-stu-id="c7798-106">The performance counters category is “BAM Interceptor.”</span></span>  
  
|<span data-ttu-id="c7798-107">计数器</span><span class="sxs-lookup"><span data-stu-id="c7798-107">Counter</span></span>|<span data-ttu-id="c7798-108">Description</span><span class="sxs-lookup"><span data-stu-id="c7798-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7798-109">Avg.失败的 BAM 事件/刷新 Avg</span><span class="sxs-lookup"><span data-stu-id="c7798-109">Avg. Failed BAM Events/Flush Avg</span></span>|<span data-ttu-id="c7798-110">在每次将数据刷新到主导入数据库期间发生的失败 BAM 事件的平均数。</span><span class="sxs-lookup"><span data-stu-id="c7798-110">The average number of failed BAM events that occurred during a flush of data to the Primary Import database.</span></span>|  
|<span data-ttu-id="c7798-111">Successful BAM Events/Flush</span><span class="sxs-lookup"><span data-stu-id="c7798-111">Successful BAM Events/Flush</span></span>|<span data-ttu-id="c7798-112">在每次将数据刷新到主导入数据库期间发生的成功 BAM 事件的平均数。</span><span class="sxs-lookup"><span data-stu-id="c7798-112">The average number of successful BAM events that occurred during a data flush to the Primary Import database.</span></span> <span data-ttu-id="c7798-113">如果回滚相应事务，则这些事件可能不会保留到数据库中。</span><span class="sxs-lookup"><span data-stu-id="c7798-113">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
|<span data-ttu-id="c7798-114">Avg.提取秒/BAM 事件</span><span class="sxs-lookup"><span data-stu-id="c7798-114">Avg. Extraction sec/BAM Event</span></span>|<span data-ttu-id="c7798-115">提取 BAM 事件花费的时间的平均值。</span><span class="sxs-lookup"><span data-stu-id="c7798-115">The average amount of time spent extracting BAM events.</span></span>|  
|<span data-ttu-id="c7798-116">Avg.刷新秒/BAM 事件</span><span class="sxs-lookup"><span data-stu-id="c7798-116">Avg. Flush sec/BAM Event</span></span>|<span data-ttu-id="c7798-117">刷新 BAM 事件花费的时间的平均值。</span><span class="sxs-lookup"><span data-stu-id="c7798-117">The average amount of time spent flushing BAM events.</span></span>|  
|<span data-ttu-id="c7798-118">Total Failed BAM Events During Flush</span><span class="sxs-lookup"><span data-stu-id="c7798-118">Total Failed BAM Events During Flush</span></span>|<span data-ttu-id="c7798-119">数据刷新期间发生的失败 BAM 事件的总数。</span><span class="sxs-lookup"><span data-stu-id="c7798-119">The total number of failed BAM events that occurred during the data flush</span></span>|  
|<span data-ttu-id="c7798-120">刷新过程中成功的 BAM 事件总数</span><span class="sxs-lookup"><span data-stu-id="c7798-120">Total Successful BAM Events During Flush</span></span>|<span data-ttu-id="c7798-121">刷新到主导入数据库的成功 BAM 事件的总数。</span><span class="sxs-lookup"><span data-stu-id="c7798-121">The total number of successful BAM events flushed to the Primary Import database.</span></span> <span data-ttu-id="c7798-122">如果回滚相应事务，则这些事件可能不会保留到数据库中。</span><span class="sxs-lookup"><span data-stu-id="c7798-122">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7798-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7798-123">See Also</span></span>  
 [<span data-ttu-id="c7798-124">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="c7798-124">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)