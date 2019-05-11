---
title: 第 2 步：配置并启动应用程序 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07fbdba63325f44a803fe4e9c5e83fbd5d31240e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392774"
---
# <a name="step-2-configure-and-start-the-application"></a>第 2 步：配置并启动应用程序
![步骤 2 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，你可以配置并启动 EAISolution 应用程序。  
  
 **目的：** 主要是关于绑定配置。  一个绑定和之间创建映射逻辑终结点，如业务流程端口或角色链接，物理终结点，如发送和接收端口或参与方。 这样，BizTalk 业务解决方案的不同组件之间的通信。 可以使用 BizTalk Server 管理控制台来创建绑定。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
- 在开始此步骤之前，必须完成[步骤 1:将项目部署](../core/step-1-deploy-the-projects.md)。  
  
- 您必须作为的成员登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
## <a name="procedures"></a>过程  
 BizTalk 应用程序是一项功能会更加快速、 更轻松地部署、 管理和故障排除 BizTalk Server 业务解决方案的 BizTalk Server。 BizTalk 应用程序是称为"项目，"BizTalk Server 业务解决方案中使用的项的逻辑分组。  有关详细信息，请参阅[什么是 BizTalk 应用程序？](../core/what-is-a-biztalk-application.md)。  在[步骤 1:将项目部署](../core/step-1-deploy-the-projects.md)，我们配置的应用程序名称为"EAISolution"，然后再部署项目。  因此，EAISolution 应用程序包含业务流程、 两个架构和映射。  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a>若要从 BizTalk Server 管理控制台打开 EAISolution 应用程序  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2. 在控制台树中的左侧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。  
  
3. 展开**BizTalk 组**，展开**应用程序**，然后单击**EAISolution**。  
  
   在 [第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)，我们创建了业务流程。  在业务流程，我们定义了逻辑端口。  在以下过程中，将定义物理端口并将物理端口绑定到逻辑端口。  
  
#### <a name="to-create-the-receiverequest-port"></a>创建 ReceiveRequest 端口  
  
1.  从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
2.  在常规选项卡上，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**EAISolutionReceiveRequestPort**。|  
    |**为失败消息启用路由功能**|（清除）|  
  
3.  单击**接收位置**，然后单击**新建**。  
  
4.  从接收位置 1 – 接收位置属性，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**EAISolutionReceiveRequestLocation**。|  
    |**类型**|选择**文件**。|  
    |**接收处理程序**|选择“BizTalkServerApplication” 。|  
    |**接收管道**|选择**XMLReceive**。|  
  
5.  单击**配置**。  
  
6.  从文件传输属性中，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|类型**C:\BTSTutorials\WareHouse\Request**。|  
  
7.  单击**确定**三次。  
  
#### <a name="to-create-the-senddecline-port"></a>若要创建 SendDecline 端口  
  
1.  从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在常规选项卡上，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**EAISolutionSendDeclinePort**。|  
    |**类型**|选择**文件**。|  
    |**发送处理程序**|选择**BizTAlkServerApplication**。|  
    |**发送管道**|选择**XML 传输**。|  
  
3.  单击**配置**。  
  
4.  从文件传输属性中，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|类型**C:\BTSTutorials\WareHouse\RequestDecline**。|  
    |**文件名**|类型**RequestDecline_%MessageID%.xml**。|  
  
5.  单击两次 **“确定”** 。  
  
#### <a name="to-create-the-sendtoerp-port"></a>若要创建 SendToERP 端口  
  
1.  从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在常规选项卡上，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**EAISolutionSendToERPPort**。|  
    |**类型**|选择**文件**。|  
    |**发送处理程序**|选择**BizTAlkServerApplication**。|  
    |**发送管道**|选择**XML 传输**。|  
  
3.  单击**配置**。  
  
4.  从文件传输属性中，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|类型**C:\BTSTutorials\ERP\Request**。|  
    |**文件名**|类型**Request_%MessageID%.xml**。|  
  
5.  单击两次 **“确定”** 。  
  
#### <a name="to-bind-the-ports"></a>若要将端口绑定  
  
1.  从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**配置**。  
  
2.  配置应用程序，在左窗格中，单击**EAIProcess**。  这是我们创建的业务流程。  
  
3.  在右窗格中，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**主机**|选择“BizTalkServerApplication” 。|  
    |**接收端口**为**ReceiveRequestPort**|选择**EAISolutionReceiveReqeustPort**。|  
    |**发送 PortsSend 端口组**为**ReceiveRequestPort**|选择**EAISolutionSendDeclinePort**。|  
    |**接收端口**为**ReceiveRequestPort**|选择**EAISolutionSendToERPPort**。|  
  
4.  单击**确定**保存配置。  
  
#### <a name="to-start-the-application"></a>若要启动该应用程序  
  
1.  从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**启动**。  
  
2.  从对话框中，单击**启动**。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，将配置并启动了 EAIApplication 应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 测试 EAI 解决方案如何处理中的消息[步骤 3:测试解决方案](../core/step-3-test-the-solution2.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：将项目部署](../core/step-1-deploy-the-projects.md)   
 [步骤 3：测试解决方案](../core/step-3-test-the-solution2.md)