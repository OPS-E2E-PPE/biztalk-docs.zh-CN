---
title: "步骤 2： 定义的业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: "49"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f181933daac5170c517a23f809eb97b54f2900
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-define-the-business-process"></a>步骤 2：定义业务流程
![步骤 2 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 8 分钟  
  
 **目标：**在此步骤中，你使用业务流程设计器来定义您的业务流程。  
  
 **用途：**的工作流的业务流程表示和自动执行用于批准库存补货请求你公司的业务流程。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前必须完成[步骤 1： 向解决方案添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md)。  
  
## <a name="procedures"></a>过程  
 开发业务流程的第一步是使用操作形状来表示业务流程。  
  
#### <a name="to-create-the-eai-business-process-workflow"></a>创建 EAI 业务流程工作流  
  
1.  从 Visual Studio 的解决方案资源管理器中，双击**EAIProcess.odx**以打开业务流程。  
  
2.  业务流程的设计器中，从业务流程工具箱中，拖动**接收**形状，然后将其之间放置**开始**（绿色圆圈） 和**结束**（红色八边形） 形状。  
  
    > [!NOTE]
    >  如果工具箱是未打开，请在**视图**菜单上，单击**工具箱**。 若要将其停靠在屏幕上，请单击图钉图标。  
  
3.  从工具箱中，将**确定**下接收形状的形状。  
  
4.  从工具箱中，将**转换**到判定形状左分支的形状。 “转换”形状将嵌套在“构造消息”形状的内部。  
  
5.  从工具箱中，将**发送**下转换形状的形状。  
  
6.  从工具箱中，将**发送**到判定形状右分支的形状。  在您添加操作形状之后，业务流程将如下所示：  
  
     ![EAI 过程](../core/media/eaiprocess.gif "eai 进程")  
  
 下一步是定义消息变量。  多个操作形状具有一个需要指定的消息属性。  
  
#### <a name="to-define-message-variables"></a>定义消息变量  
  
1.  从 Visual Studio 中，单击**视图**菜单上，单击**其他窗口**，然后单击**业务流程视图**。  
  
2.  从 Orchestration 视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Identifier**|类型**RequestMessage**。|  
    |**消息类型**|单击**架构**，然后单击**\<选择从引用程序集...>**。 从选择项目类型窗口中，单击**EAISchemas**，然后单击**请求**。 单击 **“确定”**。|  
  
4.  从 Orchestration 视图中，右键单击**消息**，然后单击**新消息**。  
  
5.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Identifier**|类型**RequestDeclineMessage**。|  
    |**消息类型**|单击**架构**，然后单击**\<选择从引用程序集...>**。 从选择项目类型窗口中，单击**EAISchemas**，然后单击**RequestDecline**。 单击 **“确定”**。|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a>若要配置形状的属性  
  
1.  在设计图面上，单击**接收**形状以选中它。  
  
2.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceiveRequest**。|  
    |**消息**|选择**RequestMessage**。|  
    |**Activate**|从下拉列表中选择**True**。|  
  
    > [!NOTE]
    >  如果属性窗口未打开，请在**视图**菜单上，单击**属性窗口**。  
  
3.  在设计图面上，单击**确定**形状。  
  
4.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**CheckGrandTotal**。|  
  
    > [!NOTE]
    >  如果属性窗口未打开，请在**视图**菜单上，单击**属性窗口**。  
  
5.  在设计图面上，单击**Rule_1**形状。  
  
6.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**DeclineRule**。|  
    |**表达式**|单击省略号 (**...**)，然后键入`RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`。 单击 **“确定”**。|  
  
7.  在设计图面上，单击**ConstructMessage_1**形状。  
  
8.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ConstructRequestDeclineMessage**。|  
    |**构造的消息**|选择**RequestDeclineMessage**。|  
  
9. 在设计图面上，单击**Transform_1**形状。  
  
10. 在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**TransformRequestToRequestDeclineMessage**。|  
    |**映射名称**|单击**...**. 从“转换配置”中，执行以下操作：<br /><br /> 输入配置信息：<br /><br /> -单击**现有映射**。<br /><br /> 完全限定的映射名称：<br /><br /> -选择**\<选择从引用的程序集 >**。  从左窗格中，选择**EAISchemas**。  从右侧窗格中选择“EAISchemas.MapToReqDecline”。  单击 **“确定”**。<br /><br /> 数据源<br /><br /> -RequestMessage<br /><br /> 目标<br /><br /> -RequestDeclineMessage|  
  
11. 在设计图面上，单击**Send_1**形状。  
  
12. 在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**SendRequestDecline**。|  
    |**消息**|选择**RequestDeclineMessage**。|  
  
13. 在设计图面上，单击**Send_2**形状。  
  
14. 在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**SendRequestToERP**。|  
    |**消息**|选择**RequestMessage**。|  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，您使用业务流程设计器定义了业务流程。  
  
## <a name="next-steps"></a>后续步骤  
 将逻辑端口添加到在业务流程[步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 向解决方案添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md)   
 [步骤 4： 生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)