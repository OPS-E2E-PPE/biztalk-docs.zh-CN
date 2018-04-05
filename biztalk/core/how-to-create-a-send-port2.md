---
title: 如何创建发送端口 2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createsendport
helpviewer_keywords:
- managing [send ports], creating
- creating, send ports
- send ports, creating
ms.assetid: 7f0d07b8-1ac5-4032-bb08-2f7e05185f86
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796ba5da53257d0f198e4b8bf13ee81835efcf4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a>如何创建发送端口
本主题将介绍如何使用 BizTalk Server 管理控制台来创建发送端口。 创建发送端口时，必须选择要创建的发送端口的类型，各类型如下：  
  
-   静态单向 — 仅发送端口 。  
  
-   静态要求响应 — 等待目标回复的发送端口 。  
  
-   动态单向 — 仅发送端口 ， 运行时可基于消息属性绑定到协议和位置 。  
  
-   动态要求响应 — 等待回复的发送端口 ， 运行时可基于消息属性绑定到协议和位置 。  
  
 创建发送端口后，您可以执行以下其他步骤来完成该配置：  
  
-   配置高级传输选项，如的次数重试发送消息失败和对于端口的服务窗口计划上的消息中所述[如何配置传输高级选项发送端口](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)。  
  
-   事件的主要传输无法正常工作中, 所述配置备份传输协议、[如何发送端口配置备份传输选项](../core/how-to-configure-backup-transport-options-for-a-send-port.md)。  
  
-   配置筛选器，以确定消息框中，从哪些消息路由到此发送端口中所述[如何将筛选器配置为发送端口](../core/how-to-configure-filters-for-a-send-port.md)。  
  
-   将一个安全证书分配给要加密或签名由发送端口中，处理的文档中所述的发送端口[如何将证书分配给发送端口](../core/how-to-assign-a-certificate-to-a-send-port.md)。  
  
-   中所述配置由发送端口中，处理消息的跟踪选项[如何配置跟踪发送端口](../core/how-to-configure-tracking-for-a-send-port.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。 此外，还需有企业单一登录 (SSO) 数据库的 SSO 关联管理员权限。 有关详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其创建发送端口的 BizTalk 组和 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击要创建的端口类型。  
  
4.  在**发送端口属性**窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|键入新发送端口的名称。 此名称在 BizTalk 组中必须是唯一的。|  
    |**传输类型**|从下拉列表中，选择适当的传输类型或传输协议。 如果端口是要求响应端口，则该列表中只显示支持要求响应的传输类型。 此属性仅对静态端口可见。|  
    |**配置**|选择传输类型后，单击**配置**以显示**传输属性**对话框中，提供特定于传输的配置选项。 此属性仅对静态端口可见。 单击**帮助**对话框中的配置说明。|  
    |**发送处理程序**|从下拉列表中选择运行发送适配器的主机实例。 此属性仅对静态端口可见。|  
    |**发送管道**|从下拉列表中选择处理通过此端口发送的消息的管道。 选择管道后，你可以单击旁边的省略号 (**...**) 按钮以显示**配置管道**对话框中，你在其中配置为此特定端口的每个实例管道属性。 单击**帮助**对话框中的配置说明。|  
    |**接收管道**|从下拉列表中选择处理通过此端口接收的消息的管道。 对通过此管道接收的消息的响应也将通过此管道发送。 选择管道后，你可以单击旁边的省略号 (**...**) 按钮以显示**配置管道**对话框中，你在其中配置为此特定端口的每个实例管道属性。 此属性仅对要求响应端口可见。|  
  
5.  如果您创建请求-响应发送端口，在左窗格中，单击**入站映射**并执行以下操作，根据需要重复如果你想要添加多个映射：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**源文档**|从下拉列表中选择入站映射的源文档。 一个发送端口可以具有多个映射，但是每个映射应具有唯一的源文档。|  
    |**地图**|从下拉列表中选择与源文档和目标文档关联的映射。|  
    |**目标文档**|从下拉列表中选择入站映射的目标文档。|  
  
6.  在左窗格中，单击**出站映射**并执行以下操作，根据需要重复如果你想要添加多个映射：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**源文档**|从下拉列表中选择出站映射的源文档。|  
    |**地图**|从下拉列表中选择与源文档和目标文档关联的映射。|  
    |**目标文档**|从下拉列表中选择出站映射的目标文档。|  
  
7.  完成配置发送端口，则单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [管理管道](../core/managing-pipelines.md)   
 [管理映射](../core/managing-maps.md)