---
title: "监视 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
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
ms.openlocfilehash: 6ac37905574090fb346aeee198ea8e92a0f436f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="7c75e-102">监视 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c75e-102">Monitoring SQL Servers</span></span>
<span data-ttu-id="7c75e-103">Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包提供主动式和反应式监视的[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]企业环境中。</span><span class="sxs-lookup"><span data-stu-id="7c75e-103">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack provides both proactive and reactive monitoring of [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] and [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] in an enterprise environment.</span></span> <span data-ttu-id="7c75e-104">可用性和配置监视，为企业级监视生成性能数据收集以及默认阈值。</span><span class="sxs-lookup"><span data-stu-id="7c75e-104">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="7c75e-105">检查帮助确保数据库可用性的本地和远程连接。</span><span class="sxs-lookup"><span data-stu-id="7c75e-105">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="7c75e-106">与嵌入的专业技能[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包，你可以主动管理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，并趋于严重之前先行确定问题。</span><span class="sxs-lookup"><span data-stu-id="7c75e-106">With the embedded expertise in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack, you can proactively manage [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and identify issues before they become critical.</span></span> <span data-ttu-id="7c75e-107">此管理包增加了安全性、 可用性和性能的你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]基础结构。</span><span class="sxs-lookup"><span data-stu-id="7c75e-107">This management pack increases the security, availability, and performance of your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="7c75e-108">Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]附带了包的管理包指南描述管理包的内容并描述如何将其部署。</span><span class="sxs-lookup"><span data-stu-id="7c75e-108">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="7c75e-109">管理包的功能包括：</span><span class="sxs-lookup"><span data-stu-id="7c75e-109">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="7c75e-110">监视包含服务的状态，如[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，报表服务器的 SQL 代理通知服务</span><span class="sxs-lookup"><span data-stu-id="7c75e-110">Monitoring the state of the included services such as [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="7c75e-111">监视数据库的状态</span><span class="sxs-lookup"><span data-stu-id="7c75e-111">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="7c75e-112">监视在数据库中，按 %或 MB 可配置的可用空间</span><span class="sxs-lookup"><span data-stu-id="7c75e-112">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="7c75e-113">确保数据库已正确配置</span><span class="sxs-lookup"><span data-stu-id="7c75e-113">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="7c75e-114">确保客户端可以连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c75e-114">Ensure clients can connect to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="7c75e-115">监视阻塞的进程</span><span class="sxs-lookup"><span data-stu-id="7c75e-115">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="7c75e-116">观看有关失败的代理程序作业和作业需要的过多的时间才能执行</span><span class="sxs-lookup"><span data-stu-id="7c75e-116">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="7c75e-117">监视复制和失败的警报的运行状况</span><span class="sxs-lookup"><span data-stu-id="7c75e-117">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="7c75e-118">监视数据库镜像的状态</span><span class="sxs-lookup"><span data-stu-id="7c75e-118">Monitor the state of Database Mirroring</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c75e-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="7c75e-119">In This Section</span></span>  
  
-   [<span data-ttu-id="7c75e-120">监视 SQL Server 代理作业和数据库</span><span class="sxs-lookup"><span data-stu-id="7c75e-120">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="7c75e-121">如何将 BizTalk Server 数据库标记为自定义监视</span><span class="sxs-lookup"><span data-stu-id="7c75e-121">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="7c75e-122">监视 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7c75e-122">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)