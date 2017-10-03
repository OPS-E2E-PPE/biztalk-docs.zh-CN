---
title: "如何停止发送端口或发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a>如何停止发送端口或发送端口组
本主题将介绍如何使用 BizTalk Server 管理控制台停止发送端口或发送端口组。 停止发送端口或发送端口组时，它不再处理消息。 BizTalk Server 挂起所有发往已停止的发送端口或发送端口组的激活消息。 停止发送端口组不会影响其包含的任何发送端口的状态。  
  
> [!NOTE]
>  默认情况下，启动 BizTalk 应用程序将启动其包含的所有项目。 有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中描述的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的帐户身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a>停止发送端口或发送端口组  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送到所需的端口组的应用程序停止。  
  
3.  单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口，，然后单击**停止**。  
  
## <a name="see-also"></a>另请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)