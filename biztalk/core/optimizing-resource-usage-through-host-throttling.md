---
title: 优化资源使用情况通过主机阻止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ada7b36453945b676db8aa897d7e0e862d3907
ms.sourcegitcommit: ec7013f5ddcd2da4291ae29ac28f965d89aa277a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "22263605"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a><span data-ttu-id="e9b6a-102">通过主机阻止优化资源使用情况</span><span class="sxs-lookup"><span data-stu-id="e9b6a-102">Optimizing Resource Usage Through Host Throttling</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e9b6a-103">使用多个不同的 Microsoft 技术，其中每个可使用内存、 磁盘和 BizTalk server 和包含 BizTalk Server 数据库的 SQL 服务器上的可用 CPU 资源的重要部分。</span><span class="sxs-lookup"><span data-stu-id="e9b6a-103">makes use of several different Microsoft technologies, each of which can consume a significant portion of the memory, disk, and CPU resources available on the BizTalk server and the SQL server that contains the BizTalk Server databases.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e9b6a-104">利用阻止机制来帮助管理可用资源，以最大程度减少使用的资源争用的使用。</span><span class="sxs-lookup"><span data-stu-id="e9b6a-104">employs a throttling mechanism to help manage the use of available resources to minimize resource use contention.</span></span> <span data-ttu-id="e9b6a-105">本主题讨论此机制的设计。</span><span class="sxs-lookup"><span data-stu-id="e9b6a-105">This topic discusses the design of this mechanism.</span></span> <span data-ttu-id="e9b6a-106">有关如何调整阻止值的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b6a-106">For information on how to adjust the throttling values, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9b6a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="e9b6a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="e9b6a-108">主机限制概述</span><span class="sxs-lookup"><span data-stu-id="e9b6a-108">What Is Host Throttling?</span></span>](../core/what-is-host-throttling.md)  
  
-   [<span data-ttu-id="e9b6a-109">BizTalk Server 如何实现主机限制</span><span class="sxs-lookup"><span data-stu-id="e9b6a-109">How BizTalk Server Implements Host Throttling</span></span>](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [<span data-ttu-id="e9b6a-110">主机限制性能计数器</span><span class="sxs-lookup"><span data-stu-id="e9b6a-110">Host Throttling Performance Counters</span></span>](../core/host-throttling-performance-counters.md)  
  
-   [<span data-ttu-id="e9b6a-111">限制设计建议</span><span class="sxs-lookup"><span data-stu-id="e9b6a-111">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)