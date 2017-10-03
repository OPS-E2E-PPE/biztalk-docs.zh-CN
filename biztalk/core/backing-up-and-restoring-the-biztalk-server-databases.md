---
title: "备份和还原的 BizTalk Server 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a>备份和还原的 BizTalk Server 数据库
本部分提供有关如何备份和还原 BizTalk Server 数据库的信息。 请按照本部分中的过程进行操作，以确保在发生硬件故障时能够还原出一致的 BizTalk Server 环境。 由于 BizTalk Server 在各数据库中执行分布式事务，所以应先备份所有数据库，然后再还原所有数据库，这是很关键的。  
  
 BizTalk Server 要求执行自定义备份过程，该过程使用完整数据库备份、日志备份以及事务性日志标记。 有关此过程的信息，请参阅[标记的事务、 完整备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单： 备份和还原 BizTalk Server 数据库](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [备份和还原数据库的最佳实践](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)  
  
-   [解决数据丢失](../core/resolving-data-loss.md)  
  
-   [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)