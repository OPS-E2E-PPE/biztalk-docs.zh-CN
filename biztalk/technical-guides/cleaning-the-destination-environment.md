---
title: 清除目标环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd24df50cd4c29dacbd9f8830f6851abdb8ed354
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397062"
---
# <a name="cleaning-the-destination-environment"></a><span data-ttu-id="3a503-102">清除目标环境</span><span class="sxs-lookup"><span data-stu-id="3a503-102">Cleaning the Destination Environment</span></span>
<span data-ttu-id="3a503-103">如果还原作业遇到无法解决的错误条件，清理目标环境，以便它可以启动从空的环境。</span><span class="sxs-lookup"><span data-stu-id="3a503-103">If the restore job encounters error conditions that cannot be resolved, clean the destination environment so that it can start from an empty environment.</span></span> <span data-ttu-id="3a503-104">运行存储的过程**sp_LogShippingClean**位于目标上的 master 数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例将"干净"的目标环境。</span><span class="sxs-lookup"><span data-stu-id="3a503-104">Running the stored procedure **sp_LogShippingClean** located in the master database on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance will “clean” the destination environment.</span></span> <span data-ttu-id="3a503-105">此过程将删除所有数据库，并删除指定的源已还原的最后一个数据集。</span><span class="sxs-lookup"><span data-stu-id="3a503-105">This procedure drops all databases and deletes the last restored data set for the specified source.</span></span>  
  
 <span data-ttu-id="3a503-106">然后再运行此过程，禁用**BTS 日志传送-还原数据库**（获取备份历史记录作业可能会继续运行） 的作业。</span><span class="sxs-lookup"><span data-stu-id="3a503-106">Before running this procedure, disable the **BTS Log Shipping - Restore Databases** job (the get backup history job may continue running).</span></span> <span data-ttu-id="3a503-107">有关禁用的详细信息**BTS 日志传送-还原数据库**作业，请参阅[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="3a503-107">For more information about disabling the **BTS Log Shipping - Restore Databases** job see [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="3a503-108">之后**sp_LogShippingClean**运行过程，在下次运行还原作业时它将查找与有效的后续日志备份集设置的最新完整备份。</span><span class="sxs-lookup"><span data-stu-id="3a503-108">After the **sp_LogShippingClean** procedure is run, the next time the restore job runs it will find the most recent full backup set with a valid subsequent log backup set.</span></span> <span data-ttu-id="3a503-109">如果此集已还原，还原作业将清除**还原**用于设置和所有后续列设置，再继续还原设置。</span><span class="sxs-lookup"><span data-stu-id="3a503-109">If this set has already been restored, the restore job clears the **Restored** column for the set and all subsequent sets and then proceeds with restoring the set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a503-110">该作业会查找后清理环境设置的最新完整备份，因为源系统上强制完整备份运行此过程之后但在之前运行还原作业。</span><span class="sxs-lookup"><span data-stu-id="3a503-110">Because the job looks for the most recent full backup set after the environment has been cleaned, force a full backup on the source system after running this procedure but before running the restore job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a503-111">**Sp_LogShippingClean**必须还原为给定的源系统的数据库以使不同的服务器已在这方面应用集相互同步的所有服务器上重复此过程。</span><span class="sxs-lookup"><span data-stu-id="3a503-111">The **sp_LogShippingClean** procedure must be repeated on all servers that are restoring databases for a given source system in order to keep the different servers in synch with each other in terms of which sets have been applied.</span></span>  
  
 <span data-ttu-id="3a503-112">若要运行**sp_LogShippingClean**过程中，连接到 master 数据库上所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例属于的灾难恢复站点，并执行以下命令中的**新查询**中可用的选项[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 为每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例：</span><span class="sxs-lookup"><span data-stu-id="3a503-112">To run the **sp_LogShippingClean** procedure, connect to the master database on all [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances that are part of the disaster recovery site and execute the following command in the **New Query** option available in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio for each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance:</span></span>  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 <span data-ttu-id="3a503-113">其中**SourceID**对应于在生产环境上配置的标识符[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="3a503-113">where **SourceID** corresponds to the identifier configured on the production [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a503-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a503-114">See Also</span></span>  
 [<span data-ttu-id="3a503-115">日志传送疑难解答</span><span class="sxs-lookup"><span data-stu-id="3a503-115">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)