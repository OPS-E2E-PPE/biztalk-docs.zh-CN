---
title: "可伸缩性概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6208319fb8c195558101433cd1668ab0e0f064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-scalability"></a><span data-ttu-id="22435-103">可伸缩性概述</span><span class="sxs-lookup"><span data-stu-id="22435-103">What Is Scalability?</span></span>
<span data-ttu-id="22435-104">可伸缩性是指系统为满足您的业务需求进行扩展的能力。</span><span class="sxs-lookup"><span data-stu-id="22435-104">Scalability is the ability of a system to expand to meet your business needs.</span></span> <span data-ttu-id="22435-105">在不对应用程序进行较大改动的情况下，可以通过添加额外的硬件或通过升级现有硬件来对系统进行扩展。</span><span class="sxs-lookup"><span data-stu-id="22435-105">You scale a system by adding extra hardware or by upgrading the existing hardware without changing much of the application.</span></span> <span data-ttu-id="22435-106">在 BizTalk Server 系统环境中，可伸缩性是指 BizTalk 能够根据吞吐量需求的增长进行扩展的能力（如果您需要缩短延迟时间）。</span><span class="sxs-lookup"><span data-stu-id="22435-106">In the context of a BizTalk Server system, scalability refers to the ability of BizTalk to scale as your throughput needs increase, and if you need to reduce latency times.</span></span>  
  
 <span data-ttu-id="22435-107">在对 BizTalk 的各个组件进行优化和调整之后，您可能仍会在 BizTalk 计算机或 MessageBox 数据库上遇到瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="22435-107">After you optimize and tune various components of BizTalk, you might still encounter bottlenecks on BizTalk computers or on the MessageBox database.</span></span> <span data-ttu-id="22435-108">在 BizTalk 环境中发生的瓶颈类型通常为 CPU、内存、输入/输出和锁争用瓶颈。</span><span class="sxs-lookup"><span data-stu-id="22435-108">The types of bottlenecks that usually occur in BizTalk environments are CPU, memory, IO and lock contention bottlenecks.</span></span> <span data-ttu-id="22435-109">在遇到瓶颈后，您可能需要升级硬件或向现有拓扑结构中添加新硬件。</span><span class="sxs-lookup"><span data-stu-id="22435-109">When you start to encounter bottlenecks, you may need to either upgrade the hardware or add new hardware into the existing topology.</span></span> <span data-ttu-id="22435-110">但幸运的是，BizTalk Server 结构使您可以轻松地向上扩展和向外扩展。例如，您可以向组中添加多台 BizTalk Server 计算机，也可以添加额外的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="22435-110">Fortunately, BizTalk Server architecture enables you to easily scale-up and scale-out. For example, you can add multiple BizTalk Server computers into the group and also add extra MessageBox databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22435-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22435-111">See Also</span></span>  
 <span data-ttu-id="22435-112">[BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="22435-112">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="22435-113">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="22435-113">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="22435-114">[BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="22435-114">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="22435-115">[SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="22435-115">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="22435-116">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="22435-116">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="22435-117">[向外扩展的处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="22435-117">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="22435-118">[向外扩展的发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="22435-118">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="22435-119">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="22435-119">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="22435-120">[向外扩展的数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="22435-120">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="22435-121">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="22435-121">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)