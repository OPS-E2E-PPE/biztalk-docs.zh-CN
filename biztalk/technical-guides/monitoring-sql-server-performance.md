---
title: 监视 SQL Server 的性能 |Microsoft Docs
description: 监视 BizTalk Server 数据库使用的性能工具、 活动监视器和数据收集
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 730896dc1cf0a465f68965f812da7311dd8664ab
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640113"
---
# <a name="monitor-sql-server-performance"></a><span data-ttu-id="28416-103">监视 SQL Server 性能</span><span class="sxs-lookup"><span data-stu-id="28416-103">Monitor SQL Server Performance</span></span>
<span data-ttu-id="28416-104">SQL Server 提供了几个工具，用于监视 SQL Server 中的事件和优化物理数据库设计。</span><span class="sxs-lookup"><span data-stu-id="28416-104">SQL Server provides several tools for monitoring events in SQL Server and for tuning the physical database design.</span></span> <span data-ttu-id="28416-105">[适用于性能监视和优化工具](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)介绍了这些工具。</span><span class="sxs-lookup"><span data-stu-id="28416-105">[Tools for Performance Monitoring and Tuning](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describes these tools.</span></span> 
  
<span data-ttu-id="28416-106">BizTalk Server 是一个占用大量数据库的过程。</span><span class="sxs-lookup"><span data-stu-id="28416-106">BizTalk Server is a database-intensive process.</span></span> <span data-ttu-id="28416-107">故障排除时 BizTalk Server 性能问题，可能非常有益，则亦检查 SQL Server 性能。</span><span class="sxs-lookup"><span data-stu-id="28416-107">when troubleshooting BizTalk Server performance issues, it can be beneficial to also check the SQL Server performance.</span></span> <span data-ttu-id="28416-108">以下工具可帮助。</span><span class="sxs-lookup"><span data-stu-id="28416-108">The following tools can help.</span></span>  
  
## <a name="sql-server-activity-monitor"></a><span data-ttu-id="28416-109">SQL Server 活动监视器</span><span class="sxs-lookup"><span data-stu-id="28416-109">SQL Server Activity Monitor</span></span>  
<span data-ttu-id="28416-110">SQL Server 活动监视器提供了有关 SQL Server 进程以及这些进程如何影响 SQL Server 的当前实例的信息。</span><span class="sxs-lookup"><span data-stu-id="28416-110">SQL Server Activity Monitor provides information about SQL Server processes and how these processes affect the current instance of SQL Server.</span></span> <span data-ttu-id="28416-111">有关详细信息，请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，并[如何： 打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。</span><span class="sxs-lookup"><span data-stu-id="28416-111">For more information, see [Activity Monitor](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), and [How to: Open Activity Monitor (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio).</span></span> 
  
## <a name="sql-serverdata-collection"></a><span data-ttu-id="28416-112">SQL 服务器数据集合</span><span class="sxs-lookup"><span data-stu-id="28416-112">SQL ServerData Collection</span></span>  
<span data-ttu-id="28416-113">SQL Server 提供了一个数据收集器，可用于获取和保存从多个源收集的数据。</span><span class="sxs-lookup"><span data-stu-id="28416-113">SQL Server provides a data collector that you can use to obtain and save data that is gathered from several sources.</span></span> <span data-ttu-id="28416-114">数据收集器，可使用数据收集容器，使您能够确定作用域和运行 SQL Server 的计算机上的数据收集的频率。</span><span class="sxs-lookup"><span data-stu-id="28416-114">The data collector enables you to use data collection containers, which enable you to determine the scope and frequency of data collection on a computer that is running SQL Server.</span></span> <span data-ttu-id="28416-115">请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。</span><span class="sxs-lookup"><span data-stu-id="28416-115">See [Data Collection](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28416-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="28416-116">See Also</span></span>  
 [<span data-ttu-id="28416-117">优化数据库性能</span><span class="sxs-lookup"><span data-stu-id="28416-117">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
