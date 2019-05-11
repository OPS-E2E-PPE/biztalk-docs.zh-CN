---
title: 备份数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0524a8f0-15a3-4731-a7bd-c0c935fff6c8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a521e88aed552bf25450cabd1dee98b508da5953
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401312"
---
# <a name="backing-up-databases"></a>备份数据库
因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用分布式事务跨多个数据库，备份 BizTalk Server 作业创建的所有同步的备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 这是通过使用标记的事务与"完全"数据库恢复模型实现的。 这是需要在数据库保持事务上一致的备份。 有关详细信息，请参阅["标记的事务、 完整备份和日志备份"](http://go.microsoft.com/fwlink/?LinkId=151565) (<http://go.microsoft.com/fwlink/?LinkId=151565>) 中的 BizTalk Server 文档。  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>备份 BizTalk Server 作业的优点  
 备份 BizTalk Server 作业是唯一受支持的备份方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 利用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]作业，以备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持在生产环境中的数据库。  
  
 如果备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不运行作业时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库事务日志将无限增长。 备份作业会截断事务日志，使其无限制地增加。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库事务日志不断增大，它们会在某个时候被填它们存储在的磁盘。  
  
> [!NOTE]
>  使用这两个备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业和日志传送是当前唯一完全记录和执行支持方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份和还原。  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>备份 BizTalk Server 作业的准则  
 应还原整个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]定期的环境。 这包括不仅的 SQL 服务器和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，但还运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 应记录并实际上发生故障之前练习这些过程。  
  
> [!NOTE]
>  备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业不会删除旧备份文件。 必须定义并采取的措施，存档旧的备份文件，并将它们从备份作业将使用的备份目录移动进程。  
  
## <a name="additional-resources"></a>其他资源  
 请参阅中的以下主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档：  
  
- 详细了解特定于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]备份和还原任务，请参阅["核对清单：备份和还原"](http://go.microsoft.com/fwlink/?LinkId=154070) (<http://go.microsoft.com/fwlink/?LinkId=154070>)。  
  
- 有关的备份和还原概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅["备份和还原 BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=154071) (<http://go.microsoft.com/fwlink/?LinkId=154071>)。  
  
- 有关配置备份 BizTalk Server 作业的详细信息，请参阅["如何向配置备份 BizTalk Server 作业"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072)。  
  
## <a name="see-also"></a>请参阅  
 [为灾难恢复使用 BizTalk Server 日志传送](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)