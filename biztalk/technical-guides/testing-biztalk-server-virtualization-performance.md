---
title: "测试 BizTalk Server 虚拟化性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cec992ab489c63f68ac4d77652209e65eff258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-biztalk-server-virtualization-performance"></a><span data-ttu-id="94673-102">测试 BizTalk Server 虚拟化性能</span><span class="sxs-lookup"><span data-stu-id="94673-102">Testing BizTalk Server Virtualization Performance</span></span>
<span data-ttu-id="94673-103">在本指南中所述的性能测试方案的每个已部署在 Microsoft 测试实验室中，物理计算机上以及然后在每个不同的系统体系结构上执行相同的负载测试了。</span><span class="sxs-lookup"><span data-stu-id="94673-103">Each of the performance test scenarios described in this guide were deployed on physical computers in a Microsoft test lab, and then the same load test was performed on each distinct system architecture.</span></span> <span data-ttu-id="94673-104">每台物理计算机上的主机操作系统已完全安装的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 64 位版本，安装了 HYPER-V 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="94673-104">The host operating system on each physical computer was a full installation of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition, with the Hyper-V server role installed.</span></span> <span data-ttu-id="94673-105">用于测试虚拟机[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]使用设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 作为来宾操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="94673-105">The virtual machines used for testing [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] were set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="94673-106">用于测试的虚拟机[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]使用设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 作为来宾操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="94673-106">The virtual machine used for testing [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] was set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="94673-107">测试方案、 测试方法、 性能测试结果和后续分析用于制定一系列的最佳实践和指南设计，实现时，以及优化虚拟化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="94673-107">The test scenarios, test methods, performance test results, and subsequent analysis were used to formulate a series of best practices and guidance for designing, implementing, and optimizing virtualized [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="94673-108">**测试方案 1： 基线**– 第一个方案旨在来确定在仅物理硬件上运行的 BizTalk Server 环境的基准性能。</span><span class="sxs-lookup"><span data-stu-id="94673-108">**Test Scenario 1: Baseline** – The first scenario was designed to establish baseline performance of a BizTalk Server environment running on physical hardware only.</span></span> <span data-ttu-id="94673-109">对于此方案 BizTalk Server 和 SQL Server 已安装，在仅物理硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="94673-109">For this scenario both BizTalk Server and SQL Server were installed and run on physical hardware only.</span></span>  
  
-   <span data-ttu-id="94673-110">**测试方案 2： 虚拟 BizTalk Server/物理 SQL Server**的第二个方案都可以确定在同一台物理服务器上的多个来宾虚拟机上托管 BizTalk Server 的性能影响。</span><span class="sxs-lookup"><span data-stu-id="94673-110">**Test Scenario 2: Virtual BizTalk Server/Physical SQL Server** - The second scenario was designed to determine the performance impact of hosting BizTalk Server on multiple guest virtual machines on the same physical server.</span></span> <span data-ttu-id="94673-111">从多个虚拟机配置了然后相比物理机处理具有相同数量的逻辑处理器的总的数字的形式执行的测试结果分散的所有虚拟机。</span><span class="sxs-lookup"><span data-stu-id="94673-111">Test results taken from multiple virtual machine configurations were then compared to a physical machine processing with the same number of logical processors as the total number dispersed across all virtual machines.</span></span>  
  
-   <span data-ttu-id="94673-112">**在单独的物理 HYPER-V 主机上的测试方案 3： 虚拟 BizTalk Server/虚拟 SQL Server** -执行的第三个方案，以确定虚拟化环境中运行 BizTalk Server 和 SQL Server 的性能影响。</span><span class="sxs-lookup"><span data-stu-id="94673-112">**Test Scenario 3: Virtual BizTalk Server/Virtual SQL Server on separate physical Hyper-V hosts** - The third scenario was conducted to determine the performance impact of running both BizTalk Server and SQL Server in a virtualized environment.</span></span> <span data-ttu-id="94673-113">执行测试，使用 HYPER-V 虚拟机上运行与 BizTalk 数据库上托管的 BizTalk Server [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] HYPER-V 虚拟机上运行的实例。</span><span class="sxs-lookup"><span data-stu-id="94673-113">Tests were performed using BizTalk Server running on Hyper-V virtual machines with the BizTalk databases hosted on a [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] instance running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="94673-114">对于此方案中，BizTalk Server 虚拟机和 SQL Server 虚拟机已托管在单独的物理 HYPER-V 主机。</span><span class="sxs-lookup"><span data-stu-id="94673-114">For this scenario, the BizTalk Server virtual machines and the SQL Server virtual machines were hosted on separate physical Hyper-V hosts.</span></span>  
  
-   <span data-ttu-id="94673-115">**测试方案 4： 服务器合并-将完整 BizTalk 组包括 SQL 到 HYPER-V 上的一台物理服务器合并**– 在此方案中，运行测试应用程序所需的所有虚拟机 (Vm) 将都托管在一台物理服务器。</span><span class="sxs-lookup"><span data-stu-id="94673-115">**Test Scenario 4: Server consolidation - Consolidating a full BizTalk Group Including SQL onto one Physical Server on Hyper-V** – In the scenario, all virtual machines (VMs) needed to run the test application are hosted on one physical server.</span></span> <span data-ttu-id="94673-116">这种情况下的用途是确定承载的性能成本[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]和[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]合并环境中虚拟机。</span><span class="sxs-lookup"><span data-stu-id="94673-116">The purpose of this scenario is to determine the performance costs of hosting [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] and [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] virtual machines in a consolidated environment.</span></span>  
  
 <span data-ttu-id="94673-117">本部分提供测试应用程序和用于每个方案的服务器体系结构的概述，并还会显示在测试期间观察到的关键性能指标 (Kpi)。</span><span class="sxs-lookup"><span data-stu-id="94673-117">This section provides an overview of the test application and the server architecture used for each scenario and also presents key performance indicators (KPIs) observed during testing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94673-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="94673-118">In This Section</span></span>  
  
-   [<span data-ttu-id="94673-119">测试方案概述</span><span class="sxs-lookup"><span data-stu-id="94673-119">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)  
  
-   [<span data-ttu-id="94673-120">测试方案服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="94673-120">Test Scenario Server Architecture</span></span>](../technical-guides/test-scenario-server-architecture.md)  
  
-   [<span data-ttu-id="94673-121">测试结果： BizTalk Server 关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="94673-121">Test Results: BizTalk Server Key Performance Indicators</span></span>](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="94673-122">测试结果： SQL Server 关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="94673-122">Test Results: SQL Server Key Performance Indicators</span></span>](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="94673-123">测试结果： 网络关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="94673-123">Test Results: Networking Key Performance Indicators</span></span>](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [<span data-ttu-id="94673-124">测试结果： 内存关键绩效指标</span><span class="sxs-lookup"><span data-stu-id="94673-124">Test Results: Memory Key Performance Indicators</span></span>](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [<span data-ttu-id="94673-125">测试结果的摘要</span><span class="sxs-lookup"><span data-stu-id="94673-125">Summary of Test Results</span></span>](../technical-guides/summary-of-test-results.md)