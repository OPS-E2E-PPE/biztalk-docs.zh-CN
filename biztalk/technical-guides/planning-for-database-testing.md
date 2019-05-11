---
title: 规划数据库测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298949e7d8f5fa30578f98cfd41dbab158893396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394610"
---
# <a name="planning-for-database-testing"></a><span data-ttu-id="892b0-102">规划数据库测试</span><span class="sxs-lookup"><span data-stu-id="892b0-102">Planning for Database Testing</span></span>
<span data-ttu-id="892b0-103">全面的压力负载测试的 BizTalk 解决方案中的图表突出的最终成功或失败的解决方案。</span><span class="sxs-lookup"><span data-stu-id="892b0-103">Thorough stress/load testing of a BizTalk solution figures prominently in the ultimate success or failure of the solution.</span></span> <span data-ttu-id="892b0-104">由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能所依赖的性能因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库、 测试和优化 BizTalk 解决方案通常侧重于测试和运行的计算机的优化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="892b0-104">Since [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance is so dependent on the performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, testing and optimization of a BizTalk solution frequently focuses on testing and optimization of the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="considerations-when-planning-for-database-testing"></a><span data-ttu-id="892b0-105">规划数据库测试时的注意事项</span><span class="sxs-lookup"><span data-stu-id="892b0-105">Considerations When Planning for Database Testing</span></span>  
 <span data-ttu-id="892b0-106">规划数据库测试时，请考虑以下方法：</span><span class="sxs-lookup"><span data-stu-id="892b0-106">Consider the following when planning for database testing:</span></span>  
  
1. <span data-ttu-id="892b0-107">**确保测试环境与生产环境尽可能真实地匹配。**</span><span class="sxs-lookup"><span data-stu-id="892b0-107">**Ensure that the test environment matches the production environment as closely as possible.**</span></span> <span data-ttu-id="892b0-108">使用如 Microsoft HYPER-V Server 2008 的虚拟环境进行单元测试是完全可以接受;但是，所有负载/压力测试都应该在针对尽可能接近地匹配最终生产环境的硬件。</span><span class="sxs-lookup"><span data-stu-id="892b0-108">Using a virtual environment such as Microsoft Hyper-V Server 2008 for unit testing is perfectly acceptable; however, all load/stress testing should be performed against hardware that matches the final production environment as closely as possible.</span></span>  
  
2. <span data-ttu-id="892b0-109">**计划度量值最大可承受吞吐量和 BizTalk Server 系统的最大可承受跟踪吞吐量**。</span><span class="sxs-lookup"><span data-stu-id="892b0-109">**Plan to measure maximum sustainable throughput and maximum sustainable tracking throughput of the BizTalk Server system**.</span></span> <span data-ttu-id="892b0-110">最大可承受吞吐量的衡量标准 BizTalk Server 系统可在生产环境中无限制处理的消息流量的最高负载。</span><span class="sxs-lookup"><span data-stu-id="892b0-110">Maximum sustainable throughput is measured as the highest load of message traffic that the BizTalk Server system can handle indefinitely in production.</span></span> <span data-ttu-id="892b0-111">请按照在 BizTalk Server 帮助中的以下主题中的步骤操作：</span><span class="sxs-lookup"><span data-stu-id="892b0-111">Follow the steps in the following topics in BizTalk Server Help:</span></span>  
  
   - <span data-ttu-id="892b0-112">[测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)。</span><span class="sxs-lookup"><span data-stu-id="892b0-112">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388).</span></span>  
  
   - <span data-ttu-id="892b0-113">[测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。</span><span class="sxs-lookup"><span data-stu-id="892b0-113">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span></span>  
  
     <span data-ttu-id="892b0-114">这些主题描述用于生成系统，应该度量的参数和一般建议在测试 MST 时应遵循针对负载的方法。</span><span class="sxs-lookup"><span data-stu-id="892b0-114">These topics describe the methodology for generating load against the system, the parameters that should be measured, and general recommendations to follow when testing MST.</span></span>  
  
3. <span data-ttu-id="892b0-115">**了解如何影响 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="892b0-115">**Understand the implications of how BizTalk Server**</span></span>  
    <span data-ttu-id="892b0-116">**实现主机阻止。**</span><span class="sxs-lookup"><span data-stu-id="892b0-116">**implements host throttling.**</span></span> <span data-ttu-id="892b0-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机阻止算法尝试中等的工作负荷[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例以确保负载没有超过主机实例的容量或任何下游主机实例。</span><span class="sxs-lookup"><span data-stu-id="892b0-117">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host throttling algorithm attempts to moderate the workload of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances to ensure that the workload does not exceed the capacity of the host instance or any downstream host instances.</span></span> <span data-ttu-id="892b0-118">该阻止机制具有自我优化和默认配置选项都适用于大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理方案。</span><span class="sxs-lookup"><span data-stu-id="892b0-118">The throttling mechanism is self tuning and the default configuration options are suitable for the majority of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processing scenarios.</span></span> <span data-ttu-id="892b0-119">但是，应该具有的限制机制实现负载/压力测试之前更好地理解。</span><span class="sxs-lookup"><span data-stu-id="892b0-119">You should, however, have a good understanding of the throttling mechanism before implementing load/stress testing.</span></span> <span data-ttu-id="892b0-120">有关详细信息，请参阅[优化资源使用情况通过主机阻止](http://go.microsoft.com/fwlink/?LinkId=155770)(<http://go.microsoft.com/fwlink/?LinkId=155770>) 在 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="892b0-120">For more information, see [Optimizing Resource Usage Through Host Throttling](http://go.microsoft.com/fwlink/?LinkId=155770) (<http://go.microsoft.com/fwlink/?LinkId=155770>) in BizTalk Server Help.</span></span>