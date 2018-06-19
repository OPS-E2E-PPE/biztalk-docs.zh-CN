---
title: 步骤 2： 将请求消息发送到 SQL Server，并接收响应 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce820ab6a1914e44239313588eaaefeb696e61d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224797"
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a>步骤 2： 将请求消息发送到 SQL Server，并接收响应
![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，你将发送要执行的请求消息**UPDATE_EMPLOYEE**存储过程和接收响应。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 1： 为 UPDATE_EMPLOYEE 存储过程创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>若要发送的请求消息和接收响应  
  
1.  与现有的业务流程下,**插入**块**确定**形状，添加**消息分配**形状。 从工具箱中，拖动**消息分配**到空间形状指示。  
  
    > [!NOTE]
    >  当删除**消息分配**形状拖到设计图面，业务流程设计器创建封闭**构造消息**为你的形状。  
  
2.  在设计图面上，右键单击**ConstructMessage_1**形状，并依次**属性窗口**。  
  
3.  在**属性**窗格**ConstructMessage_1**形状，指定以下值。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**构造的消息**|UpdateEmployee|  
    |**名称**|ConstructRequestMessage|  
  
4.  双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。  
  
5.  在**BizTalk 表达式编辑器**，添加以下：  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     在这里， **UpdateEmployee**是你在中创建一条消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)的发送请求消息**UPDATE_EMPLOYEE**存储过程。 在**MessageAssignment**调用形状， **UpdateEmployeeMessageCreator**类以创建的请求消息。 此外，你将设置请求消息的 WCF 操作。  
  
6.  向下业务流程中添加以下形状**消息分配**形状。  
  
    |形状|形状类型|属性|  
    |-----------|----------------|----------------|  
    |SendUpdateMessage|Send|-将设置**消息**到*UpdateEmployee*<br />-将设置**名称**到*SendUpdateMessage*|  
    |ReceiveUpdateResponse|Receive|-将设置**激活**到*False*<br />-将设置**消息**到*UpdateEmployeeResponse*<br />-将设置**名称**到*ReceiveUpdateResponse*|  
  
7.  将请求-响应发送端口添加到业务流程。 你将使用此端口将请求消息发送到 SQL Server 和接收响应。 设置以下属性的端口。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|发送-接收|  
    |**通信模式**|请求-响应|  
    |**Identifier**|SQLOutboundPort|  
  
     此外，从到 Operation_1 更改操作名称**UpdateEmp**。  
  
8.  端口连接到操作形状。 业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性，将操作形状连接到端口。  
  
     连接的端口和操作形状，如下所示：  
  
    -   连接**SendUpdateMessage**操作形状上的与**请求**的 handle **SQLOutboundPort**。  
  
    -   连接**ReceiveUpdateResponse**操作形状上的与**响应**的 handle **SQLOutboundPort**。  
  
9. 下图显示正在进行中业务流程。  
  
     ![更新业务流程能够发送更新消息](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 你可以在此步骤中，来更新通过添加业务流程**MessageAssignment**形状，**发送**和**接收**形状和一个端口。 连接形状，端口以将请求消息执行 UDPATE_EMPLOYEE 发送请求消息和接收响应。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步的步骤中，添加要调用插入操作的业务流程形状**Purchase_Order**表中所述[第 4 课： 执行采购订单表上的插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)   
 [第 3 课： 执行存储的过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)