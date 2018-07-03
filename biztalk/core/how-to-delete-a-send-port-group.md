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
ms.openlocfilehash: 4bf0e1a75799671ecd2e52515481c3d3be32ee67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013686"
---
# <a name="how-to-delete-a-send-port-group"></a>如何删除发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口组。 执行此操作时，该组的 BizTalk 管理数据库中的发送端口组也会被删除。 删除发送端口组不会删除该组包含的任何发送端口。  
  
 发送端口组只在符合以下条件时才可以删除：  
  
-   没有业务流程绑定到该发送端口组。 如果是这样，您可以通过执行中的说明删除绑定[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)。  
  
-   发送端口组已停止并已取消登记。 有关停止和取消登记发送端口的说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)并[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。  
  
-   没有参与方引用该发送端口组。 删除对发送端口组从参与方的引用的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-delete-a-send-port-group"></a>删除发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的发送端口组的应用程序。  
  
3. 单击**发送端口组**，右键单击发送端口组，并单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)