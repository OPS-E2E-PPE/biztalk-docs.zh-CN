---
title: "BizTalk Server 日志传送使用 Windows 群集名称和 IP 地址 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8619ea6c4eea3eefee5b86282a29e0165d0fb074
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a>BizTalk Server 日志传送使用 Windows 群集名称和 IP 地址
可以简化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用两个实例的日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集中的源和目标服务器作为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送方案。 然后，在发生灾难恢复事件，数据库恢复简化通过仅切换的名称和与群集关联的 IP 地址资源[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例如下所述。 使用此方法时无需运行 UpdateDatabase.vbs 脚本，如主题所述[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)因为数据库名称保持不变。  
  
> [!NOTE]  
>  若要增加群集的容错[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例，群集[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例应地理位置。  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a>若要实现 BizTalk Server 日志传送，它使用 Windows Server 群集名称和 IP 地址资源  
  
1.  停止生产 BizTalk 服务器。  
  
2.  执行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送还原到辅助数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集。  
  
3.  主题中所述的步骤[配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)重新配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，以便辅助[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例现在为源组和主[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例现在为目标组。  
  
4.  停止 IP 和网络名称资源 PublicSQLClustername 在主计算机上的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例。  
  
5.  配置和辅助副本上启动 PublicSQLClustername IP 和网络名称的群集资源[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例。  
  
6.  启动生产 BizTalk 服务器。  
  
7.  验证日志传送还原。  
  
8.  启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]相关的生产站点上的服务。  
  
 执行这些步骤后，BizTalk 组指向辅助[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集实例下图中所示。  
  
 下图说明了如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用两个群集的实例的日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和移动群集的名称和 IP 地址资源。  
  
 ![BizTalk 日志传送使用群集名称和 IP](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")  
  
 **使用 Windows Server 群集名称和 IP 地址资源的 BizTalk Server 日志传送的实现**  
  
## <a name="see-also"></a>另请参阅  
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)   
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)   
 [如何还原备份的 BizTalk Server 作业中的数据库](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)