---
title: "清单： 备份和还原 |Microsoft 文档"
ms.custom: 
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1d46a59-54f9-483e-9290-f4a9461006a7
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b872582cd0ad9f882dd04f641575bae9636bad
ms.sourcegitcommit: d0a1816a8dd8412906245d40c6479b08d7b3b20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="checklist-backup-and-restore"></a>清单： 备份和还原
在发生硬件故障之前先进行以下操作可确保能够还原 BizTalk Server 系统。  
  
## <a name="back-up-biztalk-server"></a>将 BizTalk Server 备份  
  
|步骤|参考|  
|----------|---------------|  
|书面记录对 BizTalk Server 系统进行的所有更改。||  
|确保您有适当的权限备份和还原 BizTalk Server。|[最低安全用户权限](../core/minimum-security-user-rights.md)|  
|学习如何备份和还原 BizTalk Server 数据库。|[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|配置用于对 BizTalk Server 数据库进行备份的备份 BizTalk Server 作业。|[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|配置用于存储数据库备份的服务器。|[如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|如果您有使用商務活動監控 (BAM)，請備份 BAM 資料庫。|[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)|  
|如果在使用企业单一登录 (SSO)，请备份主密钥。|[管理主密钥](../core/managing-the-master-secret.md)|  
|备份 BizTalk Server 配置文件。|[如何备份的 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)|  
|备份企业单一登录主密钥。|[如何备份主密钥](../core/how-to-back-up-the-master-secret.md)|  
|备份 BAM 门户应用程序池和虚拟目录配置信息。 如果没有使用 BAM，则不需要执行此步骤。|[如何备份 BAM 门户](../core/how-to-back-up-the-bam-portal.md)|  
|备份 BizTalk 应用程序。|[备份 BizTalk Server 应用程序](../core/backing-up-biztalk-server-applications.md)|  
  
## <a name="restore-biztalk-server"></a>还原 BizTalk Server  
  
|步骤|參考|  
|----------|---------------|  
|還原您的資料庫。|[如何还原数据库](../core/how-to-restore-your-databases.md)|  
|更新 BAM 資料庫名稱的參考。|[如何备份 BAM 分析和跟踪 Analysis Server 数据库](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [如何更新对 BAM Analysis Server 和星型架构数据库名称的引用](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [如何更新对 BAM 存档数据库名称的引用](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [如何更新对 BAM 主导入数据库名称和连接字符串的引用](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [如何更新对 BAM 通知引用 Services 数据库](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [如何解决未完成的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)|  
|如果您有使用「企業單一登入」，請還原主要密碼。|[管理主密钥](../core/managing-the-master-secret.md)|  
|如果运行 BizTalk Server 的计算机出现故障，请在替换计算机上安装 BizTalk Server。|[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)|  
|还原证书存储。<br /><br /> 标准版需要执行此步骤。 其他版本（例如企业版）则不需要，因为配置进程会自动完成此工作。|[如何还原证书存储](../core/how-to-restore-the-certificate-store.md)|  
|还原企业单一登录|[如何恢复企业单一登录](../core/how-to-recover-enterprise-single-sign-on.md)|  
|还原 BizTalk 组|[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)<br /><br /> 如果要还原标准版，则必须下载一个有助于恢复服务器的脚本。 下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。|  
|还原 BizTalk Server 配置|[如何恢复 BizTalk Server 配置](../core/how-to-recover-the-biztalk-server-configuration.md)|  
|如果在使用 BAM，则应该还原 BAM 警报。<br /><br /> 如果没有使用 BAM，则不需要执行此步骤。|[如何恢复 BAM 警报](../core/how-to-recover-bam-alerts.md)|  
|如果在使用 BAM，则应该还原 BAM 门户。<br /><br /> 如果没有使用 BAM，则不需要执行此步骤。|[如何恢复 BAM 门户](../core/how-to-recover-the-bam-portal.md)|  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)
