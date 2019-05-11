---
title: 如何为发送端口组配置筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c5d54608da91f76337cba13390baf5ded2b27d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341479"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a>如何为发送端口组配置筛选器
本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置发送端口组的一个或多个筛选器。 可以使用筛选器来创建简单消息传送或基于内容的路由 (CBR) 应用程序。 筛选器可以设置消息属性或字段的决定哪些消息路由到发送端口组的条件。 筛选器不筛选由业务流程路由到发送端口组的消息。  
  
 您可以创建一个或多个筛选器表达式，包含消息属性、 运算符和一个值，通过使用运算符根据属性进行验证。  
  
 例如，可以创建如下所示的表达式：  
  
 MSMQ.MsgID = 1  
  
 使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。  
  
 可以创建其他表达式并指定它们具有一个 AND 或 OR 关系与其他表达式，例如：  
  
 MSMQ.MsgID = 1 OR  
  
 SMTP.From = MyServer  
  
 在这种情况下，发送端口组将订阅拥有的所有消息到 MSMQ 消息 ID 为 1 或已从名为 MyServer 的 SMTP 服务器发送的。  
  
> [!NOTE]
>  如果一个应用程序在另一个应用程序中使用的属性架构中创建的发送端口组的筛选器，然后将第一个应用程序导入新的 BizTalk 组，不会收到的警告，该架构缺少，并且筛选功能将不正常当安装并启动应用程序。 可以通过导入包含架构，然后再安装不包含架构的应用程序的应用程序来更正此问题。  
  
> [!NOTE]
>  应用程序开发人员可以通过使用本主题中的过程在开发过程中配置发送端口组的筛选器。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-filters-for-a-send-port-group"></a>若要为发送端口组配置筛选器  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置发送端口组筛选器。  
  
3. 单击**发送端口组**，右键单击该发送端口组，单击**属性**，然后单击**筛选器**。  
  
4. 下表中所述配置筛选器，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**删除**|单击此项可删除所选的筛选器表达式。|  
   |**上移**|单击此项可在筛选器表达式序列中提前移动所选的属性。|  
   |**“下移”**|单击筛选器表达式序列中向下移动所选的属性。|  
   |**属性**|在列表中，单击要在此筛选器表达式中使用的消息属性。|  
   |**“运算符”**|键入或选择该表达式的运算符。|  
   |**ReplTest1**|键入要验证该属性的值。 接受的值类型会根据属性的类型而有所不同。 若要查看哪些类型的值接受属性，请将鼠标悬停于属性。 可接受的值如下所示：Int:（整数）这必须是整数。 字符串：字符的字符串。 dateTime:日期和/或时间。NET 支持的格式。 有关详细信息。NET 支持的时间格式，请参阅.NET Frameworks 帮助中的"DateTimeFormatInfo 类"。|  
   |**分组依据**|选择**并**或**或**以指示筛选器表达式之间的关系。|  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)