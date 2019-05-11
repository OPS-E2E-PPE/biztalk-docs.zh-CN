---
title: 如何删除 MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b5191d051e460217eccba93c0318a94357515b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338768"
---
# <a name="how-to-delete-a-messagebox-database"></a>如何删除 MessageBox 数据库
使用 BizTalk 管理控制台或 Windows Management Instrumentation (WMI) 从 BizTalk 组中删除 MessageBox 数据库。 可以从 BizTalk 组中删除 MessageBox 数据库，或您可以完全将其删除从 BizTalk Server 部署。  
  
 例如，可以删除不再使用，例如用于测试目的的数据库的 MessageBox 数据库。  
  
 从 BizTalk Server 部署中永久并完全地删除 MessageBox 数据库到有八个步骤：  
  
1.  禁止发布新消息。  
  
     在删除 MessageBox 数据库之前，必须禁用新消息的发布。 有关禁止发布新消息的信息，请参阅[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)。  
  
2.  等待缓存刷新间隔过期。  
  
     禁止发布新消息后，必须等待，然后再删除数据库。 等待时间定义为 CacheRefreshInterval 的长度的两倍。 CacheRefreshInterval 的默认值为 60 秒。 您使用**组属性**对话框可以更改缓存刷新间隔。  
  
3.  从 BizTalk 组中删除 MessageBox 数据库。  
  
     从 BizTalk 组中删除 MessageBox 数据库从 BizTalk 管理数据库中删除 MessageBox 引用。  
  
4.  重新启动包含到 MessageBox 数据库的缓存的连接的主机实例。  
  
     以物理方式删除从 SQL Server 数据库，从运行时引擎的缓存的数据库连接是否存在之前，必须重新启动主机实例。 有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。  
  
5.  停止所有的访问的数据库中的主机实例。 有关停止正在进行中的主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
     如果要删除非主 MessageBox 数据库，停止正在进行中的主机实例之前，你首先应禁止发布新消息到该消息框，请确保：  
  
    -   没有正在运行服务实例在消息框中。  
  
    -   有没有挂起 （或任何其他遗留） 实例中的消息框的左侧。  
  
    -   BAM 跟踪数据已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库 （TrackingData 表应为空）。  
  
    -   跟踪的消息正文已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
6.  确保后台 SQL Server 代理作业已完成。  
  
     从 BizTalk Server 部署永久删除 MessageBox 数据库之前，应该首先确保后台 SQL Server 代理作业已完成传输所有跟踪消息正文到 TrackingSpool 表，然后备份TrackingSpool 表。 有关检查后台 SQL Server 代理作业的状态信息，请参阅 SQL Server 联机丛书。  
  
7.  备份 TrackingSpool 表。  
  
     跟踪的消息正文会保留在 MessageBox 数据库，直到您手动备份 TrackingSpool 表到外部存储。 在备份之前，后台 SQL Server 代理作业会将消息正文从 Spool 表传输到 TrackingSpool 表。 有关手动备份 SQL Server 表的信息，请参阅 SQL Server 联机丛书。  
  
8.  从 SQL Server 中删除数据库。  
  
     从 BizTalk 组中删除 MessageBox 数据库不会以物理方式删除数据库从 Microsoft SQL Server。 若要永久删除 MessageBox 数据库，必须通过使用 SQL Server 企业管理器或 SQL Server Management Studio 从 BizTalk 组中删除后删除。  
  
## <a name="prerequisites"></a>先决条件  
 管理 MessageBox 数据库管理员必须具有所需的用户权限。 必须具有以下的用户权限，才能管理 MessageBox 数据库并禁止发布新消息：  
  
-   您必须以 BizTalk Server Administrators 组的成员身份登录。  
  
-   您必须在数据库所在的计算机上的 SQL Server 管理员。  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a>若要从 BizTalk 组中删除 MessageBox 数据库  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。  
  
3. 在详细信息窗格中，右键单击你想要删除，然后单击该消息框数据库**属性**。  
  
4. 在中**消息框属性**对话框中，选择**禁止发布新消息**复选框。  
  
5. 使用 BizTalk Server 管理控制台中的组中心页以验证消息实例都已冻结或挂起的要删除的 MessageBox 数据库。  
  
6. 等待一段时间内 CacheRefreshInterval 的长度的两倍。 CacheRefreshInterval 的默认值为 60 秒。  
  
7. 在细节窗格中，右键单击你想要删除，并单击 MessageBox 数据库**删除**。  
  
8. 阅读警告消息之后, 单击**确定**。  
  
9. 在控制台树中，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
10. 在详细信息窗格中，右键单击正在运行的所有主机实例，并停止并重新启动每一个。  
  
11. 在 MessageBox 数据库所在的服务器上，打开 SQL Server 企业管理器或 SQL Server Management Studio，具体取决于哪个版本的 SQL Server 使用的，然后删除该数据库。  
  
     有关如何删除 SQL Server 中的数据库的信息，请参阅 SQL Server 联机丛书。  
  
## <a name="see-also"></a>请参阅  
 [管理 MessageBox 数据库](../core/managing-messagebox-databases.md)   
 [如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md)   
 [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)