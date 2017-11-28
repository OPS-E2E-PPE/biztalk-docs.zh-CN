---
title: "优化通过限制的主机的资源使用情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-resource-usage-through-host-throttling"></a><span data-ttu-id="6d2e1-102">通过主机阻止优化资源使用率</span><span class="sxs-lookup"><span data-stu-id="6d2e1-102">Optimizing Resource Usage Through Host Throttling</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6d2e1-103">使用多种不同的 Microsoft 技术，其中每个可以使用的内存、 磁盘和 CPU 资源在 BizTalk server 和包含 BizTalk Server 数据库的 SQL 服务器上可用的重要部分。</span><span class="sxs-lookup"><span data-stu-id="6d2e1-103"> makes use of several different Microsoft technologies, each of which can consume a significant portion of the memory, disk, and CPU resources available on the BizTalk server and the SQL server that contains the BizTalk Server databases.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6d2e1-104">使用限制的机制，来帮助管理可用资源，以最大程度减少资源使用争用的使用。</span><span class="sxs-lookup"><span data-stu-id="6d2e1-104"> employs a throttling mechanism to help manage the use of available resources to minimize resource use contention.</span></span> <span data-ttu-id="6d2e1-105">本主题讨论此机制的设计。</span><span class="sxs-lookup"><span data-stu-id="6d2e1-105">This topic discusses the design of this mechanism.</span></span> <span data-ttu-id="6d2e1-106">有关如何调整的限制值的信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2e1-106">For information on how to adjust the throttling values, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d2e1-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="6d2e1-107">In This Section</span></span>  
  
-   [<span data-ttu-id="6d2e1-108">主机限制？</span><span class="sxs-lookup"><span data-stu-id="6d2e1-108">What Is Host Throttling?</span></span>](../core/what-is-host-throttling.md)  
  
-   [<span data-ttu-id="6d2e1-109">BizTalk Server 如何实施限制的主机</span><span class="sxs-lookup"><span data-stu-id="6d2e1-109">How BizTalk Server Implements Host Throttling</span></span>](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [<span data-ttu-id="6d2e1-110">主机限制性能计数器</span><span class="sxs-lookup"><span data-stu-id="6d2e1-110">Host Throttling Performance Counters</span></span>](../core/host-throttling-performance-counters.md)  
  
-   [<span data-ttu-id="6d2e1-111">限制的设计建议</span><span class="sxs-lookup"><span data-stu-id="6d2e1-111">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)