---
title: "如何删除 MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a12c74bfef8d6afec15b0c83f520eb4be43696c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-messagebox-database"></a>如何删除 MessageBox 数据库
使用 BizTalk 管理控制台或 Windows 管理规范 (WMI) 可以从 BizTalk 组中删除 MessageBox 数据库。 您可以从 BizTalk 组中删除 MessageBox 数据库，也可以从 BizTalk Server 部署中将其完全删除。  
  
 例如，可以删除您不再使用的 MessageBox 数据库，如用于测试目的的数据库。  
  
 若要从 BizTalk Server 部署中永久并完全地删除 MessageBox 数据库，需要执行以下八个步骤：  
  
1.  禁止发布新消息。  
  
     在删除 MessageBox 数据库之前，必须禁用新消息发布功能。 有关禁用新发布的消息的信息，请参阅[如何禁用发布新的消息](../core/how-to-disable-new-message-publication.md)。  
  
2.  等待缓存刷新间隔过期。  
  
     在您禁用新消息发布功能之后，必须等待一定时间才能删除数据库。 该等待时间定义为 CacheRefreshInterval 的两倍时间。 CacheRefreshInterval 的默认值是 60 秒。 你使用**组属性**对话框可以更改缓存刷新。  
  
3.  从 BizTalk 组中删除 MessageBox 数据库。  
  
     从 BizTalk 组中删除 MessageBox 数据库会从 BizTalk 管理数据库中删除 MessageBox 引用。  
  
4.  重新启动包含指向 MessageBox 数据库的缓存连接的主机实例。  
  
     如果存在来自运行时引擎的缓存数据库连接，则必须重新启动相应的主机实例，才能在物理上从 SQL Server 中删除该数据库。 有关启动的主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。  
  
5.  停止正在访问该数据库的所有主机实例。 要停止正在进行主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
     如果要删除非主 MessageBox 数据库，应在停止运行中的主机实例之前，先禁止向该 MessageBox 发布新消息，还要确保以下几项内容：  
  
    -   在 MessageBox 中没有正在运行的服务实例。  
  
    -   在 MessageBox 中没有挂起的（或任何其他遗留的）实例。  
  
    -   BAM 跟踪数据已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库（TrackingData 表应为空）。  
  
    -   跟踪的消息正文已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
6.  确保后台 SQL Server 代理作业完成。  
  
     从 BizTalk Server 部署中永久删除 MessageBox 数据库之前，应该首先确保后台 SQL Server 代理作业已经完成了将所有跟踪的消息正文传输到相应 TrackingSpool 表的工作，然后备份这些 TrackingSpool 表。 有关检查后台 SQL Server 代理作业的状态的信息，请参阅 SQL Server 联机丛书。  
  
7.  备份 TrackingSpool 表。  
  
     除非您手动将各 TrackingSpool 表备份到外部存储器中，否则跟踪的消息正文仍会保留在 MessageBox 数据库中。 在备份之前，后台 SQL Server 代理作业将把消息正文从 Spool 表传输到 TrackingSpool 表中。 有关手动备份 SQL Server 表的信息，请参阅 SQL Server 联机丛书。  
  
8.  从 SQL Server 中删除该数据库。  
  
     从 BizTalk 组中删除 MessageBox 数据库不会在物理上从 Microsoft SQL Server 中删除该数据库。 若要永久删除 MessageBox 数据库，在将其从 BizTalk 组中删除之后必须通过使用 SQL Server 企业管理器或 SQL Server Management Studio 来删除它。  
  
## <a name="prerequisites"></a>先决条件  
 管理 MessageBox 数据库的管理员必须具有所需的用户权限。 必须具有以下用户权限才能管理 MessageBox 数据库并禁用新消息发布：  
  
-   必须以 BizTalk Server Administrators 组成员的身份登录。  
  
-   必须是该数据库所在的计算机的 SQL Server 管理员。  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a>从 BizTalk 组中删除 MessageBox 数据库  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。  
  
3.  在详细信息窗格中，右键单击你想要删除，，然后单击的消息框数据库**属性**。  
  
4.  在**消息框属性**对话框中，选择**禁用新消息发布**复选框。  
  
5.  使用 BizTalk Server 管理控制台中的组中心页可以确定要删除的 MessageBox 数据库是否具有已冻结或挂起的消息实例。  
  
6.  等待 CacheRefreshInterval 的两倍时间。 CacheRefreshInterval 的默认值是 60 秒。  
  
7.  在详细信息窗格中，右键单击你想要删除，然后单击的 MessageBox 数据库**删除**。  
  
8.  在阅读警告消息后, 单击**确定**。  
  
9. 在控制台树中，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
10. 在详细信息窗格中，右键单击所有运行的主机实例，然后停止并重新启动每一个主机实例。  
  
11. 在 MessageBox 数据库驻留的服务器上，打开 SQL Server 企业管理器或 SQL Server Management Studio（取决于您使用的 SQL Server 的版本），然后删除该数据库。  
  
     有关如何删除 SQL Server 中的数据库的信息，请参阅 SQL Server 联机丛书。  
  
## <a name="see-also"></a>另请参阅  
 [管理 MessageBox 数据库](../core/managing-messagebox-databases.md)   
 [如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md)   
 [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)