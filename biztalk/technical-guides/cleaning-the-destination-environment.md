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
# <a name="cleaning-the-destination-environment"></a>清除目标环境
如果还原作业遇到无法解决的错误条件，清理目标环境，以便它可以启动从空的环境。 运行存储的过程**sp_LogShippingClean**位于目标上的 master 数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例将"干净"的目标环境。 此过程将删除所有数据库，并删除指定的源已还原的最后一个数据集。  
  
 然后再运行此过程，禁用**BTS 日志传送-还原数据库**（获取备份历史记录作业可能会继续运行） 的作业。 有关禁用的详细信息**BTS 日志传送-还原数据库**作业，请参阅[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。 之后**sp_LogShippingClean**运行过程，在下次运行还原作业时它将查找与有效的后续日志备份集设置的最新完整备份。 如果此集已还原，还原作业将清除**还原**用于设置和所有后续列设置，再继续还原设置。  
  
> [!NOTE]  
>  该作业会查找后清理环境设置的最新完整备份，因为源系统上强制完整备份运行此过程之后但在之前运行还原作业。  
  
> [!NOTE]  
>  **Sp_LogShippingClean**必须还原为给定的源系统的数据库以使不同的服务器已在这方面应用集相互同步的所有服务器上重复此过程。  
  
 若要运行**sp_LogShippingClean**过程中，连接到 master 数据库上所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例属于的灾难恢复站点，并执行以下命令中的**新查询**中可用的选项[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 为每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例：  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 其中**SourceID**对应于在生产环境上配置的标识符[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
## <a name="see-also"></a>请参阅  
 [日志传送疑难解答](../technical-guides/troubleshooting-log-shipping.md)