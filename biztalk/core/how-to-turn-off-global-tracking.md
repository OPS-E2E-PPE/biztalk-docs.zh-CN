---
title: 如何关闭全局跟踪 |Microsoft 文档
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
ms.openlocfilehash: c143d19e6071ca4f9ce488ae936082db86dc84dc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007094"
---
# <a name="how-to-turn-off-global-tracking"></a>如何关闭全局跟踪
默认情况下，安装 BizTalk Server 时，被启用全局跟踪。 BizTalk 跟踪 (BizTalkDTADb) 数据库的大小随着 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理系统上的数据而增大。 如果 BizTalk 跟踪数据库的大小导致磁盘性能下降，则可以从跟踪数据库中清除数据。 如果存在通过清除 BizTalk 跟踪数据库暂时得以解决的性能问题，并且希望对 BizTalk 进行控制以便不再收集跟踪信息，则可能要考虑禁用全局跟踪功能。  
  
 很重要的一点是，关闭全局跟踪会禁用整个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组的跟踪侦听器。 这意味着 BizTalk 将不跟踪其跟踪表中的事件。 或者，您可以针对单个事件关闭跟踪。  
  
> [!NOTE]
>  如果正在使用业务活动监视 (BAM)，则即使禁用全局跟踪，也应保留一个专门的跟踪主机。 这是由于 BAM 事件会使用跟踪数据解码服务 (TDDS)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a>若要关闭全局跟踪 (SQL Server 2008)  
  
1.  在 SQL 服务器上承载 BizTalk 跟踪 (BizTalkDTADb) 数据库，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，验证服务器名称和身份验证，，然后单击**连接**。  
  
3.  在 Microsoft SQL Server Management Studio，在**对象资源管理器**，展开\<*计算机名称*\>，展开**数据库**，展开**BizTalkMgmtDb**，展开**表**，右键单击**adm_Group**，然后单击**打开表**。  
  
4.  在表查看器中，水平滚动直到找到**GlobalTrackingOption**。  
  
5.  在**GlobalTrackingOption**列中，将值从 1 更改为 0，若要关闭此功能，然后按 ENTER。  
  
6.  关闭 Microsoft SQL Server Management Studio。  
  
    > [!NOTE]
    >  必须重新启动 BizTalk 主机，此更改才会生效。  
  
7.  单击**启动**，单击**程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
8.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**托管实例**。  
  
9. 在细节窗格中，右键单击每个主机，然后单击**重新启动**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [如何从 BizTalk 跟踪数据库清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)   
 [如何从 BizTalk 跟踪数据库手动清除数据](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)