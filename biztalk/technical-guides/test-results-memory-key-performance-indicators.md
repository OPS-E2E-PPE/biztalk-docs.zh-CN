---
title: 测试结果：内存关键绩效指标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b62f71a013a4e2fa36c20f1d2197db7d2f3a3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298467"
---
# <a name="test-results-memory-key-performance-indicators"></a><span data-ttu-id="b22dd-102">测试结果：内存关键性能指标</span><span class="sxs-lookup"><span data-stu-id="b22dd-102">Test Results: Memory Key Performance Indicators</span></span>
<span data-ttu-id="b22dd-103">本主题总结了内存关键绩效指标 (KPI) 的测试方案期间观察到。</span><span class="sxs-lookup"><span data-stu-id="b22dd-103">This topic summarizes Memory Key Performance Indicators (KPI) observed during the test scenarios.</span></span> <span data-ttu-id="b22dd-104">这些测试计算由可用内存 **\Memory\Available Mbytes**性能监视器计数器。</span><span class="sxs-lookup"><span data-stu-id="b22dd-104">These tests evaluated available memory as measured by the **\Memory\Available Mbytes** performance monitor counter.</span></span>  
  
## <a name="summary-of-memory-key-performance-indicators"></a><span data-ttu-id="b22dd-105">内存关键绩效指标的摘要</span><span class="sxs-lookup"><span data-stu-id="b22dd-105">Summary of Memory Key Performance Indicators</span></span>  
 <span data-ttu-id="b22dd-106">**比较内存关键绩效指标 –** 的总内存供 SQL Server 和 BizTalk Server 测量 **\Memory\Available Mbytes**所有性能监视器计数器是相当一致测试方案。</span><span class="sxs-lookup"><span data-stu-id="b22dd-106">**Comparison of Memory Key Performance Indicators –** Total memory available to SQL Server and BizTalk Server as measured by the **\Memory\Available Mbytes** performance monitor counter was fairly consistent across all test scenarios.</span></span> <span data-ttu-id="b22dd-107">中可用的平均内存到物理 BizTalk Server 计算机以及可用于虚拟机上运行的 BizTalk Server 计算机的平均内存的区别是因为，两个物理 BizTalk Server 计算机用于测试时三个虚拟机上运行的 BizTalk Server 计算机已用于测试。</span><span class="sxs-lookup"><span data-stu-id="b22dd-107">The difference in the average memory available to the physical BizTalk Server computers and the average memory available to the BizTalk Server computers running on virtual machines is due to the fact that two physical BizTalk Server computers were used for testing while three BizTalk Server computers running on virtual machines were used for testing.</span></span>  
  
 <span data-ttu-id="b22dd-108">下图阐释了在不同的测试平台上的内存性能：</span><span class="sxs-lookup"><span data-stu-id="b22dd-108">The graphic below illustrates Memory performance on the various test platforms:</span></span>  
  
 <span data-ttu-id="b22dd-109">![内存关键绩效指标](../technical-guides/media/memorykpi.gif "MemoryKPI")</span><span class="sxs-lookup"><span data-stu-id="b22dd-109">![Memory Key Performance Indicators](../technical-guides/media/memorykpi.gif "MemoryKPI")</span></span>  
  
 <span data-ttu-id="b22dd-110">下表说明了每个配置的收集 KPI 的相对性能。</span><span class="sxs-lookup"><span data-stu-id="b22dd-110">The table below illustrates the relative performance of the collected KPI’s for each configuration.</span></span> <span data-ttu-id="b22dd-111">每个结果集计算的基线配置 KPI 百分比</span><span class="sxs-lookup"><span data-stu-id="b22dd-111">Each result set is calculated as a percentage of the Baseline configuration KPI</span></span>  
  
|<span data-ttu-id="b22dd-112">KPI</span><span class="sxs-lookup"><span data-stu-id="b22dd-112">KPI</span></span>|<span data-ttu-id="b22dd-113">虚拟 BizTalk/物理 SQL</span><span class="sxs-lookup"><span data-stu-id="b22dd-113">Virtual BizTalk/Physical SQL</span></span>|<span data-ttu-id="b22dd-114">在单独的主机的虚拟 BizTalk/虚拟 SQL</span><span class="sxs-lookup"><span data-stu-id="b22dd-114">Virtual BizTalk/Virtual SQL on separate Hosts</span></span>|<span data-ttu-id="b22dd-115">合并环境上的虚拟 BizTalk/虚拟 SQL</span><span class="sxs-lookup"><span data-stu-id="b22dd-115">Virtual BizTalk/Virtual SQL on Consolidated environment</span></span>|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="b22dd-116">SQL Server 可用内存 （mb 为单位） 每个服务器</span><span class="sxs-lookup"><span data-stu-id="b22dd-116">SQL Server Available Memory (Mbytes) Per Server</span></span>|<span data-ttu-id="b22dd-117">100.1%</span><span class="sxs-lookup"><span data-stu-id="b22dd-117">100.1%</span></span>|<span data-ttu-id="b22dd-118">97.1%</span><span class="sxs-lookup"><span data-stu-id="b22dd-118">97.1%</span></span>|<span data-ttu-id="b22dd-119">103.2%</span><span class="sxs-lookup"><span data-stu-id="b22dd-119">103.2%</span></span>|  
|<span data-ttu-id="b22dd-120">总 BizTalk 可用内存 （mb 为单位）</span><span class="sxs-lookup"><span data-stu-id="b22dd-120">Total BizTalk Available Memory (Mbytes)</span></span>|<span data-ttu-id="b22dd-121">88.3%</span><span class="sxs-lookup"><span data-stu-id="b22dd-121">88.3%</span></span>|<span data-ttu-id="b22dd-122">95.9%</span><span class="sxs-lookup"><span data-stu-id="b22dd-122">95.9%</span></span>|<span data-ttu-id="b22dd-123">96%</span><span class="sxs-lookup"><span data-stu-id="b22dd-123">96%</span></span>|  
|<span data-ttu-id="b22dd-124">平均每个服务器 / BizTalk 可用内存 （mb 为单位）</span><span class="sxs-lookup"><span data-stu-id="b22dd-124">Average Per Server / BizTalk Available Memory (Mbytes)</span></span>|<span data-ttu-id="b22dd-125">58.9%</span><span class="sxs-lookup"><span data-stu-id="b22dd-125">58.9%</span></span>|<span data-ttu-id="b22dd-126">63.9%</span><span class="sxs-lookup"><span data-stu-id="b22dd-126">63.9%</span></span>|<span data-ttu-id="b22dd-127">64%</span><span class="sxs-lookup"><span data-stu-id="b22dd-127">64%</span></span>|  
  
 <span data-ttu-id="b22dd-128">有关如何评估内存性能的详细信息，请参阅**测量内存性能**主题的部分[核对清单：Hyper V 上测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。</span><span class="sxs-lookup"><span data-stu-id="b22dd-128">For more information about how to evaluate Memory performance, see the **Measuring Memory Performance** section of the topic [Checklist: Measuring Performance on Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).</span></span>