---
title: "如何创建接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.procedure.createreceiveport
helpviewer_keywords:
- receive ports, creating
- managing [receive ports], creating
- creating, receive ports
ms.assetid: 23fae441-be80-4759-b3d6-74787a40e65b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdecbc36962d3e4e45d35171747ff4c450959a83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-receive-port"></a>如何创建接收端口
本主题将介绍如何使用 BizTalk Server 管理控制台来创建接收端口。 接收端口是相似接收位置的一个逻辑分组，使用该端口，服务可通过接收数据与外部合作伙伴进行交互。  
  
 您可以创建以下类型的接收端口：  
  
-   单向端口 — 用于丢弃消息并且不等待同步回复的应用程序  
  
-   请求-响应 — 用于请求消息响应的应用程序  
  
 除了本主题中所述的配置，你还可以指定由接收端口，处理消息的跟踪选项中所述[如何配置跟踪接收端口](../core/how-to-configure-tracking-for-a-receive-port.md)。  
  
> [!NOTE]
>  如果您正在远程计算机上创建某一接收端口，并且该计算机未启用网络 DTC，则您必须在创建该接收端口后重新启动远程计算机。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-create-a-receive-port"></a>若要创建接收端口  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其创建接收端口的 BizTalk 组和 BizTalk 应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**根据为端口的类型，你想要创建。  
  
4.  在**接收端口属性**窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|键入端口的名称。|  
    |**无身份验证**|单击此选项可禁用验证。 这是默认设置。|  
    |**丢弃的消息，如果身份验证失败**|单击此选项可启用验证，但将删除未通过验证的消息。|  
    |**如果身份验证失败，则保留消息**|单击此选项可启用验证，并保留未通过验证的消息。|  
    |**启用路由失败消息**|选中此复选框可尝试将失败的所有消息路由至某个订阅应用程序（例如另一个接收端口或业务流程计划）。 清除此复选框可挂起失败的消息，并生成一个否定确认 (NACK)。 默认值为清除此复选框。 有关详细信息，请参阅[如何启用路由失败消息为接收端口](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)。|  
  
5.  在左窗格中，单击**接收位置**，并创建新此接收端口接收位置。 有关说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
6.  在左窗格中，单击**入站映射**，并执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**源文档**|从下拉列表中，选择要与此端口一起使用的源架构。|  
    |**地图**|从下拉列表中，选择要与此端口关联的映射。|  
    |**目标文档**|从下拉列表中，选择要与此端口一起使用的目标架构。|  
  
7.  如果要创建请求-响应接收端口，然后在左窗格中，单击**出站映射**，并执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**源文档**|从下拉列表中，选择要与此端口一起使用的源架构。|  
    |**地图**|从下拉列表中，选择要与此端口关联的映射。|  
    |**目标文档**|从下拉列表中，选择要与此端口一起使用的目标架构。|  
  
8.  完成配置接收端口，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收端口](../core/managing-receive-ports.md)