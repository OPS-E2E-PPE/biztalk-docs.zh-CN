---
title: "如何删除发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55b4e08fa03380c3361a44b7989301b606732d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-send-port"></a>如何删除发送端口
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序删除发送端口。 执行此操作时，发送端口也将删除从组 BizTalk 管理数据库。  
  
> [!IMPORTANT]
>  当删除发送端口时，任何正在运行的服务与该端口关联的实例不能再获取有关发送端口，例如其名称的配置信息。 尽管此信息缓存的如果服务实例必须重新发送一条消息，它将不能完成，并且将挂起消息。 在删除之前发送端口，你应验证是否有任何运行中所述服务实例，[如何发送端口的视图实例信息](../core/how-to-view-instance-information-for-a-send-port.md)。  
  
 仅当符合下列条件，你可以删除发送端口：  
  
-   业务流程不绑定到发送端口中。 如果出现这种情况，您可以通过执行中的说明删除绑定[如何取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)。  
  
-   发送端口是同时停止并取消登记。 有关停止和取消登记发送端口的说明，请参阅[如何发送端口或发送端口组中取消](../core/how-to-unenlist-a-send-port-or-send-port-group.md)和[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。  
  
-   发送端口未被方引用。 有关删除从方对发送端口的引用的说明，请参阅[如何查看或编辑方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。  
  
-   发送端口未包含在发送端口组。 有关从发送端口组中删除发送端口的说明，请参阅[如何从发送端口组中删除发送端口](../core/how-to-remove-a-send-port-from-a-send-port-group.md)。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来删除发送端口。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-delete-a-send-port"></a>若要删除发送端口  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理，展开 BizTalk 组，展开应用程序，然后展开包含你想要删除的发送端口的应用程序  
  
3.  单击**发送端口**，发送端口中，右键单击，然后单击**删除**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)