---
title: 禁止发布新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c850fc4ef38d4da6649082ddf157cc9c87b87fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385177"
---
# <a name="disable-new-message-publication"></a>禁止发布新消息

## <a name="overview"></a>概述
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来禁止发布新消息。 禁用 MessageBox 数据库停止接收新消息在 MessageBox 数据库中的发布新消息。 在某些 BizTalk Server 环境中，如果禁止主 MessageBox 数据库的新消息发布可以提高性能。 禁止发布新消息不会影响正在进行中的 MessageBox 数据库或服务实例中的现有消息。  
  
 有关使用 WMI 禁止发布新消息的信息，请参阅**MSBTS_MsgBoxSetting.DisableNewMessagePublication 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
> [!IMPORTANT]
>  在删除 MessageBox 数据库之前，必须禁用新消息的发布。 有关删除 MessageBox 数据库的信息，请参阅[如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)。  
  
## <a name="prerequisites"></a>先决条件  
 管理 MessageBox 数据库管理员必须具有所需的用户权限。 必须具有以下的用户权限，才能管理 MessageBox 数据库并禁止发布新消息：  
  
-   您必须以 BizTalk Server Administrators 组的成员身份登录。  
  
-   您必须在数据库所在的计算机上的 SQL Server 管理员。  
  
## <a name="disable-steps"></a>禁用的步骤
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。  
  
3. 在详细信息窗格中，右键单击你想要禁用，，然后单击该 MessageBox 数据库**属性**。  
  
4. 在中**消息框属性**对话框中，选择**禁止发布新消息**复选框，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理 MessageBox 数据库](../core/managing-messagebox-databases.md)   
 [添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md)   
 [删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)