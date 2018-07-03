---
title: 如何查看发送端口的实例信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc1ae4401303845f92b95e6cdf7f4903c165b07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975142"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a>如何查看发送端口的实例信息
本主题将介绍如何使用 BizTalk Server 管理控制台来查看发送端口的正在运行的服务实例列表。 服务实例是在消息被发送到发送端口时创建的发送端口服务实例。 按照本主题中的过程操作后，实例信息将显示在发送端口的“组概述”页中。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中描述的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员的帐户身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-instance-information-for-a-send-port"></a>查看发送端口的实例信息  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开要查看其服务实例信息的发送端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3. 单击**发送端口**，右键单击发送端口，指向**视图**，然后单击**实例信息**。  
  
    此页下半部分的“查询结果”面板将显示发送端口的所有运行实例。  
  
4. 若要修改查询和查看发送端口的不同的服务实例信息，请单击下面的方框**值**的搜索字段中，选择要查看，然后单击实例类型**运行查询**。 有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)   
 [如何搜索消息](../core/how-to-search-for-messages.md)   
 [如何搜索订阅](../core/how-to-search-for-subscriptions.md)