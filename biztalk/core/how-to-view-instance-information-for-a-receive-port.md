---
title: 如何查看实例信息接收端口 |Microsoft 文档
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
ms.openlocfilehash: e46da8bfb99246b67f93c02fa19689099f8acb24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256797"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a>如何查看实例信息接收端口
本主题将介绍如何使用 BizTalk Server 管理控制台查看接收端口的服务实例。 每次接收端口收到消息，都会创建一个服务实例来处理该消息。 按照本主题中的过程操作后，实例信息将显示在接收端口的“组概述”页中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-instance-information-for-a-receive-port"></a>查看接收端口的实例信息  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要查看其实例信息的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**接收端口**，选择接收端口中，单击**视图**，然后单击**实例信息**。  
  
     此页下半部分的“查询结果”面板将显示该接收端口的所有实例。  
  
4.  若要优化的查询并查看不同的实例接收端口的信息，请单击下面的框**值**为**搜索**字段中，选择要查看，，然后单击的实例类型**运行查询**。 有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收端口](../core/managing-receive-ports.md)   
 [如何运行服务实例的搜索](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)   
 [如何搜索消息](../core/how-to-search-for-messages.md)   
 [如何搜索订阅](../core/how-to-search-for-subscriptions.md)