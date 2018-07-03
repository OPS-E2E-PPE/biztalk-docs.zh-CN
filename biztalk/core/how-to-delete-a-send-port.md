---
title: 如何删除发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fd1bdab77761787cef404f318d2965f68e3a8c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973200"
---
# <a name="how-to-delete-a-send-port"></a>如何删除发送端口
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口。 执行此操作，发送端口是还从该组的 BizTalk 管理数据库中删除。  
  
> [!IMPORTANT]
>  删除发送端口时，任何正在运行的服务不再与此端口相关联的实例可以获取有关发送端口，如其名称的配置信息。 尽管此信息被缓存，如果服务实例，必须重新发送一条消息，它将不能完成，并将挂起该消息。 在删除之前的发送端口，您应该验证是否没有正在运行服务实例，如中所述[如何查看发送端口的实例信息](../core/how-to-view-instance-information-for-a-send-port.md)。  
  
 仅当满足以下条件，则可以删除发送端口：  
  
-   业务流程未绑定到发送端口。 如果是这样，您可以通过执行中的说明删除绑定[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)。  
  
-   发送端口是同时停止并取消登记。 有关停止和取消登记发送端口的说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)并[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。  
  
-   参与方未引用的发送端口。 删除对发送端口从参与方的引用的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。  
  
-   中的发送端口组不包括发送端口。 有关从发送端口组中删除发送端口的说明，请参阅[如何从发送端口组中删除发送端口](../core/how-to-remove-a-send-port-from-a-send-port-group.md)。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来删除发送端口。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-delete-a-send-port"></a>若要删除的发送端口  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk Server 管理、 展开 BizTalk 组中，展开应用程序，，然后展开包含你想要删除的发送端口的应用程序  
  
3. 单击**发送端口**，右键单击发送端口，然后单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)