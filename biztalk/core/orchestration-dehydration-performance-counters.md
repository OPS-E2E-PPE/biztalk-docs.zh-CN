---
title: "业务流程冻结性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-performance-counters"></a><span data-ttu-id="2335c-102">业务流程冻结性能计数器</span><span class="sxs-lookup"><span data-stu-id="2335c-102">Orchestration Dehydration Performance Counters</span></span>
<span data-ttu-id="2335c-103">下表列出了专门用于监视冻结行为的业务流程引擎性能计数器的名称。</span><span class="sxs-lookup"><span data-stu-id="2335c-103">The following table lists the names of Orchestration Engine performance counters that are specific to monitoring the behavior of dehydration.</span></span> <span data-ttu-id="2335c-104">使用性能监视器可以在优化冻结参数的过程中查看这些计数器。</span><span class="sxs-lookup"><span data-stu-id="2335c-104">Use Performance Monitor to watch these counters while tuning your dehydration parameters.</span></span>  
  
|<span data-ttu-id="2335c-105">冻结性能计数器</span><span class="sxs-lookup"><span data-stu-id="2335c-105">Dehydration Performance Counter</span></span>|<span data-ttu-id="2335c-106">Description</span><span class="sxs-lookup"><span data-stu-id="2335c-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="2335c-107">Dehydratable orchestrations</span><span class="sxs-lookup"><span data-stu-id="2335c-107">Dehydratable orchestrations</span></span>|<span data-ttu-id="2335c-108">当前以主机实例为宿主的能够冻结的业务流程实例数。</span><span class="sxs-lookup"><span data-stu-id="2335c-108">Number of orchestrations instances that can be dehydrated which are currently hosted by the host instance.</span></span>|  
|<span data-ttu-id="2335c-109">Dehydrating orchestrations</span><span class="sxs-lookup"><span data-stu-id="2335c-109">Dehydrating orchestrations</span></span>|<span data-ttu-id="2335c-110">正在冻结的业务流程数。</span><span class="sxs-lookup"><span data-stu-id="2335c-110">Number of orchestrations that are in the process of dehydrating.</span></span>|  
|<span data-ttu-id="2335c-111">Dehydration cycle in progress</span><span class="sxs-lookup"><span data-stu-id="2335c-111">Dehydration cycle in progress</span></span>|<span data-ttu-id="2335c-112">指示当前是否存在正在进行的冻结周期。</span><span class="sxs-lookup"><span data-stu-id="2335c-112">Indicates whether there is a dehydration cycle currently in progress.</span></span>|  
|<span data-ttu-id="2335c-113">Dehydration cycles</span><span class="sxs-lookup"><span data-stu-id="2335c-113">Dehydration cycles</span></span>|<span data-ttu-id="2335c-114">已完成的冻结周期数。</span><span class="sxs-lookup"><span data-stu-id="2335c-114">Number of dehydration cycles completed.</span></span>|  
|<span data-ttu-id="2335c-115">Dehydration threshold</span><span class="sxs-lookup"><span data-stu-id="2335c-115">Dehydration threshold</span></span>|<span data-ttu-id="2335c-116">确定是否主动冻结业务流程的时间长度（以毫秒计）。</span><span class="sxs-lookup"><span data-stu-id="2335c-116">Number in milliseconds that determines how aggressively orchestrations are being dehydrated.</span></span> <span data-ttu-id="2335c-117">如果业务流程引擎预测某个实例可以冻结一段时间，而且这段时间的长度大于此阈值，则它将冻结该实例。</span><span class="sxs-lookup"><span data-stu-id="2335c-117">If the orchestration engine predicts that an instance will be dehydratable for an amount of time longer than this threshold, it will dehydrate the instance.</span></span>|  
|<span data-ttu-id="2335c-118">Orchestrations dehydrated</span><span class="sxs-lookup"><span data-stu-id="2335c-118">Orchestrations dehydrated</span></span>|<span data-ttu-id="2335c-119">自从主机实例启动以来，冻结的业务流程实例的数量。</span><span class="sxs-lookup"><span data-stu-id="2335c-119">Number of orchestration instances dehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="2335c-120">Orchestrations dehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="2335c-120">Orchestrations dehydrated/sec</span></span>|<span data-ttu-id="2335c-121">平均每秒冻结的业务流程数。</span><span class="sxs-lookup"><span data-stu-id="2335c-121">Average number dehydrated per second.</span></span>|  
|<span data-ttu-id="2335c-122">Orchestrations rehydrated</span><span class="sxs-lookup"><span data-stu-id="2335c-122">Orchestrations rehydrated</span></span>|<span data-ttu-id="2335c-123">自从主机实例启动以来，解除冻结的业务流程实例的数量。</span><span class="sxs-lookup"><span data-stu-id="2335c-123">Number of orchestration instances rehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="2335c-124">Orchestrations rehydrated/sec</span><span class="sxs-lookup"><span data-stu-id="2335c-124">Orchestrations rehydrated/sec</span></span>|<span data-ttu-id="2335c-125">平均每秒解除冻结的业务流程数</span><span class="sxs-lookup"><span data-stu-id="2335c-125">Average number rehydrated per second</span></span>|  
|<span data-ttu-id="2335c-126">Orchestrations scheduled for dehydration</span><span class="sxs-lookup"><span data-stu-id="2335c-126">Orchestrations scheduled for dehydration</span></span>|<span data-ttu-id="2335c-127">冻结请求处于挂起状态的可冻结业务流程的数量。</span><span class="sxs-lookup"><span data-stu-id="2335c-127">Number of dehydratable orchestrations for which there is a dehydration request pending.</span></span>|