---
title: 如何添加新的 MessageBox 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cab4fd370aab2d85519b3fd52e0dadcd9583275e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247237"
---
# <a name="how-to-add-a-new-messagebox-database"></a>如何添加新的 MessageBox 数据库
可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台向 BizTalk Server 部署添加新的 MessageBox 数据库。 MessageBox 数据库是跨服务器执行协作处理的负载平衡工作项的基础。 若要增加系统可处理的消息数，则可能需要添加其他 MessageBox 数据库。  
  
 您无法在创建新的 MessageBox 数据库时已登记业务流程、发送端口或发送端口组。 已登记的业务流程、发送端口或发送端口组需要访问 BizTalk Server 必须复制到新的 MessageBox 数据库中的数据。 在访问此数据的过程中，BizTalk Server 无法将其复制到新的 MessageBox 数据库。  
  
 可以指定本地和远程数据库作为 MessageBox 数据库。 有关 BizTalk Server 数据库的信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  
  
> [!IMPORTANT]
>  必须在要添加新的 MessageBox 数据库的 SQL 服务器上运行 SQL Server 代理。  
  
## <a name="prerequisites"></a>先决条件  
 管理 MessageBox 数据库的管理员必须具有所需的用户权限。 必须具有以下用户权限才能管理 MessageBox 数据库并禁用新消息发布：  
  
-   必须以 BizTalk Server Administrators 组成员的身份登录。  
  
-   必须是该数据库所在的计算机的 SQL Server 管理员。  
  
### <a name="to-add-a-new-messagebox-database"></a>添加新的 MessageBox 数据库  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后单击**平台设置**。  
  
3.  右键单击**消息框**，单击**新建**，然后单击**消息框**。  
  
4.  在**消息框属性**对话框中，执行以下操作，并依次**确定**:  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**SQL Server**|显示承载 MessageBox 数据库的 SQL 服务器的名称。|  
    |**数据库**|显示 MessageBox 数据库的名称。|  
    |**主订阅消息框**|指示选定的 MessageBox 数据库是否为主数据库。 如果当前的 MessageBox 数据库为主数据库，则此复选框将处于选中状态并且不可用。 默认情况下，运行配置向导时创建的第一个 MessageBox 数据库为主数据库。|  
    |**禁用发布新消息**|选中此复选框可指定不希望此 MessageBox 数据库接收激活消息。|  
  
## <a name="see-also"></a>另请参阅  
 [管理 MessageBox 数据库](../core/managing-messagebox-databases.md)   
 [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)   
 [如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)   
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)