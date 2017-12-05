---
title: "监视 SQL Server |Microsoft 文档"
description: "使用 SQL Server 管理包来检查性能、 可用空间，数据库配置、 阻塞的进程、 连接、 失败 SQL 代理作业、 复制和 BizTalk Server 中的详细信息"
ms.custom: 
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31871432-e13d-4ef3-b886-16c833371f6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0e3ea9ecb9d9d910549790568d5891b72d06de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="ac16a-103">监视 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac16a-103">Monitoring SQL Servers</span></span>

## <a name="use-sql-management-pack"></a><span data-ttu-id="ac16a-104">使用 SQL 管理包</span><span class="sxs-lookup"><span data-stu-id="ac16a-104">Use SQL management pack</span></span>
<span data-ttu-id="ac16a-105">Microsoft SQL Server 管理包提供主动式和反应式监视 SQL Server 在企业环境中。</span><span class="sxs-lookup"><span data-stu-id="ac16a-105">The Microsoft SQL Server management pack provides both proactive and reactive monitoring of SQL Server in an enterprise environment.</span></span> <span data-ttu-id="ac16a-106">可用性和配置监视，为企业级监视生成性能数据收集以及默认阈值。</span><span class="sxs-lookup"><span data-stu-id="ac16a-106">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="ac16a-107">检查帮助确保数据库可用性的本地和远程连接。</span><span class="sxs-lookup"><span data-stu-id="ac16a-107">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="ac16a-108">通过 SQL Server 管理包中嵌入的专业技能，你可以主动管理 SQL Server，并变得严重之前先行确定问题。</span><span class="sxs-lookup"><span data-stu-id="ac16a-108">With the embedded expertise in the SQL Server management pack, you can proactively manage SQL Server, and identify issues before they become critical.</span></span> <span data-ttu-id="ac16a-109">此管理包增加了安全性、 可用性和性能的 SQL Server 基础结构。</span><span class="sxs-lookup"><span data-stu-id="ac16a-109">This management pack increases the security, availability, and performance of your SQL Server infrastructure.</span></span>  
  
 <span data-ttu-id="ac16a-110">附带了包的 Microsoft SQL Server 管理包指南描述管理包的内容，并描述如何将其部署。</span><span class="sxs-lookup"><span data-stu-id="ac16a-110">The Microsoft SQL Server management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="ac16a-111">管理包的功能包括：</span><span class="sxs-lookup"><span data-stu-id="ac16a-111">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="ac16a-112">监视如 SQL Server、 SQL 代理、 报表服务器、 Notification Services 包含的服务的状态</span><span class="sxs-lookup"><span data-stu-id="ac16a-112">Monitoring the state of the included services such as SQL Server, SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="ac16a-113">监视数据库的状态</span><span class="sxs-lookup"><span data-stu-id="ac16a-113">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="ac16a-114">监视在数据库中，按 %或 MB 可配置的可用空间</span><span class="sxs-lookup"><span data-stu-id="ac16a-114">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="ac16a-115">确保数据库已正确配置</span><span class="sxs-lookup"><span data-stu-id="ac16a-115">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="ac16a-116">确保客户端可以连接到 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac16a-116">Ensure clients can connect to the SQL Server</span></span>  
  
-   <span data-ttu-id="ac16a-117">监视阻塞的进程</span><span class="sxs-lookup"><span data-stu-id="ac16a-117">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="ac16a-118">观看有关失败的代理程序作业和作业需要的过多的时间才能执行</span><span class="sxs-lookup"><span data-stu-id="ac16a-118">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="ac16a-119">监视复制和失败的警报的运行状况</span><span class="sxs-lookup"><span data-stu-id="ac16a-119">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="ac16a-120">监视数据库镜像的状态</span><span class="sxs-lookup"><span data-stu-id="ac16a-120">Monitor the state of Database Mirroring</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ac16a-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ac16a-121">Next steps</span></span>
  
-   [<span data-ttu-id="ac16a-122">监视 SQL Server 代理作业和数据库</span><span class="sxs-lookup"><span data-stu-id="ac16a-122">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="ac16a-123">如何为自定义监视标记 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="ac16a-123">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="ac16a-124">监视 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="ac16a-124">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)