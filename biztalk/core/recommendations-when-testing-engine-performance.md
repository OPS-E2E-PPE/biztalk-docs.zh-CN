---
title: 引擎性能测试时的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), best practices
ms.assetid: 0aa9d833-0e7d-4347-a6ca-8d658749b4f2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a34bf5db6186eac521f0a74542cfe4c6cc8429dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972470"
---
# <a name="recommendations-when-testing-engine-performance"></a><span data-ttu-id="431aa-102">测试引擎性能时的建议</span><span class="sxs-lookup"><span data-stu-id="431aa-102">Recommendations When Testing Engine Performance</span></span>
<span data-ttu-id="431aa-103">在测试 BizTalk 引擎性能时应当遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="431aa-103">The following guidelines should be followed when testing BizTalk engine performance:</span></span>  
  
 <span data-ttu-id="431aa-104">**了解加载行为配置文件**三个负载测试所示，如有必要了解随着时间的推移处理消息负载的配置文件。</span><span class="sxs-lookup"><span data-stu-id="431aa-104">**Know your load behavior profile** As the three load tests have illustrated, it is critical to know the profile of your load in terms of messages processed over time.</span></span>  <span data-ttu-id="431aa-105">对这一点理解越深，就越能准确地测试和调整系统容量。</span><span class="sxs-lookup"><span data-stu-id="431aa-105">The better this is understood, the more accurately you can test and adjust your system capacity.</span></span> <span data-ttu-id="431aa-106">若只知道峰值吞吐量要求，则最保守的办法是调整系统大小，以便使最大可承受吞吐量等于或大于峰值负载。</span><span class="sxs-lookup"><span data-stu-id="431aa-106">If all you know is your peak throughput requirement, then the most conservative approach would be to size your system so that your maximum sustainable throughput is the same or higher than your peak load.</span></span> <span data-ttu-id="431aa-107">但是，如果可预测负载峰值和低谷，则可更好地优化系统以在峰值之间恢复正常，从而使总体部署规模更小、开销更低。</span><span class="sxs-lookup"><span data-stu-id="431aa-107">However, if you know that you have predictable peaks and valleys in your load, you can better optimize your system to recover between peaks, resulting in a smaller, less expensive overall deployment.</span></span>  
  
 <span data-ttu-id="431aa-108">**测试性能尽早**避免将大量精力在设计和测试解决方案的功能而应等到最后一分钟，若要测试生产硬件上的性能陷阱。</span><span class="sxs-lookup"><span data-stu-id="431aa-108">**Test performance early** Avoid falling into the trap of investing significant effort in designing and testing the functionality of your solution, but waiting until the last minute to test performance on production hardware.</span></span> <span data-ttu-id="431aa-109">在开发周期中，应尽可能早地在系统上运行模拟预期负载状况的性能测试。</span><span class="sxs-lookup"><span data-stu-id="431aa-109">Run performance tests on your system that simulate the expected load profile as early as you possibly can in your development cycle.</span></span> <span data-ttu-id="431aa-110">如果必须对设计或体系结构做出更改才能达到您的要求，则尽早了解这一点将有助于您争取时间再次进行调整和测试。</span><span class="sxs-lookup"><span data-stu-id="431aa-110">If you have to change anything in your design or architecture to achieve your goals knowing this early will give you time to adjust and test again.</span></span>  
  
 <span data-ttu-id="431aa-111">**测试性能时模拟预期的负载状况**有这两个主要组件：</span><span class="sxs-lookup"><span data-stu-id="431aa-111">**Emulate your expected load profile when testing performance** There are two primary components to this:</span></span>  
  
1. <span data-ttu-id="431aa-112">模拟负载随时间变化的状况。</span><span class="sxs-lookup"><span data-stu-id="431aa-112">Emulate the load profile over time.</span></span>  
  
2. <span data-ttu-id="431aa-113">尽可能长时间运行测试以评估性能的可持续性。</span><span class="sxs-lookup"><span data-stu-id="431aa-113">Run the test long enough to evaluate if it is sustainable.</span></span>  
  
   <span data-ttu-id="431aa-114">通常情况下，如果您的周期实际为一天，则应计划至少运行性能测试一天，以验证可承受性。</span><span class="sxs-lookup"><span data-stu-id="431aa-114">If, as is commonly the case, your cycles are daily in nature you should plan to run performance tests for at least one day to validate sustainability.</span></span> <span data-ttu-id="431aa-115">运行测试的时间越长越好。</span><span class="sxs-lookup"><span data-stu-id="431aa-115">The longer that you run the tests, the better.</span></span>  
  
   <span data-ttu-id="431aa-116">**模拟生产配置**示例、 数量和类型的端口，在主机和主机实例配置、 数据库配置和适配器安装程序。</span><span class="sxs-lookup"><span data-stu-id="431aa-116">**Emulate the production configuration** For example, the number and type of ports, the host and host instance configuration, database configuration, and adapter setup.</span></span> <span data-ttu-id="431aa-117">不要认为配置更改不会对性能造成很大影响。</span><span class="sxs-lookup"><span data-stu-id="431aa-117">Don’t assume that configuration changes will not significantly impact performance.</span></span>  
  
   <span data-ttu-id="431aa-118">**使用真实消息**消息大小和消息复杂性会影响性能，因此务必，测试具有相同的消息架构和计划以查看在生产环境中的实例。</span><span class="sxs-lookup"><span data-stu-id="431aa-118">**Use real messages** Message sizes and message complexity affect performance, so be sure and test with the same message schemas and instances that you plan to see in production.</span></span>  
  
   <span data-ttu-id="431aa-119">**性能测试期间模拟正常操作**尽管负载测试不包括它们的标准操作活动，例如定期数据库查询、 备份和清除将会影响可承受吞吐量，因此请确保你在性能和容量测试运行期间执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="431aa-119">**Emulate your normal operations during performance tests** Though the load tests did not include them, standard operations activities such as periodic database queries, backups, and purging will affect your sustainable throughput, so make sure you are performing these tasks during your performance and capacity test runs.</span></span> <span data-ttu-id="431aa-120">若要在生产中使用这些操作，那么这将同时包括 DTA 和 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="431aa-120">This includes both DTA and BAM tracking, if you plan to use them in production.</span></span>  
  
   <span data-ttu-id="431aa-121">**MessageBox 的 I/O 子系统的速度是成功的关键因素**执行负载测试所做的快速存储区域网络专用于此扩展的 MessageBox 数据库文件使用。甚至在这种情况下，清除作业也能够使 SQL 数据文件的空闲时间接近零。</span><span class="sxs-lookup"><span data-stu-id="431aa-121">**The speed of the I/O subsystem for the MessageBox is a key success factor** The load tests that were performed made use of a fast Storage Area Network for the MessageBox database files that is dedicated to this build-out. Even in this case, the cleanup jobs were able to drive the idle time to near zero for the SQL data file.</span></span> <span data-ttu-id="431aa-122">大多数情况下，I/O 子系统是生产系统中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="431aa-122">The I/O subsystem is frequently a bottleneck in production systems.</span></span> <span data-ttu-id="431aa-123">优化 SQL I/O 的常规策略是：如果可能，则将数据库数据文件和日志文件分别放于单独的物理驱动器上。</span><span class="sxs-lookup"><span data-stu-id="431aa-123">A common strategy to optimize SQL I/O is to place the database data file(s) and log file(s) on separate physical drives, if possible.</span></span>  
  
   <span data-ttu-id="431aa-124">**请确保所有 MessageBox 服务器上正在运行 SQL 代理**很明显，清除作业将永远不会运行如果未运行 SQL 代理，因此请确保它们运行。</span><span class="sxs-lookup"><span data-stu-id="431aa-124">**Make sure the SQL Agent is running on all MessageBox servers** Clearly, the cleanup jobs will never run if the SQL Agent is not running, so make sure these are running.</span></span>  
  
   <span data-ttu-id="431aa-125">**后台处理深度是关键指标**而不考虑其他指标，此度量值将可让你快速且轻松地评估您的系统超负荷运行或不。</span><span class="sxs-lookup"><span data-stu-id="431aa-125">**Spool depth is a key indicator** Regardless of other indicators, this measure will give you a quick and easy way to assess if your system is being overdriven or not.</span></span>