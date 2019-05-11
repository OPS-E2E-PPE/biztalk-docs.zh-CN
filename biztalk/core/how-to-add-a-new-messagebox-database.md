---
title: 如何添加新的 MessageBox 数据库 |Microsoft Docs
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
ms.openlocfilehash: b3e82e51d79e78f42881e288be02476f66405943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343752"
---
# <a name="how-to-add-a-new-messagebox-database"></a>如何添加新的 MessageBox 数据库
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台向 BizTalk Server 部署中添加新的 MessageBox 数据库。 MessageBox 数据库是跨服务器执行协作处理的负载平衡工作项的基础。 若要增加您的系统可以处理的消息数，可能需要添加其他 MessageBox 数据库。  
  
 无法创建新的 MessageBox 数据库和已登记业务流程、 发送端口，或在同一时间发送端口组。 已登记业务流程、 发送端口或发送端口组访问的数据的 BizTalk Server 必须复制到新的 MessageBox 数据库。 而访问此数据时，BizTalk Server 不能将其复制到新的 MessageBox 数据库中。  
  
 可以指定本地和远程数据库作为 MessageBox 数据库。 有关 BizTalk Server 数据库的信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  
  
> [!IMPORTANT]
>  SQL Server 代理必须在所有你想要添加新的 MessageBox 数据库的 SQL 服务器上运行。  
  
## <a name="prerequisites"></a>先决条件  
 管理 MessageBox 数据库管理员必须具有所需的用户权限。 必须具有以下的用户权限，才能管理 MessageBox 数据库并禁止发布新消息：  
  
-   您必须以 BizTalk Server Administrators 组的成员身份登录。  
  
-   您必须在数据库所在的计算机上的 SQL Server 管理员。  
  
### <a name="to-add-a-new-messagebox-database"></a>若要添加新的 MessageBox 数据库  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 BizTalk 组，然后依次**平台设置**。  
  
3. 右键单击**消息框**，单击**新建**，然后单击**消息框**。  
  
4. 在中**消息框属性**对话框中，执行以下操作，然后依次**确定**:  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**SQL Server**|显示承载 MessageBox 数据库的 SQL server 的名称。|  
   |**“数据库”**|显示 MessageBox 数据库的名称。|  
   |**主订阅 messagebox**|指示所选的 MessageBox 数据库是否为主。 如果当前的 MessageBox 数据库为主数据库，则此复选框被选中并且不可用。 运行配置向导时创建的第一个 MessageBox 数据库是默认主机。|  
   |**禁止发布新消息**|选择此复选框以指定不希望此 MessageBox 数据库接收激活消息。|  
  
## <a name="see-also"></a>请参阅  
 [管理 MessageBox 数据库](../core/managing-messagebox-databases.md)   
 [如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)   
 [如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)   
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)