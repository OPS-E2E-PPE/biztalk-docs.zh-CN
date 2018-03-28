---
title: 测试结果： 网络关键绩效指标 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bdbc2df-9d19-4ae8-b540-ec1b9a7cdbe9
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb4e10c739178e6cd923f65b51f982e05ab7f56
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="test-results-networking-key-performance-indicators"></a><span data-ttu-id="f3ba2-102">测试结果： 网络关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="f3ba2-102">Test Results: Networking Key Performance Indicators</span></span>
<span data-ttu-id="f3ba2-103">本主题总结了网络关键绩效指标 (KPI) 的测试方案期间观察到。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-103">This topic summarizes Network Key Performance Indicators (KPI) observed during the test scenarios.</span></span> <span data-ttu-id="f3ba2-104">这些测试评估网络性能测量**\Network 接口 (\*) \Bytes Total/sec**性能监视器计数器和通过度量**SQL Network Interface\Bytes Total/sec (Avg)**返回 VSTS 2008 负载测试控制器。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-104">These tests evaluated Network Performance as measured by the **\Network Interface(\*)\Bytes Total/sec** performance monitor counter and by measuring the **SQL Network Interface\Bytes Total/sec (Avg )** returned by the VSTS 2008 Load Test Controller.</span></span>  
  
## <a name="summary-of-network-key-performance-indicators"></a><span data-ttu-id="f3ba2-105">网络关键绩效指标的摘要</span><span class="sxs-lookup"><span data-stu-id="f3ba2-105">Summary of Network Key Performance Indicators</span></span>  
 <span data-ttu-id="f3ba2-106">**网络密钥性能指标 – 比较**BizTalk Server HYPER-V 虚拟机上运行的网络吞吐量观察到到范围从大约 70%到 96%的实现在物理 BizTalk 服务器上的网络吞吐量具体取决于特定的测试环境。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-106">**Comparison of Networking Key Performance Indicators –** Network throughput for BizTalk Server running on Hyper-V virtual machines was observed to range from approximately 70% to 96% of the network throughput achieved on the physical BizTalk Servers, depending on the particular test environment.</span></span> <span data-ttu-id="f3ba2-107">HYPER-V 虚拟机上运行的 SQL Server 的网络吞吐量观察到到范围从大约 68%到 81%的实现在物理 SQL 服务器上，再次根据特定的测试环境的网络吞吐量。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-107">Network throughput for SQL Server running on a Hyper-V virtual machine was observed to range from approximately 68% to 81% of the network throughput achieved on the physical SQL Server, again depending on the particular test environment.</span></span> <span data-ttu-id="f3ba2-108">观测到的网络吞吐量的增量可以被归因于 HYPER-V 虚拟机监控程序的资源要求。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-108">The delta in the observed network throughput can be attributed to the resource requirements of the Hyper-V Hypervisor.</span></span>  
  
 <span data-ttu-id="f3ba2-109">按照中的步骤[网络优化](../technical-guides/network-optimizations.md)以最大化网络吞吐量测量的 HYPER-V 虚拟机上**\Network 接口 (\*) \Bytes Total/sec**</span><span class="sxs-lookup"><span data-stu-id="f3ba2-109">Follow the steps in [Network Optimizations](../technical-guides/network-optimizations.md) to maximize network throughput on Hyper-V virtual machines as measured by **\Network Interface(\*)\Bytes Total/sec**</span></span>  
  
 <span data-ttu-id="f3ba2-110">下图阐释了在不同的测试平台上的网络性能：</span><span class="sxs-lookup"><span data-stu-id="f3ba2-110">The graphic below illustrates the network performance on the various test platforms:</span></span>  
  
 <span data-ttu-id="f3ba2-111">![网络关键绩效指标](../technical-guides/media/networkkpi.gif "NetworkKPI")</span><span class="sxs-lookup"><span data-stu-id="f3ba2-111">![Networking Key Performance Indicators](../technical-guides/media/networkkpi.gif "NetworkKPI")</span></span>  
  
 <span data-ttu-id="f3ba2-112">下表说明了每个配置的收集 KPI 的相对性能。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-112">The table below illustrates the relative performance of the collected KPI’s for each configuration.</span></span> <span data-ttu-id="f3ba2-113">每个结果集计算的基线配置 KPI 百分比</span><span class="sxs-lookup"><span data-stu-id="f3ba2-113">Each result set is calculated as a percentage of the Baseline configuration KPI</span></span>  
  
|<span data-ttu-id="f3ba2-114">KPI</span><span class="sxs-lookup"><span data-stu-id="f3ba2-114">KPI</span></span>|<span data-ttu-id="f3ba2-115">虚拟 BizTalk/物理 SQL</span><span class="sxs-lookup"><span data-stu-id="f3ba2-115">Virtual BizTalk/Physical SQL</span></span>|<span data-ttu-id="f3ba2-116">在单独的主机的虚拟 BizTalk/虚拟 SQL</span><span class="sxs-lookup"><span data-stu-id="f3ba2-116">Virtual BizTalk/Virtual SQL on separate Hosts</span></span>|<span data-ttu-id="f3ba2-117">合并环境上的虚拟 BizTalk/虚拟 SQL</span><span class="sxs-lookup"><span data-stu-id="f3ba2-117">Virtual BizTalk/Virtual SQL on Consolidated environment</span></span>|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="f3ba2-118">\Network 接口 （\*） \Bytes Total/sec （在所有 BizTalk 服务器的总平均）</span><span class="sxs-lookup"><span data-stu-id="f3ba2-118">\Network Interface(\*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)</span></span>|<span data-ttu-id="f3ba2-119">96%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-119">96%</span></span>|<span data-ttu-id="f3ba2-120">82.1%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-120">82.1%</span></span>|<span data-ttu-id="f3ba2-121">70.2%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-121">70.2%</span></span>|  
|<span data-ttu-id="f3ba2-122">SQL Network Interface\Bytes Total/sec (Avg)</span><span class="sxs-lookup"><span data-stu-id="f3ba2-122">SQL Network Interface\Bytes Total/sec (Avg )</span></span>|<span data-ttu-id="f3ba2-123">95.5%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-123">95.5%</span></span>|<span data-ttu-id="f3ba2-124">81.2%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-124">81.2%</span></span>|<span data-ttu-id="f3ba2-125">68.4%</span><span class="sxs-lookup"><span data-stu-id="f3ba2-125">68.4%</span></span>|  
  
 <span data-ttu-id="f3ba2-126">有关如何评估网络性能的详细信息，请参阅**测量网络性能**主题的部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ba2-126">For more information about how to evaluate Network performance, see the **Measuring Network Performance** section of the topic [Checklist: Measuring Performance on Hyper-V](../technical-guides/checklist-measuring-performance-on-hyper-v.md).</span></span>