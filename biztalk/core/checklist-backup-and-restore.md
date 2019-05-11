---
title: 清单：备份和还原 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1d46a59-54f9-483e-9290-f4a9461006a7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36580fea0389431cc590d44312c026261eb9dfef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357427"
---
# <a name="checklist-backup-and-restore"></a>清单：备份和还原
在您有硬件故障，以确保可以还原 BizTalk Server 系统之前，请执行以下步骤。  
  
## <a name="back-up-biztalk-server"></a>备份 BizTalk Server  
  
|步骤|参考|  
|----------|---------------|  
|为 BizTalk Server 系统保留的所有更改的书面的记录。||  
|请确保您具有相应的权限来备份和还原 BizTalk Server。|[最低安全用户权限](../core/minimum-security-user-rights.md)|  
|了解如何备份和还原 BizTalk Server 数据库。|[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|配置备份 BizTalk Server 作业备份 BizTalk Server 数据库。|[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|配置存储数据库备份的服务器。|[如何配置日志传送目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|如果使用业务活动监视 (BAM)，备份 BAM 数据库。|[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)|  
|如果使用企业单一登录 (SSO)，备份主密钥。|[管理主密钥](../core/managing-the-master-secret.md)|  
|备份 BizTalk Server 配置文件。|[如何备份 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)|  
|备份企业单一登录主密钥。|[如何备份主密钥](../core/how-to-back-up-the-master-secret.md)|  
|备份 BAM 门户的应用程序池和虚拟目录配置信息。 如果您没有使用 BAM，您不需要执行此步骤。|[如何备份 BAM 门户](../core/how-to-back-up-the-bam-portal.md)|  
|备份 BizTalk 应用程序。|[备份 BizTalk Server 应用程序](../core/backing-up-biztalk-server-applications.md)|  
  
## <a name="restore-biztalk-server"></a>还原 BizTalk Server  
  
|步骤|参考|  
|----------|---------------|  
|还原数据库。|[如何还原数据库](../core/how-to-restore-your-databases.md)|  
|更新对 BAM 数据库名称的引用。|[如何备份 BAM 分析和跟踪分析服务器数据库](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [如何更新对 BAM 分析服务器和星型架构数据库名称的引用](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [如何更新对 BAM 存档数据库名称的引用](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [如何更新对 BAM 主导入数据库名称和连接字符串引用](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [如何更新对 BAM Notification Services 数据库](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [如何解析不完整的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)|  
|如果使用企业单一登录，则还原主密钥。|[管理主密钥](../core/managing-the-master-secret.md)|  
|如果运行 BizTalk Server 的计算机出现故障，则在替代计算机上安装 BizTalk Server。|[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)|  
|还原证书存储区。<br /><br /> 此步骤是必需的标准版。 它不需要的其他版本，如 Enterprise Edition 中，因为配置过程自动执行此操作。|[如何还原证书存储区](../core/how-to-restore-the-certificate-store.md)|  
|还原企业单一登录|[如何恢复企业单一登录](../core/how-to-recover-enterprise-single-sign-on.md)|  
|还原 BizTalk 组|[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)<br /><br /> 如果要还原标准版，你必须下载一个有助于恢复服务器脚本。 下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。|  
|还原 BizTalk Server 配置|[如何恢复 BizTalk Server 配置](../core/how-to-recover-the-biztalk-server-configuration.md)|  
|如果在使用 BAM，则应该还原 BAM 警报。<br /><br /> 如果您没有使用 BAM，您不需要执行此步骤。|[如何恢复 BAM 警报](../core/how-to-recover-bam-alerts.md)|  
|如果在使用 BAM，则应该还原 BAM 门户。<br /><br /> 如果您没有使用 BAM，您不需要执行此步骤。|[如何恢复 BAM 门户](../core/how-to-recover-the-bam-portal.md)|  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)
