---
title: 更新到 BAM 主导入数据库的引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301821"
---
# <a name="update-references-to-the-bam-primary-import-database"></a>更新到 BAM 主导入数据库的引用
如果备份出现系统或数据故障时你 BAM 主导入数据库时，你可以将该备份还原到另一台计算机，并重命名备份。  
  
 BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAM 主导入数据库。 BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。 有关与 BAM 事件总线服务的详细信息，请参阅主题[管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。  
  
 若要还原 BAM 主导入数据库，执行中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。 此外，你必须使用新的服务器名称和数据库名称来更新 BAM SSIS 包。  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a>如何更新对 BAM 主导入数据库的引用  
 有关如何更新 BAM 主导入数据库，对引用的说明[更新到新的 BAM 主导入数据库的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)。  
  
## <a name="see-also"></a>另请参阅  
 [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)