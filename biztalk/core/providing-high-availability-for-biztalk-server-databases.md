---
title: 有关 BizTalk Server 数据库提供高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- databases, architecture
- SQL Server, clustering
- servers, clustering
- databases, high availability
- architecture
- databases, clustering
- BizTalk Server, architecture
- Windows clustering
- high availability, databases
- clustering, databases
- data, persistence
- SQL Server Analysis Services
ms.assetid: 47fbc402-9e46-41dd-bc12-d1cde1982576
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0505691eafa6a6cf2215282635c303a55e9b1ce8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398422"
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a><span data-ttu-id="7ac62-102">为 BizTalk Server 数据库提供高可用性</span><span class="sxs-lookup"><span data-stu-id="7ac62-102">Providing High Availability for BizTalk Server Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7ac62-103">很大程度上依赖于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实现数据持久性。</span><span class="sxs-lookup"><span data-stu-id="7ac62-103">relies heavily on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] for data persistence.</span></span> <span data-ttu-id="7ac62-104">所有其他组件和中的主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有特定的角色过程中集成完全不同的业务应用程序 （例如，接收、 处理或路由消息），只有数据库计算机捕获此工作并将其保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="7ac62-104">All other components and hosts in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific roles in the process of integrating disparate business applications (for example, receiving, processing, or routing messages), but the database computer captures this work and persists it to disk.</span></span>  
  
 <span data-ttu-id="7ac62-105">若要提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，使用 Windows Server 故障转移群集来配置运行 SQL Server 创建服务器群集的两个数据库计算机。</span><span class="sxs-lookup"><span data-stu-id="7ac62-105">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, use Windows Server Failover Clustering to configure two database computers that are running SQL Server to create a server cluster.</span></span> <span data-ttu-id="7ac62-106">服务器群集提供冗余和容错能力的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="7ac62-106">Server clustering provides redundancy and fault tolerance for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="7ac62-107">与负载平衡群集，不同的一组计算机共同作用以提高可用性和可伸缩性、 服务器群集通常涉及对数据库中的计算机的主动/被动配置，因此这一台计算机将提供备份对于其他资源。</span><span class="sxs-lookup"><span data-stu-id="7ac62-107">Unlike load-balanced clustering, where a group of computers functions together to increase availability and scalability, server clustering typically involves a pair of database computers in an active/passive configuration so that one computer provides backup resources for the other.</span></span>  
  
 <span data-ttu-id="7ac62-108">下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过主动/被动服务器群集的高可用性的数据库层。</span><span class="sxs-lookup"><span data-stu-id="7ac62-108">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tier with high availability through active/passive server clustering.</span></span>  
  
 <span data-ttu-id="7ac62-109">![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="7ac62-109">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="7ac62-110">如果主动数据库计算机遇到错误或失败，被动计算机将变为活动状态，并假定对数据库资源的控制，直到修复失败的计算机。</span><span class="sxs-lookup"><span data-stu-id="7ac62-110">If the active database computer encounters errors or fails, the passive computer becomes active and assumes control over the database resources until the failed computer is repaired.</span></span> <span data-ttu-id="7ac62-111">数据库服务故障转移和恢复到新的主动计算机的数据连接，并使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序继续运行。</span><span class="sxs-lookup"><span data-stu-id="7ac62-111">The database service fails over and restores data connections to the new active computer and enables the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application to continue functioning.</span></span>  
  
 <span data-ttu-id="7ac62-112">有关信息的数据库的情况下安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac62-112">For information about the databases that are installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="7ac62-113">有关备份您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac62-113">For information about backing up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ac62-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="7ac62-114">In This Section</span></span>  
  
-   [<span data-ttu-id="7ac62-115">横向扩展数据库</span><span class="sxs-lookup"><span data-stu-id="7ac62-115">Scaled-Out Databases</span></span>](../core/scaled-out-databases.md)  
  
-   [<span data-ttu-id="7ac62-116">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7ac62-116">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [<span data-ttu-id="7ac62-117">SQL Server 故障转移期间 BizTalk Server 主机实例在的行为</span><span class="sxs-lookup"><span data-stu-id="7ac62-117">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [<span data-ttu-id="7ac62-118">SQL Server 数据库镜像、卷影复制服务和 AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7ac62-118">SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn</span></span>](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ac62-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac62-119">See Also</span></span>  
 <span data-ttu-id="7ac62-120">[为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="7ac62-120">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="7ac62-121">BizTalk Server 高可用性示例方案</span><span class="sxs-lookup"><span data-stu-id="7ac62-121">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)