---
title: "清除目标环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4023492bf79223b3ba6b1db5cedebadf88feb9c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cleaning-the-destination-environment"></a><span data-ttu-id="a5171-102">清除目标环境</span><span class="sxs-lookup"><span data-stu-id="a5171-102">Cleaning the Destination Environment</span></span>
<span data-ttu-id="a5171-103">如果还原作业遇到无法解决的错误条件，清除目标环境，以便它可以开始从空环境。</span><span class="sxs-lookup"><span data-stu-id="a5171-103">If the restore job encounters error conditions that cannot be resolved, clean the destination environment so that it can start from an empty environment.</span></span> <span data-ttu-id="a5171-104">运行存储的过程**sp_LogShippingClean**位于目标上的 master 数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例将"清理"目标环境。</span><span class="sxs-lookup"><span data-stu-id="a5171-104">Running the stored procedure **sp_LogShippingClean** located in the master database on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance will “clean” the destination environment.</span></span> <span data-ttu-id="a5171-105">此过程将删除所有数据库，并删除指定的源中最后一个的还原的数据集。</span><span class="sxs-lookup"><span data-stu-id="a5171-105">This procedure drops all databases and deletes the last restored data set for the specified source.</span></span>  
  
 <span data-ttu-id="a5171-106">在运行此过程之前, 禁用**BTS 日志传送的还原数据库**（get 备份历史记录作业可能继续运行） 的作业。</span><span class="sxs-lookup"><span data-stu-id="a5171-106">Before running this procedure, disable the **BTS Log Shipping - Restore Databases** job (the get backup history job may continue running).</span></span> <span data-ttu-id="a5171-107">有关禁用**BTS 日志传送的还原数据库**作业，请参阅[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="a5171-107">For more information about disabling the **BTS Log Shipping - Restore Databases** job see [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="a5171-108">后**sp_LogShippingClean**运行过程，在还原作业运行的下一步时，它将查找设置与有效的后续日志备份集的最新完整备份。</span><span class="sxs-lookup"><span data-stu-id="a5171-108">After the **sp_LogShippingClean** procedure is run, the next time the restore job runs it will find the most recent full backup set with a valid subsequent log backup set.</span></span> <span data-ttu-id="a5171-109">如果此集已还原，还原作业清除**还原**设置和所有后续列设置，然后在继续使用还原的集。</span><span class="sxs-lookup"><span data-stu-id="a5171-109">If this set has already been restored, the restore job clears the **Restored** column for the set and all subsequent sets and then proceeds with restoring the set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5171-110">作业会查找最新完整备份后环境已清理设置，因为强制源系统上的完整备份，运行此过程之后但在之前运行还原作业。</span><span class="sxs-lookup"><span data-stu-id="a5171-110">Because the job looks for the most recent full backup set after the environment has been cleaned, force a full backup on the source system after running this procedure but before running the restore job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5171-111">**Sp_LogShippingClean**必须还原给定的源系统的数据库，以使不同的服务器已根据其应用集相互同步的所有服务器上重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a5171-111">The **sp_LogShippingClean** procedure must be repeated on all servers that are restoring databases for a given source system in order to keep the different servers in synch with each other in terms of which sets have been applied.</span></span>  
  
 <span data-ttu-id="a5171-112">若要运行**sp_LogShippingClean**过程中，连接到 master 数据库上所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例属于的灾难恢复站点，并执行以下命令在**新查询**中提供的选项[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 为每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例：</span><span class="sxs-lookup"><span data-stu-id="a5171-112">To run the **sp_LogShippingClean** procedure, connect to the master database on all [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances that are part of the disaster recovery site and execute the following command in the **New Query** option available in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio for each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance:</span></span>  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 <span data-ttu-id="a5171-113">其中**SourceID**对应于对生产配置的标识符[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="a5171-113">where **SourceID** corresponds to the identifier configured on the production [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5171-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5171-114">See Also</span></span>  
 [<span data-ttu-id="a5171-115">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="a5171-115">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)