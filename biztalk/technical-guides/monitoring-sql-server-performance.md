---
title: 监视 SQL Server 的性能 |Microsoft 文档
description: 监视使用性能工具、 活动监视器和数据收集的 BizTalk Server 数据库
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
ms.openlocfilehash: 1e4f9db738298ec2a242350faae3ba5bc9da1c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007894"
---
# <a name="monitor-sql-server-performance"></a><span data-ttu-id="a4321-103">监视 SQL Server 性能</span><span class="sxs-lookup"><span data-stu-id="a4321-103">Monitor SQL Server Performance</span></span>
<span data-ttu-id="a4321-104">SQL Server 提供几种工具，用于监视 SQL Server 中的事件和优化物理数据库设计。</span><span class="sxs-lookup"><span data-stu-id="a4321-104">SQL Server provides several tools for monitoring events in SQL Server and for tuning the physical database design.</span></span> <span data-ttu-id="a4321-105">[用于性能监视和优化工具](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)介绍了这些工具。</span><span class="sxs-lookup"><span data-stu-id="a4321-105">[Tools for Performance Monitoring and Tuning](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describes these tools.</span></span> 
  
<span data-ttu-id="a4321-106">BizTalk Server 是一个需要进行大量数据库的过程。</span><span class="sxs-lookup"><span data-stu-id="a4321-106">BizTalk Server is a database-intensive process.</span></span> <span data-ttu-id="a4321-107">在解决 BizTalk Server 性能问题时，它是有益的还要检查 SQL Server 性能。</span><span class="sxs-lookup"><span data-stu-id="a4321-107">when troubleshooting BizTalk Server performance issues, it can be beneficial to also check the SQL Server performance.</span></span> <span data-ttu-id="a4321-108">以下工具可以帮助。</span><span class="sxs-lookup"><span data-stu-id="a4321-108">The following tools can help.</span></span>  
  
## <a name="sql-server-activity-monitor"></a><span data-ttu-id="a4321-109">SQL Server 活动监视器</span><span class="sxs-lookup"><span data-stu-id="a4321-109">SQL Server Activity Monitor</span></span>  
<span data-ttu-id="a4321-110">SQL Server 活动监视器提供有关 SQL Server 过程和了解这些进程如何影响当前的 SQL Server 实例的信息。</span><span class="sxs-lookup"><span data-stu-id="a4321-110">SQL Server Activity Monitor provides information about SQL Server processes and how these processes affect the current instance of SQL Server.</span></span> <span data-ttu-id="a4321-111">有关详细信息，请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，和[如何： 打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。</span><span class="sxs-lookup"><span data-stu-id="a4321-111">For more information, see [Activity Monitor](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), and [How to: Open Activity Monitor (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio).</span></span> 
  
## <a name="sql-serverdata-collection"></a><span data-ttu-id="a4321-112">SQL ServerData 集合</span><span class="sxs-lookup"><span data-stu-id="a4321-112">SQL ServerData Collection</span></span>  
<span data-ttu-id="a4321-113">SQL Server 提供了可用于获取和保存数据，则通过多个来源收集的数据收集器。</span><span class="sxs-lookup"><span data-stu-id="a4321-113">SQL Server provides a data collector that you can use to obtain and save data that is gathered from several sources.</span></span> <span data-ttu-id="a4321-114">数据收集器，可使用使你可以确定的范围和频率的运行 SQL Server 的计算机上的数据收集的数据集合容器。</span><span class="sxs-lookup"><span data-stu-id="a4321-114">The data collector enables you to use data collection containers, which enable you to determine the scope and frequency of data collection on a computer that is running SQL Server.</span></span> <span data-ttu-id="a4321-115">请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。</span><span class="sxs-lookup"><span data-stu-id="a4321-115">See [Data Collection](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4321-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4321-116">See Also</span></span>  
 [<span data-ttu-id="a4321-117">优化数据库性能</span><span class="sxs-lookup"><span data-stu-id="a4321-117">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)