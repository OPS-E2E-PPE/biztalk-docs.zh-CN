---
title: 清单：备份和还原 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3233d941e17e23e07895586b711d47ee86cdc15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357456"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a>清单：备份和还原 BizTalk Server 数据库
然后再尝试备份或还原 BizTalk Server，请务必熟悉所涉及的过程。  
  
## <a name="backing-up-biztalk-server"></a>备份 BizTalk Server  
  
|步骤|参考|  
|----------|---------------|  
|了解如何备份和还原 BizTalk Server。|[备份和还原数据库的最佳做法](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|请确保您具有相应的权限来备份和还原 BizTalk Server。|[最低安全用户权限](../core/minimum-security-user-rights.md)|  
|配置备份 BizTalk Server 作业。|[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|配置存储备份的服务器。|[如何配置日志传送目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|如果使用业务活动监视 (BAM)，备份 BAM 数据库。|[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)|  
|如果使用企业单一登录，请备份主密钥。|[管理主密钥](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a>还原 BizTalk Server  
  
|步骤|参考|  
|----------|---------------|  
|还原数据库。|[如何还原数据库](../core/how-to-restore-your-databases.md)|  
|更新对 BAM 数据库名称的引用。|[如何备份 BAM 分析和跟踪分析服务器数据库](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [如何更新对 BAM 分析服务器和星型架构数据库名称的引用](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [如何更新对 BAM 存档数据库名称的引用](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [如何更新对 BAM 主导入数据库名称和连接字符串引用](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [如何更新对 BAM Notification Services 数据库](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [如何解析不完整的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)|  
|如果使用企业单一登录，则还原主密钥。|[管理主密钥](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)