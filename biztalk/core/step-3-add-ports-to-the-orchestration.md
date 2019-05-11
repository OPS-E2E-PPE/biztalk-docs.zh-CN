---
title: 步骤 3：向业务流程添加端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310c9b5640d8b975e2f11f7ab52d314236c0d43e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392697"
---
# <a name="step-3-add-ports-to-the-orchestration"></a>步骤 3：向业务流程添加端口
![步骤 3，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，将向 EAIProcess 业务流程添加三个端口和配置它们。  
  
 **目的：** 端口指定如何将消息发送到您的业务流程和从其他业务流程接收消息。 每个端口都具有一个类型、 方向和绑定，它们共同确定通信、 通信模式、 位置或从其发送或接收消息和如何进行通信的方向。 创建和配置在此步骤中的三个端口实现以下角色：  
  
- **ReceiveRequestPort**从仓库接收库存补货请求消息。  
  
- **SendToERP**将转发到 ERP 系统的请求消息。  
  
- **SendDeclinePort**将请求拒绝消息回仓库。  
  
  有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前，必须完成[步骤 2:定义业务流程](../core/step-2-define-the-business-process.md)。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-create-and-configure-receiverequestport"></a>若要创建和配置 ReceiveRequestPort  
  
1.  在解决方案资源管理器中双击**EAIProcess.odx**。  
  
2.  在业务流程设计器中，从业务流程工具箱中拖动**端口**形状添加到左侧**端口图面**并行**ReceiveRequest**形状。 端口配置向导会自动启动。  
  
3.  在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
4.  上**端口属性**页上，执行以下操作，并单击**下一步**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceiveRequestPort**。|  
  
5.  上**选择端口类型**页上，执行以下操作，并单击**下一步**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**选择要用于此端口的端口类型**|选择**创建新的端口类型**选项。|  
    |**端口类型名称：**|类型**ReceiveRequestPortType**。|  
    |**通信模式**|选择**单向**。|  
    |**访问限制**|选择**内部-仅限于此项目**。|  
  
6.  上**端口绑定**页上，执行以下操作，并单击**下一步**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**端口通信方向**|选择**我将始终接收此端口上的消息**。|  
    |**端口绑定**|在中，选择**以后指定**。|  
  
7.  上**完成端口向导**页上，单击**完成**。  
  
#### <a name="to-create-and-configure-senddeclineport"></a>若要创建和配置 SendDeclinePort  
  
1.  从业务流程工具箱中拖动**端口**形状添加到左侧**端口图面**并行**SendRequestDecline**形状。  
  
2.  使用下表中的信息来创建**SendDeclinePort**发送端口。  
  
    |属性|ReplTest1|  
    |--------------|-----------|  
    |**名称**|类型**SendDeclinePort**。|  
    |**选择要用于此端口的端口类型**|选择**创建新的端口类型**。|  
    |**端口类型名称**|类型**SendDeclinePortType**。|  
    |**通信模式**|选择**单向**。|  
    |**访问限制**|选择**内部-仅限于此项目**。|  
    |**端口通信方向**|从下拉列表中，选择**我将始终在消息端口上发送此**。|  
    |**端口绑定**|从下拉列表中，选择**以后指定**。|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a>若要创建和配置 SendToERPPort  
  
1.  从业务流程工具箱中拖动**端口**形状添加到右侧**端口图面**并行**SendToERP**形状。  
  
2.  使用下表中的信息以完成端口配置向导**SendToERP**发送端口。  
  
    |属性|ReplTest1|  
    |--------------|-----------|  
    |**名称**|类型**SendToERPPort**。|  
    |**选择要用于此端口的端口类型**|选择**创建新的端口类型**。|  
    |**端口类型名称**|类型**SendToERPPortType**。|  
    |**通信模式**|选择**单向**选项。|  
    |**访问限制**|选择**内部-仅限于此项目**选项。|  
    |**端口通信方向**|从下拉列表中，选择**我将始终在消息端口上发送此**。|  
    |**端口绑定**|从下拉列表中，选择**以后指定**。|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a>若要将端口连接到操作形状  
  
-   在业务流程设计器中，在设计图面上，将操作形状的每个端口到相应的绿色控点的绿色箭头状手柄:  
  
    |此端口连接|至此操作形状|  
    |-----------------------|--------------------------|  
    |**ReceiveReqPort**|**Receive_Request**|  
    |**SendDeclinePort**|**Send_ReqDenied**|  
    |**SendToERP**|**Send_ReqToERP**|  
  
     下图显示了所有连接的端口的 EAIProcess 业务流程。  
  
     ![具有已连接端口的 EAIProcess 业务流程。](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，将向 EAIProcess 业务流程添加了三个端口和配置它们。  
  
## <a name="next-steps"></a>后续步骤  
 生成项目[步骤 4:生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：向解决方案中添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [步骤 2：定义业务流程](../core/step-2-define-the-business-process.md)   
 [步骤 4：生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)