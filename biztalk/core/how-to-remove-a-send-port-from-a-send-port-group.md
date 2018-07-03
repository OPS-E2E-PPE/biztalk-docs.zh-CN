---
title: 如何从发送端口组中删除发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ce54faf09b45a46d2ac5150e1c2bbbe88c8ccac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018920"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a>如何从发送端口组中删除发送端口
本主题将介绍如何使用 BizTalk Server 管理控制台从发送端口组中删除发送端口。 执行此操作时，不会从应用程序或 BizTalk 管理数据库中删除发送端口。  
  
 删除发送端口时，该发送端口必须处于已停止状态或已取消登记状态。  
  
> [!NOTE]
>  若要将消息路由，发送端口组必须包含至少一个发送端口。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a>若要从发送端口组中删除发送端口  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要从发送端口组中删除发送端口。  
  
3. 单击**发送端口组**，右键单击发送端口组，并单击**属性**。  
  
4. 下**名称**，单击发送端口以删除，然后单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)   
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)