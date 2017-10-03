---
title: "建议在测试时引擎性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: maximum sustainable throughput (MST), best practices
ms.assetid: 0aa9d833-0e7d-4347-a6ca-8d658749b4f2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fc2d81ca8121fe625a30258070281d2b3ff4bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="recommendations-when-testing-engine-performance"></a><span data-ttu-id="3b4a3-102">测试引擎性能时的建议</span><span class="sxs-lookup"><span data-stu-id="3b4a3-102">Recommendations When Testing Engine Performance</span></span>
<span data-ttu-id="3b4a3-103">在测试 BizTalk 引擎性能时应当遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="3b4a3-103">The following guidelines should be followed when testing BizTalk engine performance:</span></span>  
  
 <span data-ttu-id="3b4a3-104">**知道负载行为配置文件**如三个负载测试具有所示，它知道至关重要的消息所进行随着时间的推移处理负载的配置文件。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-104">**Know your load behavior profile** As the three load tests have illustrated, it is critical to know the profile of your load in terms of messages processed over time.</span></span>  <span data-ttu-id="3b4a3-105">对这一点理解越深，就越能准确地测试和调整系统容量。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-105">The better this is understood, the more accurately you can test and adjust your system capacity.</span></span> <span data-ttu-id="3b4a3-106">若只知道峰值吞吐量要求，则最保守的办法是调整系统大小，以便使最大可承受吞吐量等于或大于峰值负载。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-106">If all you know is your peak throughput requirement, then the most conservative approach would be to size your system so that your maximum sustainable throughput is the same or higher than your peak load.</span></span> <span data-ttu-id="3b4a3-107">但是，如果可预测负载峰值和低谷，则可更好地优化系统以在峰值之间恢复正常，从而使总体部署规模更小、开销更低。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-107">However, if you know that you have predictable peaks and valleys in your load, you can better optimize your system to recover between peaks, resulting in a smaller, less expensive overall deployment.</span></span>  
  
 <span data-ttu-id="3b4a3-108">**测试性能尽早**避免落在投资中设计和测试你的解决方案的功能，但是等待一分钟的大量精力，来测试生产硬件上的性能的陷阱。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-108">**Test performance early** Avoid falling into the trap of investing significant effort in designing and testing the functionality of your solution, but waiting until the last minute to test performance on production hardware.</span></span> <span data-ttu-id="3b4a3-109">在开发周期中，应尽可能早地在系统上运行模拟预期负载状况的性能测试。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-109">Run performance tests on your system that simulate the expected load profile as early as you possibly can in your development cycle.</span></span> <span data-ttu-id="3b4a3-110">如果必须对设计或体系结构做出更改才能达到您的要求，则尽早了解这一点将有助于您争取时间再次进行调整和测试。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-110">If you have to change anything in your design or architecture to achieve your goals knowing this early will give you time to adjust and test again.</span></span>  
  
 <span data-ttu-id="3b4a3-111">**模拟你的预期的负载配置文件，测试性能时**到这两个主组件：</span><span class="sxs-lookup"><span data-stu-id="3b4a3-111">**Emulate your expected load profile when testing performance** There are two primary components to this:</span></span>  
  
1.  <span data-ttu-id="3b4a3-112">模拟负载随时间变化的状况。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-112">Emulate the load profile over time.</span></span>  
  
2.  <span data-ttu-id="3b4a3-113">尽可能长时间运行测试以评估性能的可持续性。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-113">Run the test long enough to evaluate if it is sustainable.</span></span>  
  
 <span data-ttu-id="3b4a3-114">通常情况下，如果您的周期实际为一天，则应计划至少运行性能测试一天，以验证可承受性。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-114">If, as is commonly the case, your cycles are daily in nature you should plan to run performance tests for at least one day to validate sustainability.</span></span> <span data-ttu-id="3b4a3-115">运行测试的时间越长越好。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-115">The longer that you run the tests, the better.</span></span>  
  
 <span data-ttu-id="3b4a3-116">**模拟生产配置**示例、 数量和类型的端口，在主机和主机实例配置、 数据库配置和适配器安装程序。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-116">**Emulate the production configuration** For example, the number and type of ports, the host and host instance configuration, database configuration, and adapter setup.</span></span> <span data-ttu-id="3b4a3-117">不要认为配置更改不会对性能造成很大影响。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-117">Don’t assume that configuration changes will not significantly impact performance.</span></span>  
  
 <span data-ttu-id="3b4a3-118">**使用实际消息**消息大小和消息复杂性会影响性能，因此在一定的并且使用相同的消息架构和你打算在生产中看到的实例进行测试。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-118">**Use real messages** Message sizes and message complexity affect performance, so be sure and test with the same message schemas and instances that you plan to see in production.</span></span>  
  
 <span data-ttu-id="3b4a3-119">**性能测试中模拟正常操作**尽管负载测试不包括它们的标准操作活动，例如定期数据库查询，备份，并清除将影响你可持续吞吐量，因此请确保你在性能和容量测试运行期间执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-119">**Emulate your normal operations during performance tests** Though the load tests did not include them, standard operations activities such as periodic database queries, backups, and purging will affect your sustainable throughput, so make sure you are performing these tasks during your performance and capacity test runs.</span></span> <span data-ttu-id="3b4a3-120">若要在生产中使用这些操作，那么这将同时包括 DTA 和 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-120">This includes both DTA and BAM tracking, if you plan to use them in production.</span></span>  
  
 <span data-ttu-id="3b4a3-121">**MessageBox 的 I/O 子系统的速度是关键成功因素**执行的负载测试所做的专用于此生成扩展 MessageBox 数据库文件使用的快速存储区域网络。甚至在这种情况下，清除作业也能够使 SQL 数据文件的空闲时间接近零。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-121">**The speed of the I/O subsystem for the MessageBox is a key success factor** The load tests that were performed made use of a fast Storage Area Network for the MessageBox database files that is dedicated to this build-out. Even in this case, the cleanup jobs were able to drive the idle time to near zero for the SQL data file.</span></span> <span data-ttu-id="3b4a3-122">大多数情况下，I/O 子系统是生产系统中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-122">The I/O subsystem is frequently a bottleneck in production systems.</span></span> <span data-ttu-id="3b4a3-123">优化 SQL I/O 的常规策略是：如果可能，则将数据库数据文件和日志文件分别放于单独的物理驱动器上。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-123">A common strategy to optimize SQL I/O is to place the database data file(s) and log file(s) on separate physical drives, if possible.</span></span>  
  
 <span data-ttu-id="3b4a3-124">**请确保 SQL 代理运行所有 MessageBox 服务器上**很明显，清理作业将永远不会运行如果 SQL 代理未运行，因此请确保它们运行。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-124">**Make sure the SQL Agent is running on all MessageBox servers** Clearly, the cleanup jobs will never run if the SQL Agent is not running, so make sure these are running.</span></span>  
  
 <span data-ttu-id="3b4a3-125">**假脱机深度是关键指标**而不考虑其他指示器，此度量值将为你提供快速方便地评估是否或不在输出过度你的系统。</span><span class="sxs-lookup"><span data-stu-id="3b4a3-125">**Spool depth is a key indicator** Regardless of other indicators, this measure will give you a quick and easy way to assess if your system is being overdriven or not.</span></span>