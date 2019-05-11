---
title: 备份和还原 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6fbf2bfec008d48623aa5238d1208d55460f0cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358672"
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a>备份和还原 BizTalk Server 数据库
本部分提供有关如何备份和还原 BizTalk Server 数据库的信息。 应遵循此部分以确保能够还原出现硬件故障一致的 BizTalk Server 环境中的过程。 BizTalk Server 在数据库之间执行分布式的事务，因此很关键备份，然后还原所有数据库。  
  
 BizTalk Server 需要使用完整数据库备份和日志备份一起使用以及事务性日志标记的自定义备份进程。 有关此过程的信息，请参阅[标记的事务、 完整备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单：备份和还原 BizTalk Server 数据库](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [备份和还原数据库的最佳做法](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)  
  
-   [解决数据丢失问题](../core/resolving-data-loss.md)  
  
-   [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)