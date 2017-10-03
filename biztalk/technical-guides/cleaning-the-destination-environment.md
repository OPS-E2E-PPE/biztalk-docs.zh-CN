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
# <a name="cleaning-the-destination-environment"></a>清除目标环境
如果还原作业遇到无法解决的错误条件，清除目标环境，以便它可以开始从空环境。 运行存储的过程**sp_LogShippingClean**位于目标上的 master 数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例将"清理"目标环境。 此过程将删除所有数据库，并删除指定的源中最后一个的还原的数据集。  
  
 在运行此过程之前, 禁用**BTS 日志传送的还原数据库**（get 备份历史记录作业可能继续运行） 的作业。 有关禁用**BTS 日志传送的还原数据库**作业，请参阅[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。 后**sp_LogShippingClean**运行过程，在还原作业运行的下一步时，它将查找设置与有效的后续日志备份集的最新完整备份。 如果此集已还原，还原作业清除**还原**设置和所有后续列设置，然后在继续使用还原的集。  
  
> [!NOTE]  
>  作业会查找最新完整备份后环境已清理设置，因为强制源系统上的完整备份，运行此过程之后但在之前运行还原作业。  
  
> [!NOTE]  
>  **Sp_LogShippingClean**必须还原给定的源系统的数据库，以使不同的服务器已根据其应用集相互同步的所有服务器上重复此过程。  
  
 若要运行**sp_LogShippingClean**过程中，连接到 master 数据库上所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例属于的灾难恢复站点，并执行以下命令在**新查询**中提供的选项[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 为每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例：  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 其中**SourceID**对应于对生产配置的标识符[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)