---
title: "查看历史记录将备份还原 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa5a7fbe2b0e731920880570b0555402ba162c7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-the-history-of-restored-backups"></a>查看已还原备份的历史记录
若要确定最近成功还原的备份集，请查看 Master.dbo.bts_LogShippingHistory 表的内容。 此表由获取备份历史记录作业来填充，由还原数据库作业来更新。 如果备份还原成功，则 Restored 列将设为 1，RestoredDateTime 将设为当前日期和时间。  
  
 成功还原了所有要从特定备份集还原到服务器的数据库后，该备份集 ID 将被写入 Master.dbo.bts_LogShippingLastRestoreSet 表。  
  
## <a name="gaps-in-the-restore-process"></a>还原过程中的间隔  
 在 Master.dbo.bts_LogShippingHistory 表中查看记录时，可能会发现还原的备份集中存在间隔。 这可能由多种原因引起。 但是，即使出现间隔，仍可恢复目标系统（即备份计算机）的稳定性。 必须在出现间隔后进行完整备份集的还原以修复目标系统。 如果在出现间隔后不进行完整备份集的还原，则目标环境将是不稳定的。  
  
> [!NOTE]
>  仅在重新创建数据库以及修复日志历史记录备份链中的问题时，才需要还原完整备份。 多数情况下，并不还原完整备份集，因为它们不是日志备份链的一部分。  
  
## <a name="see-also"></a>另请参阅  
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)