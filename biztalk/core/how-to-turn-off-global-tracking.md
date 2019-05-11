---
title: 如何关闭全局跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4b12b84ed107c07055a75ace23fea368040935
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383620"
---
# <a name="how-to-turn-off-global-tracking"></a>如何禁用全局跟踪
默认情况下，安装 BizTalk Server 时启用全局跟踪。 BizTalk 跟踪 (BizTalkDTADb) 数据库的速度增长的大小随着[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理您的系统上的数据。 如果 BizTalk 跟踪数据库的大小导致磁盘性能下降，可以从跟踪数据库中清除数据。 如果您遇到暂时解决通过清除 BizTalk 跟踪数据库的性能问题，并且你想要配置 BizTalk，不再收集跟踪信息，你可能想要考虑禁用全局跟踪。  
  
 务必了解，关闭全局跟踪会禁用整个的跟踪侦听器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这意味着 BizTalk 将不跟踪其跟踪表中的事件。 或者，你可以关闭对各个事件的跟踪。  
  
> [!NOTE]
>  如果使用业务活动监视 (BAM)，您应维护专用的跟踪主机，即使禁用全局跟踪。 这是因为 BAM 事件会使用跟踪数据解码服务 (TDDS)。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a>若要关闭全局跟踪 (SQL Server 2008)  
  
1. 在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL server，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2. 在中**连接到服务器**对话框中，验证服务器名称和身份验证，然后单击**Connect**。  
  
3. 在 Microsoft SQL Server Management Studio，在**对象资源管理器**，展开\<*计算机名称*\>，展开**数据库**，展开**BizTalkMgmtDb**，展开**表**，右键单击**adm_Group**，然后单击**打开表**。  
  
4. 在表查看器中，水平滚动直至找到**GlobalTrackingOption**。  
  
5. 在中**GlobalTrackingOption**列中，将值从 1 更改为 0，若要关闭此功能，然后按 ENTER。  
  
6. 关闭 Microsoft SQL Server Management Studio。  
  
   > [!NOTE]
   >  您必须重新启动 BizTalk 主机的更改才会生效。  
  
7. 单击**启动**，单击**程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
8. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。  
  
9. 在细节窗格中，右键单击每个主机，然后单击**重新启动**。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [如何从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)   
 [如何从 BizTalk 跟踪数据库中手动清除数据](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)