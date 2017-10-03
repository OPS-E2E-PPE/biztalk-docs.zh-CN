---
title: "如何查看为业务流程的实例信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84129d48fba15dadfc97722ead85b1535a8fa597
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a>如何查看为业务流程的实例信息
本主题介绍如何使用 BizTalk Server 管理控制台来查看业务流程的实例信息。 服务实例是 BizTalk Server 正在处理或已经序列化到 MessageBox 中以便进一步处理或跟踪的业务流程实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-instance-information-for-an-orchestration"></a>查看业务流程的实例信息  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要查看实例信息业务的流程的应用程序。  
  
3.  单击**业务流程**，选择你想要查看实例信息、 业务的流程单击**视图**，然后选择**实例信息**。  
  
     此页下半部分的“查询结果”面板将显示该业务流程的所有实例。  
  
     若要优化业务流程的查询和查看不同的实例信息，请单击下面的框**值**对于的搜索字段中，选择要查看，，然后单击的实例类型**运行查询**。 有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何运行服务实例的搜索](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)   
 [如何搜索消息](../core/how-to-search-for-messages.md)   
 [如何搜索订阅](../core/how-to-search-for-subscriptions.md)