---
title: 如何查看实例信息的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ece5525e18eda82d480adec407f92f9f632453e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970246"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a>如何查看实例信息的接收端口
本主题将介绍如何使用 BizTalk Server 管理控制台查看接收端口的服务实例。 每次接收端口收到消息，都会创建一个服务实例来处理该消息。 按照本主题中的过程操作后，实例信息将显示在接收端口的“组概述”页中。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-instance-information-for-a-receive-port"></a>查看接收端口的实例信息  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开要查看其实例信息的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3. 单击**接收端口**，选择接收端口，单击**视图**，然后单击**实例信息**。  
  
    此页下半部分的“查询结果”面板将显示该接收端口的所有实例。  
  
4. 若要修改查询和查看接收端口的其他实例信息，请单击下面的框**值**有关**搜索**字段中，选择要查看，然后单击实例类型**运行查询**。 有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)   
 [如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)   
 [如何搜索消息](../core/how-to-search-for-messages.md)   
 [如何搜索订阅](../core/how-to-search-for-subscriptions.md)