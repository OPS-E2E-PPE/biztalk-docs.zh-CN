---
title: "如何为发送端口组配置筛选器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632b9232e87448ddb27d71735b09598b1a9fbc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a>如何为发送端口组配置筛选器
本主题将介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为发送端口组配置一个或多个筛选器。 您可以使用筛选器来创建简单消息传送或基于内容的路由 (CBR) 应用程序。 筛选器可以设置消息属性或字段的条件，这些条件决定哪些消息将被路由到发送端口组。 筛选器不筛选由业务流程路由到发送端口组的消息。  
  
 您可以创建一个或多个筛选器表达式，表达式包含消息属性、运算符以及使用此运算符根据该属性进行验证的值。  
  
 例如，您可以创建如下所示的表达式：  
  
 MSMQ.MsgID = 1  
  
 使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。  
  
 您可以创建其他表达式，并指定该表达式与其他表达式有 AND 或 OR 关系，例如：  
  
 MSMQ.MsgID = 1 OR  
  
 SMTP.From = MyServer  
  
 在这种情况下，发送端口组将订阅 MSMQ 消息 ID 为 1 或发自名为 MyServer 的 SMTP 服务器的所有消息。  
  
> [!NOTE]
>  如果您在一个应用程序中为发送端口组创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。 解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来为发送端口组配置筛选器。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-filters-for-a-send-port-group"></a>为发送端口组配置筛选器  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置发送端口组筛选器的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**发送端口组**，右键单击发送端口组，单击**属性**，然后单击**筛选器**。  
  
4.  下表中所述配置筛选器，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**删除**|单击此项可删除所选的筛选器表达式。|  
    |**上移**|单击此项可在筛选器表达式序列中向上移动所选的属性。|  
    |**下移**|单击此项可在筛选器表达式序列中向下移动所选的属性。|  
    |**属性**|在列表中，单击要在此筛选器表达式中使用的消息属性。|  
    |**运算符**|为表达式键入或选择运算符。|  
    |**值**|键入要根据该属性验证的值。 不同属性类型可接受的值类型不同。 若要查看某个属性可接受哪些类型的值，请将鼠标悬停在该属性上。 下面是可接受的值：Int：(Integer) ，它必须是整数。 字符串： 一个字符串。 dateTime： 日期和/或时间。NET 支持的格式。 有关 .NET 支持的时间格式的详细信息，请参阅 .NET Frameworks 帮助中的“DateTimeFormatInfo 类”。|  
    |**分组依据**|选择**和**或**或**以指示筛选器表达式之间的关系。|  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)