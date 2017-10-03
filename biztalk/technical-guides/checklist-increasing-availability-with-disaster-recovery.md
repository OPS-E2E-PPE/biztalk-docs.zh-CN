---
title: "清单： 提高可用性与灾难恢复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b315110-206a-4fa7-9bde-abab1429c83b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8790d82e3e5830e8145a8af2614413936f3e4b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-increasing-availability-with-disaster-recovery"></a>清单： 提高可用性与灾难恢复
本主题介绍的步骤，你应遵循以提高可用性的生产型的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用灾难恢复的环境。 与容错能力和/或负载平衡提供高可用性后通常实现灾难恢复。  
  
## <a name="backing-up-biztalk-server"></a>备份 BizTalk Server  
  
|步骤|参考|  
|----------|---------------|  
|保留对所有更改的写入的记录你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。||  
|确保你具有适当的权限来备份和还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|请参阅[最低安全用户权限](http://go.microsoft.com/fwlink/?LinkId=154374)(http://go.microsoft.com/fwlink/?LinkId=154374)|  
|创建用于存储的高可用文件共享[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志。 通过使用 Windows 群集在硬件级别使用 SAN 和/或在 Windows 服务器级别配置高可用文件共享。|请参阅[如何在群集上创建文件共享](http://support.microsoft.com/kb/224967)(http://support.microsoft.com/kb/224967)|  
|安装并提供一个或多个备用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用作的目标实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 有关硬件和目标数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例应匹配的硬件和数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在生产环境中的实例。 这将确保目标[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例可以处理用作生产的相同负荷[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。|请参阅[安装 SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=154377) (http://go.microsoft.com/fwlink/?LinkId=154377)|  
|准备灾难恢复站点。|[准备灾难恢复站点](../technical-guides/prepare-the-disaster-recovery-site.md)|  
|备份和还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库|-   [备份和还原数据库的最佳实践](http://go.microsoft.com/fwlink/?LinkId=157758)(http://go.microsoft.com/fwlink/?LinkId=157758)<br />-   [备份和还原 BizTalk Server 数据库](http://go.microsoft.com/fwlink/?LinkId=157757)(http://go.microsoft.com/fwlink/?LinkId=157757)|  
|配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。|[配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)|  
|配置备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。|[如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkID=154072)(http://go.microsoft.com/fwlink/?LinkID=154072)|  
|配置存储备份的服务器。|[如何为日志传送配置的目标系统](http://go.microsoft.com/fwlink/?LinkID=151402)(http://go.microsoft.com/fwlink/?LinkID=151402)|  
|如果在使用业务活动监视 (BAM)，请备份 BAM 数据库。|[备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)|  
|如果要使用 BAM，备份 BAM 门户应用程序池和虚拟目录配置信息。 如果没有使用 BAM，则不需要执行此步骤。|[如何备份 BAM 门户](http://go.microsoft.com/fwlink/?LinkId=154378)(http://go.microsoft.com/fwlink/?LinkId=154378)|  
|备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置文件。|[如何备份的 BizTalk Server 配置](http://go.microsoft.com/fwlink/?LinkId=154379)(http://go.microsoft.com/fwlink/?LinkId=154379)|  
|如果你使用企业单一登录，则备份主密钥服务器。|[如何备份主密钥](http://go.microsoft.com/fwlink/?LinkID=151395)(http://go.microsoft.com/fwlink/?LinkID=151395)|  
  
## <a name="restoring-biztalk-server"></a>还原 BizTalk Server  
  
|步骤|参考|  
|-----------|---------------|  
|还原 BizTalk 组。|[还原 BizTalk 组](../technical-guides/restoring-the-biztalk-group.md)|  
|恢复运行的运行时计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|[恢复运行时计算机](../technical-guides/recovering-the-runtime-computers.md)|  
|恢复 BAM 警报。|[如何恢复 BAM 警报](http://go.microsoft.com/fwlink/?LinkId=154380)(http://go.microsoft.com/fwlink/?LinkId=154380)|  
|恢复 BAM 门户。|[如何恢复 BAM 门户](http://go.microsoft.com/fwlink/?LinkId=154381)(http://go.microsoft.com/fwlink/?LinkId=154381)|  
|还原主密钥服务器。|[如何还原主密钥](http://go.microsoft.com/fwlink/?LinkId=151394)(http://go.microsoft.com/fwlink/?LinkId=151394)|  
|还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。|[如何还原数据库](http://go.microsoft.com/fwlink/?LinkId=151406)(http://go.microsoft.com/fwlink/?LinkId=151406)|  
|更新对 BAM 数据库名称的引用。|-   [更新到新的 BAM 主导入数据库的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)<br />-   [更新到新的 BAM 存档数据库的引用](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)<br />-   [更新到新的 BAM 星型架构数据库的引用](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)<br />-   [更新到新的 BAM 分析数据库的引用](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)<br />-   [更新到新的 BAM 通知引用 Services 数据库](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)<br />-   [如何解决未完成的活动实例](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)|  
  
## <a name="see-also"></a>另请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)