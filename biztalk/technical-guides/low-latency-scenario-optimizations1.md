---
title: "低延迟方案 Optimizations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2957888253826845ea9a941ad7fce8fd7a2ed7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="low-latency-scenario-optimizations"></a><span data-ttu-id="61e11-102">低延迟方案优化</span><span class="sxs-lookup"><span data-stu-id="61e11-102">Low-Latency Scenario Optimizations</span></span>
<span data-ttu-id="61e11-103">默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对吞吐量，而不是低延迟进行了优化。</span><span class="sxs-lookup"><span data-stu-id="61e11-103">By default, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="61e11-104">下列优化已应用到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]测试方案用于本指南。</span><span class="sxs-lookup"><span data-stu-id="61e11-104">The following optimizations were applied to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the test scenario used for this guide.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61e11-105">这些优化将提高延迟，但可能在执行此操作对整体吞吐量一些成本。</span><span class="sxs-lookup"><span data-stu-id="61e11-105">These optimizations will improve latency but may do so at some cost to overall throughput.</span></span>  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a><span data-ttu-id="61e11-106">增加的 BizTalk Server 主机内部消息队列大小</span><span class="sxs-lookup"><span data-stu-id="61e11-106">Increase the BizTalk Server host internal message queue size</span></span>  
 <span data-ttu-id="61e11-107">每个 BizTalk 主机有其自己的内部内存中队列。</span><span class="sxs-lookup"><span data-stu-id="61e11-107">Each BizTalk host has its own internal in-memory queue.</span></span> <span data-ttu-id="61e11-108">增加此队列从 100 到 1000，以提高性能的低延迟方案的默认值的大小。</span><span class="sxs-lookup"><span data-stu-id="61e11-108">Increase the size of this queue from the default value of 100 to 1000 to improve performance for a low-latency scenario.</span></span> <span data-ttu-id="61e11-109">有关修改的内部消息队列大小的值的详细信息，请参阅"如何为修改默认主机限制设置"中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)。</span><span class="sxs-lookup"><span data-stu-id="61e11-109">For more information about modifying the value of the internal message queue size, see “How to Modify the Default Host Throttling Settings” in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] help at [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225).</span></span>  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a><span data-ttu-id="61e11-110">减小 BizTalk Server 管理数据库的 adm_ServiceClass 表中的 MaxReceiveInterval 值</span><span class="sxs-lookup"><span data-stu-id="61e11-110">Reduce the MaxReceiveInterval value in the adm_ServiceClass table of the BizTalk Server management database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="61e11-111">使用轮询机制从 Messagebox 中其主机队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="61e11-111"> uses a polling mechanism to receive messages from its host queues in the Messagebox.</span></span> <span data-ttu-id="61e11-112">**MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) 数据库 adm_ServiceClass 表中的值是以每个 BizTalk 主机实例将等待的毫秒为单位的最大值之前它轮询 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="61e11-112">The **MaxReceiveInterval** value in the adm_ServiceClass table of the BizTalk Management (BizTalkMgmtDb) database is the maximum value in milliseconds that each BizTalk host instance will wait until it polls the MessageBox.</span></span> <span data-ttu-id="61e11-113">Adm_ServiceClass 表包含以下服务类型的记录包含：</span><span class="sxs-lookup"><span data-stu-id="61e11-113">The adm_ServiceClass table contains a record for the following service types:</span></span>  
  
-   <span data-ttu-id="61e11-114">**XLANG/S** – 表示 BizTalk 业务流程主机实例</span><span class="sxs-lookup"><span data-stu-id="61e11-114">**XLANG/S** – for BizTalk orchestration host instances</span></span>  
  
-   <span data-ttu-id="61e11-115">**消息传送 InProcess** – 进程内主机实例</span><span class="sxs-lookup"><span data-stu-id="61e11-115">**Messaging InProcess** – for in-process host instances</span></span>  
  
-   <span data-ttu-id="61e11-116">**MSMQT** – MSMQT 适配器主机实例</span><span class="sxs-lookup"><span data-stu-id="61e11-116">**MSMQT** – for MSMQT adapter host instances</span></span>  
  
-   <span data-ttu-id="61e11-117">**消息传送 Isolated** – 用于外进程主机实例，使用 HTTP、 SOAP、 和某些 WCF 接收适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="61e11-117">**Messaging Isolated** – for out of process host instances, used by the HTTP, SOAP, and certain WCF receive adapter handlers</span></span>  
  
 <span data-ttu-id="61e11-118">默认情况下，此值设置为 500 毫秒，针对吞吐量，而不是低延迟进行了优化。</span><span class="sxs-lookup"><span data-stu-id="61e11-118">By default, this value is set to 500 milliseconds, which is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="61e11-119">在某些情况下，可以通过减小此值进行改进延迟。</span><span class="sxs-lookup"><span data-stu-id="61e11-119">In certain scenarios, latency can be improved by reducing this value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61e11-120">为此值的更改影响所有类型的实例关联的服务，因此，请小心谨慎以更改此值之前评估所有主机实例上的影响。</span><span class="sxs-lookup"><span data-stu-id="61e11-120">Changes to this value impact all instances of the associated service type, therefore, take care to evaluate the impact on all host instances before changing this value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61e11-121">仅当 Messagebox 不具有任何剩余的未处理的消息，才能使用此值。</span><span class="sxs-lookup"><span data-stu-id="61e11-121">This value is only used if the Messagebox has no remaining unprocessed messages.</span></span> <span data-ttu-id="61e11-122">如果没有在消息框中，未处理消息的常量囤积[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将尝试处理消息，而无需等到上轮询延迟。</span><span class="sxs-lookup"><span data-stu-id="61e11-122">If there is a constant backlog of unprocessed messages in the Messagebox, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will attempt to process the messages without waiting on the polling delay.</span></span> <span data-ttu-id="61e11-123">在处理所有消息之后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将开始轮询使用 MaxReceiveInterval 为指定的值。</span><span class="sxs-lookup"><span data-stu-id="61e11-123">After all messages are processed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will begin polling using the value specified for MaxReceiveInterval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61e11-124">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Messagebox 数据库实例，减小值 MaxReceiveInterval 可能会保存 Messagebox 数据库实例的 SQL Server 计算机上的 CPU 使用率过高的主机实例的比值较高的环境。</span><span class="sxs-lookup"><span data-stu-id="61e11-124">In a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a high ratio of host instances to Messagebox database instances, decreasing the value for MaxReceiveInterval may cause excessive CPU utilization on the SQL Server computer that houses the Messagebox database instance.</span></span> <span data-ttu-id="61e11-125">例如，如果 MaxReceiveInterval 减小到较低的值 (\< 100) 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中的使用单个消息框和 > 50 主机实例，SQL Server 上的 CPU 使用率可能攀升超过 50%。</span><span class="sxs-lookup"><span data-stu-id="61e11-125">For example, if the MaxReceiveInterval is decreased to a low value (\< 100) in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a single Messagebox and > 50 host instances, CPU utilization on the SQL Server may climb above 50%.</span></span> <span data-ttu-id="61e11-126">由于与不断轮询主机队列关联的开销很重要，则可能出现这种现象。</span><span class="sxs-lookup"><span data-stu-id="61e11-126">This phenomenon can occur because the overhead associated with continually polling host queues is significant.</span></span> <span data-ttu-id="61e11-127">如果你 MaxReceiveInterval 的值减小至小于 100，你还应该评估这对 SQL Server 计算机的 CPU 使用率的影响。</span><span class="sxs-lookup"><span data-stu-id="61e11-127">If you reduce MaxReceiveInterval to a value less than 100, you should also evaluate the impact that this has on your SQL Server computer’s CPU utilization.</span></span>