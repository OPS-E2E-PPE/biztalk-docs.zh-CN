---
title: 测试 BizTalk Server 虚拟化性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f07c6bf8371e1db84ed574d7c737d4cc5b3903b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993694"
---
# <a name="testing-biztalk-server-virtualization-performance"></a><span data-ttu-id="13aca-102">测试 BizTalk Server 虚拟化性能</span><span class="sxs-lookup"><span data-stu-id="13aca-102">Testing BizTalk Server Virtualization Performance</span></span>
<span data-ttu-id="13aca-103">在本指南中所述的性能测试方案的每个已部署在 Microsoft 测试实验室中，物理计算机上，然后在每个不同的系统体系结构上执行相同的负载测试。</span><span class="sxs-lookup"><span data-stu-id="13aca-103">Each of the performance test scenarios described in this guide were deployed on physical computers in a Microsoft test lab, and then the same load test was performed on each distinct system architecture.</span></span> <span data-ttu-id="13aca-104">每台物理计算机上的主机操作系统已完全安装的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 64 位版本，安装了 HYPER-V 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="13aca-104">The host operating system on each physical computer was a full installation of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition, with the Hyper-V server role installed.</span></span> <span data-ttu-id="13aca-105">用于测试 BizTalk Server 使用的虚拟机设置的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 作为来宾操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="13aca-105">The virtual machines used for testing BizTalk Server were set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="13aca-106">用于测试 SQL Server 的虚拟机使用已设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 作为来宾操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="13aca-106">The virtual machine used for testing SQL Server was set up with [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Enterprise, 64-Bit Edition as the guest operating system.</span></span> <span data-ttu-id="13aca-107">测试方案、 测试方法、 性能测试结果和后续分析已用于明确表述一系列最佳实践和设计、 实现、 指南和优化虚拟化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="13aca-107">The test scenarios, test methods, performance test results, and subsequent analysis were used to formulate a series of best practices and guidance for designing, implementing, and optimizing virtualized [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="13aca-108">**测试方案 1： 基线**– 确定基准性能的仅物理硬件上运行的 BizTalk Server 环境所需的第一个方案。</span><span class="sxs-lookup"><span data-stu-id="13aca-108">**Test Scenario 1: Baseline** – The first scenario was designed to establish baseline performance of a BizTalk Server environment running on physical hardware only.</span></span> <span data-ttu-id="13aca-109">这种情况下为 BizTalk Server 和 SQL Server 已安装，并仅物理硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="13aca-109">For this scenario both BizTalk Server and SQL Server were installed and run on physical hardware only.</span></span>  
  
- <span data-ttu-id="13aca-110">**测试方案 2： 虚拟 BizTalk/物理服务器的 SQL Server** -第二个方案都可以确定在同一台物理服务器上的多个来宾虚拟机上托管 BizTalk Server 的性能影响。</span><span class="sxs-lookup"><span data-stu-id="13aca-110">**Test Scenario 2: Virtual BizTalk Server/Physical SQL Server** - The second scenario was designed to determine the performance impact of hosting BizTalk Server on multiple guest virtual machines on the same physical server.</span></span> <span data-ttu-id="13aca-111">测试结果来自配置已然后处理的物理机到比较具有相同数量的逻辑处理器的总数的多个虚拟机分布在所有虚拟机。</span><span class="sxs-lookup"><span data-stu-id="13aca-111">Test results taken from multiple virtual machine configurations were then compared to a physical machine processing with the same number of logical processors as the total number dispersed across all virtual machines.</span></span>  
  
- <span data-ttu-id="13aca-112">**在单独的物理 HYPER-V 主机上的测试方案 3： 虚拟 BizTalk 服务器/虚拟 SQL Server** -执行的第三个方案，以确定虚拟化环境中运行 BizTalk Server 和 SQL Server 的性能影响。</span><span class="sxs-lookup"><span data-stu-id="13aca-112">**Test Scenario 3: Virtual BizTalk Server/Virtual SQL Server on separate physical Hyper-V hosts** - The third scenario was conducted to determine the performance impact of running both BizTalk Server and SQL Server in a virtualized environment.</span></span> <span data-ttu-id="13aca-113">使用 BizTalk Server 与 BizTalk 数据库托管在 HYPER-V 虚拟机上运行的 SQL Server 实例上运行的 HYPER-V 虚拟机上执行测试。</span><span class="sxs-lookup"><span data-stu-id="13aca-113">Tests were performed using BizTalk Server running on Hyper-V virtual machines with the BizTalk databases hosted on a SQL Server instance running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="13aca-114">对于此方案，BizTalk Server 虚拟机和 SQL Server 虚拟机已托管在单独的物理 HYPER-V 主机上。</span><span class="sxs-lookup"><span data-stu-id="13aca-114">For this scenario, the BizTalk Server virtual machines and the SQL Server virtual machines were hosted on separate physical Hyper-V hosts.</span></span>  
  
- <span data-ttu-id="13aca-115">**测试方案 4： 服务器合并的合并完整 BizTalk 组包括 SQL 到一台物理服务器上的 HYPER-V** – 在方案中，运行测试应用程序所需的所有虚拟机 (Vm) 都位于一台物理服务器上。</span><span class="sxs-lookup"><span data-stu-id="13aca-115">**Test Scenario 4: Server consolidation - Consolidating a full BizTalk Group Including SQL onto one Physical Server on Hyper-V** – In the scenario, all virtual machines (VMs) needed to run the test application are hosted on one physical server.</span></span> <span data-ttu-id="13aca-116">此方案的目的是确定的托管 SQL Server 和统一的环境中的 BizTalk Server 虚拟机的性能成本。</span><span class="sxs-lookup"><span data-stu-id="13aca-116">The purpose of this scenario is to determine the performance costs of hosting SQL Server and BizTalk Server virtual machines in a consolidated environment.</span></span>  
  
  <span data-ttu-id="13aca-117">本部分提供了测试应用程序和用于每个方案的服务器体系结构的概述，并还展示了在测试期间观察到的关键绩效指标 (Kpi)。</span><span class="sxs-lookup"><span data-stu-id="13aca-117">This section provides an overview of the test application and the server architecture used for each scenario and also presents key performance indicators (KPIs) observed during testing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13aca-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="13aca-118">In This Section</span></span>  
  
-   [<span data-ttu-id="13aca-119">测试方案概述</span><span class="sxs-lookup"><span data-stu-id="13aca-119">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)  
  
-   [<span data-ttu-id="13aca-120">测试方案服务器体系结构</span><span class="sxs-lookup"><span data-stu-id="13aca-120">Test Scenario Server Architecture</span></span>](../technical-guides/test-scenario-server-architecture.md)  
  
-   [<span data-ttu-id="13aca-121">测试结果：BizTalk Server 关键性能指标</span><span class="sxs-lookup"><span data-stu-id="13aca-121">Test Results: BizTalk Server Key Performance Indicators</span></span>](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="13aca-122">测试结果：SQL Server 关键性能指标</span><span class="sxs-lookup"><span data-stu-id="13aca-122">Test Results: SQL Server Key Performance Indicators</span></span>](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [<span data-ttu-id="13aca-123">测试结果：网络服务关键性能指标</span><span class="sxs-lookup"><span data-stu-id="13aca-123">Test Results: Networking Key Performance Indicators</span></span>](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [<span data-ttu-id="13aca-124">测试结果：内存关键性能指标</span><span class="sxs-lookup"><span data-stu-id="13aca-124">Test Results: Memory Key Performance Indicators</span></span>](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [<span data-ttu-id="13aca-125">测试结果摘要</span><span class="sxs-lookup"><span data-stu-id="13aca-125">Summary of Test Results</span></span>](../technical-guides/summary-of-test-results.md)