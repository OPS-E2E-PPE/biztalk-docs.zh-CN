---
title: BizTalk Server 日志传送使用 Windows 群集名称和 IP 地址 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2696f608f13244d5f00922b01d9e069a0ad6268d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401062"
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a><span data-ttu-id="d653e-102">BizTalk Server 日志传送使用 Windows 群集名称和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d653e-102">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>
<span data-ttu-id="d653e-103">可以简化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用两个实例的日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集中的源和目标服务器作为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送方案。</span><span class="sxs-lookup"><span data-stu-id="d653e-103">It is possible to simplify [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two instances of a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster as the source and destination servers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping scenario.</span></span> <span data-ttu-id="d653e-104">然后，发生灾难恢复时，发生数据库恢复简化通过只切换的名称和与群集关联的 IP 地址资源[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例如下所述。</span><span class="sxs-lookup"><span data-stu-id="d653e-104">Then, in the event of a disaster recovery event, database recovery is simplified by merely switching the name and IP address resources associated with the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances as described below.</span></span> <span data-ttu-id="d653e-105">使用此方法时无需运行 UpdateDatabase.vbs 脚本，如本主题中所述[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)因为数据库名称保持不变。</span><span class="sxs-lookup"><span data-stu-id="d653e-105">When using this approach there is no need to run the UpdateDatabase.vbs script as described in the topic [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) because the database name is unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d653e-106">若要提高容错能力的聚集[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例，聚集[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应地理位置上相隔实例。</span><span class="sxs-lookup"><span data-stu-id="d653e-106">To increase fault tolerance for the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances, the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances should be geographically separated.</span></span>  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a><span data-ttu-id="d653e-107">若要实现 BizTalk Server 日志传送，它使用 Windows Server 群集名称和 IP 地址资源</span><span class="sxs-lookup"><span data-stu-id="d653e-107">To implement BizTalk Server log shipping using a Windows Server Cluster name and IP address resource</span></span>  
  
1. <span data-ttu-id="d653e-108">停止生产 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="d653e-108">Stop the production BizTalk servers.</span></span>  
  
2. <span data-ttu-id="d653e-109">执行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送还原到辅助数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="d653e-109">Perform a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping restore to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  
  
3. <span data-ttu-id="d653e-110">请按照主题中所述的步骤[配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)若要重新配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，以便辅助[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例现在是源组和主[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例现在是目标组。</span><span class="sxs-lookup"><span data-stu-id="d653e-110">Follow the steps described in the topic [Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) to reconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping so that the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the source group and the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the destination group.</span></span>  
  
4. <span data-ttu-id="d653e-111">停止 IP 和网络名称资源 PublicSQLClustername 主[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例。</span><span class="sxs-lookup"><span data-stu-id="d653e-111">Stop the IP and network name resource PublicSQLClustername on the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
5. <span data-ttu-id="d653e-112">配置并在辅助副本上启动 PublicSQLClustername IP 和网络名称群集资源[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例。</span><span class="sxs-lookup"><span data-stu-id="d653e-112">Configure and start the PublicSQLClustername IP and network name cluster resources on the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
6. <span data-ttu-id="d653e-113">启动生产 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="d653e-113">Start the production BizTalk servers.</span></span>  
  
7. <span data-ttu-id="d653e-114">验证日志传送还原。</span><span class="sxs-lookup"><span data-stu-id="d653e-114">Verify the log-shipping restore.</span></span>  
  
8. <span data-ttu-id="d653e-115">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]相关的生产站点上的服务。</span><span class="sxs-lookup"><span data-stu-id="d653e-115">Start [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related services on the production site.</span></span>  
  
   <span data-ttu-id="d653e-116">执行这些步骤后，BizTalk 组指向辅助[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="d653e-116">After performing these steps, the BizTalk group is pointing to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance as illustrated in the following figure.</span></span>  
  
   <span data-ttu-id="d653e-117">下图说明了如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用两个群集的实例的日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和移动群集的名称和 IP 地址资源。</span><span class="sxs-lookup"><span data-stu-id="d653e-117">The following figure illustrates how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two clustered instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and moving the clustered name and IP address resource.</span></span>  
  
   <span data-ttu-id="d653e-118">![使用群集名称和 IP 的 BizTalk 日志传送](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span><span class="sxs-lookup"><span data-stu-id="d653e-118">![BizTalk Log Shipping using a Cluster name and IP](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span></span>  
  
   <span data-ttu-id="d653e-119">**BizTalk Server 日志传送的实现，使用 Windows Server 群集的名称和 IP 地址资源**</span><span class="sxs-lookup"><span data-stu-id="d653e-119">**BizTalk Server Log Shipping implementation using Windows Server cluster name and IP address resources**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d653e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d653e-120">See Also</span></span>  
 <span data-ttu-id="d653e-121">[数据库的高可用性](../technical-guides/high-availability-for-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d653e-121">[High Availability for Databases](../technical-guides/high-availability-for-databases.md) </span></span>  
 <span data-ttu-id="d653e-122">[配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="d653e-122">[Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) </span></span>  
 [<span data-ttu-id="d653e-123">如何在备份 BizTalk Server 作业中还原数据库</span><span class="sxs-lookup"><span data-stu-id="d653e-123">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)