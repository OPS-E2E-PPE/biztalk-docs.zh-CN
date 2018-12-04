---
title: 步骤 2： 将请求消息发送到 SQL Server 并接收响应 |Microsoft Docs
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
ms.openlocfilehash: 55c2c6095c9e0c7bf88ec22a296ccc6483c62472
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826309"
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a>步骤 2： 将请求消息发送到 SQL Server 并接收响应
![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，将发送要执行的请求消息**UPDATE_EMPLOYEE**存储过程，并接收响应。  
  
## <a name="prerequisites"></a>必要条件  
 你必须已完成[步骤 1： 为 UPDATE_EMPLOYEE 存储过程创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>若要发送的请求消息并接收响应  
  
1.  现有业务流程，向下**插入**块**判定**形状中，添加**消息赋值**形状。 从工具箱拖动**消息赋值**到空间形状表示。  
  
    > [!NOTE]
    >  放置**消息赋值**形状拖到设计图面上，业务流程设计器创建封闭**构造消息**为你的形状。  
  
2.  在设计图面上，右键单击**ConstructMessage_1**形状，然后依次**属性窗口**。  
  
3.  在中**属性**窗格**ConstructMessage_1**形状中，指定以下值。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**构造的消息**|UpdateEmployee|  
    |**名称**|ConstructRequestMessage|  
  
4.  双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。  
  
5.  在中**BizTalk 表达式编辑器**，添加以下：  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     在这里， **UpdateEmployee**是你在中创建的消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)用于将请求消息发送**UPDATE_EMPLOYEE**存储过程。 在中**MessageAssignment**形状中，调用**UpdateEmployeeMessageCreator**类，以创建请求消息。 此外，您设置请求消息的 WCF 操作。  
  
6.  将以下形状添加到在业务流程**消息赋值**形状。  
  
    |形状|形状类型|Properties|  
    |-----------|----------------|----------------|  
    |SendUpdateMessage|Send|-设置**消息**到*UpdateEmployee*<br />-设置**名称**到*SendUpdateMessage*|  
    |ReceiveUpdateResponse|Receive|-设置**激活**到*False*<br />-设置**消息**到*UpdateEmployeeResponse*<br />-设置**名称**到*ReceiveUpdateResponse*|  
  
7.  将请求-响应发送端口添加到业务流程。 将使用此端口将请求消息发送到 SQL Server 并接收响应。 设置端口的以下属性。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|发送-接收|  
    |**通信模式**|请求-响应|  
    |**Identifier**|SQLOutboundPort|  
  
     此外，更改操作名称从为 Operation_1 **UpdateEmp**。  
  
8.  将端口连接到操作形状。 在业务流程设计器中，在设计图面上，将的操作形状的端口到相应的绿色句柄的绿色箭头状手柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性，将操作形状连接到端口。  
  
     按如下所示连接端口和操作形状：  
  
    -   连接**SendUpdateMessage**到操作形状**请求**的处理**SQLOutboundPort**。  
  
    -   连接**ReceiveUpdateResponse**到操作形状**响应**的处理**SQLOutboundPort**。  
  
9. 下图显示了正在进行中业务流程。  
  
     ![更新发送更新消息的业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 通过添加在此步骤中，更新了业务流程**MessageAssignment**形状**发送**并**接收**形状和端口。 连接形状和端口以发送请求消息执行 UPDATE_EMPLOYEE 请求消息和接收响应。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步，添加业务流程形状上调用插入操作**Purchase_Order**表，如中所述[第 4 课： 执行采购订单表上的插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1： 创建请求消息为 UPDATE_EMPLOYEE 存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)   
 [第 3 课：执行存储过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)
