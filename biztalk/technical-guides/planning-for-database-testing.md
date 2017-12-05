---
title: "规划数据库测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3849b68af9fdd4e457a8e1e492134a87dc1655bd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-database-testing"></a><span data-ttu-id="a31d7-102">计划测试数据库</span><span class="sxs-lookup"><span data-stu-id="a31d7-102">Planning for Database Testing</span></span>
<span data-ttu-id="a31d7-103">全面的压力负载测试的 BizTalk 解决方案中的图表突出解决方案 ultimate 成功与否。</span><span class="sxs-lookup"><span data-stu-id="a31d7-103">Thorough stress/load testing of a BizTalk solution figures prominently in the ultimate success or failure of the solution.</span></span> <span data-ttu-id="a31d7-104">由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能所依赖的性能因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库、 测试和优化 BizTalk 解决方案经常侧重于测试和运行的计算机的优化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="a31d7-104">Since [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance is so dependent on the performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, testing and optimization of a BizTalk solution frequently focuses on testing and optimization of the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="considerations-when-planning-for-database-testing"></a><span data-ttu-id="a31d7-105">规划数据库测试时的注意事项</span><span class="sxs-lookup"><span data-stu-id="a31d7-105">Considerations When Planning for Database Testing</span></span>  
 <span data-ttu-id="a31d7-106">规划数据库测试时，请考虑以下方法：</span><span class="sxs-lookup"><span data-stu-id="a31d7-106">Consider the following when planning for database testing:</span></span>  
  
1.  <span data-ttu-id="a31d7-107">**确保测试环境与生产环境尽可能真实地匹配。**</span><span class="sxs-lookup"><span data-stu-id="a31d7-107">**Ensure that the test environment matches the production environment as closely as possible.**</span></span> <span data-ttu-id="a31d7-108">使用适用于单元测试的虚拟环境，例如 Microsoft HYPER-V Server 2008 是完全可以接受;但是，应对尽可能匹配最终生产环境的硬件执行所有负载/压力测试。</span><span class="sxs-lookup"><span data-stu-id="a31d7-108">Using a virtual environment such as Microsoft Hyper-V Server 2008 for unit testing is perfectly acceptable; however, all load/stress testing should be performed against hardware that matches the final production environment as closely as possible.</span></span>  
  
2.  <span data-ttu-id="a31d7-109">**计划度量值最大可持续吞吐量和 BizTalk Server 系统最大可持续跟踪吞吐量**。</span><span class="sxs-lookup"><span data-stu-id="a31d7-109">**Plan to measure maximum sustainable throughput and maximum sustainable tracking throughput of the BizTalk Server system**.</span></span> <span data-ttu-id="a31d7-110">最大可持续吞吐量被指 BizTalk Server 系统可以在生产中无限期地处理的消息流量的最高负载。</span><span class="sxs-lookup"><span data-stu-id="a31d7-110">Maximum sustainable throughput is measured as the highest load of message traffic that the BizTalk Server system can handle indefinitely in production.</span></span> <span data-ttu-id="a31d7-111">请按照 BizTalk Server 帮助中的以下主题中的步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a31d7-111">Follow the steps in the following topics in BizTalk Server Help:</span></span>  
  
    -   <span data-ttu-id="a31d7-112">[衡量最大可持续引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)。</span><span class="sxs-lookup"><span data-stu-id="a31d7-112">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388).</span></span>  
  
    -   <span data-ttu-id="a31d7-113">[衡量最大可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。</span><span class="sxs-lookup"><span data-stu-id="a31d7-113">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span></span>  
  
     <span data-ttu-id="a31d7-114">这些主题描述用于生成针对系统、 应进行衡量，参数和一般建议在测试 MST 时应遵循的负载的方法。</span><span class="sxs-lookup"><span data-stu-id="a31d7-114">These topics describe the methodology for generating load against the system, the parameters that should be measured, and general recommendations to follow when testing MST.</span></span>  
  
3.  <span data-ttu-id="a31d7-115">**了解如何影响 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="a31d7-115">**Understand the implications of how BizTalk Server**</span></span>  
     <span data-ttu-id="a31d7-116">**实现限制的主机。**</span><span class="sxs-lookup"><span data-stu-id="a31d7-116">**implements host throttling.**</span></span> <span data-ttu-id="a31d7-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]限制算法的主机尝试进行的工作负荷的中等[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例以确保工作负荷不超过的主机实例的容量或任何下游托管实例。</span><span class="sxs-lookup"><span data-stu-id="a31d7-117">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host throttling algorithm attempts to moderate the workload of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances to ensure that the workload does not exceed the capacity of the host instance or any downstream host instances.</span></span> <span data-ttu-id="a31d7-118">此限制的机制是自我调整和默认配置选项都适用于大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理方案。</span><span class="sxs-lookup"><span data-stu-id="a31d7-118">The throttling mechanism is self tuning and the default configuration options are suitable for the majority of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processing scenarios.</span></span> <span data-ttu-id="a31d7-119">但是，应，具有更好地理解实现负载/压力测试前的限制机制。</span><span class="sxs-lookup"><span data-stu-id="a31d7-119">You should, however, have a good understanding of the throttling mechanism before implementing load/stress testing.</span></span> <span data-ttu-id="a31d7-120">有关详细信息，请参阅[优化资源使用通过主机限制](http://go.microsoft.com/fwlink/?LinkId=155770)(http://go.microsoft.com/fwlink/?LinkId=155770) BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="a31d7-120">For more information, see [Optimizing Resource Usage Through Host Throttling](http://go.microsoft.com/fwlink/?LinkId=155770) (http://go.microsoft.com/fwlink/?LinkId=155770) in BizTalk Server Help.</span></span>