---
title: "如何配置应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, applications
- applications, configuring
ms.assetid: e1cd1efb-e1ea-4344-8e23-668628d6c5a9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888fc0ff78ebac3ac2314fe3106de4b7b6b51f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-application"></a>如何配置应用程序
本主题介绍如何使用 BizTalk Server 管理控制台配置应用程序中的项目，其步骤如下所示：  
  
-   将逻辑端口和角色链接绑定到物理端口和参与方。  
  
-   将业务流程映射到应执行这些业务流程的主机。  
  
-   配置发送和接收端口、发送端口组及接收端口位置。  
  
 如果应用程序不包含至少一个业务流程、发送端口、发送端口组、接收端口或接收位置，则本主题中的信息不适用。  
  
 在完成此配置之后, 你将能够启动该应用程序中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
> [!NOTE]
>  也可以对应用程序中的项目分别进行配置。 有关配置各个项目的详细信息，请参阅本主题末尾的链接。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-an-application"></a>若要配置应用程序  
  
1.  单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，右键单击该应用程序，，然后单击**配置**。  
  
3.  在**业务流程**列表的左窗格中，单击一个业务流程下, 表中所述配置属性，然后单击**确定**。 如果没有在此应用程序，没有业务流程**业务流程**列表不显示。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**主机**|从下拉列表中，选择要登记该应用程序的主机。|  
    |**绑定的入站逻辑端口**|显示逻辑入站端口的名称。 在业务流程的端口图面上可以找到逻辑端口。|  
    |**绑定-接收端口**|从下拉列表中，选择要绑定到相应入站逻辑端口的物理接收端口。 此列表包括当前应用程序中的端口以及任何引用的应用程序中的端口。|  
    |**绑定的出站的逻辑端口**|显示逻辑出站端口的名称。 在业务流程的端口图面上可以找到逻辑端口。|  
    |**绑定-发送端口/发送端口组**|从下拉列表中，选择要绑定到相应出站逻辑端口的发送端口或发送端口组。 此列表包括当前应用程序中的端口以及任何引用的应用程序中的端口。|  
  
4.  在**消息**的左窗格中列表中，单击**发送端口和发送端口组**下, 表中所述配置属性，然后单击**确定**。 此列表显示了当前应用程序中的所有发送端口和发送端口组。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**新建**|单击此项可创建新的发送端口或发送端口组。 用于发送端口是相同的可用选项，右键单击时**发送端口**节点在控制台树中并指向**新建**。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建发送端口组](../core/how-to-create-a-send-port-group.md)。|  
    |**属性**|单击此项可显示所选发送端口或发送端口组的属性。 如果选择发送端口，**发送端口属性**页面将显示，你可在其中配置端口。 如果你选择发送端口组，**发送端口组属性**页面将显示，你可在其中配置发送端口组。 有关配置属性的详细信息，请参阅[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)。|  
    |**名称**|显示物理发送端口的名称。|  
    |**Filter**|显示应用于该发送端口的筛选器表达式。 在中设置筛选器**发送端口属性**窗口。|  
    |**URI**|显示所选端口的 URI。|  
  
5.  在**消息**的左窗格中列表中，单击**接收端口和位置**下, 表中所述配置属性，然后单击**确定**。 此列表显示了当前应用程序中的所有接收端口和接收位置。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**新建**|单击此项可创建一个新的接收端口。 选项新建接收端口是相同的可用选项，右键单击时**接收端口**节点在控制台树中并指向**新建**。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。|  
    |**属性**|单击此项可显示所选项的属性。 如果选择了接收端口，**接收端口属性**页面将显示，你可在其中配置端口。 如果选择了接收位置，**接收位置属性**页面将显示，你可在其中配置接收位置。 若要选择接收端口，请单击右侧的粗体文本**接收端口**。 有关配置属性的详细信息，请参阅[管理接收端口](../core/managing-receive-ports.md)。 另请参阅[管理接收位置](../core/managing-receive-locations.md)。|  
    |**名称**|显示与接收端口关联的接收位置的名称。|  
    |**URI**|显示所选接收位置的 URI。|  
  
6.  在左窗格中，单击**角色链接**，配置下表中所述的属性，然后单击**确定**。 如果在应用程序，没有任何角色链接**角色链接**链接不会显示。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**登记**|单击此项可显示**登记方**对话框中，你可以在其中选择角色定义的交换中存在要加入的参与方。|  
    |**取消登记**|单击此项可从参与交换的参与方中删除所选参与方。|  
    |**绑定**|单击此项可通过参与方在角色链接和物理端口之间建立连接。|  
    |**方**|显示已登记到此角色的一个或多个参与方的名称。|  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [管理业务流程](../core/managing-orchestrations.md)   
 [管理角色链接](../core/managing-role-links.md)   
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)   
 [管理接收端口](../core/managing-receive-ports.md)   
 [管理接收位置](../core/managing-receive-locations.md)