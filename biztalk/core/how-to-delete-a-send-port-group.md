---
title: 如何删除发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3edf36e0e7d8eaa512b8495e53097261e5c9be6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385349"
---
# <a name="how-to-delete-a-send-port-group"></a>如何删除发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口组。 执行此操作，发送端口组是还从该组的 BizTalk 管理数据库中删除。 删除发送端口组不会删除它包含任何发送端口。  
  
 可以删除发送端口组，仅当满足以下条件：  
  
-   业务流程未绑定到发送端口组。 如果是这样，您可以通过执行中的说明删除绑定[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)。  
  
-   发送端口组是同时停止并取消登记。 有关停止和取消登记发送端口的说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)并[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。  
  
-   参与方未引用的发送端口组。 删除对发送端口组从参与方的引用的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-delete-a-send-port-group"></a>若要删除发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的发送端口组的应用程序。  
  
3. 单击**发送端口组**，右键单击发送端口组，并单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)