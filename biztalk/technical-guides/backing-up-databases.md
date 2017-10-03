---
title: "备份数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0524a8f0-15a3-4731-a7bd-c0c935fff6c8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6a4b40be0a9a7d4846dd965a4d9f934e69690e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-databases"></a>备份数据库
因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用分布式事务跨多个数据库，备份 BizTalk Server 作业创建的所有同步的备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 这可以通过使用"完整"数据库恢复模式的事务进行标记。 这是必需的可以跨数据库事务上一致的备份。 有关详细信息，请参阅["标记的事务，完整备份和日志备份"](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565) BizTalk Server 文档中。  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>备份 BizTalk Server 作业的优点  
 备份 BizTalk Server 作业是唯一受支持的备份方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 利用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]作业，以备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持在生产环境中的数据库。  
  
 如果备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不运行作业时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库事务日志将会增长不受限制。 备份作业将截断事务日志，这使它们保持无限增长。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库事务日志不断增长，它们无法在某一时刻填它们驻留在该磁盘。  
  
> [!NOTE]  
>  使用这两个备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业和日志传送是当前唯一完全记录和支持方法执行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份和还原。  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>备份 BizTalk 服务器作业的准则  
 你应还原整个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]定期的环境。 这包括不仅的 SQL server 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，但还运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 你应记录并实际发生故障之前执行这些过程。  
  
> [!NOTE]  
>  备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业不会删除旧的备份文件。 必须定义并将进程来存档旧的备份文件，并将它们从备份作业使用的备份目录移动。  
  
## <a name="additional-resources"></a>其他资源  
 请参阅中的以下主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档：  
  
-   有关特定详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]备份和还原任务，请参阅["清单:: 备份和还原"](http://go.microsoft.com/fwlink/?LinkId=154070) (http://go.microsoft.com/fwlink/?LinkId=154070)。  
  
-   有关备份和还原的概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅["Backing Up 和还原 BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=154071) (http://go.microsoft.com/fwlink/?LinkId=154071)。  
  
-   有关配置 BizTalk Server 中备份作业的详细信息，请参阅["如何为配置备份 BizTalk Server 作业"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 日志传送以实现灾难恢复](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)