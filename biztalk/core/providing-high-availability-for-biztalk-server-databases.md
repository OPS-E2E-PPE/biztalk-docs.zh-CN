---
title: BizTalk Server 数据库提供高可用性 |Microsoft 文档
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
ms.openlocfilehash: 3648a8f6d48bbfd6cf67995e1d314511b70db7bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269341"
---
# <a name="providing-high-availability-for-biztalk-server-databases"></a><span data-ttu-id="bacd8-102">为 BizTalk Server 数据库提供高可用性</span><span class="sxs-lookup"><span data-stu-id="bacd8-102">Providing High Availability for BizTalk Server Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bacd8-103">很大程度上依赖[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实现数据持久性。</span><span class="sxs-lookup"><span data-stu-id="bacd8-103"> relies heavily on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] for data persistence.</span></span> <span data-ttu-id="bacd8-104">在将完全不同的业务应用程序（例如，接收、处理或路由消息）相集成的过程中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的其他所有组件和主机都具有特定的角色，只有数据库计算机会捕获此工作并将其保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="bacd8-104">All other components and hosts in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific roles in the process of integrating disparate business applications (for example, receiving, processing, or routing messages), but the database computer captures this work and persists it to disk.</span></span>  
  
 <span data-ttu-id="bacd8-105">若要提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，使用 Windows Server 故障转移群集配置运行 SQL Server 创建服务器群集的两个数据库计算机。</span><span class="sxs-lookup"><span data-stu-id="bacd8-105">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, use Windows Server Failover Clustering to configure two database computers that are running SQL Server to create a server cluster.</span></span> <span data-ttu-id="bacd8-106">服务器群集为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库提供冗余和容错功能。</span><span class="sxs-lookup"><span data-stu-id="bacd8-106">Server clustering provides redundancy and fault tolerance for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="bacd8-107">与负载平衡群集（其中一组计算机共同作用以提高可用性和可伸缩性）不同，服务器群集通常只包含两台采用主动/被动配置的数据库计算机，以便其中一台计算机可为另一台计算机提供备份资源。</span><span class="sxs-lookup"><span data-stu-id="bacd8-107">Unlike load-balanced clustering, where a group of computers functions together to increase availability and scalability, server clustering typically involves a pair of database computers in an active/passive configuration so that one computer provides backup resources for the other.</span></span>  
  
 <span data-ttu-id="bacd8-108">下图显示了通过主动/被动服务器群集确保其高度可用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库层。</span><span class="sxs-lookup"><span data-stu-id="bacd8-108">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tier with high availability through active/passive server clustering.</span></span>  
  
 <span data-ttu-id="bacd8-109">![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="bacd8-109">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="bacd8-110">如果主动数据库计算机遇到错误或失败，则被动计算机将变为主动并承担对数据库资源的控制，直至修复该出错的计算机。</span><span class="sxs-lookup"><span data-stu-id="bacd8-110">If the active database computer encounters errors or fails, the passive computer becomes active and assumes control over the database resources until the failed computer is repaired.</span></span> <span data-ttu-id="bacd8-111">数据库服务将进行故障转移，并恢复与新的主动计算机的数据连接，然后启用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序继续运行。</span><span class="sxs-lookup"><span data-stu-id="bacd8-111">The database service fails over and restores data connections to the new active computer and enables the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application to continue functioning.</span></span>  
  
 <span data-ttu-id="bacd8-112">有关安装的数据库信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="bacd8-112">For information about the databases that are installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="bacd8-113">有关备份你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="bacd8-113">For information about backing up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bacd8-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="bacd8-114">In This Section</span></span>  
  
-   [<span data-ttu-id="bacd8-115">向外扩展的数据库</span><span class="sxs-lookup"><span data-stu-id="bacd8-115">Scaled-Out Databases</span></span>](../core/scaled-out-databases.md)  
  
-   [<span data-ttu-id="bacd8-116">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bacd8-116">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)  
  
-   [<span data-ttu-id="bacd8-117">在 SQL Server 故障转移期间的 BizTalk Server 主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="bacd8-117">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)  
  
-   [<span data-ttu-id="bacd8-118">SQL Server 数据库镜像，卷影复制服务和 AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="bacd8-118">SQL Server database mirroring, Volume Shadow Copy service and AlwaysOn</span></span>](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
  
## <a name="see-also"></a><span data-ttu-id="bacd8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bacd8-119">See Also</span></span>  
 <span data-ttu-id="bacd8-120">[为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="bacd8-120">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="bacd8-121">示例 BizTalk Server 高可用性方案</span><span class="sxs-lookup"><span data-stu-id="bacd8-121">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)